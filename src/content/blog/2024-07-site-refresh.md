---
title: 'A deliberately small personal site'
description: 'Why I rebuilt eainjon.es with Astro and how I plan to keep it fast and boring.'
pubDate: '2024-07-15'
heroImage: '../../assets/blog-placeholder-1.jpg'
---

When I finally sat down to rebuild this site I wrote three bullet points at the top of a notebook page:

1. The site should be embarrassingly fast on spotty Wi-Fi.
2. Every word needs to live in a format that I can edit from a phone.
3. Deployments should be automatic even if I go on vacation for a month.

Astro checks those boxes with very little code. It gets me islands when I need them, MDX support for notes like this one, and a routing system that feels closer to classic HTML than a heavy framework. The starter template already ships with an RSS feed and sitemap so I simply trimmed the defaults and dropped in my own metadata.

I leaned into content collections because I want to keep writing friction low. Each post is just a Markdown file in `src/content/blog`. Frontmatter handles the title, summary, and hero image. Astro takes care of type safety so I know when I forget a field.

The other big win is centralizing shared data in `src/consts.ts`. Navigation, social links, and contact info all live in the same place which means the header, footer, and RSS feed pull from a single source of truth. Editing the site now usually means touching one file:

```
src/consts.ts     # metadata
src/pages/index   # landing content
src/content/blog  # posts
```

This level of simplicity is intentional. I oscillate between client projects, advisory work, and tinkering with automation. The last thing I need is a personal website that requires “yak shaving” every time I want to publish a note or update availability.

If you’re in the same boat, clone this repository and plug in your own content. Everything stays static so it runs anywhere from GitHub Pages to Cloudflare Pages or even behind a password on Netlify. Let the big clouds worry about servers while you focus on writing.
