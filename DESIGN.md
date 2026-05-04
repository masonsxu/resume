---
version: beta
name: Specsheet
revision_of: Midnight Pearl Archive
description: 一份打印出来的程序运维规格说明（A program operations specification, printed）。象牙白纸面承载墨黑文字，唯一一条印章红顶饰条提示"这是一份正式文档"。IBM Plex Sans 与 IBM Plex Mono 二字体家族构成全部字体语言 —— 没有衬线，没有古典装饰，没有圆角，没有阴影，没有 tag 胶囊。所有信息以 dl/dd、ul/li、article 这些被 ATS 完整识别的语义结构承载。罗马数字 I / II / III 担任段落编号，等宽体接管所有「机器可读字段」（时间戳、技术栈、版本号），人眼读黑体，机器读等宽，HR 看红印 —— 三种受众各取所需。

colors:
  paper: "#fdfdfb"
  paper-print: "#ffffff"
  ink: "#0d0d0d"
  ink-soft: "#4a4a4a"
  ink-mute: "#737373"
  ink-faint: "#a3a3a3"
  hairline: "#d4d4d4"
  hairline-strong: "#a8a8a8"
  seal: "#b91c1c"
  seal-soft: "rgba(185, 28, 28, 0.85)"
  selection: "rgba(185, 28, 28, 0.12)"

typography:
  display:
    fontFamily: "'IBM Plex Sans', 'PingFang SC', 'Source Han Sans SC', 'Microsoft YaHei', sans-serif"
    fontSize: clamp(1.85rem, 4vw, 2.35rem)
    fontWeight: 600
    lineHeight: 1.15
    letterSpacing: -0.012em
  display-en:
    fontFamily: "'IBM Plex Sans', sans-serif"
    fontSize: clamp(0.95rem, 1.4vw, 1.05rem)
    fontWeight: 400
    lineHeight: 1.4
    letterSpacing: 0.04em
    textTransform: none
    color: "{colors.ink-soft}"
  role:
    fontFamily: "'IBM Plex Sans', 'PingFang SC', sans-serif"
    fontSize: 0.985rem
    fontWeight: 500
    lineHeight: 1.4
    letterSpacing: 0
  section-title:
    fontFamily: "'IBM Plex Sans', 'PingFang SC', sans-serif"
    fontSize: 0.78rem
    fontWeight: 600
    lineHeight: 1
    letterSpacing: 0.18em
    textTransform: uppercase
  section-number:
    fontFamily: "'IBM Plex Mono', 'SFMono-Regular', monospace"
    fontSize: 0.74rem
    fontWeight: 500
    letterSpacing: 0.1em
    color: "{colors.seal}"
  item-title:
    fontFamily: "'IBM Plex Sans', 'PingFang SC', sans-serif"
    fontSize: 0.96rem
    fontWeight: 600
    lineHeight: 1.4
  item-meta:
    fontFamily: "'IBM Plex Sans', 'PingFang SC', sans-serif"
    fontSize: 0.85rem
    fontWeight: 500
    lineHeight: 1.4
    color: "{colors.ink-soft}"
  body:
    fontFamily: "'IBM Plex Sans', 'PingFang SC', 'Source Han Sans SC', sans-serif"
    fontSize: 0.895rem
    fontWeight: 400
    lineHeight: 1.62
  caption:
    fontFamily: "'IBM Plex Sans', 'PingFang SC', sans-serif"
    fontSize: 0.78rem
    fontWeight: 400
    lineHeight: 1.5
    color: "{colors.ink-mute}"
  mono-time:
    fontFamily: "'IBM Plex Mono', 'SFMono-Regular', monospace"
    fontSize: 0.78rem
    fontWeight: 400
    letterSpacing: 0
    color: "{colors.ink-soft}"
    fontVariantNumeric: tabular-nums
  mono-stack:
    fontFamily: "'IBM Plex Mono', 'SFMono-Regular', monospace"
    fontSize: 0.755rem
    fontWeight: 400
    lineHeight: 1.55
    letterSpacing: -0.005em
    color: "{colors.ink-soft}"
  mono-metric:
    fontFamily: "'IBM Plex Mono', 'SFMono-Regular', monospace"
    fontSize: inherit
    fontWeight: 600
    fontVariantNumeric: tabular-nums
    color: "{colors.seal}"
  print-base:
    fontSize: 10.4pt
    lineHeight: 1.55

rounded:
  none: 0px

