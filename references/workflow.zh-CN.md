# 可视化 HTML 单页 · 检查清单（Canonical）

## 单仓 vs 整合页

- **单仓（默认）：** `web/<owner>-<repo>.html` 或用户指定路径。  
- **维护者实验室：** 如 `30_resources/oss-skill-lab/<owner>-<repo>.html`。  
- **多仓库：** 默认**多文件**；要单页 Tab 再单独约定。

## 结构偏好

1. **Hero + meta** 在前，**`.viz-panel`** 主路径在**长文 Tab 之前**。  
2. **步进节点数**随真实仓库，**勿写死条数**。  
3. **轨道字 / 模拟器** 与 **学习** Tab 叙事一致。

## 宿主表述

优先使用用户当前环境（**Cursor / Claude Code / Windsurf / OpenClaw**）。

## 数据

Star/Fork/创建时间尽量用 GitHub API；页脚注明快照时间。

## 不要做

- 把主 walkthrough 塞到页面最底部。  
- **`.viz-panel` + sticky** 时滥用 **`overflow: hidden`**。

## 版式（Canonical）

- **`.viz-panel`** → **`.viz-sticky-stack`**（`.viz-head` + `.viz-rail-captions`）→ **`.viz-grid`**（`.viz-canvas` + `.anno`）。  
- **样本：** `web/colleague-skill-prototype-gold.html`、`web/lark-minutes-tasks-walkthrough.html`（金 / 银各一份）。  
- 色板默认 **Lab·Canonical**（`ui-tokens.zh-CN.md`）。

## 生成后自检

- [ ] 主标题未沦为 Inter/Roboto 堆栈  
- [ ] 无大紫渐变铺底，对比度可读  
- [ ] 版心留白适中（`ui-tokens.zh-CN.md`）  
- [ ] **`.viz-sticky-stack`** 正确，**顶栏与轨道字不叠字**  
- [ ] **窄屏** 标题与控制条可换行、不裁切  
- [ ] 上一步/下一步/自动/重置正常，注解与 SVG 步进同步  
