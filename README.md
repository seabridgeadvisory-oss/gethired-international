# Get Hired International

Marketing site for **Get Hired International** — career coaching for expats and
internationals job hunting in the Netherlands.

Live: https://gethired-international.com

## Structure

```
index.html                     Homepage (single scrolling page)
og-image.jpg                   Social share card (1200×630)
robots.txt                     Crawl directives
sitemap.xml                    5 URLs, submitted to Google Search Console
images/                        Photography
articles/<slug>/index.html     One page per article
```

Static HTML. No build step, no dependencies, no framework.

## Deploying

Vercel serves this directly from the repository root — no build command, no
output directory, no framework preset. Pushing to `main` deploys to production;
every other branch and pull request gets its own preview URL.

Vercel project settings that matter:

- **Framework Preset:** Other
- **Root Directory:** `./` (leave blank)
- **Build Command:** leave blank
- **Output Directory:** leave blank

`vercel.json` pins `trailingSlash: true`. Every canonical tag and every sitemap
entry ends in a slash, so without this one page would answer on two addresses.
Do not change it without updating those at the same time.

## Editing

- **Design tokens** (colour, type, spacing) live in the `:root` block at the top
  of each file's `<style>`.
- **Fonts**: Newsreader (display) + Archivo (body), loaded from Google Fonts.
- **Contact form** posts to FormSubmit; the address is in the inline script at
  the bottom of `index.html`.
- **Testimonials**: a styled but commented-out section sits above `id="clients"`
  in `index.html`. Uncomment it and replace the placeholders with real quotes.

## Adding an article

Copy any folder under `articles/`, change the slug, the `<title>`, the meta
description, the canonical URL, the JSON-LD block and the body. Then add the new
URL to `sitemap.xml` and a card to the Insights section of `index.html`.
