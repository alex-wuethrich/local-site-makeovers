# QA checklist

Run through this before calling any new site done (used by the `/new-site` skill, but applies to manual edits too).

- [ ] **Responsive**: no horizontal scroll or broken layout at ~375px width.
- [ ] **No fabricated content**: every testimonial, name, phone number, email, and address is either real or an explicit `[TODO: ...]` marker — nothing invented-but-plausible.
- [ ] **Title/meta**: `<title>` and meta description are specific to this business, no leftover placeholder text.
- [ ] **Nav anchors**: every nav link's `#id` matches a real section id on the page.
- [ ] **Alt text**: every `<img>` has meaningful alt text (or `alt=""` if purely decorative).
- [ ] **Footer year**: current year is set via script, not hardcoded.
- [ ] **Contact links**: `tel:`/`mailto:` hrefs are correctly formatted and match the displayed text.
- [ ] **No em dashes**: body copy uses short hyphens (` - `), not em dashes (—).
- [ ] **Favicon**: present and business-appropriate (e.g. emoji-based `data:` favicon), not the browser default.
- [ ] **No build artifacts**: no `node_modules/`, no unused dependencies — site opens directly from `index.html`.
- [ ] **Own repo**: site lives in its own GitHub repo (not a folder in this toolkit repo), with GitHub Pages enabled and the live URL confirmed.
