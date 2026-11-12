# Scientific Figure Rebuilder

中文 | [English](#english)

一个面向 Codex 的科研图示重建技能：帮助 AI Agent 根据参考图片或已有 Office 文件，制作**可继续编辑**的 Visio 图或 PowerPoint 图示。

## 适合做什么

- 重建论文中的模型结构图、系统架构图、流程图和多面板示意图。
- 根据参考图调整现有图示的文字、布局、颜色或连接关系。
- 制作可编辑的 Visio `.vsdx` 或 PowerPoint `.pptx`，并按需检查预览及导出结果。

目标是尽量保留可单独编辑的形状、文字和连接线，而不是把整张参考图插入文件。Visio 和 PowerPoint 的可编辑版本需要分别制作和验证；从 Visio 导出的一整页图片不能当作原生可编辑 PPT。

## 使用前须知

- 这是给 AI Agent 使用的**工作流程和检查指南**，不是自带转换程序的一键工具；生成方式和效果取决于所使用的 Agent、模型和可用工具。
- 使用 Office 自动化时，需要目标机器上有可用的 Visio 或 PowerPoint、相应许可及适合运行的 Windows 环境。远程或非交互式 SSH 环境不一定能正常启动 Office。
- 复杂插画可能需要作为独立图片素材保留，具体可编辑程度应在交付时说明；不要把整个页面当成图片交付并声称全部可编辑。
- 本技能面向结构示意图，不适合替代基于真实实验数据绘制统计图；不应根据图片猜测或编造数据。

## 安装

先克隆仓库并进入目录：

```bash
git clone https://github.com/2859493743/scientific-figure-rebuilder.git
cd scientific-figure-rebuilder
```

在 Windows PowerShell 中，将技能目录复制到当前用户的 Codex 技能目录：

```powershell
Copy-Item -Recurse .\scientific-figure-rebuilder "$env:USERPROFILE\.codex\skills\scientific-figure-rebuilder"
```

如果目标目录已存在，请先检查并备份，避免覆盖已有技能。安装后按需重启或重新加载 Codex，让它发现新技能。

## 使用示例

把参考图交给 Codex，并说明需要的格式和编辑粒度，例如：

> 使用 `scientific-figure-rebuilder`，把这张模型结构图重建为可编辑的 Visio 文件。保留原图中的模块文字和箭头方向，并给我一张预览图。

如果还需要可编辑的 PowerPoint，可以补充：

> 同时制作一份 PowerPoint 原生形状版本，保证主要模块和连接线可以分别编辑；请说明哪些复杂素材仍是图片。

检查结果时，建议在 Visio 或 PowerPoint 中打开文件，尝试移动模块、修改文字，并核对箭头、布局和参考图中的技术关系。

## 项目结构与许可

```text
scientific-figure-rebuilder/
├── README.md
├── LICENSE
└── scientific-figure-rebuilder/
    └── SKILL.md
```

本项目采用 [MIT 许可证](LICENSE)。Microsoft Visio 和 PowerPoint 是独立的商业产品，不随本项目分发。

---

## English

A Codex-compatible skill for rebuilding research architecture diagrams and flowcharts as editable Microsoft Visio or PowerPoint figures.

## What it does

- Reconstructs diagrams from reference images or edits existing Office diagrams.
- Distinguishes editable Visio output from a separately editable PowerPoint output.
- Guides verification of labels, layout, connectors and exports.

This is an instruction skill, not a turnkey converter. The agent must select and implement appropriate drawing tools for each task. Visio and PowerPoint automation depends on locally available applications, licenses and a suitable interactive Windows environment. It does not promise fully automatic reconstruction or support for every drawing format. Statistical charts should be produced from the actual data with appropriate plotting tools.

## Install

Copy the `scientific-figure-rebuilder` folder into your Codex skills directory, for example on Windows:

```powershell
Copy-Item -Recurse .\scientific-figure-rebuilder "$env:USERPROFILE\.codex\skills\scientific-figure-rebuilder"
```

Restart or reload the agent if required. Do not overwrite an existing skill without checking it first.

Example request: “Rebuild this model diagram as an editable Visio file and a separate editable PowerPoint slide. Preserve the arrow directions and provide previews.”

## License

MIT; see [LICENSE](LICENSE). Microsoft Visio and PowerPoint are separate proprietary products and are not distributed by this repository.
