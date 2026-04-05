# Walkthrough 单页版式（README 级 HTML）

这是 **Web Learning GitHub** **对外交付**的版式：**SVG 流程**、**与步进同步的右侧说明**、**学习 / 模拟器 / 深度探索** Tab、可选 **`journey-fold`**。根目录 **`SKILL.md`** 要求模型按此生成。

## 本仓库参考实现（各一份 HTML）

- **金样本：** **`web/colleague-skill-prototype-gold.html`** — 分叉（Work / Persona），六步 · 上游 **titanwings/colleague-skill**。
- **银样本：** **`web/lark-minutes-tasks-walkthrough.html`** — 线性管线，七节点 · 上游 **zarazhangrui/lark-minutes-tasks**。

## 结构约定（HTML / CSS）

1. **Hero** — 标题、安装提示、语言与主题；如 `is-zh` / `is-en`、`theme-dark` / `theme-light`。  
2. **`.viz-panel`** — 主 walkthrough 卡片。  
   - **`.viz-sticky-stack`** 包住 **`.viz-head`** 与 **`.viz-rail-captions`**。  
     - **`.viz-panel` 不要用 `overflow: hidden`**（会与 sticky 冲突、叠字）。  
     - **sticky** 在 **`.viz-sticky-stack`**，**不要**单独粘在 `.viz-head`。  
   - **`.viz-head`** — 副标题、步进计数、上一步 / 下一步 / 自动播放 / 重置。  
   - **`.viz-rail-captions`** — 流程图上方左右短标签。  
   - **`.viz-grid`** — 宽屏双列：**`.viz-canvas`**（SVG）+ **`.anno`**；可由 **`.viz-grid`** 做**下圆角** + `overflow: hidden`。  
3. **Tabs** — 学习 / 模拟器 / 深度探索（或英文标签）。  
4. **`<details class="journey-fold">`** — 可选；中文 summary 建议 **「装好以后怎么用（与组件路径、模拟器对照）」**。  
5. **Hero 导语** — 可写 **（与组件路径、模拟器对照）**。

## 交互

- 步进驱动节点 / 连线的 `.on`，并更新右侧注解。  
- **自动播放**、**重置** 语义与 `aria-pressed` 一致。  
- 注解含标签时用 **`innerHTML`**。

## 数据

尽量使用真实 GitHub meta；**步数随仓库**，勿凑数。

## 视觉

遵守 **`frontend-design-notes.zh-CN.md`**、**`ui-tokens.zh-CN.md`**。

## 维护者本地归档

草稿可在本仓库外（如 `30_resources/oss-skill-lab/walkthrough-gold-silver-lab/`）；**`web/sample-*-canonical.html`** 为入库对照样本。
