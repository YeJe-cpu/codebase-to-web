---
name: web-learning-github
description: "Agent skill：Agent Skill 仓 → 单个自包含 HTML — SVG 组件路径、步进注解、学习/模拟器/深度探索 Tab、journey-fold 折叠清单。默认 web/<owner>-<repo>.html。语言随用户或 README 级双语切换。宿主：Cursor、Claude Code、Windsurf、OpenClaw。"
---

# Agent Skill 仓 → 单文件可视化 walkthrough（Web Learning GitHub）

## 目标

产出**可本地双击**的单个 HTML，说明某个 Agent Skill 仓 **安装 → 触发 → 读文件顺序**，并带上 Star/Fork 与目录上下文——偏**学习与路径理解**，不是业务脚手架生成器。

## 产出语言（必遵守）

- **默认：**随用户提示的**主导语言**单页输出（中文或英文为主；混杂时随主导；未说明时国际化场景可偏英文）。
- **README / 演示：**需要双语界面时 → **单文件** + **EN | 中文** 切换（`html.is-en` / `is-zh`），元数据条与目录树共用一套数据。

## 落盘规则

- **克隆本 skill 包：** 一仓 **`web/<owner>-<repo>.html`**（默认）或用户指定路径。
- **维护者实验室：** 可写 **`30_resources/oss-skill-lab/<owner>-<repo>.html`**（相对含 `30_resources/` 的工作区）；以当场约定为准。
- **多仓库：**无特殊要求时**优先多文件**；若要单页 Tab 再在对话里定。

## 宿主（旅程 / 安装表述）

| 宿主 | 典型目录 |
|------|----------|
| **Cursor** | `.agents/skills/<skill-folder>/` |
| **Claude Code** | `~/.claude/skills/<skill-folder>/` |
| **Windsurf** | 以官方文档为准 |
| **OpenClaw** | 如 `~/.openclaw/skills/` — [Skills](https://docs.openclaw.ai/skills/) |

未指定宿主时可用 **「宿主 / Agent IDE」**。

## 区块顺序（典型）

1. **GitHub 元数据条** — 链接、Star、Fork、创建时间  
2. **Hero** — 场景、安装提示、主题与语言切换  
3. **`.viz-panel`** — **`.viz-sticky-stack`**（`.viz-head` + `.viz-rail-captions`）+ **`.viz-grid`**（SVG + **`.anno`**）；**步数随真实仓库**  
4. **Tabs** — 学习 / 模拟器 / 深度探索  
5. **目录树** + **README 式要点**  
6. **`journey-fold`** — 折叠区「装好以后怎么用」等；建议 summary：**「装好以后怎么用（与组件路径、模拟器对照）」**。**本仓库金 / 银参考页均包含**。

## 交互与版式（Canonical，必遵守）

必读 **`references/walkthrough-canonical-ui.zh-CN.md`** 与 **`references/workflow.zh-CN.md`**。

**必须做到：**

- **`.viz-sticky-stack`** 包住 **`.viz-head`** 与 **`.viz-rail-captions`**；**sticky 在外层**，不要只粘在 `.viz-head`
- **`.viz-panel`：** 使用 sticky 时 **勿 `overflow: hidden`**
- **`.viz-grid`：** 可负责下圆角 + `overflow: hidden`
- 注解含 `<code>` / `<strong>` 时用 **`innerHTML`**

**本仓库参考页**（由真实 GitHub skill 仓转生的金 / 银样本，各仅一份）：

- `web/colleague-skill-prototype-gold.html` · 上游 **titanwings/colleague-skill**
- `web/lark-minutes-tasks-walkthrough.html` · 上游 **zarazhangrui/lark-minutes-tasks**

## 配色与装饰

遵守 **`references/ui-tokens.zh-CN.md`**、**`references/frontend-design-notes.zh-CN.md`**。

## 扩展阅读

- **`references/README.md`**
- **`references/workflow.zh-CN.md`**

**English:** `SKILL.md`, `references/*.md`。
