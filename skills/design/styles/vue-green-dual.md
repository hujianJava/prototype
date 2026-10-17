---
version: alpha
name: "Video Engine · Vue Green × Ink Dark"
description: "视频引擎双主题设计系统:亮色为 Vue 官网气质的工程绿(提取自 2026-09-21 产品评审稿 HTML),深色为同色相推导的 Ink 主题;平铺发丝线、零投影、文档级排版、克制的信息密集风格。"
colors:
  # ── 亮色主题(light,默认)──────────────────────────
  primary: "#2f8a61"        # 品牌绿:填充、边框、图标、大标题
  primary-text: "#27744F"   # 绿色文字专用(正文/标签/徽章字号下的 AA 安全绿)
  primary-bg: "#eaf6f0"     # 绿色浅底:徽章、callout、选中态
  on-primary: "#ffffff"     # 绿色填充上的文字
  primary-hover: "#27744F"  # 主按钮 hover 加深
  info: "#1d5fd0"
  info-bg: "#eaf1fd"
  warning: "#b45309"
  warning-bright: "#e8a33d" # 琥珀亮色:星级、警示左色条
  warning-bg: "#fef5e7"
  error: "#d92d20"
  error-bg: "#fdecea"
  ink: "#16191d"            # 一级文字
  ink-2: "#4d5661"          # 二级文字
  ink-3: "#8a939e"          # 三级文字/占位
  page: "#f6f7f8"           # 页面底
  surface: "#ffffff"        # 卡片纸面
  surface-alt: "#fafbfc"    # 卡内嵌套浅灰、表头、目录条
  surface-muted: "#f2f4f6"  # 更深一层的灰底、neutral 徽章
  line: "#e4e7ea"           # 发丝线(默认)
  line-strong: "#cdd3d9"    # 强分隔线
  line-subtle: "#f0f2f4"    # 弱分隔线(行内)
  highlight: "#fff8e1"      # 行内关键词高亮底
  callout-warm: "#fffaf5"   # 暖色 callout 底
  # ── 深色主题(dark,经 data-theme 切换)──────────────
  dark-page: "#0f1215"
  dark-surface: "#16191d"
  dark-surface-alt: "#1d2228"
  dark-surface-muted: "#232930"
  dark-primary: "#42b883"   # Vue 官网亮绿,深底上作文字/图标均达 AA
  dark-on-primary: "#0d2318"
  dark-primary-bg: "#173226"
  dark-primary-hover: "#5cc795"
  dark-ink: "#e8ebee"
  dark-ink-2: "#aab2bc"
  dark-ink-3: "#7a838e"
  dark-line: "#2e353d"
  dark-line-strong: "#3c444e"
  dark-line-subtle: "#22282f"
  dark-info: "#7cabf5"
  dark-info-bg: "#14233c"
  dark-warning: "#e8a33d"
  dark-warning-bg: "#2f2410"
  dark-error: "#f0857a"
  dark-error-bg: "#3a1815"
  dark-highlight: "#33290f"
