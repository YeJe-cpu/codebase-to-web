# Codebase to Web

**Codebase to Web** is an **agent skill** for **Cursor**, **Claude Code**, **Windsurf**, **OpenClaw**, and similar hosts. Point it at an **Agent Skill repository** on GitHub and it produces a **single HTML file**: a **scrollable, visual map** of how **user-facing actions** connect to **what the host, model, and agents do underneath**—not a pile of tiny Markdown files, but one page you can **read like a UI/UX walkthrough**.

**Repo:** [github.com/YeJe-cpu/codebase-to-web](https://github.com/YeJe-cpu/codebase-to-web) · [中文说明](README.zh-CN.md)

---

## Who is this for?

* **Vibe coders / learners** browsing GitHub who want to **get oriented fast**: install location, trigger phrases, and **which files load in what order**.  
* **Anyone reading OSS skill repos** where the README sells the idea but the **real entrypoints** live in hooks, `references/`, or subcommands—this page lines up **visible path** and **backstage mechanics**.  
* **People who need to ship or align**: one **double-clickable `.html`** (or a link) that explains the call graph to teammates or contributors.

---

## What’s inside the generated page?

You get **one self-contained `.html`** (no separate build step). Typical sections, top to bottom:

1. **Repo meta bar** — link, stars, forks, created-at, with an optional **snapshot** timestamp in the footer.  
2. **Plain-language intro** — what the repo is **for**, in one breath.  
3. **Component path (step-through)** — chat-style beats: user input → host/routing → which `SKILL.md` / `references/` loads → next model or agent move. Length follows the **real** repo; no forced “always four bubbles.”  
4. **Steps (surface vs backstage)** — what you **do in the UI** vs **what runs behind** (files read, hooks, commands).  
5. **Repository tree** — matches the repo layout so you can spot paths **not spelled out in the README**.  
6. **README context bullets** — short signals: demand, distribution, moat-ish notes, compliance flags—**fewer browser tabs**.  
7. **Visual system** — default **Lab·Canonical** (warm editorial type, comfortable measure); avoids cliché purple gradients and generic Inter hero type. Optional cool/engineering variants on request. Informed by [Anthropic `frontend-design`](https://github.com/anthropics/skills/tree/main/skills/frontend-design).

**Google Fonts** may need **one online load** the first time you open the file; after that it can be viewed offline in the browser cache.

### Screenshots in this README

Add an image file (e.g. `assets/preview.png`) and reference it:

```markdown
![Example page](./assets/preview.png)
```

GitHub renders Markdown images automatically once the file is in the repo.

---

## What we optimize for

* **Path first** — **who loads whom** before long prose.  
* **Surface × backstage** — tie each user-visible step to **model/agent behavior**.  
* **One artifact** — a **single overview page**, not a mandatory quiz-based “course loop” (different use case from deep **application-code** curricula—see acknowledgements).  
* **Less tab-hopping** — stars, tree, and README angles on **one** page.

---

## What’s in this repository?

The clone **is** the publishable skill bundle:

```
codebase-to-web/
├── SKILL.md              # primary instructions (most hosts read this)
├── SKILL.zh-CN.md        # Chinese mirror (optional; merge if your host reads one file)
├── references/           # layout, checklist, design constraints for HTML generation
├── web/                  # default output folder (generated .html usually gitignored; may contain .gitkeep)
├── README.md
├── README.zh-CN.md
└── LICENSE
```

| Path | Role |
|------|------|
| `SKILL.md`, `SKILL.zh-CN.md` | Generation rules, section order, **output language** policy |
| `references/` | See [`references/README.md`](references/README.md) |
| `web/` | Default save location, typically `web/<owner>-<repo>.html` |

---

## Install

Copy the **`codebase-to-web`** folder into the skills path your host expects:

| Host | Typical location |
|------|------------------|
| **Cursor** | e.g. `.agents/skills/codebase-to-web/` in the project |
| **Claude Code** | e.g. `~/.claude/skills/codebase-to-web/` |
| **Windsurf** | per current product docs |
| **OpenClaw** | e.g. `~/.openclaw/skills/` or workspace `skills/` — [OpenClaw · Skills](https://docs.openclaw.ai/skills/) |

**Page language** (all-English vs all-Chinese) follows the skill files—see `SKILL.md` / `SKILL.zh-CN.md`.

### Default output path

**`web/<owner>-<repo>.html`**, or override in your prompt.

---

## Example prompts

* “Generate a single HTML for `owner/repo` that maps **install → trigger → file order**.”  
* “Put the **component path** first as step-through bubbles, then **surface vs backstage** steps.”  
* “把这个仓库做成一页可调用的路径说明 HTML。”

---

## Design notes (short)

**Path before essays**; **prefer step-through over walls of text**; **one sharable `.html`**.

---

## Acknowledgements (and how this relates to *Codebase to Course*)

We’re grateful for **[zarazhangrui/codebase-to-course](https://github.com/zarazhangrui/codebase-to-course)** (*Codebase to Course*)—a polished project that turns codebases into **structured, course-like learning**. A high star count there mostly tells you **the problem is real**, not that smaller tools “lose by comparison.”

**Different lane:** they shine on **deep, curriculum-style walks through application code**; we focus on **one visual HTML map** for **Agent Skill repos**—install/trigger/load order and **what happens under each user action**. Both can coexist.

| | Codebase to Course | Codebase to Web |
|---|---|---|
| Typical input | Application / product repos | **Skill** bundles (`SKILL.md`, hooks, `references/`) |
| Experience | Modular, course-shaped depth | **Single-page** overview; **no mandatory Q&A course loop** |
| Idea we borrowed | Strong **component-path / timeline** clarity | Same: put the **step-through path up front** |
| Our emphasis | — | **User step ↔ model/agent behavior**; stars, tree, README context on one page |

If anything here misstates their latest behavior, open an issue and we’ll fix the copy.

---

## License

MIT — [LICENSE](LICENSE).

## Contributing

[CONTRIBUTING.md](CONTRIBUTING.md).
