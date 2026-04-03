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

- **对外开源的 skill 包（本仓库）**：一个仓库 → **一个 HTML** → **`web/<owner>-<repo>.html`**。
- **维护者本机实验室**（多项目工作区）：用户希望生成物**不进 skill 仓**或统一放在 **OSS 实验目录**时，可另写或只写 **`30_resources/oss-skill-lab/<owner>-<repo>.html`**（相对于同时包含 `web-learning-github/` 与 `30_resources/` 的父目录；他人克隆后若无此路径，以用户当场约定为准）。
- **多仓库**：同一需求多仓或要 Tab 合一页时，可输出整合 HTML；无偏好时 **优先多文件**。
- 若 **`web/`** 与 **实验室目录** 都要，在对话里**确认**；**陌生人只用本 skill 时默认仍写 `web/`**。

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

## 视觉与版式（FD‑pass 壳）

除非用户另有要求，**版式与交互对齐 fd-pass 实验室页**：

- **页面**：`.shell`、渐变底、`.hint`、`.meta-bar`、`.plain`、`.blurb`、`.section-title`、`.readme-box`、`footer`（参见本仓 `web/YeJe-cpu-web-learning-github.html` 或任 `*.fd-pass.html` 参考）。
- **组件路径**：`.path-wrap` → `.chat-window` → `.chat-messages`（带头像气泡）、`.chat-typing` 内 **`#<chatWindowId>-typing-avatar`**、控制条含 **下一条 / 全部播放 / 重播** 与 **`.chat-progress`**。
- **分步**：`.step` + **`.grid2`**（宽屏两列）：`.card.user`（表面上）与 `.card.back`（背后）。
- **目录树**：`pre.tree`，可用 `.f` / `.n` 区分路径与注释。

读 `references/ui-tokens.zh-CN.md`、`references/frontend-design-notes.zh-CN.md`。**Lab·Canonical** 色板；**变体 A/B** 仅用户要「盲盒 / wildcard」时使用。

## Chat 脚本

每个 `.chat-window`：`typing-avatar` id = `{chatWindowId}-typing-avatar`；`.chat-message` 初始 `display:none`；**fd-pass 同款** 逐步展示、**全部播放**、**重播**；进度为「已 reveal / 总数」。

## 扩展阅读（中文）

先看 **`references/README.md`**。

- `references/workflow.zh-CN.md`
- `references/ui-tokens.zh-CN.md`
- `references/frontend-design-notes.zh-CN.md`

**English:** `SKILL.md` + `references/*.md`。
