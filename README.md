# site-pitch-toolkit

Shared tooling for building pitch websites for local businesses — redesigns built to show owners what a modern site could look like.

This repo holds the **process**, not the sites. Each business site lives in its own separate GitHub repo (see `AGENTS.md`), created and built via the `/new-site` skill.

## What's here

- `AGENTS.md` — conventions every site must follow (structure, design philosophy, content-honesty rule, technical bar).
- `template/` — a plain structural starting point (sections only, no visual style) for a new site's skeleton.
- `docs/qa-checklist.md` — checklist run before any site is called done.
- `.claude/skills/new-site/SKILL.md` — the `/new-site` skill: intake → bespoke build → its own repo → QA → live URL.

## Workflow

1. Open Claude Code with this repo (`C:\Claude`) as the working directory so the `/new-site` skill is available.
2. Run `/new-site` and answer the intake questions for the business.
3. The skill creates a new GitHub repo for that business, builds the site, and enables GitHub Pages.
4. Visit the shop with the live URL to show them.

Site repos live locally under `C:\Sites\<business-slug>\`, hosted at `https://alex-wuethrich.github.io/<business-slug>/`.
