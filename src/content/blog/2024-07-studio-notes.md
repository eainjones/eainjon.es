---
title: 'Studio notes: automation, documentation, and care plans'
description: 'What I am helping clients with this month and how those learnings shape my own site.'
pubDate: '2024-07-05'
heroImage: '../../assets/blog-placeholder-3.jpg'
---

This summer has been about two things: automation glue for tiny teams and better documentation for everyone.

### Automating the boring parts

Most of my clients operate with fewer than ten people. They do not need an enterprise ERP—they need well-chosen zaps and scripts that keep the shop running. Recent wins:

* **Inventory syncs** that treat Shopify as the source of truth and update Airtable over scheduled Workers.
* **Content ingest pipelines** that let a nonprofit publish from Notion while Astro handles the display layer.
* **Quality gates** that run Lighthouse audits on pull requests so regressions get caught before launch.

### Documentation as a service

I have also been embedding with product teams that need better onboarding. My playbook usually includes:

1. Shadow a sprint, write down the actual process, and compare it to the docs.
2. Produce a concise runbook in Markdown and publish it alongside the code.
3. Record short Loom-style walkthroughs that show how to fix common breakages.

It sounds simple, but the combination reduces the stress level of the next on-call engineer dramatically.

### Care plans

Every build now ships with optional “care plans”—small monthly retainers where I handle updates, dependencies, and uptime monitoring. They are cheaper than scrambling to find help when something breaks, and they give me continuous feedback about the tools I recommend.

If you need a partner that can both build and stick around, [send me a note](mailto:hello@eainjon.es). I would love to help.
