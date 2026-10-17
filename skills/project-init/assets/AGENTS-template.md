# AGENTS.md — <项目名>

> 本文件是项目宪法：所有 AI agent（原型/实现/测试）动手前必须先读本文件。
> 只写"这个项目的事实"，方法论在各 skill 中，两者不要混。保持一页以内；内容与事实不符时立即更新。

## 项目是什么

<一两句话>

## 技术栈与版本

- 前端：React 18 + TypeScript + Vite + Tailwind CSS + shadcn/ui（声明必须与 package.json 实际依赖一致；若按 DESIGN.md 规格手写组件，此处如实写"手写组件体系，规格源 DESIGN.md §4"，不留 shadcn/ui 的虚名）
- 包管理器：npm
- 后端：<无 / …>
- 视觉风格：见根目录 DESIGN.md（唯一视觉事实来源，UI 一律遵循）

## 目录结构

- `prototype/` — 可交互原型（生产同构体；数据访问统一走 `src/lib/api.ts`，mock 实现在 `src/mocks/`）
- `docs/specs/YYYY-MM-DD-<slug>/` — 每需求一个目录：SPEC.md、TECH.md（按需）、acceptance-*.md（验收报告）
- `<src/ 或 web/>` — 生产代码
- `tests/e2e/` — 沉淀的 Playwright 回归用例（如有）

## 常用命令

- 原型本地运行（局域网可访问，老板演示用）：`cd prototype && npm run dev -- --host`
- 生产启动：<…>
- 测试：<…>

## 全局约定登记

<跨文件隐式约定的唯一登记处：代码显式了还不够，散在多个文件里的全局约定必须在这里有入口，防止后来的 agent 不知道它们的存在。初始化时可整体留待补，节不删；/prototype 与 /implement 产出下列约定时必须当场回写。>

- 全局错误策略位置：<哪个文件集中声明了请求层错误拦截，如 prototype/src/main.tsx 的请求客户端配置；含会话过期/服务端错误的跳转行为>
- 持久化键清单：<cookie / localStorage：键名、语义、有效期>
- 定制过的 shadcn/ui 组件：<src/components/ui/ 下被本地修改过的组件，防 `shadcn add` 更新时覆盖定制；无则写"无">

## 现有系统与边界

<列出已有服务/表/公共模块：什么必须复用、什么禁止绕开自建、什么禁止修改。绿地项目写"无（绿地项目）">

## 协作纪律

- 只基于 `status: APPROVED` 的 SPEC 实现；APPROVED 的 SPEC 不可原地修改（走 /spec-freeze 出新版本）
- SPEC 只在 /spec-freeze 产出（老板确认后出生）；原型阶段不创建、不更新 `docs/specs/` 下的任何文件
- 需求变更：先改 SPEC，再改代码，再重跑受影响验收条目
- UI 一律以 DESIGN.md 的 tokens + prototype/ 为基准，不自由发挥
- 各阶段提交由对应 skill 自动完成，无需手工管理：`project-init:`（首次提交）/ `prototype:`（每轮迭代）/ `design:`（风格变更与微调）/ `spec:`（起草与冻结，冻结含 tag `spec/<slug>-vN`）/ `implement(<slug>): AC-00X`（每条验收标准一次提交；修复轮 `implement(<slug>): fix …`）/ `accept:`（验收报告与回归用例）。不属于任何 skill 的操作用 `deploy:` / `release:` / `chore:` 前缀，不用裸 `fix:` / `feat:`
