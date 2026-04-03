---
name: codebase-to-web
description: "中文版技能说明（与 SKILL.md 行为一致）。产出语言：用户主要用中文对话则整页中文；主要用英文则整页英文。默认输出 web/<owner>-<repo>.html。宿主：Cursor、Claude Code、Windsurf、OpenClaw。"
---

# Agent Skill 仓 → 单文件可视化 HTML（Codebase to Web）

## 产出语言（必遵守）

- 用户以**中文**为主 → 生成的 HTML **全文中文**（标题、大白话、journey、分步标签、README 要点、页脚）。
- 用户以**英文**为主 → **全文英文**。
- 中英混杂 → 随**主导语言**；不清楚时，若用户未声明，可默认中文（你在纯中文工作区时）或英文（国际化仓库 clone 时以 `SKILL.md` 为准）。

> 多数宿主只会自动读 **`SKILL.md`**。若你的环境只加载一份文件，可把本文件内容合并进 `SKILL.md`，或按 README 用符号链接/拷贝（团队自定）。

## 目标

交付**本地可双击打开**的单文件 HTML，帮助读者理解「装完 / 触发之后谁在对谁做什么」，并对照 Star/Fork 与目录结构。

## 落盘规则（重要）

- **默认**：一个仓库 → **一个独立 HTML** → **`web/<owner>-<repo>.html`**（或用户在对话里指定的目录）。保持一仓一文件。
- **多仓库**：用户在同一条需求里给出 2+ 个仓库，或要求「整合成 Tab 页」时，可输出单一整合 HTML；无偏好时 **优先多个单文件**。
- 不要把生成的 HTML 散落在与项目无关的路径根目录；与用户约定统一输出目录（本 skill 默认识别 **`web/`**）。

## 宿主与安装路径（生成说明文 / journey 时可引用）

| 宿主 | 典型 skill 目录（示例） |
|------|-------------------------|
| **Cursor** | 项目内 `.agents/skills/<skill-folder>/`（或.team 约定） |
| **Claude Code** | `~/.claude/skills/<skill-folder>/` |
| **Windsurf** | 以 Windsurf / Cascade 当前文档为准 |
| **OpenClaw** | 如 `~/.openclaw/skills/`、`~/.agents/skills/`、工作区 `skills/` 等，参见 [OpenClaw · Skills](https://docs.openclaw.ai/skills/) |

若用户未指定宿主，正文可用泛称 **「宿主 / Agent IDE」**。

## 固定版式顺序

1. **GitHub 元数据条**：链接、`stargazers_count`、`forks_count`、`created_at`（UTC）。
2. **大白话**（`plain`）：零术语场景句。
3. **交付物 blurb**：Markdown / Hook / 脚本等形态。
4. **组件路径（必须在分步旅程之前）**：可播放 journey；`data-sender`；复杂项目 6–15 条。**可**点名 Cursor / Claude Code / OpenClaw。
5. **分步旅程**：每步「表面上」/「背后」。
6. **仓库骨架**：`pre.tree`。
7. **README 简析**：需求 / 传播 / 壁垒 / 合规，各 1 bullet。

## 视觉

读 `references/ui-tokens.zh-CN.md` 与 `references/frontend-design-notes.zh-CN.md`。变体 A/B 仅用户明确要求或「盲盒」时使用。

## Chat 脚本

每个 `.chat-window`：`typing-avatar` id 为 `{chatWindowId}-typing-avatar`；消息初始 `display:none`；进度按 `.chat-message` 自动计算。

## 扩展阅读（中文）

先看 **`references/README.md`**（用大白话说明本目录每个文件是干什么的）。

- `references/workflow.zh-CN.md`
- `references/ui-tokens.zh-CN.md`
- `references/frontend-design-notes.zh-CN.md`

**English:** `SKILL.md` + `references/*.md`（无 `.zh-CN` 后缀）。
