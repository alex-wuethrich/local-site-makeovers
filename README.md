# Local Site Makeovers

Redesigns of local business websites, built as pitches to show owners what a modern site could look like.

## Structure

Each business gets its own folder under `/sites/`:

```
sites/
  _template/       starter template — copy this for each new business
  <business-slug>/ e.g. joes-pizza, main-street-dentist
```

## Workflow

1. Find a local business with an outdated/broken site.
2. Copy `sites/_template` to `sites/<business-slug>`.
3. Fill in real business info (name, hours, services, phone, address, photos).
4. Commit and push — GitHub Pages serves it automatically.
5. Visit the shop with the live URL to show them.

## Hosting

Deployed via GitHub Pages. Each site is a static folder — no build step required.

Live at: `https://alex-wuethrich.github.io/local-site-makeovers/sites/<business-slug>/`
