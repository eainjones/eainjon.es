# eainjon.es

Personal website + writing hub for Eain Jones. Built with Astro, Markdown content collections, and zero client-side JavaScript. Everything in this repo can be deployed to any static host (GitHub Pages, Cloudflare Pages, Netlify, etc.).

## Tech overview

- **Framework**: [Astro 5](https://astro.build)
- **Styling**: vanilla CSS with a lightweight global stylesheet
- **Content**: Markdown/MDX via `src/content/blog`
- **Metadata**: centralized in `src/consts.ts` so navigation, social links, and contact info stay in sync
- **Feeds**: automatic RSS + sitemap via official Astro integrations

## Getting started

```bash
npm install        # install dependencies
npm run dev        # start a dev server on http://localhost:4321
npm run build      # output the static site to dist/
npm run preview    # serve the production build locally
```

## Content & customization

| Area            | How to update it                                                                    |
| --------------- | ------------------------------------------------------------------------------------ |
| Site metadata   | `src/consts.ts` – edit `SITE_TITLE`, `SITE_DESCRIPTION`, nav, and social links here. |
| Home page copy  | `src/pages/index.astro`                                                              |
| About page      | `src/pages/about.astro`                                                              |
| Blog posts      | `src/content/blog/*.md(x)` – each post is a Markdown/MDX file with Astro frontmatter.|
| Styles          | `src/styles/global.css` plus page-level `<style>` tags.                              |

Adding a new post is as simple as creating `src/content/blog/my-post.md`:

```md
---
title: 'Meaningful title'
description: 'Short summary for cards and RSS'
pubDate: '2024-07-15'
heroImage: '../../assets/blog-placeholder-1.jpg'
---

Your Markdown content goes here.
```

Astro validates the frontmatter at build time, so you will get type errors if you forget a required field.

## Deployment

Both GitHub Pages and Cloudflare Pages work out of the box because the project emits static files to `dist/`.

### GitHub Pages (via GitHub Actions)

1. Push this repository to GitHub.
2. In the repo settings enable Pages with “GitHub Actions” as the source.
3. The workflow in `.github/workflows/deploy.yml` runs on every push to `main`, executes `npm ci && npm run build`, and deploys the artifact.

No extra configuration is needed unless you want environment variables (add them under **Settings -> Secrets and variables -> Actions**).

### Cloudflare Pages

1. Create a new Pages project and connect it to this repository.
2. Build command: `npm run build`
3. Output directory: `dist`
4. (Optional) Configure preview deployments for every branch.

Cloudflare handles HTTPS certificates automatically. If you ever switch hosts, you do not have to change code—just point the new service at the same build command and output folder.

## Notes

- `astro.config.mjs` already has the official sitemap and MDX integrations enabled.
- Fonts live in `public/fonts`, so customizing typography is as easy as swapping the `.woff` files.
- Feel free to duplicate this structure for your own site—just update the metadata constants and start publishing.
