---
name: design
description: 管理项目视觉风格基线 DESIGN.md：从本地风格库选择风格（airbnb 等）、项目中途切换风格、或按参考网站/截图复刻全新风格并入库。文件格式严格遵循 Google 官方 DESIGN.md 规范（google-labs-code/design.md）。当用户提到设计风格、视觉风格、换风格、复刻某网站风格、"做成 xx 那样的 UI"、选风格时使用。
---

# 视觉风格管理（DESIGN.md）

DESIGN.md 是项目的视觉唯一事实来源：/prototype 和 /implement 都读它，所以**风格从原型到生产的一致性由这一个文件自动保证**——不存在"原型一个样、上线另一个样"。

**格式的唯一权威是 Google 官方规范** github.com/google-labs-code/design.md，全文快照在本 skill 的 `references/spec.md`（含官方示例）。复刻或校验文件前先读它。awesome-design-md 只是风格素材库，不是规范来源。

## 规范要点（速查；细节与示例以 references/spec.md 为准）

文件 = 可选 YAML frontmatter（机器可读 tokens）+ Markdown 正文（人类可读的规则与语境）。**token 是规范值，prose 解释应用语境**，两者分工不重复。

**frontmatter 字段**：`version`（可选，当前 "alpha"）、`name`、`description`（可选）、`omitted`（可选）、`colors`、`typography`、`rounded`、`spacing`、`components`。
- colors：任意合法 CSS 颜色，hex 为推荐默认；**primary 必须定义**。
- typography：fontFamily / fontSize / fontWeight / lineHeight（推荐无单位倍数）/ letterSpacing / fontFeature / fontVariation；一个体系通常 9–15 个层级。
- spacing：Dimension 或纯数字（如列数、比例）；rounded：Dimension。**Dimension 单位只允许 px / em / rem**。
- components：组件名 → 属性表；变体用关联键表达（`button-primary` / `button-primary-hover`）；合法属性：backgroundColor、textColor、typography、rounded、padding、size、height、width。

**引用语法**：`{colors.primary}`——花括号内是对象路径；除 components 内可引用复合值（如 `{typography.label-md}`）外，引用必须指向基本值，不能指向组。

**正文章节**（`##` 二级标题，按固定顺序；不相关的可省略，省略时在 frontmatter 用 `omitted` 声明并给原因，不要静默跳过）：
1. Overview（别名 Brand & Style）
2. Colors（primary 必须定义）
3. Typography
4. Layout（别名 Layout & Spacing）
5. Elevation & Depth（别名 Elevation）
6. Shapes
7. Components
8. Do's and Don'ts

**未知内容规则**：未知章节标题、未知 token 名 → 保留不报错；未知组件属性 → 接受但警告；**重复章节标题 → 整个文件被拒**。

**推荐 token 命名**（规范给的约定，非强制）：colors 用 primary / secondary / tertiary / neutral / surface / on-surface / error；typography 用 headline-\* / body-\* / label-\*；rounded 用 none / sm / md / lg / xl / full。

## 两个扩展章节（借鉴 awesome-design-md；规范对未知章节容忍保留，附在官方 8 章之后）

- `## Responsive Behavior`：断点、触控目标、折叠策略——原型与实现直接要用。
- `## Known Gaps`：如实声明未提取/不确定的部分，防止消费方把缺失当默认。

明确不采用 awesome-design-md 的：Agent Prompt Guide（为陌生 agent 冷启动准备的现成 prompt；我们的消费方是自家 skill，直接读文件，无冷启动问题）；preview.html 视觉目录（给人眼浏览用，读者是 agent 时无意义）。

## 三种动作

### 1. 选风格（select）

本地风格库在本 skill 的 `styles/` 目录（当前缓存：`airbnb.md`）。库内文件是社区按"官方规范 + 扩展章节"产出的实例，可能省略官方可选章节（如 Shapes、Do's and Don'ts）——**省略可选章节本身合规，照常消费，不要擅自修复库文件**。
联网时可扩充库存：`npx getdesign@latest add <name>`，或从 awesome-design-md 仓库拉 raw 文件（路径形如 `design-md/<name>/DESIGN.md`），存入 `styles/`。

### 2. 换风格（switch）

项目已有 DESIGN.md 时替换为新风格。替换前必须告知影响面并得到确认：
- prototype 所有页面需按新 tokens 重渲染；
- 已 APPROVED 的 SPEC 若含视觉验收内容，需走 /spec-freeze 出新版本。
列出受影响页面清单再动手，替换后逐页重渲染并自查。

### 3. 复刻风格（replicate）

用户给参考站或截图 → 先读 `references/spec.md`，按官方规范产出：
- frontmatter 五个 token 块齐全（colors / typography / rounded / spacing / components），primary 必有；
- 正文按官方顺序 8 章节；不适用的章节用 `omitted` 声明原因；
- 本 skill 家规（在规范可选项之上加严）：`Do's and Don'ts` 必写且正反例都要有——这是防 AI 自由发挥的核心护栏；`Responsive Behavior` 与 `Known Gaps` 两个扩展章节必附。

产出后存入 `styles/` 库，并实例化为项目根目录 DESIGN.md。

## 纪律

- DESIGN.md 只管"长什么样"。业务规则归 SPEC.md，技术方案归 TECH.md，三者在目录和内容上都不混。
- tokens 必须具体到可直接写代码（hex、px），禁止"温暖的红"这类形容词；prose 解释"何时何处用哪个 token"，不重复 token 的值。
- 复刻是提取公开可见的设计规律（颜色、字号、间距），不是复制品牌资产（logo、插画、文案）。
- 风格变更落盘后提交（`git commit -m "design: 采用/切换/复刻 <风格名>"`；不换风格的中途微调用 `design: 调整 <改了什么>`）；由此引起的原型重渲染按原型规则单独提交，保证每次风格切换可追溯、可回滚。
