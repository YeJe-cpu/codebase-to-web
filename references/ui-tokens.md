# Visual HTML page · design tokens (self-contained)

Follow **frontend-design** discipline: intentional type and color, purposeful whitespace (see `frontend-design-notes.md`).

---

## Lab·Canonical (default · warm editorial typography)

**Fraunces + Source Sans 3**, terracotta accent, warm paper gray. **Prefer** this set for new pages.

### Google Fonts

```
https://fonts.googleapis.com/css2?family=Fraunces:ital,opsz,wght@0,9..144,600;0,9..144,700;1,9..144,500&family=Source+Sans+3:ital,wght@0,400;0,500;0,600;1,400&family=JetBrains+Mono:wght@400;500&display=swap
```

### :root (summary)

- `--page-bg: #e8e2d8`; `--surface: #fffdf8`; `--accent: #9c4221`; `--accent-light: #ffedd5`; `--code-bg: #25201c`
- Use this file as the source of truth for full variables when generating.

### Shell width · gutters (mid values)

```css
.shell {
  max-width: min(52rem, calc(100vw - 2.5rem));
  margin: 0 auto;
  padding: clamp(2.5rem, 6vw, 4rem) clamp(1.35rem, 4vw, 2.25rem) clamp(4rem, 8vw, 5.5rem);
}
```

Subheads `max-width: 44rem`; `footer.note` may use `max-width: 52rem`.

---

## Lab·Variant A · Cool Studio

- **Outfit + Newsreader**; `--accent: #0369a1`; cool gray-blue. Use when the user asks for “cold / SaaS” or a wildcard.

## Lab·Variant B · Technical

- **Sora + IBM Plex Serif**; `--accent: #0f766e`; optional `.warn` compliance strip. Use for “engineering / architecture” tone or wildcard.

### Wildcard ratio

- **Default:** Canonical. In a batch, **at most one** variant page.

---

## Avoid

No Inter / Roboto / Arial for the main headline; no huge purple-gradient hero; no heavy noise texture as the entire background.
