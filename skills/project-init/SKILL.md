---
name: project-init
description: 初始化新项目的全局底座：git 仓库、AGENTS.md（项目宪法）、DESIGN.md（视觉风格基线）、目录约定。开任何新项目/新仓库的第一条命令。当用户说"初始化项目""新项目开始""搭底座""建 AGENTS.md"或要为新项目建立规范时使用。
---

# 项目底座初始化

一个新项目的全部公共约定只在这里产生一次，之后 /prototype、/implement、/accept 都基于这些文件工作，不再重复交代。本流程族的完整链路：

```
/project-init → /design → /prototype → 老板确认 → /spec-freeze → /implement → /accept
```

三层分离原则（务必遵守）：
- **方法论**在 skill 里（跨项目复用）；
- **项目事实**在 AGENTS.md / DESIGN.md（每项目一份，本 skill 生成）；
- **需求状态**在 docs/specs/ 的 SPEC.md + prototype/（每需求一份）。

skill 里永远不写具体项目信息，AGENTS.md 里永远不写方法论。

## 执行流程

1. **问询（一次问全，别挤牙膏）**：
   - 项目名与一句话定位；
   - 是否有后端及现有系统（默认纯前端）；
   - 技术栈确认——默认 React + TypeScript + Vite + Tailwind CSS + shadcn/ui，用户没有明确换栈就不要改。
2. **git**：当前目录不是 git 仓库则 `git init`。版本、冻结、回滚全靠 git，这是整套流程的前提（SPEC 的 APPROVED 冻结用 commit 哈希引用），不要跳过。
3. **生成 AGENTS.md**：复制 `assets/AGENTS-template.md`，与用户逐项确认后填充。"现有系统与边界"一节若用户答不上来要追问——这是防止 coding agent 自建重复设施的关键防线。"全局约定登记"一节初始化时可整体留待补，但节本身不删——它是跨文件隐式约定（全局错误策略、持久化键、定制过的 ui 组件）的唯一登记处，/prototype 与 /implement 产出这类约定时回写进来。
4. **生成 DESIGN.md**：问用户选什么视觉风格。本地风格库在 `~/.agents/skills/design/styles/`（当前缓存：airbnb）。选定后把风格文件复制到项目根目录 DESIGN.md。用户想换风格或复刻新风格时，见 /design skill 的流程。
5. **建目录骨架**：`prototype/`（可留空，/prototype 时再建应用）、`docs/specs/`、`.gitignore`（至少包含：`node_modules/`、`dist/`、`*.tsbuildinfo`、`.env*`、`.DS_Store`）。
6. **收尾**：git add + 首次 commit（`project-init: 项目底座初始化`），把项目结构树输出给用户过目。

## 纪律

- AGENTS.md 保持一页以内；只陈述事实，不含教程性内容。
- AGENTS.md 的"全局约定登记"随代码演进维护：代码里出现新的全局错误策略、持久化键、被定制的 shadcn/ui 组件时，当场回写。代码自身显式了还不够，跨文件的隐式约定必须有一个 agent 能找到的入口，否则后来者不知道它们的存在。
- 告诉用户：之后每次新会话，让 agent 先读 AGENTS.md 与 DESIGN.md 再动手。