typography:
  display-lg:
    fontFamily: '"Noto Sans CJK SC","PingFang SC","Microsoft YaHei",-apple-system,"Segoe UI",sans-serif'
    fontSize: 31px
    fontWeight: 800
    lineHeight: 1.35
    letterSpacing: "-0.01em"
  headline-lg:
    fontFamily: '"Noto Sans CJK SC","PingFang SC","Microsoft YaHei",-apple-system,"Segoe UI",sans-serif'
    fontSize: 22px
    fontWeight: 700
    lineHeight: 1.4
    letterSpacing: "-0.01em"
  headline-md:
    fontFamily: '"Noto Sans CJK SC","PingFang SC","Microsoft YaHei",-apple-system,"Segoe UI",sans-serif'
    fontSize: 17px
    fontWeight: 700
    lineHeight: 1.5
  body-lg:
    fontFamily: '"Noto Sans CJK SC","PingFang SC","Microsoft YaHei",-apple-system,"Segoe UI",sans-serif'
    fontSize: 16px
    fontWeight: 400
    lineHeight: 1.75
  body-md:
    fontFamily: '"Noto Sans CJK SC","PingFang SC","Microsoft YaHei",-apple-system,"Segoe UI",sans-serif'
    fontSize: 15px
    fontWeight: 400
    lineHeight: 1.75
  body-sm:
    fontFamily: '"Noto Sans CJK SC","PingFang SC","Microsoft YaHei",-apple-system,"Segoe UI",sans-serif'
    fontSize: 14px
    fontWeight: 400
    lineHeight: 1.7
  label-lg:
    fontFamily: '"Noto Sans CJK SC","PingFang SC","Microsoft YaHei",-apple-system,"Segoe UI",sans-serif'
    fontSize: 13px
    fontWeight: 600
    lineHeight: 1.6
  caption-md:
    fontFamily: '"Noto Sans CJK SC","PingFang SC","Microsoft YaHei",-apple-system,"Segoe UI",sans-serif'
    fontSize: 13px
    fontWeight: 400
    lineHeight: 1.6
  caption-sm:
    fontFamily: '"Noto Sans CJK SC","PingFang SC","Microsoft YaHei",-apple-system,"Segoe UI",sans-serif'
    fontSize: 12px
    fontWeight: 400
    lineHeight: 1.6
  label-sm:
    fontFamily: '"Noto Sans CJK SC","PingFang SC","Microsoft YaHei",-apple-system,"Segoe UI",sans-serif'
    fontSize: 12px
    fontWeight: 800
    lineHeight: 1.5
    letterSpacing: "0.06em"
  kicker:
    fontFamily: '"Noto Sans CJK SC","PingFang SC","Microsoft YaHei",-apple-system,"Segoe UI",sans-serif'
    fontSize: 12px
    fontWeight: 700
    lineHeight: 1.4
    letterSpacing: "0.16em"
  micro:
    fontFamily: '"Noto Sans CJK SC","PingFang SC","Microsoft YaHei",-apple-system,"Segoe UI",sans-serif'
    fontSize: 11px
    fontWeight: 800
    lineHeight: 1.4
    letterSpacing: "0.03em"
rounded:
  none: 0px
  xs: 3px
  sm: 5px
  md: 8px
  lg: 12px
  full: 9999px
spacing:
  base: 4px
  xs: 4px
  sm: 8px
  md: 12px
  lg: 16px
  xl: 20px
  xxl: 24px
  xxxl: 32px
  section: 52px
  gutter: 18px
  container: 1080px
components:
  button-primary:
    backgroundColor: "{colors.primary}"
    textColor: "{colors.on-primary}"
    rounded: "{rounded.md}"
    height: 40px
    typography: "{typography.label-lg}"
  button-primary-hover:
    backgroundColor: "{colors.primary-hover}"
  button-secondary:
    backgroundColor: "{colors.surface}"
    textColor: "{colors.primary-text}"
    rounded: "{rounded.md}"
    height: 40px
    typography: "{typography.label-lg}"
  button-secondary-hover:
    backgroundColor: "{colors.primary-bg}"
  badge:
    backgroundColor: "{colors.primary-bg}"
    textColor: "{colors.primary-text}"
    rounded: "{rounded.sm}"
    typography: "{typography.micro}"
  badge-neutral:
    backgroundColor: "{colors.surface-muted}"
    textColor: "{colors.ink-2}"
  badge-error:
    backgroundColor: "{colors.error-bg}"
    textColor: "{colors.error}"
  badge-warning:
    backgroundColor: "{colors.warning-bg}"
    textColor: "{colors.warning}"
  badge-info:
    backgroundColor: "{colors.info-bg}"
    textColor: "{colors.info}"
  card:
    backgroundColor: "{colors.surface}"
    rounded: "{rounded.lg}"
    padding: 24px
  card-muted:
    backgroundColor: "{colors.surface-alt}"
    rounded: "{rounded.md}"
    padding: 16px
  callout:
    backgroundColor: "{colors.primary-bg}"
    rounded: "{rounded.md}"
    padding: 12px
  input:
    backgroundColor: "{colors.surface}"
    textColor: "{colors.ink}"
    rounded: "{rounded.md}"
    height: 40px
    typography: "{typography.body-md}"
  input-focus:
    borderColor: "{colors.primary}"
  appbar:
    backgroundColor: "{colors.surface}"
    height: 56px
    typography: "{typography.caption-sm}"
---

# Video Engine · Vue Green × Ink Dark

## Overview

视频引擎(AI 短视频生成工具)的界面气质:**克制的工程感 + 文档级可读性 + 信息密集而不拥挤**,与 Vue 官网同源的技术社区审美。视觉上零投影、零渐变堆砌,层级完全由"灰阶色调分层 + 1px 发丝线"表达;一个深工程绿(`#2f8a61`)是全站唯一的品牌色,只给最重要的交互与状态。

