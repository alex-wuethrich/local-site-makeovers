---
name: new-site
description: Scaffold and build a new bespoke pitch website for a local business as its own standalone GitHub repo. Use when the user wants to start a new site or pitch a new local business.
---

# Build a new pitch site

Follow `AGENTS.md` at the repo root for all conventions (bespoke design philosophy, reusable behavior patterns, content-honesty rule, technical bar). This skill is the step-by-step process for producing one new site end-to-end, as its own repo — never as a folder inside this toolkit repo.

## 1. Get the business slug

If not already given, ask for the business name and derive a `kebab-case` slug. Check `gh repo view alex-wuethrich/<slug>` to confirm that repo doesn't already exist.

## 2. Intake

Ask the user for (batch these into one or two questions, don't interrogate one field at a time):

- Business type/category and general vibe (e.g. cozy, modern, playful, upscale).
- Business name and tagline (or ask you to propose a few).
- Services or products offered — enough detail to write real copy, not filler.
- Hours and location.
- Real phone number, email, and/or address.
- Any real testimonials or quotes on hand (if none, don't fabricate — see content-honesty rule).
- Any brand preferences: colors, fonts, existing logo/photos.

Anything the user doesn't have yet gets an explicit `[TODO: ...]` marker in the output — never invent it.

## 3. Design

Based on the intake, decide a bespoke visual identity for this business specifically: a font pairing, a color palette, and a couple of small decorative touches that fit its vibe. Do not reuse another business's specific design — `template/` gives you the section skeleton only (hero, offerings, story/about, hours, contact, footer), not the look.

## 4. Create the repo

- `gh repo create alex-wuethrich/<slug> --public --description "..."`
- Local checkout at `C:\Sites\<slug>\` — `mkdir`, `git init -b main`, `git remote add origin https://github.com/alex-wuethrich/<slug>.git`.

## 5. Build

In `C:\Sites\<slug>\`, create `index.html`, `styles.css`, `script.js` (if using the mobile nav toggle or scroll-reveal patterns from `AGENTS.md`), and a short `README.md` (business name, one line of description, the live Pages URL). Write real copy from the intake answers. Keep it a static site: no build step, no dependencies beyond optionally a Google Fonts `<link>`.

## 6. QA

Run through every item in `docs/qa-checklist.md` against the new site before calling it done. Fix anything that fails.

## 7. Commit, push, and go live

- `git add -A && git commit` and push to `origin main`.
- Enable GitHub Pages: `gh api -X POST repos/alex-wuethrich/<slug>/pages -f "source[branch]=main" -f "source[path]=/"`.
- Report the live URL to the user: `https://alex-wuethrich.github.io/<slug>/` (takes a few minutes to propagate the first time).

## 8. Hand off

Tell the user the site is ready for review — check it live, add real photos if any were missing, and follow up on any `[TODO]` markers left from the intake.
