---
name: codebase-to-web
description: "Agent skill: GitHub Agent Skill repo → self-contained single-file HTML walkthrough (meta, journey chat, user vs behind-the-scenes, tree, README bullets). Default web/<owner>-<repo>.html. Hosts: Cursor, Claude Code, Windsurf, OpenClaw. Match page language to the user. Lab·Canonical visuals + frontend-design discipline."
---

# Agent Skill repo → single-file visual HTML (Codebase to Web)

## Goal

Deliver a **double-clickable** single HTML file that explains **who talks to whom after install/trigger**, with Star/Fork and repo layout context.

## Output language (required)

- If the user writes mainly in **English**, generate the **entire HTML page in English** (headings, blurbs, journey copy, step labels, bullets, footer).
- If the user writes mainly in **Chinese (中文)**, generate the **entire page in 中文**.
- Mixed prompts: follow the **dominant** language; if unclear, **default to English** for this OSS bundle unless the user asks for 中文.

## File output rules

- **Default:** one repo → one file → **`web/<owner>-<repo>.html`** (or a directory the user specifies).
- **Multiple repos** in one request, or explicit “single tabbed page”: you may emit one combined HTML; if no preference, **prefer separate files**.
- Keep outputs under an agreed folder; **default `web/`**.

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

## Visuals

Read `references/ui-tokens.md` (Lab·Canonical default) and `references/frontend-design-notes.md`. Variants A/B only when the user asks or wants a “wildcard” look.

## Chat widget

Per `.chat-window`: `typing-avatar` id = `{chatWindowId}-typing-avatar`; messages start `display:none`; progress from `.chat-message` count.

## More

Start here if the folder names look cryptic: **`references/README.md`** (plain-language map).

- `references/workflow.md`
- `references/ui-tokens.md`
- `references/frontend-design-notes.md`

**Chinese:** `SKILL.zh-CN.md`, `references/*.zh-CN.md`.
