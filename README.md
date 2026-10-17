# 原型技能包（产品经理专用）

标准化的「产品经理 → 开发」原型交付流程：用 AI 对话产出**可点击、可运行、带完整 git 历史**的原型项目，交给开发继续冻结需求与实现。

## 给产品经理：只需要说这一句话

把本仓库地址发给你的 AI agent，说：

> 克隆 https://github.com/hujianJava/prototype.git，按 README 把 skills/ 里的技能安装好。

安装完成后，用自然语言说"帮我起个新原型项目：xxx"即可开始。

## 给 AI agent：安装步骤

### 1. 克隆仓库

```bash
git clone https://github.com/hujianJava/prototype.git
```

### 2. 安装技能

把仓库 `skills/` 下的 5 个目录**整体复制**到宿主工具的技能目录：

- ZCode / 跨工具标准位：`~/.agents/skills/`（Windows：`C:\Users\<用户名>\.agents\skills`）
- Claude Code：`~/.claude/skills/`

Windows PowerShell（在仓库根目录执行）：

```powershell
$dst = "$env:USERPROFILE\.agents\skills"
New-Item -ItemType Directory -Force $dst | Out-Null
Copy-Item -Recurse -Force .\skills\* $dst
```

macOS / Linux：

```bash
mkdir -p ~/.agents/skills
cp -R skills/* ~/.agents/skills/
```

目录名不要改（必须与各 SKILL.md 的 `name` 一致）。

### 3. 验证安装

新开一个会话，确认技能可被发现；或直接确认 `~/.agents/skills/prototype/SKILL.md` 等文件存在。

### 4. 安装完成后，向用户输出上手引导（必须执行）

安装验证通过后，**不要只回复"装好了"**——直接向用户输出下面这段说明（可按实际情况微调，保持简短、口语化）：

> ✅ 原型技能已装好。日常你只需要记住**一个入口：`prototype-handoff`**。它会按你要做的事自动路由：
>
> - 新建项目 → `project-init`（初始化底座）
> - 定/换风格、改设计规范 → `design`（之后每次改设计规范都必须走它）
> - 做/改原型 → `prototype`（之后每次原型改动都必须走它）
> - 交付给开发 → 先做交付自检，再用 `prototype-export` 导出
>
> 你不需要记其他技能名。每次开始一个新动作时说"用 prototype-handoff"，或直接说要做的事（如"改个原型""准备交接"），入口技能会带你走完每一步。

### 5. 更新

`git pull` 后重新执行第 2 步的复制命令（复制会覆盖旧版本）。

## 技能清单

| 技能 | 用途 | 触发说法 |
|---|---|---|
| `project-init` | 新项目底座（AGENTS.md + DESIGN.md + 目录约定） | "起个新项目" |
| `design` | 选风格 / 换风格 / 复刻参考站风格 | "用 xx 风格" |
| `prototype` | 对话生成并迭代可点击原型 | "出原型 / 改原型" |
| `prototype-handoff` | 交付契约与交付前自检 | "准备交接" |
| `prototype-export` | 导出原型项目（推送远端或含历史的 bundle） | "导出 / 交给开发" |

## 标准流程

```
project-init → design → prototype（老板点、迭代若干轮）
→ prototype-handoff（交付前自检）→ prototype-export（推送远端或导出 bundle）
```

**SPEC 冻结、生产实现、验收是开发侧流程，不在本包内。** 开发接手后会运行 /spec-freeze，用原型项目的逐轮提交信息逐轮回放业务规则。

两条硬规则：**原型阶段的任何改动都走 `prototype` 技能**；**`DESIGN.md` / 视觉风格的任何调整都走 `design` 技能**——跳过技能直接改文件，会绕过 mock 隔离、三态要求、提交纪律与设计 tokens。

## 硬性约束

1. 只做原型：不写 SPEC、不碰 `docs/specs/`；不写生产代码；不跑实现/验收流程。
2. 技术栈固定 React + TS + Vite + Tailwind + shadcn；数据全部 mock，统一走 `prototype/src/lib/api.ts`，页面不直连 mock。
3. 每轮原型达到可演示状态就 commit，提交信息必须含「改了什么 + 老板反馈要点」；**会话结束前必须提交**，不留未提交改动。
4. 不修改本仓库；不 rebase / force-push 原型项目的提交历史。

## 常见问题

- **工具只支持 rules 类配置（Cursor / Trae 等）**：把 `skills/` 下各 SKILL.md 的正文粘进规则文件，并在开头注明 `design/styles` 与 `design/references` 的绝对路径。
- **没有 GitHub 访问**：让仓库所有者打包发送（zip 包含 `skills/` 目录），安装步骤相同。
- **导出时没有远端仓库**：`prototype-export` 会生成 git bundle（单文件含全部历史），开发可直接 `git clone <bundle>` 还原。