目标用户是内容运营/创作者,界面是桌面优先的工作台(视频生成页 + 任务列表页);产品产出 9:16 竖版成片,Web 界面本身保持常规横向布局。

双主题是系统的一等公民,不是附加项:

- **亮色(默认)**:Vue 官网气质的工程绿,提取自 2026-09-21 产品评审稿。
- **深色(Ink)**:同色相推导——亮色的三档 ink 文字灰在深色中反转为三档表面色,品牌绿提亮为 Vue 官网绿 `#42b883` 以在深底上保持对比度。

切换主题只重映射颜色 token;布局、间距、圆角、字号、字重完全不变。

## Colors

品牌绿是唯一的强调色;蓝/琥珀/红是语义状态色,各有配套浅底(bg 变体)用于徽章与 callout;灰阶分"文字三档 + 表面四档 + 发丝线三档"。

| 语义 token | 亮色(默认) | 深色(dark) | 用途 |
|---|---|---|---|
| `primary` | `#2f8a61` | `#42b883` | 品牌绿:主按钮底、选中态、边框、图标、≥17px 加粗标题 |
| `primary-text` | `#27744F` | `#42b883` | 绿色文字专用:链接、kicker、徽章字(小字号 AA 安全) |
| `primary-bg` | `#eaf6f0` | `#173226` | 绿色浅底:徽章底、绿色 callout 底、选中行底 |
| `on-primary` | `#ffffff` | `#0d2318` | 绿色填充上的文字 |
| `info` / `info-bg` | `#1d5fd0` / `#eaf1fd` | `#7cabf5` / `#14233c` | 信息提示族 |
| `warning` / `warning-bg` | `#b45309` / `#fef5e7` | `#e8a33d` / `#2f2410` | 警告族;`warning-bright #e8a33d` 用于星级与警示左色条 |
| `error` / `error-bg` | `#d92d20` / `#fdecea` | `#f0857a` / `#3a1815` | 错误族(P0 徽章、失败态) |
| `ink` / `ink-2` / `ink-3` | `#16191d` / `#4d5661` / `#8a939e` | `#e8ebee` / `#aab2bc` / `#7a838e` | 一/二/三级文字与占位符 |
| `page` | `#f6f7f8` | `#0f1215` | 页面底色 |
| `surface` | `#ffffff` | `#16191d` | 卡片纸面 |
| `surface-alt` | `#fafbfc` | `#1d2228` | 卡内嵌套浅灰:表头、目录条、次要面板 |
| `surface-muted` | `#f2f4f6` | `#232930` | 最深表面层:neutral 徽章底、代码/预览区 |
| `line` / `line-strong` / `line-subtle` | `#e4e7ea` / `#cdd3d9` / `#f0f2f4` | `#2e353d` / `#3c444e` / `#22282f` | 发丝线三档 |
| `highlight` | `#fff8e1` | `#33290f` | 行内关键词高亮底(配 `ink` 文字、600 字重) |
| `callout-warm` | `#fffaf5` | `#2f2410` | 暖色 callout 底(琥珀族) |

关键纪律:浅色主题下 `#42b883`(Vue 官网亮绿)**禁止**用作文字或填充——在白底上对比度仅约 2.4:1;它只属于深色主题(在 `#16191d` 上约 7.3:1)或非文字装饰。反之,深色主题下绿色一律用 `#42b883`,不用 `#2f8a61`(深底上发闷)。

## Typography

CJK 优先的现代无衬线体系,单一字体栈贯穿全部层级;字号取文档级紧凑 scale(11–31px),行高宽松(基础 1.75)以消化中文长句;只用 400 / 600 / 700 / 800 四档字重。

- **display-lg(31px/800):** 页面主标题,字距 -0.01em 微收紧,每页最多一次。
- **headline-lg(22px/700):** 区块标题,可配 2px `ink` 色顶部分节线(评审稿签名样式)。
- **headline-md(17px/700):** 卡片标题、表单组标题。
- **body-lg / body-md / body-sm(16/15/14px):** 正文三档;`body-md` 15px 是全局默认正文字号。
- **label-lg(13px/600):** 导航项、列表项标题、按钮文字。
- **caption-md / caption-sm(13/12px):** 元信息、时间戳、辅助说明(`ink-3`)。
- **label-sm(12px/800 + 0.06em):** 卡片左上角 eyebrow 小标(全大写英文/数字,中文加粗即可)。
- **kicker(12px/700 + 0.16em):** 页首绿色引导词,全大写英文或短语,绿色一律用 `primary-text`。
- **micro(11px/800 + 0.03em):** 徽章专用,配语义浅底。

