# Visual HTML walkthrough — preferences & checklist

## Single file vs merged page

- **Single repo (default for OSS bundle):** write `web/<owner>-<repo>.html` (or user-chosen path).
- **Author lab folder:** if the user wants outputs under their OSS lab tree, use e.g. `30_resources/oss-skill-lab/<owner>-<repo>.html` (path relative to their multi-project root); confirm in chat.
- **Multiple repos in one request:** merged tabbed HTML **or** separate files; if no preference, **prefer separate files**.

## Structure preferences

1. **Component path / journey first** — before long-form steps; don’t force a fixed message count; follow the real branching path.
2. **Granular step journey** — install / first touch / happy path / failure paths as needed.
3. **Research questions the page should answer:** journey UX; artifact shape; what README popularity implies.

## Host wording

Name the host the user actually uses (**Cursor / Claude Code / Windsurf / OpenClaw**). OpenClaw resolution order: [OpenClaw · Skills](https://docs.openclaw.ai/skills/).

## Data

- Stars/forks/created_at from GitHub API when possible; footer **snapshot** time.
- Without API: “see repo page” + link.

## Do not

- Push the component-path block to the bottom of the page.

## Layout & palette (FD‑pass)

- **Shell:** match **fd-pass** structure: `.meta-bar`, `.path-wrap` / `.chat-window` (Next · Play all · Reset · progress), `.grid2` two-column steps (`.card.user` / `.card.back`), `.readme-box`, colored `pre.tree` where helpful.
- Tokens: **Lab·Canonical** in `ui-tokens.md`; variants A/B only for “wildcard” requests.

## Post-gen sanity check

- [ ] Display font for main title is not Inter / Roboto
- [ ] No huge purple-gradient hero; no heavy noise texture across the whole page
- [ ] Comfortable margins (`.shell` in `ui-tokens.md`)
- [ ] `typing-avatar` id matches `chat-window` id rule (`#<id>-typing-avatar`)
- [ ] Journey chat has **Next**, **Play all**, **Reset** and live **progress**
- [ ] Surface / backstage use **two columns** at ≥720px (`.grid2`)
