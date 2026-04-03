# Track A — README（开发者营销取向·中文版）

本文件是**可选置顶 README**：用 **[jonathimer/devmarketing-skills](https://github.com/jonathimer/devmarketing-skills)** 的开发者受众思路来写（实在话、可验证、少空词）。

**说明：** 本仓库 **不包含** devmarketing-skills 的 Markdown 文件；需 **另外安装**（`npx add-skill jonathimer/devmarketing-skills` 或自行 clone）。下表只说明 **写这份 README 时参照了对方哪几个子 skill 的视角**。

| devmarketing-skills 子目录 | 在本 README 中的用法 |
|---------------------------|---------------------|
| [developer-audience-context](https://github.com/jonathimer/devmarketing-skills/tree/main/skills/developer-audience-context) | 读者 = 已用 Claude Code / Cursor、会收藏 Skill 仓，但**不愿先钻十几层目录**的人。 |
| [github-presence](https://github.com/jonathimer/devmarketing-skills/tree/main/skills/github-presence) | 一屏说清：**是什么 / 怎么装 / 产出什么文件 / 和别的主页怎么分工**。 |
| [devrel-content](https://github.com/jonathimer/devmarketing-skills/tree/main/skills/devrel-content) | 先写 **行为**（双击 HTML），再写愿景。 |
| [open-source-marketing](https://github.com/jonathimer/devmarketing-skills/tree/main/skills/open-source-marketing) | MIT、单一用途、欢迎 PR，不堆营销腔。 |

---

## 痛点（开发者听得懂）

不信任的不是 Markdown，是**调用顺序不明**：

- 宿主**到底扫哪个目录**？
- **用户第一眼操作**和 **agent 先读的文件** 分别是什么？
- Star 多到底是 **真需求** 还是 **套壳引流**？

单靠平铺的 `SKILL.md`，**不一定**能回答 **journey**。

---

## 我们交付什么

**一个 skill**，一种产出：**单文件 HTML（Skill 实验室页）**：

1. GitHub 元数据（页脚注明快照时间）  
2. 大白话（一句话说清干嘛的）  
3. **组件路径 journey**（可步进对话：谁加载谁）  
4. 分步：表面上 vs 背后  
5. 目录树 + README 简析（传播 / 壁垒 / 合规）

生成内容默认 **中文** 实验室叙事；需要全英文可在提示里说明。

---

## 老实交代边界

- **不是** [codebase-to-course](https://github.com/zarazhangrui/codebase-to-course) 那种 **互动课程**（测验、模块进度等）。那种更适合 **应用代码仓**；我们是 **Skill / Agent 技能包** 的 **一页地图**。  
- 字体默认走 Google Fonts（也可 fork 后自建字体）。

---

## 安装

1. 拷贝本目录到 `~/.claude/skills/` 或 `.agents/skills/`。  
2. 对模型说：把 `owner/repo` **做成 Skill 实验室单页**。  
3. 默认输出：`skill-lab/<owner>-<repo>.html`。

---

## 为什么这篇 README 长这样

因为：**承认取舍**、指向 **互补** 明星项目（codebase-to-course）、告诉你 **落地文件名**。若 journey 画错，开 issue 贴仓库地址和真实调用链——改 skill，不靠重写 slogan。

---

## 许可证

MIT，见 [LICENSE](../LICENSE)。视觉纪律参考 [Anthropic frontend-design](https://github.com/anthropics/skills/tree/main/skills/frontend-design)（不随仓分发原文）。