## Layout

内容列 **max-width 1080px 居中**;页面底 `page` 灰上放白色"纸面"(`surface`,以 1px `line` 发丝线描边代替投影),纸面内再嵌 `surface-alt` 灰面板形成三层深度。

- 间距基距 4px;常用档 12 / 16 / 20 / 24px;卡片内边距 16–24px;区块纵向间隔 `section` 52px。
- 双栏内容用 1fr 1fr 网格,`gutter` 18px。
- 导航/目录条:白底 + 底部 1px `line` 发丝线,高约 56px。
- 大分节(评审稿签名):标题上方 2px 实线 `ink` + 26px 留白。
- 表单区、任务列表行内,垂直节奏统一走 4px 倍数。

## Elevation & Depth

**零投影。** 不使用任何 `box-shadow` 投影、浮雕或渐变叠加。层级表达只有三种手段:

1. **色调分层**:页面灰(`page`)→ 白纸面(`surface`)→ 卡内灰(`surface-alt` / `surface-muted`),三层即最深。
2. **发丝线**:`box-shadow: 0 0 0 1px var(--line)` 或等价 `border: 1px solid`,默认 `line`,强调 `line-strong`,行内弱分隔 `line-subtle`。
3. **左侧色条 callout**:3px 实线语义色 + 配套浅底 + 非对称圆角,用于强调块。

深色主题完全同构:表面层反转(更深 = 更"下沉"改为 更亮 = 更"浮起"的暗色分层),发丝线换 `dark-line` 系,仍是零投影。

## Shapes

温和圆角,最大不超过 12px;无圆形容器、无超大圆角。

- `xs 3px`:行内高亮、极小元素。
- `sm 5px`:徽章。
- `md 8px`:按钮、输入框、嵌套面板、callout 右侧圆角。
- `lg 12px`:卡片、图表面板、对话框。
- `full 9999px`:仅用于 chip、头像、开关轨道。
- callout 非对称:左 0 右 8 8 0(`border-radius: 0 8px 8px 0`),因为左侧被 3px 色条占据。

## Components

所有组件零投影,靠发丝线与色调分层成型。深色主题下组件结构与尺寸不变,仅按 Theming 章的映射表换色。

| 组件 | 规格 |
|---|---|
| **主按钮** | 高 40px,圆角 8px,水平内边距 18px,底 `primary`,字 `on-primary` + `label-lg`;hover 加深为 `primary-hover`;深色主题底 `dark-primary`、字 `dark-on-primary`(深字亮底) |
| **次按钮** | 同尺寸;白底 + 1px `line` 发丝线,字 `primary-text`;hover 底变 `primary-bg` |
| **徽章** | `micro` 字号,padding 2px 8px,圆角 5px;语义族:绿/蓝/琥珀/红 = `*-bg` 底 + 对应深色字;neutral = `surface-muted` 底 + `ink-2` 字 |
| **卡片** | `surface` 白底,1px `line`,圆角 12px,内边距 22–24px;卡片头部条可配 `surface-alt` 底 + 底部分隔线(12px 800 eyebrow 风格标题) |
| **嵌套面板** | 卡片内的次级块:`surface-alt` 底、圆角 8px、内边距 12–16px,无描边(色调即可分层) |
| **callout** | 左 3px 语义色实条 + 语义浅底 + `0 8px 8px 0` 圆角 + padding 12px 16px;绿 = `primary-bg`/`primary`,琥珀 = `callout-warm`/`warning-bright` |
| **输入框** | 高 40px,圆角 8px,白底 + 1px `line`;聚焦描边换 `primary`(1px,不加光晕);占位符 `ink-3` |
| **导航/页头** | 白底(`surface`),底部 1px `line`,高 56px;当前项绿字 `primary-text` + 600 字重 |
| **行内高亮** | `highlight` 底 + padding 1px 5px + 圆角 3px + 600 字重,用于关键词强调 |
| **星级/评分** | `warning-bright #e8a33d` 实心与空心(空心用 `line-strong` 描边) |

## Do's and Don'ts