spacing:
  px-1: 4px
  px-2: 8px
  px-3: 12px
  px-4: 16px
  px-5: 24px
  px-6: 32px
  px-7: 48px
  px-section: 22px
  print-section: 12pt

components:
  page-canvas:
    backgroundColor: "{colors.paper}"
    padding: 32px 24px
    color: "{colors.ink}"
    description: "无渐变、无网格、无光晕，单一象牙白底色"
  resume-sheet:
    backgroundColor: "{colors.paper}"
    border: none
    rounded: "{rounded.none}"
    shadow: none
    maxWidth: 760px
    padding: 0
    description: "无卡片化包裹，文档直接坐落在象牙白底色上"
  seal-line:
    height: 4px
    backgroundColor: "{colors.seal}"
    width: 56px
    marginBottom: 18px
    description: "全简历唯一的装饰，模拟红色印章 / 文档编号"
  hero-block:
    paddingBottom: 20px
    borderBottom: "1px solid {colors.hairline}"
    marginBottom: 22px
  hero-name:
    typography: "{typography.display}"
    color: "{colors.ink}"
    marginBottom: 4px
  hero-name-en:
    typography: "{typography.display-en}"
    color: "{colors.ink-mute}"
    fontWeight: 400
    marginLeft: 10px
  hero-role:
    typography: "{typography.role}"
    color: "{colors.ink}"
    marginBottom: 12px
  hero-contacts:
    typography: "{typography.mono-time}"
    color: "{colors.ink-soft}"
    fontStyle: normal
    description: "纯文本流，竖线分隔，全部使用 IBM Plex Mono 等宽体"
  section:
    marginBottom: 18px
    pageBreakInside: avoid
  section-header:
    display: flex
    alignItems: baseline
    gap: 10px
    marginBottom: 10px
    paddingBottom: 6px
    borderBottom: "1px solid {colors.hairline}"
  section-number:
    typography: "{typography.section-number}"
    minWidth: 22px
  section-title:
    typography: "{typography.section-title}"
    color: "{colors.ink}"
    flex: 1
  experience-article:
    marginBottom: 14px
    pageBreakInside: avoid
  experience-header:
    display: flex
    justifyContent: space-between
    alignItems: baseline
    gap: 16px
    marginBottom: 4px
  experience-title:
    typography: "{typography.item-title}"
    color: "{colors.ink}"
  experience-time:
    typography: "{typography.mono-time}"
    color: "{colors.ink-soft}"
    whiteSpace: nowrap
  experience-meta:
    typography: "{typography.item-meta}"
    color: "{colors.ink-soft}"
    marginBottom: 6px
  bullet-list:
    listStyle: none
    paddingLeft: 16px
    description: "前缀 ›  字符（U+203A），代替项目符号；ATS 解析时仅看到正文"
  bullet-item:
    typography: "{typography.body}"
    color: "{colors.ink}"
    marginBottom: 4px
    paddingLeft: 0
  metric-inline:
    typography: "{typography.mono-metric}"
    description: "成果数字 / 百分比 / 量级；红色 + 等宽 + 加粗"
  metric-grid:
    display: grid
    gridTemplateColumns: repeat(4, 1fr)
    gap: 12px
    padding: 14px 0
    borderTop: "1px solid {colors.hairline}"
    borderBottom: "1px solid {colors.hairline}"
    marginBottom: 18px
  metric-cell:
    display: flex
    flexDirection: column
    gap: 2px
  metric-cell-value:
    typography: "{typography.mono-metric}"
    fontSize: 1.4rem
    color: "{colors.seal}"
  metric-cell-label:
    typography: "{typography.caption}"
    color: "{colors.ink-mute}"
  skills-dl:
    display: grid
    gridTemplateColumns: 150px 1fr
    rowGap: 8px
    columnGap: 16px
    description: "definition list，dt 是技能域，dd 是逗号分隔的技术栈纯文本流"
  skills-dt:
    typography: "{typography.item-meta}"
    color: "{colors.ink}"
    fontWeight: 600
  skills-dd:
    typography: "{typography.mono-stack}"
    color: "{colors.ink-soft}"
    margin: 0
  link-inline:
    color: "{colors.ink}"
    textDecoration: underline
    textDecorationColor: "{colors.hairline-strong}"
    textUnderlineOffset: 2px
    description: "黑色 + 下划线，ATS 解析最稳定，无需色觉辅助"
  selection-style:
    backgroundColor: "{colors.selection}"
    description: "拖蓝时显示淡红色调，呼应印章色"
  resume-footer:
    marginTop: 24px
    paddingTop: 12px
    borderTop: "1px solid {colors.hairline}"
    typography: "{typography.caption}"
    color: "{colors.ink-mute}"
