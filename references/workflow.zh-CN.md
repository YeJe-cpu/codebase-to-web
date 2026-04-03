# 可视化 HTML 页 · 用户偏好与检查清单

## 单仓库 vs 整合页

- **单仓库（默认）**：新建 `web/<owner>-<repo>.html`（或用户在对话里指定的目录）。
- **多仓库一次交付**：用户在一句话里列出 2+ 个 GitHub 仓库，或明说「合成一个 Tab 页」→ 可输出整合 HTML，或分别输出多个单文件；若无偏好，**优先多个单文件**。

## 用户明确偏好的结构

1. **组件路径前置**：必须在「分步旅程」之前；条数按真实路径展开，避免强行固定 4 条丢分支。
2. **分步旅程要细**：安装 / 首触 / 顺利路径 / 异常路径等可拆步。
3. **研究者三问**（内容上要能回答）：Journey UI；交付物形态；README 热度从何而来。

## 宿主表述

旅程气泡或安装说明需点名时，优先使用用户当前环境（**Cursor / Claude Code / Windsurf / OpenClaw** 等）。OpenClaw 路径与优先级参见 [OpenClaw · Skills](https://docs.openclaw.ai/skills/)。

## 数据

- Star/Fork/创建时间以 GitHub API 为准；页脚注明「快照」时间。
- 无 API 时写「以仓库页为准」并给链接。

## 不要做

- 不要把组件路径放到页面最底部。

## 版心与配色

- 默认 **Lab·Canonical**，见 `ui-tokens.zh-CN.md`。
- 变体 A/B 仅用户要换气质或盲盒时使用。

## 检查清单（生成后目测）

- [ ] 主标题不是 Inter / Roboto 堆栈
- [ ] 背景无大紫渐变主导、无重噪点磨砂铺满
- [ ] 版心留白适中（`ui-tokens.zh-CN.md` 中的 `.shell` 公式）
- [ ] `typing-avatar` id 与 `chat-window` id 一致