- **Do** 每个视图只保留一个绿色主行动(主按钮);其余行动降级为次按钮或文字链。
- **Don't** 不要用绿色同时强调多个按钮,也不要让状态色(蓝/琥珀/红)抢主行动的视觉权重。
- **Do** 表达层级只用"色调分层 + 发丝线"。
- **Don't** 禁止任何 `box-shadow` 投影、彩色阴影、渐变按钮、玻璃拟态。
- **Do** 浅色主题下,绿色文字(链接、kicker、徽章字)一律用 `primary-text #27744F`;`primary #2f8a61` 只用于填充、边框、图标和 ≥17px 加粗标题。
- **Don't** 浅色主题下禁止用 `#42b883` 做文字或按钮底(白底对比约 2.4:1);它是深色主题专属绿。
- **Do** 字号、字重只从 typography scale 取档;同屏强调字重以一种为主(600 或 700)。
- **Don't** 不要发明 scale 外的字号(如 18px 正文)、不要同屏混用 600/700/800 三档强调。
- **Do** 切换主题只换颜色 token,布局/间距/圆角/字号保持不变。
- **Don't** 深色主题不要用纯黑 `#000000` 做底、纯白 `#ffffff` 做正文;一律走 `dark-*` token。
- **Do** 中文界面用默认 CJK 字体栈,数字/英文自动回落到同栈西文字体。
- **Don't** 不要引入第二套字体(衬线、等宽仅限代码场景且需经 SPEC 确认)。

## Theming

双主题机制:**`<html data-theme="dark">` 切换,CSS 自定义属性整体重映射**。亮色为默认根值,深色为作用域覆盖;Tailwind 侧配置 `darkMode: ["data-theme", "dark"]`,语义色注册为 CSS 变量引用而非硬编码 hex。

- 组件一律引用语义名(`primary`、`surface`、`line`…),深色样式由变量层自动生效,**禁止**在组件里写死任何 hex。
- frontmatter 中 `dark-*` 前缀 token 即深色规范值,完整映射见 Colors 章表格。
- 注意深色主题的两处反转约定:绿色填充上的文字由白改深(`on-primary → dark-on-primary`);徽章/callout 的"深字浅底"翻转为"亮字深底"。
- 主题选择持久化到本地;首帧跟随系统偏好(`prefers-color-scheme`),避免闪白。

## Responsive Behavior

- **≥1080px(桌面,主战场):** 1080px 居中容器;生成页双栏(表单列 + 预览列)、任务列表单列满宽。
- **768–1079px(平板/窄窗口):** 单栏堆叠;预览区置顶或折叠;侧栏/目录收进抽屉。
- **<768px(移动):** 全部单栏;工具条折叠为底部操作;触控目标最小 40×40px。
- 9:16 成片预览区任何断点下保持竖版宽高比,按容器宽度等比缩放,不裁切。
- 断点为从 1080px 容器与评审稿目录条窄屏隐藏行为推导的约定值,实现时如需微调须回写本文件。

## Known Gaps

- **深色主题为推导而非提取**:评审稿 HTML 只有亮色版;深色按同色相反转推导,对比度按 AA 目标设计(主要文字对 ≥4.5:1),实现时需逐屏复核。
- **交互态为推导**:hover/active/focus 色(primary-hover、input 聚焦描边)为按色阶规律派生,HTML 本身是静态文档。
- **主按钮白字对比 4.27:1,略低于 AA 4.5**:接受为品牌决策(与 Vue 官网按钮同量级);若需严格 AA,按钮底可降为 `#27744F`(5.7:1),届时回写本文件。
- **中间字号已归档**:HTML 中 13.5px / 12.5px 归入 13px 与 12px 档;`#f7f8fa` 归入 `surface-alt`;`#cdd3d9` 保留为 `line-strong`;10px 圆角归入 `lg 12px` 档。
- **组件为按设计语言推导**:按钮、输入框、导航、chip 等是依评审稿既有语言(hairline、浅底徽章、callout)推导的生产组件规格;评审稿本身不含这些控件。
- **字体栈补齐**:在评审稿栈基础上补了 `"Segoe UI"` 以覆盖 Windows 西文渲染,未引入新家族。
- **来源说明**:AGENTS.md 提到"五风格设计稿"HTML,当前根目录不存在该文件;本 DESIGN.md 按用户指示仅基于 `视频引擎_产品Review_v2_2026-09-21.html` 提取。
