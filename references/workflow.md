# Visual HTML walkthrough — checklist (Canonical)

## Single file vs merged page

- **Single repo (default):** `web/<owner>-<repo>.html` (or user path).
- **Author lab:** e.g. `30_resources/oss-skill-lab/<owner>-<repo>.html` when that tree exists.
- **Multiple repos:** separate files unless the user wants one tabbed page.

## Structure

1. **Hero + meta** first; then **`.viz-panel`** (component path) **before** long prose tabs.
2. **Steps / beats:** follow the real repo—**no fixed bubble or node count**.
3. **Rail captions + optional simulator** should align with the story you tell in **Learn**.

## Host wording

Use the user’s real host when known (**Cursor / Claude Code / Windsurf / OpenClaw**).

## Data

Stars / forks / `created_at` from GitHub API when possible; footer **snapshot** time.

## Do not

- Push the main walkthrough block to the bottom of the page.
- Use **`overflow: hidden`** on **`.viz-panel`** together with a sticky header stack (breaks layout).

## Layout (Canonical)

- **`.viz-panel`** → **`.viz-sticky-stack`** (`.viz-head` + `.viz-rail-captions`) → **`.viz-grid`** (`.viz-canvas` + `.anno`).
- **Samples:** `web/colleague-skill-prototype-gold.html`, `web/lark-minutes-tasks-walkthrough.html`.
- Tokens: **Lab·Canonical** in `ui-tokens.md` unless the user requests a variant.

## Post-gen sanity check

- [ ] Title font is not Inter / Roboto cliché for the main headline
- [ ] No huge purple-gradient hero; readable contrast
- [ ] Comfortable page margins (see `ui-tokens.md`)
- [ ] **`.viz-sticky-stack`** correct; **no title/rail overlap**
- [ ] **Narrow screens:** title + controls wrap without clipping
- [ ] Prev / Next / Auto / Reset behave; annotations stay in sync with the SVG step
