# Repo to Skill Lab

一款 **Claude Code** skill：把 GitHub 上的 **Agent Skill 仓库** 变成**漂亮、自持的单文件 HTML「实验室」**。

指向一个 skill 仓，拿回**可双击打开**的页面——带**区块化阅读**、**可步进的组件路径 journey**（谁加载谁）、**大白话**、**目录树**、以及 **README 热度简析**——避免典型大紫渐变「AI 皮肤」。

> **README 双轨（任选其一作为 GitHub 默认显示）：**  
> - **Track B（本文件）** — 段落节奏 **严格对标** [zarazhangrui/codebase-to-course](https://github.com/zarazhangrui/codebase-to-course)。  
> - **Track A** — 用 [jonathimer/devmarketing-skills](https://github.com/jonathimer/devmarketing-skills) 的开发者受众视角来写，**并注明参照了哪些子 skill**（**不随本仓捆绑**）。见 [Track A 中文](docs/README-track-a.zh-CN.md) · [Track A EN](docs/README-track-a.md)。  
> **仓库取名：** [docs/REPO_NAME_IDEAS.md](docs/REPO_NAME_IDEAS.md) · **GitHub About 怎么填：** [docs/GITHUB-ABOUT.md](docs/GITHUB-ABOUT.md)

[English (Track B)](README.md)

---

## 适合谁？

**「收藏了_skill_但还要干活的人」** —— 你已经在用 Claude Code、Cursor、Windsurf 等。你会 **star 各种 skill 仓**（或内置 `anthropics/skills`、社区包、公司内 `SKILL.md` 树）。能用，但缺一张**可信的** **安装 → 触发 → 读哪些文件 → README  hype 意味着什么** 的总图。

**目标很实际，不做论文：**

* **指挥 agent**：斜杠命令 / 目录到底怎么扫  
* **快速验 README**：「只要 clone」是否掩盖了 Hook  
* ** onboarding 同事**：不用屏幕共享十几份 Markdown  
* ** Maintainer 对齐**：共享同一份 HTML 实验室稿  

---

## 实验室页长什么样？

**单个 `.html`** —— 无需打包、`npm install`；字体首次需联网（Google Fonts）。包含：

* **GitHub 元数据条** —— Star / Fork / 创建时间（页脚注明**快照**）
* **大白话** —— 一句话说清干嘛的  
* **可步进 journey** —— 用户 → 宿主 → skill / ref …（**条数随真实路径**，不设死四格演示）
* **分步** —— 表面上 vs 背后（文件 / Hook）
* **目录树** —— 与 README 对齐的 monospace 骨架  
* **README 简析** —— 需求 / 传播 / 壁垒 / 合规，各一行  
* **有辨识度的视觉** —— 默认 **Lab·Canonical**（Fraunces + Source Sans 3 + 陶土强调）；理念对齐 [Anthropic `frontend-design`](https://github.com/anthropics/skills/tree/main/skills/frontend-design)；可要求冷色 / 青绿工程变体  

---

## 怎么用

### 作为 Claude Code skill

1. 将 `repo-to-skill-lab` 文件夹复制到 `~/.claude/skills/`（Cursor 可用 `.agents/skills/repo-to-skill-lab/`）。  
2. 在项目里对模型说：**「把 `owner/repo` 做成 Skill 实验室单页。」**

### 产出路径

默认 **`skill-lab/<owner>-<repo>.html`**；可在对话里改输出目录。

---

## 触发示例

* “把这个 skill 仓生成实验室 HTML”  
* “组件路径 journey 在前，再分步”  
* “单页讲清 `SKILL.md` 树”  
* “Turn this skills repo into a Skill Lab HTML”

---

## 设计理念

### 先 journey，再文件夹

学习材料常从树开始；从业者从**输入什么**、**回来什么**开始。本 skill **强制组件路径先于长文分步**。

### 能走流程就不用长段

能用**步进对话**或**树**表达的，不写六段说明；每块 blurb 控制在两三句。

### 单文件、可分享

文件名 **`owner-repo.html`**，方便 diff、打包、附件；**无构建**就少一层「产物对不上」的风险。

### 与 Codebase to Course 互补

**应用代码**深读用 [zarazhangrui/codebase-to-course](https://github.com/zarazhangrui/codebase-to-course)；**Skill 包 / 触发链**用 **Repo to Skill Lab**。

---

## 目录结构

```
repo-to-skill-lab/
├── SKILL.md
├── references/
├── docs/                    # Track A、取名、GitHub About
├── skill-lab/
├── README.md
└── README.zh-CN.md          # Track B（本文件）
```

详见英文 [README.md](README.md) 中的完整树。

---

## 许可证

MIT — 见 [LICENSE](LICENSE)。
