# Codebase to Web

**Codebase to Web** 是跑在 **Cursor、Claude Code、Windsurf、OpenClaw** 等环境里的 **Agent skill**。你对准 GitHub 上的某个 **Agent Skill 仓库**，它会生成 **单个 HTML 文件**：把「用户怎么操作、怎么触发」和「背后宿主、模型、Agent 各做了什么」整理成 **一条可在浏览器里滚动查看的可视化路径**——不是再堆一叠分散的 Markdown，而是一张网页里的 **流程 + 说明**。

**仓库：** [github.com/YeJe-cpu/codebase-to-web](https://github.com/YeJe-cpu/codebase-to-web) · [English](README.md)

---

## 适合谁？

- **Vibe coder / 想少踩坑的人**：刷 GitHub、想学别人的 skill/工具链，想 **更快搞清**「装在哪、怎么触发、谁先读哪个文件」。  
- **读开源的日常场景**：README 常写得很高概念，**真实入口**在 Hook、`references/`、子命令里——这一页把 **用户可见路径** 和 **幕后机制** 放在一起。  
- **要交付、对齐、写文档的人**：需要 **一个 `.html` 或一个链接**，把调用关系讲给同事或贡献者听。

---

## 生成的可视化网页里有什么？

得到的是 **本地双击即可打开的单个 `.html`**（不需要再跑打包命令）。常见版块从上往下包括：

1. **仓库信息条** — 链到 GitHub，展示 Star / Fork / 创建时间（页脚可注明数据 **快照时间**）。  
2. **大白话引言** — 用一句话说清这个仓 **解决什么问题**、给谁用。  
3. **组件路径（可步进）** — 类似对话气泡，**一步一步** 播放：用户输入 → 宿主/路由 → 读到哪份 `SKILL.md` 或 `references/` → 模型或 Agent 下一步……条数按 **真实仓库** 展开，不硬套固定步数。  
4. **分步说明（表面上 / 背后）** — 每一步你在 UI 上在做什么，对应 **背后在读文件、跑 Hook、还是走子命令**。  
5. **目录树** — 和仓库实际结构一致的树状展示，方便对照「README 里没写全的路径」。  
6. **README 侧写** — 几条短 bullet，例如需求感、传播点、壁垒或合规注意等，帮助判断项目在社群里的位置。  
7. **版式与字体** — 默认暖色编辑向的 **Lab·Canonical**（有识别度的标题字体 + 舒适版心），刻意避开「大紫渐变 + 万能 Inter 标题」的廉价感；需要可换冷色/工程向变体。视觉纪律参考 [Anthropic `frontend-design`](https://github.com/anthropics/skills/tree/main/skills/frontend-design)。

若页面里引用了 **Google Fonts**，**第一次**打开通常需要联网；之后同一文件可离线查看。

### 想插图？

Markdown 支持图片。例如在仓库里新建 `assets/preview.png`，在本 README 里写：

```markdown
![页面预览示例](./assets/preview.png)
```

推送到 GitHub 后，在仓库首页就能看到缩略图；本地编辑同样生效。

---

## 我们想强调的几件事

- **路径优先**：先看 **谁先加载谁**、用户一句话触发了哪条链，再去读长篇说明。  
- **表面 × 背后**：每个关键步骤都尽量回答 **界面层在干什么、底下模型/Agent 在干什么**。  
- **一页总览**：输出是 **单文件可视化说明**，不强制「课堂闯关式」问答（和「把业务仓做成系统课」类产品 **场景不同**，见文末致谢）。  
- **少翻 tab**：Star、目录树、README 侧写放在同一页，减少在 GitHub 与本地文件之间来回跳。

---

## 本仓库里每个路径是干什么的？

克隆下来的 **就是** 可发布的 skill 包，典型布局如下：

```
codebase-to-web/
├── SKILL.md              # 多数宿主默认读取的技能说明（英文主文）
├── SKILL.zh-CN.md        # 中文规则副本（可与上一文件二选一或自行合并）
├── references/           # 生成 HTML 时的版式、流程与审美约束
├── web/                  # 默认输出目录（生成的 .html 通常不入库；可有 .gitkeep）
├── README.md
├── README.zh-CN.md
└── LICENSE
```

| 路径 | 作用 |
|------|------|
| `SKILL.md`、`SKILL.zh-CN.md` | 规定 **生成逻辑、章节顺序、产出语言** 等 |
| `references/` | 具体见 [`references/README.md`](references/README.md)（版心配色、检查项、设计纪律） |
| `web/` | 在对话里生成页面时的 **默认保存位置**，一般为 `web/<owner>-<repo>.html` |

---

## 如何安装

把 **`codebase-to-web`** 文件夹原样放进你的宿主所要求的 skills 目录：

| 宿主 | 常见示例 |
|------|-----------|
| **Cursor** | 如项目内 `.agents/skills/codebase-to-web/` |
| **Claude Code** | 如 `~/.claude/skills/codebase-to-web/` |
| **Windsurf** | 以产品官方文档中的 skills 路径为准 |
| **OpenClaw** | 如 `~/.openclaw/skills/` 或工作区内的 `skills/` 等，加载顺序见 [OpenClaw · Skills](https://docs.openclaw.ai/skills/) |

**输出语言**（整页中文或英文）由 `SKILL.md` / `SKILL.zh-CN.md` 约定，随你的对话语言走。

### 默认输出路径

**`web/<owner>-<repo>.html`**；也可以在提示里改成别的目录名。

---

## 怎么用（提示词示例）

- 「帮我把 `owner/repo` 生成一页 **安装→触发→读文件顺序** 的单文件 HTML。」  
- 「**组件路径**要做成可步进的气泡，再放 **表面上/背后** 分步。」  
- “Turn `owner/repo` into one self-contained HTML that maps user actions to agent behavior.”

---

## 设计理念（短）

**先路径、后长文**；**能点着看就不堆长段落**；**单文件 HTML 可分享**。

---

## 致谢与和 Codebase to Course 的关系

思路受到 **[zarazhangrui/codebase-to-course](https://github.com/zarazhangrui/codebase-to-course)**（*Codebase to Course*）的启发：他们把代码仓做成 **可结构化解锁的学习/课程体验**，需求清晰、完成度高，社区 Star 多说明这条路 **被大量开发者验证过**。

**我们不会拿 star 数去和对方「比个头」。** 更实在的分工是：**对方偏应用代码的系统化学习**；**我们偏 Agent Skill 包的一条可视化用户路径**——赛道不同，可以并存；若你愿意同时用两个工具，也互不挡道。

| | Codebase to Course | Codebase to Web（本仓库） |
|---|---|---|
| 典型输入 | 应用 / 产品代码仓 | `SKILL.md`、Hook、`references/` 等 **技能包** |
| 体验重心 | 课程式模块与深度 | **单页**总览；**不强制**课堂问答流 |
| 借鉴点 | 清晰的 **组件路径 / 时间线** 表达方式 | 同样在页面 **靠前** 用可步进路径讲清先后顺序 |
| 我们的侧重点 | — | **用户侧操作** 与 **模型/Agent 侧动作** 的对照；Star、树、README 辅助信息 |

若你对上游项目最新能力更熟悉，欢迎开 issue 帮我们 **更正表述**。

---

## 许可证

MIT — 见 [LICENSE](LICENSE)。
