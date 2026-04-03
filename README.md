# Repo to Skill Lab

A **Claude Code** skill that turns **Agent Skill repositories** on GitHub into a **beautiful, self-contained, single-page HTML lab**.

Point it at a skills repo. Get back a **stunning lab you can double-click**—with **scroll-friendly sections**, an **interactive step-through journey** (who loads whom), **plain-language blurbs**, a **repo tree**, and **README “why it spreads”** context—without the typical purple-gradient AI look.

> **README tracks (pick one for your GitHub default):**  
> - **Track B (this file)** — same **section rhythm** as [zarazhangrui/codebase-to-course](https://github.com/zarazhangrui/codebase-to-course).  
> - **Track A** — developer-native positioning using lenses from [jonathimer/devmarketing-skills](https://github.com/jonathimer/devmarketing-skills) (not bundled; [Track A EN](docs/README-track-a.md) · [Track A 中文](docs/README-track-a.zh-CN.md)).  
> **Repo names:** [docs/REPO_NAME_IDEAS.md](docs/REPO_NAME_IDEAS.md) · **GitHub About box:** [docs/GITHUB-ABOUT.md](docs/GITHUB-ABOUT.md)

[中文说明（Track B）](README.zh-CN.md)

---

## Who is this for?

**“Skill hoarders who still have a job to do”** — you already use Claude Code, Cursor, Windsurf, or similar. You **star skill repos** (or vendor `anthropics/skills`, community packs, in-house `SKILL.md` trees). They work. But you don’t yet have a **single, trustworthy map** of **install path → trigger → which file fires → what the README hype implies**.

**Your goals are practical, not academic:**

* **Steer agents** with the right slash-command or folder layout  
* **Spot lies fast** when README says “just clone” but hooks live elsewhere  
* **Onboard a teammate** without screen-sharing fifteen Markdown tabs  
* **Talk maintainer-to-maintainer** with a shared artifact (the HTML lab)

You’re not trying to become a DevRel deck designer. You want **one honest page**.

---

## What the lab looks like

The output is a **single HTML file** — no bundler, no `npm install`, works offline after first font load (Google Fonts). It includes:

* **GitHub meta bar** — stars, forks, created-at (footer marks **snapshot time**)
* **Plain-language blurb** — what the repo is *for* in one breath  
* **Interactive journey** — “next message” chat tracing **user → host → skill / ref → …** (not a fixed 4-bubble toy; length follows the real path)
* **User vs behind-the-scenes steps** — what you see in the product vs what files/hooks actually run  
* **Repository tree** — monospace skeleton aligned with the README  
* **README heat bullets** — demand / distribution / moat / compliance, one line each  
* **Warm, distinctive design** — **Lab·Canonical** tokens (Fraunces + Source Sans 3 + terracotta accent + balanced column). Ideas aligned with [Anthropic `frontend-design`](https://github.com/anthropics/skills/tree/main/skills/frontend-design); optional cool / teal variants on request.

---

## How to use

### As a Claude Code skill

1. Copy the `repo-to-skill-lab` folder into `~/.claude/skills/` (or `.agents/skills/repo-to-skill-lab/` for Cursor-style layouts).  
2. Open any project in Claude Code / Cursor.  
3. Say: *“Turn `owner/repo` into a Skill Lab HTML page.”*

### Output path

By default: **`skill-lab/<owner>-<repo>.html`**. Change the folder in your prompt if you want another path.

---

## Trigger phrases

* “Turn this skills repo into a Skill Lab HTML”
* “Generate a lab page for this Agent Skill repo”
* “Explain this `SKILL.md` tree as a single interactive page”
* “Journey first, then step-by-step — 实验室页”
* “把这个仓库做成 Skill 实验室单页”

---

## Design philosophy

### Install first, journey second

Skills education usually *starts* at folder trees. Practitioners *start* at **what they type** and **what answers come back**. This skill **forces the journey block before** the long-form steps—so the mental model sticks.

### Show the call path, don’t bury it

If something can be a **step-through chat** or a **tree**, it shouldn’t be six paragraphs of prose. Max **2–3 sentences** per blurb block; heavier detail belongs in collapsibles or follow-on docs you already maintain.

### One artifact, one URL-shaped name

The HTML filename is **`owner-repo.html`** so it’s easy to diff, zip, or attach. No build step means **CI can’t lie** about “what shipped”.

### Original structure, honest wording

Directory lists track the **real repo**. Meta numbers come from **GitHub API** when available; footer tells readers the snapshot is **time-bounded**.

### Pair with *Codebase to Course*

Use [zarazhangrui/codebase-to-course](https://github.com/zarazhangrui/codebase-to-course) when the subject is **application code** (modules, quizzes, deep runtime). Use **Repo to Skill Lab** when the subject is **`SKILL.md` ecosystems** (packaging, triggers, references).

---

## Skill structure

```
repo-to-skill-lab/
├── SKILL.md
├── references/
│   ├── workflow.md
│   ├── ui-tokens.md
│   └── frontend-design-notes.md
├── docs/
│   ├── README-track-a.md          # Developer-marketing edition
│   ├── README-track-a.zh-CN.md
│   ├── REPO_NAME_IDEAS.md
│   └── GITHUB-ABOUT.md            # Description + Topics
├── skill-lab/                     # default output (gitignored *.html)
├── README.md                      # Track B (this file)
└── README.zh-CN.md
```

---

## License

MIT — see [LICENSE](LICENSE).

---

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md). PRs that improve journey fidelity or EN-first output are especially welcome.
