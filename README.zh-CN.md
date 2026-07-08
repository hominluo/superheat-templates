# Superheat™ 模板库

[English](README.md) · **中文**

品牌标准的模板、设计系统和 AI 智能体技能,用于制作 **Superheat 融资路演 PPT、销售 PPT 和白皮书**
—— 让团队里的任何人都能快速做出格式规范、符合品牌的文档,而不用从空白页开始。
可以手动使用,也可以直接让 **Claude Code** 或 **Codex** 帮你生成(见[使用方法](#使用方法))。

> 加热器只是商品,**呈现方式**不该是。每一份 Superheat 的 PPT 和白皮书都应看起来出自同一体系
> —— 同样的橙色、同样的 Geist 标题、同样的 DM Mono 数字、同样的像素风格。

## 目录结构

```
superheat-templates/
├── design-system/     品牌规范:颜色、字体、组件、语气 + 标准 CSS
│   ├── README.md              ← 品牌手册(从这里开始)
│   ├── superheat-tokens.css   ← 颜色、字体族、reset
│   ├── superheat-deck.css     ← 16:9 PPT 布局 + 组件
│   └── superheat-whitepaper.css ← Letter 页面布局 + 组件
├── templates/         复制即用的起点(自包含 HTML)
│   ├── pitch-deck/     template.html + 说明  → 16:9 幻灯片,横向 PDF
│   └── whitepaper/     template.html + 说明  → US-Letter 页面,纵向 PDF
├── components/        每种区块的可复制粘贴代码(数字、表格、卡片……)
├── skills/            AI 智能体技能 —— “做一个关于 X 的 Superheat PPT”
│   ├── superheat-pitch-deck/
│   └── superheat-whitepaper/
├── examples/          指向标准参考 PPT 和白皮书的说明
├── AGENTS.md          智能体操作手册(Codex 及任意工具)—— 工作流 + 品牌规则
├── CLAUDE.md          Claude Code 专用说明(其余遵循 AGENTS.md)
└── CONTRIBUTING.md    如何修改品牌规则并保持一致
```

## 使用方法

**最简单:直接让 AI 智能体来做。** 在 **Claude Code** 或 **Codex** 中打开本仓库,然后说:

> “用这份 memo 做一个 Superheat 路演 PPT。” · “写一份关于 X 的 Superheat 白皮书。”

智能体会自动读取规则(`CLAUDE.md` / [`AGENTS.md`](AGENTS.md)),复制对应模板,填充你的内容,
并生成可直接打印成 PDF 的 HTML 文件。无需任何配置。

*在 Claude Code 里想把它变成一个命令?* 安装一次技能即可:

```bash
cp -r superheat-templates/skills/*  ~/.claude/skills/
```

**或者手动制作。** 复制 [`templates/pitch-deck/template.html`](templates/pitch-deck/)
或 [`templates/whitepaper/template.html`](templates/whitepaper/),替换其中的 `[[占位符]]`,
在 Chrome 中打开,打印成 PDF。无需构建,无依赖。

## 品牌速览

- **颜色:** 唯一强调色 —— Superheat 橙 `#FF5500` —— 配黑/白底。绝不使用第二种颜色。
- **字体:** **Geist**(标题和正文,字重 400/300)、**DM Mono**(所有数字和数据)、
  **Press Start 2P**(像素风小标题和标签)。通过 Google Fonts 加载。
- **手法:** 标题用两种颜色表达重点 —— 铺垫用黑色,落点用 `<span class="a">橙色</span>`。
  数字一律用等宽字体。每页只留一个橙色亮点。
- **语气:** 用论断而非标签;数字优先;始终保留诚实的注脚。

完整规则 → [`design-system/README.md`](design-system/README.md)

## 导出 PDF

两个模板都能在 Chrome 中零配置打印(`Ctrl/Cmd-P` → **另存为 PDF**、**开启背景图形**、**边距设为无**):

- **PPT** → 布局选**横向**,若有选项选纸张 `1280×720`。
- **白皮书** → 布局选**纵向**,纸张选 **Letter (8.5×11)**。

## 参考资料

本设计系统提炼自 Superheat 现有的战略 PPT 和白皮书 memo。参见 [`examples/`](examples/)
了解它们在 [`superheat-workspace`](https://github.com/hominluo/superheat-workspace) 仓库中的位置。

---

由 Superheat 团队维护。要修改品牌规则?请先阅读 [`CONTRIBUTING.md`](CONTRIBUTING.md)
—— CSS 有意分布在两处(设计系统 + 模板),必须保持同步。
