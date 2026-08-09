---
name: new-site
description: Scaffold and build a new bespoke pitch website for a local business in this repo (sites/<slug>/). Use when the user wants to start a new site, pitch a new local business, or add a business to sites/.
---

# Build a new pitch site

Follow `AGENTS.md` at the repo root for all conventions (bespoke design philosophy, reusable behavior patterns, content-honesty rule, technical bar). This skill is the step-by-step process for producing one new site end-to-end.

## 1. Get the business slug

If not already given, ask for the business name and derive a `kebab-case` slug for `sites/<slug>/`. Confirm the slug doesn't already exist under `sites/`.

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

Based on the intake, decide a bespoke visual identity for this business specifically: a font pairing, a color palette, and a couple of small decorative touches that fit its vibe. Do not reuse another business's specific design — `sites/_template/` gives you the section skeleton only (hero, offerings, story/about, hours, contact, footer), not the look.

## 4. Build

Create `sites/<slug>/index.html`, `styles.css`, and `script.js` (if using the mobile nav toggle or scroll-reveal patterns from `AGENTS.md`). Write real copy from the intake answers. Keep it a static site: no build step, no dependencies beyond optionally a Google Fonts `<link>`.

## 5. QA

Run through every item in `docs/qa-checklist.md` against the new site before calling it done. Fix anything that fails.

## 6. Hand off

Tell the user the site is ready for review, and point them to the existing `README.md` workflow to finish: review the content, drop in real photos, commit, and push (GitHub Pages serves it automatically at `https://alex-wuethrich.github.io/local-site-makeovers/sites/<slug>/`).
