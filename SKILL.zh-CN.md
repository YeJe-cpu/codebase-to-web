---
name: web-learning-github
description: "Agent skill（Web Learning GitHub）：与 SKILL.md 行为一致。默认整页随对话语言；可应用户要求生成带中英文切换的单个 HTML。默认输出 web/<owner>-<repo>.html。宿主：Cursor、Claude Code、Windsurf、OpenClaw。"
---

# Agent Skill 仓 → 单文件可视化 HTML（Web Learning GitHub）

## 产出语言（必遵守）

- 用户以**中文**为主 → 生成的 HTML **全文中文**。
- 用户以**英文**为主 → **全文英文**。
- 中英混杂 → 随**主导语言**；未声明时国际化 clone 以 `SKILL.md` 默认可偏英文。

### 可选：同一 HTML 内中英文切换

用户**明确要求**「一个文件里 EN / 中文 点按钮切换」且不要两个文件时：为每段可见内容做 **英文块 + 中文块**（如 `i18n-en` / `i18n-zh`），加 **EN | 中文** 或下拉框与少量 JS 切换显隐；**默认**以用户先发语言或英文为主。GitHub 元数据区与目录树可共用，标签翻译即可。

> 多数宿主只会自动读 **`SKILL.md`**。若环境只加载一份，可把本文件合并进 `SKILL.md` 或按团队约定 symlink。

## 目标

交付**本地可双击打开**的单文件 HTML，帮助读者理解「装完 / 触发之后谁在对谁做什么」，并对照 Star/Fork 与目录结构——偏**学习、扫盲与路径理解**，不是帮你生成上线代码脚手架。

## 落盘规则（重要）

- **默认**：一个仓库 → **一个独立 HTML** → **`web/<owner>-<repo>.html`**。
- **多仓库**：同一条需求多个仓或要求 Tab 整合时，可输出单一整合 HTML；无偏好时 **优先多个单文件**。
- 产出放在约定目录，本 skill 默认识别 **`web/`**。

本仓库自带 **`web/index.html`**（中英切换示意）、**`web/demo.html`**（跳转至前者）；为他人仓库生成说明时请写入 **`web/<owner>-<repo>.html`**，勿覆盖上述文件。

## 宿主与安装路径（生成说明文 / journey 时可引用）

| 宿主 | 典型 skill 目录（示例） |
|------|-------------------------|
| **Cursor** | 项目内 `.agents/skills/<skill-folder>/` |
| **Claude Code** | `~/.claude/skills/<skill-folder>/` |
| **Windsurf** | 以 Windsurf / Cascade 当前文档为准 |
| **OpenClaw** | 如 `~/.openclaw/skills/`、`~/.agents/skills/`、工作区 `skills/` 等，参见 [OpenClaw · Skills](https://docs.openclaw.ai/skills/) |

若用户未指定宿主，正文可用泛称 **「宿主 / Agent IDE」**。

## 固定版式顺序

1. **GitHub 元数据条**  
2. **大白话**  
3. **交付物 blurb**  
4. **组件路径（必须在分步旅程之前）**  
5. **分步旅程**（表面上 / 背后）  
6. **仓库骨架** `pre.tree`  
7. **README 简析**  

## 视觉

读 `references/ui-tokens.zh-CN.md` 与 `references/frontend-design-notes.zh-CN.md`。**Lab·Canonical** 为默认视觉代号；变体 A/B 仅用户明确要求时使用。

## Chat 脚本

每个 `.chat-window`：`typing-avatar` id 为 `{chatWindowId}-typing-avatar`；消息初始 `display:none`；进度按 `.chat-message` 自动计算。

## 扩展阅读（中文）

先看 **`references/README.md`**。

- `references/workflow.zh-CN.md`
- `references/ui-tokens.zh-CN.md`
- `references/frontend-design-notes.zh-CN.md`

**English:** `SKILL.md` + `references/*.md`。