---

## Migration Notes

> 从「Midnight Pearl Archive」到「Specsheet」是一次**视觉语言的根本切换**，不是小改动。

| 维度 | 旧（Archive） | 新（Specsheet） | 动机 |
|---|---|---|---|
| 主色 | 深海军蓝 #244e8f + 陶土橙 #9b4b20 | 墨黑 #0d0d0d + 印章红 #b91c1c | 切掉"古典蓝"，换上"工程文档红" |
| 标题字体 | Source Han Serif（思源宋体）| IBM Plex Sans 600 | 移除"档案学术"语感，转向"现代工程"语感 |
| 时间线 | 装饰性左轨 + 圆点 | 全部移除，仅靠 hairline 与 baseline 对齐 | ATS 解析时圆点可能干扰文本提取 |
| 技能 tag | 999px 胶囊 | dl/dd 逗号分隔的纯文本流 | tag 胶囊是 ATS 解析最大杀手 |
| 链接 | 海军蓝 #244e8f 字色 | 墨黑 + 下划线 | 不依赖色觉，PDF 与黑白打印兼容 |
| 圆角 | 30px / 12px / 999px | 0px（全局无圆角）| 印刷文档没有圆角 |
| 阴影 | 主卡 box-shadow | 完全移除 | 印刷品没有阴影 |
| 装饰 | 网格底纹 + 径向光晕 + 顶部渐变 bar | 单条 4px × 56px 印章红顶饰 | 一处即可，多则杂 |
| 主卡圆角包裹 | 30px 圆角纸卡浮于桌面 | 文档直接坐于象牙白底 | 去除"卡片化"，回归"页面" |
| 行高 | 1.72 | 1.62（屏幕）/ 1.55（打印）| 提高信息密度 |
| 内容宽度 | 880px | 760px | A4 内容区贴近真实印刷尺度 |

**保留的设计基因**：
- 数字使用单色加粗强调（从橙色 → 红色，但语义连续）。
- section 标题前置短引导（从 hairline → 罗马数字 mono），仍然是"段落抬头"的形式表达。
- 打印模式深度优化（A4 双页规则未变）。

## Print Tuning Log

> 实际 A4 PDF 导出验证后的打印态字号微调记录（v1 初版 → v2 调优）。

| 元素 | v1（初版）| v2（调优后）| Δ | 调优原因 |
|---|---|---|---|---|
| 主字号 base | 9.6pt | 10.4pt | +8.3% | 第一页底部空白 ~139pt 过大、整体视觉局促 |
| 行高 print | 1.5 | 1.55 | +3.3% | 字号增大同步提升呼吸感 |
| Bullet 字号 | 9pt | 9.8pt | +8.9% | 与主字号同步上调 |
| Profile 段落 | 9.2pt | 10pt | +8.7% | 与主字号同步 |
| Hero 姓名 | 19pt | 21pt | +10.5% | 强化视觉锚点 |
| Metric 大数字 | 14pt | 15.5pt | +10.7% | HR 扫读命中点更突出 |
| Experience 标题 | 9.8pt | 10.6pt | +8.2% | 公司 / 项目名权重 |
| Section 间距 | 8pt | 12pt | +50% | 拉开段落层次节奏 |
| Article 间距 | 6pt | 8pt | +33% | 项目之间更清晰 |
| Hero 块下间距 | 9pt | 13pt | +44% | Hero 与 Section I 之间 |
| 印章条尺寸 | 38×2.5pt | 44×3pt | 加粗加宽 | 视觉锚点更明确 |

**核心洞察**：A4 内容区可用约 796pt（297mm - 16mm margin × 2），v1 字号下两页内容合计仅约 1300pt，远低于上限 1592pt。**10.4pt 是「双页内容自然填充」与「可读性最舒适」之间的甜蜜点**。

**后续微调建议**：如内容增减导致溢出或空缺，按此优先级动手 ——
1. 先调 `bullet-list li margin-bottom`（步进 0.5pt）
2. 再调 `article margin-bottom`（步进 0.5pt）
3. 最后调 `section margin-bottom`（步进 1pt）
4. **不要轻易动主字号 base** —— 一旦改动会引发整套字号梯度连锁调整。

## Overview

