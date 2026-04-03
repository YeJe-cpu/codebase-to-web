# Web Learning GitHub

## What it is & who it’s for

An **agent skill** for **Cursor, Claude Code, Windsurf, OpenClaw**, and similar hosts: point it at an **Agent Skill repo on GitHub** and get a **single self-contained HTML** that traces the UI/UX path—what you do in the product vs what the host and model load next. Meant for **learning and orientation**, not for turning an app codebase into a shipped web product.

**Who is it for?** Vibe coders and anyone on GitHub who wants to see **where to install**, **what triggers the skill**, and **which files load in what order**. READMEs are often high-level while real entrypoints sit under hooks, `references/`, or subcommands—this page is **one scrollable map** instead of many small Markdown hops.

中文：[README.zh-CN.md](README.zh-CN.md) · Repository: [YeJe-cpu/web-learning-github](https://github.com/YeJe-cpu/web-learning-github)

---

## Demo & what’s inside the page

Three captures below show the **English** UI of this repo’s sample [`web/YeJe-cpu-web-learning-github.html`](web/YeJe-cpu-web-learning-github.html) (open locally after clone). **Images first, text after.** Toggle **English / 中文** at the top; the component path has **Next · Play all · Reset** (fd-pass layout).

![Overview — hero, meta, plain-language intro, deliverables (English)](assets/demo-en-hero.png)

![Component path bubbles and two-column step journey (English)](assets/demo-en-path-steps.png)

![Playback — Next, Play all, Reset (English, GIF)](assets/demo-en-interaction.gif)

**Typical sections in that HTML:** repo meta (link, stars, forks, created time), plain-language blurb, a **step-through component path** (message count follows the **real** repo—not fixed), **two-column** surface vs backstage on wide screens, tree, README-flavoured bullets. Defaults follow **Lab·Canonical** (warm editorial) and [Anthropic frontend-design](https://github.com/anthropics/skills/tree/main/skills/frontend-design) discipline. First load may fetch Google Fonts; then you can use it offline from cache.

Shorter sample: [`web/demo.html`](web/demo.html). Full walkthrough matching the screenshots: **`web/YeJe-cpu-web-learning-github.html`**.

---

## How to use

1. Copy the `web-learning-github` folder into your host’s skills directory (examples below).
2. In chat, ask for an HTML walkthrough of a repo (see trigger phrases).

| Host | Typical path |
|------|----------------|
| Cursor | e.g. `.agents/skills/web-learning-github/` in the project |
| Claude Code | e.g. `~/.claude/skills/web-learning-github/` |
| Windsurf | follow current product docs |
| OpenClaw | e.g. `~/.openclaw/skills/` or workspace `skills/` — [OpenClaw · Skills](https://docs.openclaw.ai/skills/) |

Generated pages default to `web/<owner>-<repo>.html`. You can override the folder in the prompt. Output language (or a bilingual toggle in one file) is described in `SKILL.md` and `SKILL.zh-CN.md`.

### Trigger phrases

- “Turn `owner/repo` into one HTML that maps install → trigger → file order.”
- “Component path first as bubbles, then surface vs backstage steps.”
- “One HTML with EN / 中文 toggle for every section.”
- 「把这个仓库做成一页路径说明 HTML。」

---

## Design philosophy

Path before long prose. Prefer a step-through call graph over walls of text. One file you can share or archive.

---

## Skill layout

```
web-learning-github/
├── SKILL.md
├── SKILL.zh-CN.md
├── references/
├── assets/             # README demo images
├── web/
│   ├── demo.html
│   └── YeJe-cpu-web-learning-github.html
├── README.md
├── README.zh-CN.md
└── LICENSE
```

Details for `references/` are in [`references/README.md`](references/README.md).

---

## Acknowledgements

[zarazhangrui/codebase-to-course](https://github.com/zarazhangrui/codebase-to-course) (*Codebase to Course*) turns application codebases into rich, interactive single-page courses (modules, quizzes, visualizations)—a different and valuable problem. We borrow the idea of putting a clear **component path / timeline** up front; our focus is Agent Skill repos and a single-page map of user action vs agent behavior, without a mandatory course loop. Both can coexist. If our comparison misstates their current README, open an issue.

| | Codebase to Course | Web Learning GitHub |
|---|---|---|
| Typical input | Application / product repos | Skill bundles (`SKILL.md`, hooks, `references/`) |
| Experience shape | Course-style depth | One-page overview |
| Shared idea | Clear ordering of who loads whom | Same: step-through path first |
| Emphasis here | — | User step ↔ model/agent; meta, tree, README hints on one page |

---

## License

MIT — see [LICENSE](LICENSE).

## Contributing

[CONTRIBUTING.md](CONTRIBUTING.md).
