---
title: 'GitHub Pages vs. Cloudflare Pages for personal sites'
description: 'How I host this site for free and the knobs I tweak on each platform.'
pubDate: '2024-07-12'
heroImage: '../../assets/blog-placeholder-2.jpg'
---

The two hosts I recommend to clients who just need static files on the internet are GitHub Pages and Cloudflare Pages. They both have free tiers, support custom domains, and integrate nicely with Astro.

## GitHub Pages

* **Best for** folks already storing code on GitHub.
* **Build command**: `npm run build`
* **Output directory**: `dist`
* **Why I like it**: first-party GitHub Actions workflow, automatic HTTPS, and simple permissions.

I keep a deploy workflow in `.github/workflows/deploy.yml`. Whenever `main` changes the action checks out the repo, runs `npm ci && npm run build`, and ships the result to the GitHub Pages CDN. The `docs` branch dance is gone—everything is artifact based now.

## Cloudflare Pages

* **Best for** teams that need branch previews, KV, or Workers integrations.
* **Build command**: `npm run build`
* **Output directory**: `dist`
* **Why I like it**: branch previews, instant rollbacks, and generous bandwidth limits.

After connecting the repository you can configure environment variables and custom headers inside the Pages dashboard. I normally create a production project that points at `main` and a preview project that listens to every branch. This makes it easy to show stakeholders a link without touching GitHub settings.

## Which one should you pick?

Honestly, it comes down to where you already live. For this site GitHub Pages is enough, but I keep the option to flip the switch to Cloudflare Pages by reusing the same `npm run build` output. Both providers happily serve the static `dist` directory Astro generates.

Cheap (or free) infrastructure means I can spend more time writing and less time moving YAML around. That is a trade I will make every single day.
