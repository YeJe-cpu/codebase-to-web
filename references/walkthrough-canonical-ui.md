# Walkthrough UI layout (README-grade single HTML)

This is the **shipped** layout for **Web Learning GitHub**: **SVG flow + step-synced explainer**, **Learn / Simulator / Deep dive** tabs, optional **`journey-fold`**. Root **`SKILL.md`** requires agents to follow it.

## Reference implementations in this repo

- **Gold:** **`web/colleague-skill-prototype-gold.html`** — branching flow (Work / Persona), six beats · upstream **titanwings/colleague-skill**.
- **Silver:** **`web/lark-minutes-tasks-walkthrough.html`** — linear pipeline, seven nodes · upstream **zarazhangrui/lark-minutes-tasks**.

## Structure (HTML/CSS contract)

1. **Hero** — title, install hint, language + theme toggles where needed; body class e.g. `is-zh` / `is-en`, `theme-dark` / `theme-light`.
2. **`.viz-panel`** — main walkthrough card.
   - **`.viz-sticky-stack`** wraps **`.viz-head`** + **`.viz-rail-captions`**.
     - **Do not** set `overflow: hidden` on `.viz-panel` if you use sticky headers: it breaks stacking and can make the title rail overlap.
     - **Sticky** applies to **`.viz-sticky-stack`** (single layer), not separately to `.viz-head`.
   - **`.viz-head`** — caption (e.g. “Component path · Step”), step pill, Prev / Next / Auto-play / Reset.
   - **`.viz-rail-captions`** — short L/R labels above the diagram (e.g. 录入 / 蒸馏 · 妙记 / 执行).
   - **`.viz-grid`** — two columns on wide screens: **`.viz-canvas`** (SVG nodes + paths) + **`.anno`** (title, card, footnotes). Bottom corners: give **`.viz-grid`** bottom border-radius + `overflow: hidden` so the panel still looks clipped while the sticky stack works.
3. **Tabs** — **学习 / 模拟器 / 深度探索** (or EN labels): switch panels without leaving the page.
4. **`<details class="journey-fold">`** — optional “after install” checklist; Chinese summary line should stay consistent, e.g. **「装好以后怎么用（与组件路径、模拟器对照）」**.
5. **Hero lead** — when describing the strip, you may mirror **（与组件路径、模拟器对照）**.

## Interaction

- Step index drives **node** and **path** classes (`.on`), and updates **annotation** copy (headline + “what this step does” + short zh/en notes).
- **Auto-play** toggles `aria-pressed` and a timer; **Reset** returns to step 0.
- Annotation bodies may use **`innerHTML`** when they include `<code>` or `<strong>` (avoid double-escaping).

## Data

Use real GitHub meta when possible; step count follows the repo (no padding to a magic number).

## Palette & typography

Follow **`frontend-design-notes.md`** and **`ui-tokens.md`** (no Inter-for-hero clichés, readable contrast). Lab-style warm accents are the default; variants allowed within discipline.

## Author lab archive

Maintainer drafts may live outside this repo (e.g. `30_resources/oss-skill-lab/walkthrough-gold-silver-lab/`). The **`web/sample-*-canonical.html`** files are the **checked-in** snapshots.
