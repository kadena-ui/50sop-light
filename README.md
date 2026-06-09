# 50 Shades of Paid — Static Site

Static HTML site for **kadenatate.com**, deployed via GitHub and Cloudflare Pages.

## Repo structure

```
50sop-light/  (repo root)
|-- index.html                            <- homepage, served at kadenatate.com/
|-- about.html
|-- blog.html
|-- canvases.html
|-- contact.html
|-- diagnostics.html
|-- legal.html
|-- mastermind.html
|-- media.html
|-- newsletter.html
|-- product-business-stress-test.html
|-- service-business-stress-test.html
|-- shop.html
|
|-- favicon.ico                           <- browser tab icon (K monogram, gold on midnight blue)
|-- favicon-96x96.png
|-- apple-touch-icon.png                  <- iPhone home screen icon
|-- web-app-manifest-192x192.png          <- Android home screen icon
|-- web-app-manifest-512x512.png
|-- site.webmanifest                      <- PWA manifest, branded as "Kadena Tate"
|
|-- Blog/                                 <- blog post content (posts.json)
|-- email-templates/                      <- GoHighLevel email templates (reference only, not served)
|
`-- README.md                             <- this file
```

All 13 HTML pages live at the repo root, alongside the favicon asset files.

## Current state of the site

- Every page has a consistent nav and footer
- Both the nav and footer **Blog** link on every page points to `blog.html` (internal, same-window)
- No external `revenueremix.com` Blog references remain anywhere in the site
- All internal `.html` links have been audited and resolve to real files
- Favicon installed on every page: browser tabs, iPhone home screen, Android home screen, Windows taskbar

## Deployment

Cloudflare Pages is configured to deploy directly from this GitHub repo:

- **Build command:** (none — static site)
- **Build output directory:** `/` (root)
- **Branch:** `main`

Any commit pushed to `main` triggers an automatic redeploy. No build step required.

## What does NOT get deployed to the live site

- `email-templates/` — these HTML files live inside GoHighLevel's email builder, not on the website. They're kept here only as a backup reference copy.
- `README.md` — ignored by Cloudflare Pages.

## Paid / member-only content

Mastermind deliverables (the 9 canvas PDFs, etc.) are NOT stored in this repo. Anything in this repo is publicly accessible on the live site, so gated content belongs in a system that checks membership before serving files. The canvas PDFs are delivered through GoHighLevel's Memberships area.

## Future cleanup (optional)

- Image assets are currently embedded as base64 inside the HTML files. If a redesign happens, consider extracting them into an `images/` folder to reduce HTML file size.