Specsheet 把简历重新定位为**一份打印出来的程序运维规格说明**。受众有三：
1. **ATS 系统（机器读）** —— 用语义化 HTML 与纯文本流确保关键词被完整提取。
2. **HR / 招聘经理（人扫）** —— 用红色 metric、加粗公司名、右对齐时间戳让 30 秒筛选拿到关键事实。
3. **技术面试官（人读）** —— 用紧凑 STAR 结构 bullet 与等宽技术栈让深度阅读时上下文清晰。

**视觉骨架**：象牙白纸面（`{colors.paper}` — #fdfdfb）+ 墨黑文字（`{colors.ink}` — #0d0d0d）+ 一条 4px × 56px 印章红顶饰（`{component.seal-line}`）。除此之外没有任何"装饰元素" —— 没有渐变、没有阴影、没有圆角、没有网格底、没有图标库引入。

**字体单一家族**：IBM Plex Sans + IBM Plex Mono。中文走 PingFang SC / 思源黑体 fallback。**整份简历不出现一个衬线字符**。这与上一版（思源宋体标题）形成最强对比 —— Archive 是档案，Specsheet 是说明书。

**信息分层**：
- 黑体（Sans）—— 给人读：姓名、角色、bullet。
- 等宽体（Mono）—— 给机器读：时间戳、技术栈、邮箱、URL。
- 印章红 —— 给 HR 看：成果数字（10+, 99.9%, 50%, 4h→30min）。

**密度策略**：760px 内容宽度，10.4pt 打印基准（v2 调优值，初版 9.6pt），行高 1.55，section 间距 12pt。两页预算：第一页 = Hero + Metric Grid + Profile + Experience；第二页 = Selected Projects + Skills + Open Source + Education。

**关键特征**：
- 极少用 ID 选择器，全靠类与语义化标签 —— ATS 解析友好。
- 数字用 `<span class="metric">` 包裹，红色 + 等宽 + 加粗。
- 链接全部 `<a>` 标签 + `href` + 黑色下划线，PDF 中 100% 可点击且文本可识别。
- 罗马数字 section 编号（I / II / III ...）使用 IBM Plex Mono，染印章红。
- 唯一可视装饰：顶部 4px × 56px 红色印章条，模拟"已盖章 / 已认证"语义。
- 全简历无 box-shadow、无 transform、无 animation（除 prefers-reduced-motion 默认禁用之外）。

## Colors

> **来源**：单页面、单光照模式、印刷友好。

