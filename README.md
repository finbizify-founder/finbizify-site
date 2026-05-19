# finbizify-site

Public marketing landing page for **FinBizify** — self-paced AP Business + Personal Finance learning for high school students. Lives at https://finbizify.com.

## Stack

- **Hosting:** Cloudflare Pages (auto-deploys on every push to `main`)
- **DNS:** Cloudflare (`finbizify.com` and `www.finbizify.com`)
- **Content management:** Notion page → Claude regenerates `index.html` → commit → auto-deploy
- **Stack:** Static HTML + inline CSS + vanilla JS theme toggle. No build step, no framework, no JavaScript dependencies in production.

## Files

| File | Purpose |
|---|---|
| `index.html` | The entire landing page — markup, CSS, theme-toggle script, all in one file |
| `_headers` | Cloudflare Pages config: security headers + cache rules |
| `.gitignore` | Ignores common cruft (OS files, editor swap files, etc.) |
| `README.md` | This file |

## Editing the page

1. Open the Notion CMS page: **FinBizify Landing Page Content (finbizify.com)** under FinBizify Content Hub
2. Edit the relevant copy block(s)
3. Start a Claude session and say "Regenerate the FinBizify landing page HTML from the Notion CMS"
4. Claude produces an updated `index.html`
5. Commit and push to this repo — Cloudflare Pages auto-deploys in ~30 seconds

## Local preview

`index.html` is fully self-contained. Open it directly in any browser to preview.

## Deployment notes

- Cloudflare Pages project is wired to this GitHub repo's `main` branch
- Build settings: framework = none, build command = (blank), output directory = `/`
- Preview deployments: every non-`main` branch gets its own `*.pages.dev` URL automatically

## Pre-launch checklist (open items)

- [ ] Replace favicon placeholder (currently an SVG data URI in `<head>`) with a real `/favicon.ico`
- [ ] Create and add `/og-image.png` (1200×630) for social link previews
- [ ] Wire the "Join the waitlist" CTAs (currently link to dead `#waitlist` anchor) to a real form or `/waitlist` page
- [ ] Add Privacy Policy + Terms links to footer (required for a minor-audience site)
- [ ] Verify factual claims: exact AP exam name, lesson/unit counts, launch date
- [ ] Decide on fonts: current Fraunces/Inter vs brand brief's DM Serif Display/Plus Jakarta Sans
