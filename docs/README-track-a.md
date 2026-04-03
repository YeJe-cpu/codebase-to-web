# Track A — README (Developer marketing edition)

This file is an **alternate top-level README** you can paste into GitHub if you prefer positioning driven by **[jonathimer/devmarketing-skills](https://github.com/jonathimer/devmarketing-skills)**—honest, developer-native framing (no fluff, proof over adjectives).

**Important:** This repo **does not ship** `devmarketing-skills` inside the bundle. That project is a **separate install** (`npx add-skill jonathimer/devmarketing-skills` or clone). Below we only cite **which skills from that pack** informed this README’s structure.

| Lens (from devmarketing-skills) | How we used it here |
|--------------------------------|---------------------|
| [developer-audience-context](https://github.com/jonathimer/devmarketing-skills/tree/main/skills/developer-audience-context) | Primary reader = someone who **already uses** Claude Code / Cursor / agents and **hoards SKILL repos** but won’t read 12 nested Markdown files before lunch. |
| [github-presence](https://github.com/jonathimer/devmarketing-skills/tree/main/skills/github-presence) | One screen = **what it is**, **one command path**, **one output artifact**, **one comparison** (vs reading raw `SKILL.md`). |
| [devrel-content](https://github.com/jonathimer/devmarketing-skills/tree/main/skills/devrel-content) | Lead with **behavior** (“double-click HTML”) not vision (“revolutionize”). |
| [open-source-marketing](https://github.com/jonathimer/devmarketing-skills/tree/main/skills/open-source-marketing) | No fake roadmap, no “synergy”—MIT, single purpose, PRs welcome. |

---

## The problem (developer-native)

You don’t distrust Markdown. You distrust **uncertainty about call order**:

- *Which folder does the host actually load?*
- *What’s the first user-visible step vs the first file the agent reads?*
- *Is the README star count “real demand” or “repo in a bundle”?*

A flat `SKILL.md` answers *text*. It doesn’t always answer **journey**.

---

## What we ship

**One skill.** One output shape: **single-file HTML** (“Skill Lab page”) with:

1. **GitHub meta** (stars/forks/created—snapshot in footer so nobody argues later)  
2. **Plain-language blurb** (what the repo *does* in one breath)  
3. **Component-path journey** (chat you can step through—*who loads whom*)  
4. **Steps** (what you see vs what happens “under the hood”)  
5. **Tree** + **README heat bullets** (why it spreads / where it’s brittle / compliance)

Default narrative language for generated pages is **Chinese** (实验室页). Ask EN-only in your prompt if you want.

---

## Honest limitations

- This is **not** a full interactive course (no quiz engine, no module progress bar). For that, use [codebase-to-course](https://github.com/zarazhangrui/codebase-to-course) on **application** repos.  
- Output needs **Google Fonts once** (or self-host if you fork the skill).

---

## Install (same as main repo)

1. Copy this folder to `~/.claude/skills/` or `.agents/skills/`.  
2. Say: **“Turn `owner/repo` into a Skill Lab HTML.”**  
3. Find output under `skill-lab/<owner>-<repo>.html` by default.

---

## Why trust this pitch?

Because it admits tradeoffs, points to a **complementary** star repo (`codebase-to-course`), and tells you **exactly** what file you get. If we’re wrong, open an issue with the repo URL and the wrong call path—we’ll fix the skill, not the landing page grammar.

---

## License

MIT — see [LICENSE](../LICENSE).

Visual discipline borrows ideas from [Anthropic `frontend-design`](https://github.com/anthropics/skills/tree/main/skills/frontend-design) (not bundled).