### 纸面与文字
- **象牙白纸面** (`{colors.paper}` — #fdfdfb)：屏幕底色。比纯白柔和 1%，但比羊皮纸（#ece8df）冷 3%，去除任何"古典"暗示。
- **打印纯白** (`{colors.paper-print}` — #ffffff)：仅在 `@media print` 下激活，确保油墨吸附准确。
- **墨黑** (`{colors.ink}` — #0d0d0d)：全部正文、标题、链接。**不使用纯黑** #000，避免屏幕上"黑得过于清脆"，但保留印刷态的视觉权威。
- **柔墨** (`{colors.ink-soft}` — #4a4a4a)：副标题、time 标签、experience-meta、bullet item 二级注。
- **静墨** (`{colors.ink-mute}` — #737373)：caption、metric label、footer 文字。
- **微墨** (`{colors.ink-faint}` — #a3a3a3)：极少使用，留作未来 disabled 状态预留。

### 印章红（唯一 accent）
- **印章红** (`{colors.seal}` — #b91c1c)：**全简历唯一的非中性色**。出现位置：
  1. 顶部 4px × 56px 印章条（`{component.seal-line}`）。
  2. 罗马数字 section 编号（I / II / III）。
  3. metric 数字（`{component.metric-inline}` / `{component.metric-cell-value}`）。
  4. 选中文字时的拖蓝色（`::selection`）。
- **印章红 软调** (`{colors.seal-soft}` — rgba(185, 28, 28, 0.85))：仅在视觉强调需要稍弱时使用（当前未使用，留作预留）。
- **绝对禁止**：印章红绝不染**链接**、**正文**、**标题**、**边线**。它是"已批注 / 已盖章"的视觉证据，扩散即失效。

### 边线
- **细 hairline** (`{colors.hairline}` — #d4d4d4)：section 顶 / 底分割线、Hero block 底边、metric-grid 上下边。1px 宽，全简历主要的"结构线"。
- **粗 hairline** (`{colors.hairline-strong}` — #a8a8a8)：链接的下划线色。比文字本身浅 70%，让下划线在打印时仍然可见但不抢戏。

### 选择态
- **拖蓝** (`{colors.selection}` — rgba(185, 28, 28, 0.12))：用户选中文字时显示淡红底色，呼应印章红，强化"这是一份正式批注的文档"的语感。

## Typography

### Font Family
- **Sans (display + body)**：`'IBM Plex Sans', 'PingFang SC', 'Source Han Sans SC', 'Microsoft YaHei', sans-serif`。
  - **Why IBM Plex Sans**：IBM 在 2018 年为公司技术文档体系设计的开源字体，原生带有"工程文档"基因。比 Inter 字身略瘦、比 Roboto 略硬、字怀更小，在打印 10pt 下保持卓越的可读性。中文 fallback 到 PingFang SC，西文与中文比例约为 1:1.04，渲染稳定。
- **Mono (machine-readable)**：`'IBM Plex Mono', 'SFMono-Regular', 'Cascadia Code', 'Consolas', monospace`。
  - **Why IBM Plex Mono**：与 Plex Sans 同家族同语种支持，字距稳定，启用 `font-variant-numeric: tabular-nums` 后数字纵向严格对齐。所有"机器可读字段"（时间戳、技术栈、邮箱、URL、metric 数字）都用它，让阅读层级一目了然。
- **不使用 Serif**：与上一版最大切割。Specsheet 不要任何"档案 / 学术"语感。

### Hierarchy

| Token | Size | Weight | Line Height | Letter Spacing | Use |
|---|---|---|---|---|---|
| `{typography.display}` | clamp(29.6 → 37.6px) | 600 | 1.15 | -0.012em | 姓名 H1 |
| `{typography.display-en}` | clamp(15.2 → 16.8px) | 400 | 1.4 | 0.04em | "Masons Xu" 英文名（display 旁附属）|
| `{typography.role}` | 15.76px | 500 | 1.4 | 0 | 求职定位副标题 |
| `{typography.section-title}` | 12.5px | 600 | 1 | 0.18em | uppercase section 标题 |
| `{typography.section-number}` | 11.84px | 500 | — | 0.1em | 罗马数字编号（mono）|
| `{typography.item-title}` | 15.36px | 600 | 1.4 | — | 项目 / 公司 title |
| `{typography.item-meta}` | 13.6px | 500 | 1.4 | — | 角色 / 副标题 |
| `{typography.body}` | 14.32px | 400 | 1.62 | — | bullet 与正文 |
| `{typography.caption}` | 12.5px | 400 | 1.5 | — | metric label / footer |
| `{typography.mono-time}` | 12.5px | 400 | — | 0 | 时间戳、联系方式（mono）|
| `{typography.mono-stack}` | 12.08px | 400 | 1.55 | -0.005em | 技术栈纯文本流（mono）|
| `{typography.mono-metric}` | inherit | 600 | — | — | 内联 metric（mono + 红色）|
| `{typography.print-base}` | 10.4pt | 400 | 1.55 | — | 打印模式正文基准 |

### Principles

- **二字体家族二分法**。Sans 给人读，Mono 给机器读。任何信息只要包含「时间」「URL」「技术名」「数字成果」，自动归属 Mono。
- **小字距 0.18em uppercase**。section 标题用 letter-spacing 0.18em + uppercase，模拟"打字机时代的章节标题"。配合罗马数字编号，整体语感是「RFC 文档 / IEEE 论文 / 旧版 IBM 手册」。
- **Display 字号有 clamp**。从 29.6px → 37.6px 自适应，移动端不溢出。
- **数字永远 tabular-nums**。所有时间戳、metric 数字启用 `font-variant-numeric: tabular-nums`，纵向严格对齐，模拟 spreadsheet 列对齐感。
- **weight 阶梯**：400 / 500 / 600。**禁用 700**（避免标题过粗变成"广告"），**禁用 300**（避免在打印态消失）。
- **行高 1.62 屏幕、1.55 打印**。屏幕保持论文级可读性，打印态略微压缩以满足两页规则。

### Note on Font Substitutes
- IBM Plex 通过 Google Fonts CDN 加载，子集包含 latin + latin-ext，能 cover 全部西文需求。中文走 PingFang SC（macOS / iOS 系统自带）→ Source Han Sans SC → Microsoft YaHei（Windows） fallback。
- 如果离线环境无法加载 Google Fonts，fallback 链最终落到 system-ui。在该退化下，Specsheet 视觉风格仍能保留约 85%（核心是无衬线 + 等宽 + 印章色 + 罗马数字编号）。
- **绝对避免** 使用 Inter 作为 Plex 替代 —— 它已被滥用至失去工程语感。

## Layout

### Spacing System
- **8px 网格**为主，但允许 4px 半步用于紧凑列表。
- **Tokens**：`{spacing.px-1}` 4px · `{spacing.px-2}` 8px · `{spacing.px-3}` 12px · `{spacing.px-4}` 16px · `{spacing.px-5}` 24px · `{spacing.px-6}` 32px · `{spacing.px-7}` 48px · `{spacing.px-section}` 22px。
- **Section 间距**：`section { margin-bottom: 18px }`，section header 内有 6px padding-bottom + 1px hairline。
- **打印态压缩**：所有 margin / padding 在 `@media print` 下统一压缩至 60-70%，section 间距压到 12pt（v2 调优后值）。

### Grid & Container
- **主纸面宽度**：`max-width: 760px`。这是 A4 (210mm = 794px) 内容区的接近值，转换到打印态时几乎 1:1 还原。
- **桌面屏幕**：760px 居中显示在 `{component.page-canvas}` 上，左右各留约 32px 视觉气量。
- **Metric Grid**：4 列等宽，gap 12px，仅 Hero 下方使用一次。
- **Skills DL**：`grid-template-columns: 150px 1fr`，dt 固定 150px 宽，dd 自适应。这样所有 dt 标签纵向严格对齐，模拟 man page 的 `.IP` 缩进。

### Whitespace Philosophy
密度高但留白克制。每一处留白都是"语义间隔"：
- section 之间 18px = "翻篇"。
- experience-article 之间 14px = "下一段同源经历"。
- bullet 之间 4px = "同主题继续"。
- hero 与第一个 section 之间 22px = "标题页结束，正文开始"。

不留装饰性留白。任何 > 32px 的纵向空白都被视为"超预算"。

## Elevation & Depth

| Level | Treatment | Use |
|---|---|---|
| Flat | 无 | 全部元素 |
| Hairline | 1px `{colors.hairline}` | section header 底、Hero block 底、metric-grid 上下、footer 顶 |
| Underline | 1px `{colors.hairline-strong}` | 链接下划线 |
| Seal Line | 4px × 56px `{colors.seal}` solid bar | 顶部唯一装饰，模拟红色印章 |

**Shadow 哲学**：**完全没有 box-shadow**。这是 Specsheet 与 Archive 最干净的切割。所有"层级"由 hairline 完成，所有"权重"由字号 / 字重完成，所有"强调"由颜色（印章红）完成。

### Decorative Depth
**只有一处装饰** —— 顶部 4px × 56px 的印章红横条 `{component.seal-line}`。
- 不是宽度全屏的 banner，而是一个左对齐、有限宽度的"印记"。
- 模拟红色印章 / 橡皮章 / 文档编号条 的视觉。
- 在打印态保留为同色硬条（`-webkit-print-color-adjust: exact`）。

## Shapes

### Border Radius Scale
- **`{rounded.none}` 0px** 是唯一的圆角值。
- 所有元素（包括如果未来引入的按钮、卡片、输入框）都必须 `border-radius: 0`。
- 例外：无。

### Photography Geometry
- **零图像引用**。当前简历的 SVG logo 也被取消 —— Specsheet 是纯文字文档，姓名本身就是"标识"。

## Components

### Page Container
**`{component.page-canvas}`** — `body`。象牙白底色，32px 上下 padding + 24px 左右 padding（移动端缩小）。无背景渐变、无网格、无光晕。

**`{component.resume-sheet}`** — `main.resume`。760px 居中。**没有 border、没有圆角、没有阴影、没有内边距框** —— 它就是一张纸，直接坐落在象牙白底色上，与 page-canvas 在视觉上是一体的（`{colors.paper}` 与底色相同）。

### Seal Line
**`{component.seal-line}`** — `<hr class="seal-line">`。位于 hero 顶部。
- 4px 高 × 56px 宽。
- `background-color: {colors.seal}`。
- 上下 margin：0 0 18px 0。
- 全简历**唯一**的视觉装饰，承担"这是一份正式文档"的全部视觉证据。

### Hero Block
**`{component.hero-block}`** — `<header>`。内含：
1. `{component.seal-line}` —— 印章顶饰。
2. `<h1 class="hero-name">徐俊飞 <span class="hero-name-en">Masons Xu</span></h1>` —— 中英文姓名一行。
3. `<p class="hero-role">Go 后端架构师 · 分布式系统 · 云原生基础设施</p>` —— 副标题。
4. `<address class="hero-contacts">` —— mono 等宽体的联系方式流，使用 ` · ` 分隔。
5. 1px hairline 底边 + 22px margin-bottom。

### Section Header
**`{component.section-header}`** — 每个 section 顶部。
- `display: flex; align-items: baseline; gap: 10px`。
- 左：`<span class="section-number">I</span>` —— 罗马数字 mono 编号（红色）。
- 右：`<h2 class="section-title">PROFILE</h2>` —— uppercase Sans 标题（黑色）。
- 底：1px hairline 分割线。

### Experience Article
**`{component.experience-article}`** — `<article>` 包裹一段经历或项目。
- 顶部 `<header class="experience-header">`：left = item-title（公司 / 项目名）、right = mono time（`<time>` 标签）—— flex justify-between。
- 中间 `<p class="experience-meta">`：角色 / 定位副标题（柔墨色）。
- 下方 `<ul class="bullet-list">`：3-4 条 STAR 结构 bullet。
- 不需要 left rail、不需要圆点装饰。

### Metric Grid
**`{component.metric-grid}`** — Hero 后紧跟的关键指标 4 格。
- `grid-template-columns: repeat(4, 1fr)`，gap 12px。
- 每格 `{component.metric-cell}`：
  - 大数字（`{component.metric-cell-value}`）—— 1.4rem mono 红色加粗。
  - 小标签（`{component.metric-cell-label}`）—— 0.78rem caption 静墨。
- 上下各 1px hairline，构成"数据带"。
- 这是简历中**信息密度最高**的一段，HR 30 秒扫读的命中点。

### Bullet List
**`{component.bullet-list}`** — 不带项目符号的 ul。
- `list-style: none; padding-left: 16px`。
- 每个 `<li>` 在 ::before 显示 `›` 字符（U+203A）+ 8px 右间距。
- ATS 解析时，list-style: none 让 OCR 跳过装饰直接读 li 内容；`›` 字符放在 ::before 也不会被提取（伪元素 content 不进入 DOM 文本流）。

### Inline Metric
**`{component.metric-inline}`** — `<span class="metric">{value}</span>`。
- 字体 IBM Plex Mono、weight 600、color 印章红、tabular-nums。
- 用于句中数字：「响应时间降低 <span class="metric">50%</span>」「<span class="metric">99.9%</span> 可用性」。
- 不影响 ATS：包裹的仍然是普通文本。

### Skills (Definition List)
**`{component.skills-dl}`** — `<dl>`。
- `grid-template-columns: 150px 1fr`，rowGap 8px。
- `<dt>` 是技能域标题（黑色 Sans 加粗）。
- `<dd>` 是逗号分隔的纯文本流（mono 柔墨色）。
- **关键**：技能 dd 是纯文本，**没有 span tag、没有圆点、没有胶囊**。这让 ATS 100% 完整提取关键词。

例：
```html
<dl class="skills-dl">
  <dt>Go Distributed</dt>
  <dd>Go 1.24+, Kitex RPC, Hertz HTTP, gRPC, Thrift IDL, Wire DI, etcd, Casbin RBAC</dd>
</dl>
```

### Link
**`{component.link-inline}`** — `<a>`。
- `color: {colors.ink}` 黑色（不染色）。
- `text-decoration: underline`，下划线色 `{colors.hairline-strong}` (#a8a8a8)。
- `text-underline-offset: 2px`，让下划线与字底有 2px 呼吸。
- 在 PDF 中保留 href，可点击。
- 视觉上像"被铅笔划线的页码引用"。

### Selection
**`{component.selection-style}`** — `::selection`。
- background: rgba(185, 28, 28, 0.12)。
- 用户选中文字时呈现淡红色调。

### Footer
**`{component.resume-footer}`** — `<footer>`。
- 顶部 1px hairline。
- 12px padding-top。
- caption 字号，静墨色。
- 内容：版本号 / 更新日期 / 来源 URL —— 像 RFC 文档底部的元数据。

## Do's and Don'ts

### Do
- 用 `{colors.seal}` 印章红**只**承担三件事：顶饰条、罗马数字编号、metric 数字。
- 所有时间戳、技术栈、URL、邮箱用 IBM Plex Mono 等宽体 + tabular-nums。
- bullet 用 STAR 结构：「在 X 场景下，通过 Y 方法，实现 Z 量化结果」—— Z 用 `<span class="metric">` 包裹。
- 使用语义化标签：`<article>`, `<header>`, `<time>`, `<address>`, `<dl>`, `<dt>`, `<dd>`, `<h1>`-`<h3>`。这些 ATS 全部认。
- section 标题用 uppercase + 0.18em letter-spacing，配合罗马数字编号，模拟 RFC 段落抬头。
- 链接保持黑色 + 灰色下划线，PDF 中 href 与文本同步可识别。
- 数字永远 mono + tabular-nums，纵向对齐让 HR 扫读更快。

### Don't
- 不要给链接染印章红 —— 它是 metric 专属。
- 不要使用 box-shadow / transform / animation（除 fade-in 之类无害的可访问性动画）。
- 不要使用圆角 —— 全局 0px。
- 不要使用 tag 胶囊 / Chip 组件 —— ATS 杀手。技能必须用 dl/dd 纯文本流。
- 不要使用衬线字体 —— 会立刻打回 Archive 老路。
- 不要使用项目符号（实心圆点）—— 用 `›` 字符代替，但放在伪元素中避免 ATS 提取。
- 不要使用多列布局 —— ATS 解析多列时极易错乱。
- 不要使用图标库 / SVG icon —— 文字简历不需要图标。
- 不要 inline 样式 —— 全部走类与 CSS 变量。
- 不要在打印态保留任何阴影 / 渐变 / 不透明度 < 1。
- 打印基准应在 9.5-11pt 区间调优 —— 当前 10.4pt 是 A4 双页与可读性平衡的甜蜜点；低于 9.5pt 损可读性，高于 11pt 易爆三页。

## Responsive Behavior

### Breakpoints

| Name | Width | Key Changes |
|---|---|---|
| Mobile | ≤ 720px | page-canvas padding 缩到 20px 16px；hero-name clamp 自动缩小；metric-grid 改为 2×2 网格；skills-dl 改为单列堆叠 |
| Desktop | > 720px | 760px max-width 居中；metric-grid 4 列；skills-dl 双列 grid |
| Print A4 | `@page A4 8mm 8mm` | 字号 10.4pt / 1.55 行高；section 间距 12pt；强制 2 页内 |

### Touch Targets
- 链接最小高度 ~22px（行高 1.62 × 13.6px ≈ 22px），移动端可点。
- 联系方式 hero-contacts 包含 mailto: 与 https:// URL，全部可点击。

### Collapsing Strategy
- 单列原本就是默认状态，collapsing 主要是 metric-grid（4 → 2 列）和 skills-dl（双列 → 单列）。
- 没有 nav，没有 sidebar，没有 sticky，没有 modal。

## Iteration Guide

1. 始终用 token 而非 hex —— 颜色升级只改 `:root`。
2. 新增 section 时遵守 `<section>` → `<header class="section-header">` → `<span class="section-number">` + `<h2 class="section-title">` 的模式。
3. 新增数字必须 `<span class="metric">` 包裹。
4. 新增技术栈必须放进 `<dl class="skills-dl">` 的 `<dd>`，纯文本逗号分隔。
5. 任何"想加视觉装饰"的提议都必须先解释"为什么 hairline 和印章红不够"。
6. 任何打印模式调整必须用 Chrome 的"另存为 PDF"功能验证 A4 双页（不是 Microsoft Print to PDF）。
7. 任何对 ATS 友好性的修改必须先在 jobscan.co 或类似工具检查关键词识别率。

## Known Gaps

- **暗色模式**：未实现，预留色 token 时已经预设 `prefers-color-scheme: dark` 支持，未来可加深底色 + 反转 ink。
- **多语言切换**：当前是中文为主 + 英文混排，没有完整 i18n 路径；如果要给海外公司投递，需要一份英文版（可复用同一套 CSS 与 DESIGN.md，仅替换内容）。
- **照片**：刻意不加。Specsheet 的语感拒绝照片 —— 工程文档不放作者头像。如果某些行业（金融、咨询）必须要照片，可以在 hero-block 内右浮 80×100px 的灰度照片，但要单独评估。
- **图标**：刻意不加。所有"标签"都用文字承载（Email / GitHub / Phone）。
- **下载按钮 / Print 按钮**：当前没有内嵌交互组件。如果在网页版需要"下载 PDF"按钮，应放在 hero-contacts 行右端，用 `{component.link-inline}` 样式（黑字 + 下划线）。
- **PWA / Service Worker**：超出文档语义范围。
- **打印态字色折扣**：某些低端打印机无法保留 #b91c1c 印章红，会渲染成深紫红 —— 这是物理层限制，不是 CSS 问题。
- **ATS 识别率**：尽管已极力优化，但每个 ATS 厂商（Workday / Greenhouse / Lever）的解析器实现有差异。建议对每家目标公司做一次 jobscan 验证，并保留一份 .docx 版本作为兜底。
