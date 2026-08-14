# Agent instructions for this repo

This is **`site-pitch-toolkit`** — shared process and tooling for building pitch websites for real local businesses. It does not contain the sites themselves. These rules exist so any Claude Code session can build a new site correctly without re-deriving the process each time.

## Structure: one repo per business

Every business site is its own **separate GitHub repo** (`https://github.com/alex-wuethrich/<business-slug>`), not a folder in this repo. Local checkouts live under `C:\Sites\<business-slug>\`, this toolkit repo stays at `C:\Claude`. Each site repo contains just `index.html`, `styles.css`, `script.js` (if needed), and a short `README.md` — static only, no build step, no bundler, no npm dependencies, everything runs by opening `index.html` directly in a browser.

`template/` in *this* repo is a plain structural starting point (sections, no build step), not a visual style to copy verbatim — see Design philosophy below.

## Design philosophy: bespoke every time

Every site should have its own visual identity — fonts, color palette, and small decorative touches — tailored to that specific business's vibe (cozy bakery vs. modern dentist vs. hardware store should not look the same). Do not reuse another business's specific design as a template. `template/` gives you the section skeleton (hero, offerings, story/about, hours or process, contact, footer) to start from structurally; the look and feel should be designed fresh for each business based on its intake answers.

## Reusable behavior patterns

These are generic, framework-agnostic patterns — reuse the *behavior*, not literal copy-pasted files, since markup/class names will differ per bespoke design:

- **Footer year**: set the current year into a `<span id="year">` via a one-line script (`document.getElementById('year').textContent = new Date().getFullYear();`) instead of hardcoding a year that goes stale.
- **Mobile nav toggle**: a button toggles an `open`/expanded class on the nav container; clicking a nav link closes it again. Keep it a few lines of vanilla JS — no dependency needed.
- **Scroll-reveal**: use an `IntersectionObserver` to add an `in`/visible class to elements as they scroll into view, rather than a JS animation library.

## Content honesty (hard rule)

Never fabricate testimonials, reviews, customer names, or contact details (phone numbers, emails, addresses). If real information hasn't been supplied yet, leave an explicit, unmissable placeholder like `[TODO: phone number]` instead of a plausible-looking fake. A pitch site is meant to be shown to the real owner — invented "customer quotes" or fake numbers undermine that and are not acceptable even as a mockup.

## Copy style

Don't use em dashes (—) in body copy - they read as generated/AI-written. Use a short hyphen with spaces (` - `) instead, or restructure the sentence.

## Baseline technical bar

Every site must:
- Be mobile responsive (check at ~375px width, no horizontal scroll).
- Use semantic headings and real alt text on images.
- Have a business-specific `<title>` and meta description — no leftover placeholder text (e.g. "Business Name").
- Include a favicon (there's no existing site to copy one from — add a simple one, e.g. an emoji-based `data:` URI favicon).
- Use correctly formatted `tel:`/`mailto:` links.

Before calling a site done, run through `docs/qa-checklist.md`.

## Building a new site

Use the `/new-site` skill (`.claude/skills/new-site/SKILL.md`), run from this repo (`C:\Claude`), to build a new business site end-to-end: intake → bespoke build → **its own new GitHub repo** → QA checklist → GitHub Pages enabled → live URL reported back. See the skill file for the exact steps.
