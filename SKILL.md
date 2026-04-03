---
name: web-learning-github
description: "Agent skill (Web Learning GitHub): GitHub Agent Skill repo → self-contained single-file HTML walkthrough (meta, journey chat, surface vs backstage, tree, README bullets). Default web/<owner>-<repo>.html. Hosts: Cursor, Claude Code, Windsurf, OpenClaw. Match page language to user unless bilingual toggle requested. Lab·Canonical visuals + frontend-design discipline."
---

# Agent Skill repo → single-file visual HTML (Web Learning GitHub)

## Goal

Deliver a **double-clickable** single HTML file that explains **who talks to whom after install/trigger**, with Star/Fork and repo layout context—**learning / orientation**, not a shipping scaffold generator.

## Output language (required)

- If the user writes mainly in **English**, generate the **entire HTML page in English** (headings, blurbs, journey copy, step labels, bullets, footer).
- If the user writes mainly in **Chinese (中文)**, generate the **entire page in 中文**.
- Mixed prompts: follow the **dominant** language; if unclear, **default to English** for this OSS bundle unless the user asks for 中文.

### Optional: one file, EN / 中文 toggle

If the user **explicitly** asks for **both languages in one HTML** with a **UI switch** (no second file): duplicate each user-visible block into paired sections (e.g. `div` with `class="i18n i18n-en"` / `i18n-zh`), add **EN | 中文** buttons or a `<select>`, and a few lines of JS that toggles `display` / `hidden` or a root `lang` class. **Default** the toggle to the user’s first message language or **English**. Keep **one** shared GitHub meta bar and **one** tree; translate labels only.

## File output rules

- **Published OSS skill bundle (this repo):** one repo → one file → **`web/<owner>-<repo>.html`** (or a directory the user specifies).
- **Author local lab (multi-project workspace):** when the user asks to keep generated walkthroughs **out of the skill repo** or under their **OSS lab folder**, also write (or only write) **`30_resources/oss-skill-lab/<owner>-<repo>.html`** relative to the parent workspace that holds `web-learning-github/` and `30_resources/` — adjust the path if their tree differs; **do not** imply that path exists for every downloader of the skill.
- **Multiple repos** in one request, or explicit “single tabbed page”: you may emit one combined HTML; if no preference, **prefer separate files**.
- Agree the output directory in chat if **both** `web/` and lab paths apply; **default for strangers cloning the skill remains `web/`**.

## Hosts (for journey/install copy)

When naming the host in journey bubbles or install steps, follow the user’s real environment. Examples (always verify against vendor docs):

| Host | Typical skill path (examples) |
|------|-------------------------------|
| **Cursor** | Project `.agents/skills/<skill-folder>/` (or team convention) |
| **Claude Code** | `~/.claude/skills/<skill-folder>/` |
| **Windsurf** | Per current Windsurf / Cascade docs (often project-level skills) |
| **OpenClaw** | e.g. `~/.openclaw/skills/`, `~/.agents/skills/`, or workspace `skills/` — load order: [OpenClaw · Skills](https://docs.openclaw.ai/skills/) |

If unknown, say **“host / agent IDE”** instead of a single brand.

## Section order

1. **GitHub meta bar** — link, `stargazers_count`, `forks_count`, `created_at` (UTC).
2. **Plain blurb** — jargon-free scenario sentence.
3. **Deliverable blurb** — Markdown vs hooks vs scripts, etc.
4. **Component path / journey (before long steps)** — playable chat; `data-sender` roles; length follows real paths (often 6–15 beats for complex repos). May mention Cursor / Claude Code / OpenClaw per table.
5. **Step journey** — per step “on the surface” / “behind the scenes”.
6. **Repo tree** — `pre.tree` monospace.
7. **README bullets** — demand / distribution / moat / compliance, one each.

## Visuals & layout (FD‑pass shell)

Match the **frontend-design / fd-pass** lab shell unless the user asks otherwise:

- **Page:** `.shell`, gradient page background, `.hint`, `.meta-bar`, `.plain`, `.blurb`, `.section-title`, `.readme-box`, `footer.note` (see repo sample `web/YeJe-cpu-web-learning-github.html` or any `*.fd-pass.html` lab reference).
- **Component path:** `.path-wrap` → `.chat-window` → `.chat-messages` (stacked avatar bubbles), `.chat-typing` with **`#<chatWindowId>-typing-avatar`**, `.chat-controls` with **Next**, **Play all** (auto-advance), **Reset**, and **`.chat-progress`** (`index / total`).
- **Steps:** `.step` + **`.grid2`** (≥720px two columns): `.card.user` (“surface”) and `.card.back` (“backstage”).
- **Tree:** `pre.tree` with optional `.f` / `.n` spans for paths vs notes.

Read `references/ui-tokens.md` (Lab·Canonical tokens) and `references/frontend-design-notes.md`. **Variants A/B** only when the user asks for a “wildcard” palette.

## Chat widget

Per `.chat-window`: `typing-avatar` id = `{chatWindowId}-typing-avatar`; `.chat-message` elements start `display:none`; **`initChat`-style** controls: step forward, play all, reset; progress from `.chat-message` count.

## More

Start here if the folder names look cryptic: **`references/README.md`** (plain-language map).

- `references/workflow.md`
- `references/ui-tokens.md`
- `references/frontend-design-notes.md`

**Chinese:** `SKILL.zh-CN.md`, `references/*.zh-CN.md`.
