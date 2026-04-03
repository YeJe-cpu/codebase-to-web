# 可视化 HTML 页 · 视觉 token（自持）

对齐 **frontend-design** 纪律：有主见的字体与配色、意图明确的留白（见 `frontend-design-notes.zh-CN.md`）。

---

## Lab·Canonical（默认 · Developer-Marketing 暖编辑风）

**Fraunces + Source Sans 3**、陶土强调色、暖灰纸感。新产出 **优先** 使用本组。

### Google Fonts

```
https://fonts.googleapis.com/css2?family=Fraunces:ital,opsz,wght@0,9..144,600;0,9..144,700;1,9..144,500&family=Source+Sans+3:ital,wght@0,400;0,500;0,600;1,400&family=JetBrains+Mono:wght@400;500&display=swap
```

### :root（摘要）

- `--page-bg: #e8e2d8`；`--surface: #fffdf8`；`--accent: #9c4221`；`--accent-light: #ffedd5`；`--code-bg: #25201c`
- 完整变量与说明以生成时读本文为准。

### 版心 · 页边距（中间值）

```css
.shell {
  max-width: min(52rem, calc(100vw - 2.5rem));
  margin: 0 auto;
  padding: clamp(2.5rem, 6vw, 4rem) clamp(1.35rem, 4vw, 2.25rem) clamp(4rem, 8vw, 5.5rem);
}
```

副标题 `max-width: 44rem`；`footer.note` 可 `max-width: 52rem`。

---

## Lab·Variant A · Cool Studio

- **Outfit + Newsreader**；`--accent: #0369a1`；浅灰蓝气质。用户点「冷色 / SaaS」或盲盒时使用。

## Lab·Variant B · Technical

- **Sora + IBM Plex Serif**；`--accent: #0f766e`；可选 `.warn` 合规条。用户点「工程 / 架构页」或盲盒时使用。

### 盲盒比例

- **默认**：Canonical。同一批多仓任务中变体 **至多一张**。

---

## 禁止

主标题不要用 Inter / Roboto / Arial；不要大紫渐变铺满背景；页面不要重噪点磨砂大底。
