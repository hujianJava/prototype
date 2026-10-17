---
name: prototype-export
description: 把原型项目连同完整 git 历史交付给开发：推送到远端仓库，或生成含全部提交记录的 git bundle / 压缩包，并产出交接清单。当产品经理说"导出原型""交给开发""打包原型""提交到 GitHub/公司 Git""把项目发给他"时使用。
---

# 原型项目导出（含 git 历史）

交付物 = **项目文件 + 完整提交历史**。只有最新文件、没有历史的交付是残废的：开发冻结需求时要逐轮回放提交信息找业务规则，缺历史就只能靠猜。

前置：先按 /prototype-handoff 的交付前自检跑一遍（工作区干净、每轮提交信息含"改动 + 老板反馈要点"、新克隆可运行）。**导出不能掩盖未提交的改动**——有未提交内容先按 prototype 纪律补提交，再导出。

## 模式 A：推送到远端（首选）

适用：有可写远端（公司 Git / GitHub / Gitee）。

1. 确认远端：`git remote -v`；没有则让用户提供地址：`git remote add origin <url>`。
2. 推送：`git push -u origin HEAD`。**不要 force-push、不要 rebase**（开发会基于历史打冻结 tag）。
3. 验证：`git ls-remote origin` 能看到该提交哈希；浏览器打开仓库确认文件可见。
4. 生成交接清单（见下）。

## 模式 B：离线导出（无远端权限 / 内网隔离 / 直接发文件）

首选 **git bundle**（单文件、含全部历史、可校验）：

```bash
git bundle create <项目名>-<YYYYMMDD>.bundle --all
git bundle verify <项目名>-<YYYYMMDD>.bundle
sha256sum <项目名>-<YYYYMMDD>.bundle    # Windows: certutil -hashfile <file> SHA256
```

开发这样还原：`git clone <项目名>-<YYYYMMDD>.bundle <目录名>`。

备选：整个目录压缩，**必须包含 `.git/`**，否则历史丢失；压完解压抽查 `git log` 仍可用。

## 交接清单（每次导出必附）

两种方式任选：直接写进发给开发的交接消息（推荐，不产生文件）；或生成 `EXPORT-INFO.md`——**必须在推送/打包之前随改动一起提交**（`prototype: 导出清单`），否则未提交的文件不会进入历史，开发也收不到。内容：

- 项目名 / 仓库地址或 bundle 文件名
- 分支与最新提交哈希、提交总数
- 逐轮记录摘要：`git log --reverse --oneline` 的输出（每轮一行，含反馈要点）
- 原型运行命令
- 已 mock 的数据范围；待开发确认的技术点
- 导出时间与校验值（bundle 模式附 sha256）

## 交付后

把仓库地址 / bundle 文件 + 交接清单发给开发，等待开发运行 /spec-freeze。开发可能回来问业务规则，保持可联系。
