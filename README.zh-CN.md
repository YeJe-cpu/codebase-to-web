# Web Learning GitHub

跑在 Cursor、Claude Code、Windsurf、OpenClaw 等环境里的 Agent skill。对准 GitHub 上的 Agent Skill 仓库，可生成单个自包含 HTML：沿着「你怎么操作」和「宿主 / 模型 / Agent 在背后做什么」把路径铺开。适合学习与捋清调用关系，不是把业务代码一键变成可上线网站的工具。

English：[README.md](README.md) · 仓库：[YeJe-cpu/web-learning-github](https://github.com/YeJe-cpu/web-learning-github)

---

## 适合谁？

Vibe coder、以及常刷 GitHub、想搞清某个 skill 仓怎么装、怎么触发、文件加载顺序的人。

README 往往写得很概括，真实入口在 Hook、`references/` 或子命令里——这一页用可滚动的单文件把路径和幕后机制放在一起。

---

## 生成的页面长什么样？

产出是单个 HTML（无需打包）。常见结构：

- 仓库信息（链接、Star、Fork、时间；页脚可写快照说明）
- 一两句大白话
- 可步进的组件路径（用户 → 宿主 → 读到哪份 `SKILL.md` / `references/` → 下一步）— 步数随真实仓库变化
- 表面上 / 背后的分步说明
- 目录树
- 简短的 README 侧写（需求、传播、注意点）
- 默认版式代号 Lab·Canonical（暖色、清晰版心），纪律上可参考 [Anthropic frontend-design](https://github.com/anthropics/skills/tree/main/skills/frontend-design)。首次打开若用 Google Fonts 可能要联网，之后可依赖缓存离线看。

### 示例页

克隆后打开 [`web/index.html`](web/index.html)，右上角 **English / 中文** 可切换全文。（[`web/demo.html`](web/demo.html) 会跳转到同一页。）配图可放 `assets/demo-screenshot.png`，写 `![预览](./assets/demo-screenshot.png)`。

**GitHub Pages（可选）：** 仓库 Settings → Pages → 从分支发布 → 根目录选 **`/web`**，站点首页即为该双语页（例：`https://YeJe-cpu.github.io/web-learning-github/`）。

---

## 怎么用

1. 将 `web-learning-github` 文件夹拷入宿主规定的 skills 目录（见下表）。
2. 在对话里说明要对哪个仓库生成 HTML（见触发示例）。

| 宿主 | 常见路径 |
|------|-----------|
| Cursor | 如 `.agents/skills/web-learning-github/` |
| Claude Code | 如 `~/.claude/skills/web-learning-github/` |
| Windsurf | 以官方文档为准 |
| OpenClaw | 如 `~/.openclaw/skills/` 或工作区 `skills/`，见 [OpenClaw · Skills](https://docs.openclaw.ai/skills/) |

默认保存为 `web/<owner>-<repo>.html`，可在提示里改目录。整页语言或「单文件内中英切换」见 `SKILL.md` / `SKILL.zh-CN.md`。

### 触发示例

- 「把 `owner/repo` 做成一页：安装 → 触发 → 读文件顺序。」
- 「组件路径用气泡步进，再写表面上/背后。」
- 「一个 HTML，顶部中英切换，段落双语。」
- “Turn `owner/repo` into one HTML with EN/中文 toggle.”

---

## 设计理念

先路径、后长文；能步进就不堆大段；单文件好分享。

---

## 目录结构

```
web-learning-github/
├── SKILL.md
├── SKILL.zh-CN.md
├── references/
├── web/
│   ├── index.html      # 中英切换示例（默认入口）
│   └── demo.html       # 跳转至 index.html
├── README.md
├── README.zh-CN.md
└── LICENSE
```

`references/` 说明见 [`references/README.md`](references/README.md)。

---

## 致谢

[zarazhangrui/codebase-to-course](https://github.com/zarazhangrui/codebase-to-course)（Codebase to Course）把应用代码仓做成互动单页「课程」，模块与可视化都很完整，是很好的参照。我们借鉴的是「把时间线上谁先加载谁讲清楚」这一点；定位侧重点是 Agent Skill 包与用户—Agent 路径的一页地图，不强调课堂闯关。两者互补。若我们对上游描述过时，欢迎开 issue。

| | Codebase to Course | Web Learning GitHub |
|---|---|---|
| 典型输入 | 应用 / 产品代码仓 | 技能包（`SKILL.md`、Hook、`references/` 等） |
| 体验形态 | 课程式深度 | 单页总览 |
| 共同点 | 清晰的组件路径与时间线 | 同样把步进路径放在靠前位置 |
| 我们侧重的 | — | 用户操作与模型/Agent 的对照；元信息、树、README 提示同页呈现 |

---

## 许可证

MIT — 见 [LICENSE](LICENSE)。
