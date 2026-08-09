# Agent instructions for this repo

This repo produces pitch websites for real local businesses (see `README.md` for the outreach workflow and hosting). These rules exist so any Claude Code session can build a new site correctly without re-deriving the process each time.

## Structure

- One folder per business under `sites/<business-slug>/` — `index.html`, `styles.css`, and `script.js` if any interactivity is used.
- `sites/_template/` is a plain structural starting point (sections, no build step), not a visual style to copy verbatim — see Design philosophy below.
- Static only: no build step, no bundler, no npm dependencies. Everything must run by opening `index.html` directly in a browser.

## Design philosophy: bespoke every time

Every site should have its own visual identity — fonts, color palette, and small decorative touches — tailored to that specific business's vibe (cozy bakery vs. modern dentist vs. hardware store should not look the same). Do not reuse another business's specific design as a template. `_template` gives you the section skeleton (hero, offerings, story/about, hours or process, contact, footer) to start from structurally; the look and feel should be designed fresh for each business based on its intake answers.

## Reusable behavior patterns

These are generic, framework-agnostic patterns — reuse the *behavior*, not literal copy-pasted files, since markup/class names will differ per bespoke design:

- **Footer year**: set the current year into a `<span id="year">` via a one-line script (`document.getElementById('year').textContent = new Date().getFullYear();`) instead of hardcoding a year that goes stale.
- **Mobile nav toggle**: a button toggles an `open`/expanded class on the nav container; clicking a nav link closes it again. Keep it a few lines of vanilla JS — no dependency needed.
- **Scroll-reveal**: use an `IntersectionObserver` to add an `in`/visible class to elements as they scroll into view, rather than a JS animation library.

## Content honesty (hard rule)

Never fabricate testimonials, reviews, customer names, or contact details (phone numbers, emails, addresses). If real information hasn't been supplied yet, leave an explicit, unmissable placeholder like `[TODO: phone number]` instead of a plausible-looking fake. A pitch site is meant to be shown to the real owner — invented "customer quotes" or fake numbers undermine that and are not acceptable even as a mockup.

## Baseline technical bar

Every site must:
- Be mobile responsive (check at ~375px width, no horizontal scroll).
- Use semantic headings and real alt text on images.
- Have a business-specific `<title>` and meta description — no leftover placeholder text (e.g. "Business Name").
- Include a favicon (there's no existing site to copy one from — add a simple one, e.g. an emoji-based `data:` URI favicon).
- Use correctly formatted `tel:`/`mailto:` links.

Before calling a site done, run through `docs/qa-checklist.md`.

## Building a new site

Use the `/new-site` skill (`.claude/skills/new-site/SKILL.md`) to scaffold and build a new business site end-to-end: intake questions → bespoke build → QA checklist. After that, finish with the manual steps in `README.md` (review, add real photos, commit, push).
