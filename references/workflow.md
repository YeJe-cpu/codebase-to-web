# Visual HTML walkthrough — preferences & checklist

## Single file vs merged page

- **Single repo (default):** write `web/<owner>-<repo>.html` (or user-chosen path).
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

## Layout & palette

- Default **Lab·Canonical** in `ui-tokens.md`.
- Variants A/B only when the user wants a different tone or a one-off “wildcard”.

## Post-gen sanity check

- [ ] Display font for main title is not Inter / Roboto
- [ ] No huge purple-gradient hero; no heavy noise texture across the whole page
- [ ] Comfortable margins (`.shell` in `ui-tokens.md`)
- [ ] `typing-avatar` id matches `chat-window` id rule
