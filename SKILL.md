---
name: web-learning-github
description: "Agent skill: Agent Skill repo → single self-contained HTML — SVG component path, step-synced notes, Learn/Simulator/Deep dive tabs, journey-fold checklist. Default web/<owner>-<repo>.html. EN/中文 per user or bilingual toggle for README demos. Hosts: Cursor, Claude Code, Windsurf, OpenClaw."
---

# Agent Skill repo → single-file visual walkthrough (Web Learning GitHub)

## Goal

Deliver a **double-clickable** single HTML that explains **install → trigger → what loads** for an Agent Skill repo, with Star/Fork and tree context—**learning / orientation**, not an app scaffold.

## Output language (required)

- **Default:** one language matching the user’s prompt (dominant **English** or **中文**; if unclear, default **English** unless they prefer 中文).
- **README / demo:** when bilingual UI is required, one HTML with **EN | 中文** toggle (`html.is-en` / `is-zh`) and paired blocks—one meta bar, one tree.

## File output rules

- **Cloned skill bundle:** one repo → **`web/<owner>-<repo>.html`** (default) or a path the user specifies.
- **Author lab:** optionally **`30_resources/oss-skill-lab/<owner>-<repo>.html`** when that workspace layout exists—confirm in chat.
- **Multiple repos:** separate files by default unless the user asks for one tabbed page.

## Hosts (journey / install copy)

| Host | Typical skill path |
|------|---------------------|
| **Cursor** | `.agents/skills/<skill-folder>/` |
| **Claude Code** | `~/.claude/skills/<skill-folder>/` |
| **Windsurf** | per current docs |
| **OpenClaw** | e.g. `~/.openclaw/skills/` — [Skills](https://docs.openclaw.ai/skills/) |

If unknown, say **“host / agent IDE”**.

## Section order (typical)

1. **GitHub meta bar** — link, stars, forks, `created_at`.
2. **Hero** — scenario, install hint, theme/lang toggles if needed.
3. **`.viz-panel`** — **`.viz-sticky-stack`** (`.viz-head` + `.viz-rail-captions`) + **`.viz-grid`** (SVG + **`.anno`**). **Step count follows the real repo**—never pad.
4. **Tabs** — Learn, Simulator, Deep dive (labels may be EN/zh).
5. **Repo tree** + **README-style bullets**.
6. **`journey-fold`** — expandable “after install” checklist; e.g. **「装好以后怎么用（与组件路径、模拟器对照）」**. **Gold and silver reference HTML in this repo both include it.** Hero may use the same parenthetical when describing the strip.

## Interaction & layout (Canonical — required)

Read **`references/walkthrough-canonical-ui.md`** and **`references/workflow.md`**.

**Non‑negotiables:**

- **`.viz-sticky-stack`** wraps **`.viz-head`** + **`.viz-rail-captions`**; **sticky on the stack**, not on the head alone.
- **`.viz-panel`:** do **not** use **`overflow: hidden`** with sticky (causes overlap/clipping).
- **`.viz-grid`:** bottom **border-radius** + `overflow: hidden` is OK for the diagram + annotation block.
- Rich annotation lines: **`innerHTML`** when using `<code>` / `<strong>`.

**Reference HTML in this repo** (gold / silver samples from real GitHub skill repos):

- `web/colleague-skill-prototype-gold.html` — upstream **titanwings/colleague-skill**
- `web/lark-minutes-tasks-walkthrough.html` — upstream **zarazhangrui/lark-minutes-tasks**

## Color & surface

Follow **`references/ui-tokens.md`** and **`references/frontend-design-notes.md`** (**frontend-design** discipline; Lab·Canonical as default token story).

## More

- **`references/README.md`**
- **`references/workflow.md`**

**Chinese:** `SKILL.zh-CN.md`, `references/*.zh-CN.md`.
