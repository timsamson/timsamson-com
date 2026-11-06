---
status: current
updated: 2026-11-05
purpose: Requirements, inferred from the code. Status marks built vs planned.
---

# Requirements

All inferred from code on `origin/main` (f4f8115); none were written down by Tim. Status = built.

| Id | Requirement | Evidence |
|---|---|---|
| R-01 | Home page with hero, bio, category-filtered post list | `src/pages/index.astro` |
| R-02 | Each post renders from Markdown at `/blog/<slug>` | `src/pages/blog/[slug].astro`, `src/content/blog/` |
| R-03 | Post front matter is validated at build time | `src/content.config.ts:4-14` |
| R-04 | `/privacy` page for the Chief of Staff OAuth consent screen | `src/pages/privacy.astro`, f4f8115 |
| N-01 | Fully static output | `astro.config.mjs` (`output: 'static'`) |
| N-02 | Security headers on all routes | `public/_headers` |
| N-03 | Canonical URL on every page | `src/layouts/Layout.astro` |
