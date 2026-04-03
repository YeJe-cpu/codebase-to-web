# 开源发布检查清单（给维护者）

## README 双轨

- **Track B（默认）：** 根目录 [README.md](../README.md) — 段落对标 [codebase-to-course](https://github.com/zarazhangrui/codebase-to-course)。  
- **Track A（开发者营销）：** [README-track-a.md](README-track-a.md) / [README-track-a.zh-CN.md](README-track-a.zh-CN.md) — 明确列出参照的 [devmarketing-skills](https://github.com/jonathimer/devmarketing-skills) **子 skill**（本仓库不捆绑该包）。

方法论安装：`npx add-skill jonathimer/devmarketing-skills`（可选）。

## 仓库基础

- [ ] GitHub **About** 描述与 Topics：抄 [GITHUB-ABOUT.md](GITHUB-ABOUT.md)  
- [ ] `README.md` 首屏说清：**输入 / 输出 / 与 codebase-to-course 互补**
- [ ] `LICENSE` 已选（当前 MIT）
- [ ] Topics：`agent-skills` `claude-code` `cursor` `skill` `static-html` `education`

## 蹭热点（得体、不尬）

- **Agent Skills** 生态：在 README 里用一节对照 `codebase-to-course`，标明 **互补** 而非竞争  
- **Anthropic skills**：致谢 `frontend-design` 纪律（已写在 `references/frontend-design-notes.md`）  
- **中文受众**：明确写 Chinese-first，吸引双语文档用户

## 演示资产（强烈建议下一迭代补）

- [ ] 在 `skill-lab/` 放 1～2 个 **匿名化示例 HTML**（或截图），降低 clone 门槛  
- [ ] 若发 HN / X：一条具体 **before/after**（README 迷宫 vs 单页 journey）

## 可选安装 devmarketing-skills

```bash
npx add-skill jonathimer/devmarketing-skills
# 或 clone 到本地后把 skills/ 合并进 agent
```

用于打磨置顶描述、Show HN 草稿、技术线程结构（本仓库不捆绑该依赖）。

本工作区已可本地参考：`30_resources/_vendor/devmarketing-skills/`（若你 clone 了完整 `emo专用` 工程）。
