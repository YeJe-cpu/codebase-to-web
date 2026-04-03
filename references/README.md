# `references/` 是干嘛的？（帮你打消困惑）

这一整包就是 **一个 skill**：根目录的 `SKILL.md` 告诉模型**要做什么事**；`references/` 里是**生成那张可视化 HTML 时要遵守的细节**——相当于「出图规范」「排版与配色手册」，**不是**三个别的产品名称。

下面是每个文件一句话人话版：

## `workflow.md` / `workflow.zh-CN.md`

**流程与检查清单**：默认一仓一单文件还是多仓合并、journey 要放在前面、生成完要自检什么（别把好内容塞到页面最底下）。  
→ 模型按这个来，**网页结构不会乱**。

## `ui-tokens.md` / `ui-tokens.zh-CN.md`

**视觉 token**：用什么 Google Fonts、`.shell` 版心多宽、默认暖陶土色还是用户要的冷色/青色变体。  
→ 页面长什么样，主要**由这里定调**（避免每张都像大紫渐变 AI 模板）。

## `frontend-design-notes.md` / `frontend-design-notes.zh-CN.md`

**和 Anthropic 的 `frontend-design` 思路对齐的纪律**：主标题别用 Inter 堆满、别用脏渐变当背景，等等。  
→ 本仓库**不捆绑**上游代码，只是生成 HTML 时**照着这个审美约束**来。

---

**English:** same idea—`references/` holds **implementation notes for HTML generation**, not separate apps. Pair `*.md` (English) with `*.zh-CN.md` (中文).
