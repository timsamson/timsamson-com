# timsamson-com

**Coasters and Cupcakes** — Tim Samson's personal site and blog.

**Live:** https://timsamson.com · Cloudflare Pages project `timsamson-com`

Astro 5 with Tailwind. A hero, a bio, and a category-filtered post list; posts are Markdown in an
Astro content collection.

> This is the personal site. It is **not** RocketRez or iQueue infrastructure — those live on the
> `iqueue.software` and `timsamson.com` *subdomain* surfaces documented in the respective repos.
> Nothing here reads production data.

## Layout

| Path | What it is |
|---|---|
| `src/pages/index.astro` | Home — hero, bio, category filter, post list |
| `src/pages/blog/[slug].astro` | Post template |
| `src/layouts/Layout.astro` | Shared shell |
| `src/content/blog/*.md` | The posts |
| `src/content.config.ts` | Collection schema (Zod) |
| `src/styles/global.css` | Tailwind entry |
| `public/` | Static assets |

## Adding a post

Drop a `.md` file in `src/content/blog/`. The schema is enforced at build time — a missing or
mistyped field fails the build rather than shipping a broken card:

```yaml
---
title: "Post title"
date: 2026-10-16
updated: 2026-10-20      # optional
excerpt: "One line for the card."
categories: ["Marketing"]  # Recipes · Marketing · Travel · Life Lessons
readTime: 6                # minutes, number not string
image: "/images/foo.jpg"   # optional
---
```

Categories on the home page are a fixed list in `index.astro` (`All Posts`, `Recipes`,
`Marketing`, `Travel`, `Life Lessons`). A post tagged with anything outside that list will not get
a filter chip — add it there too.

## Develop

```bash
npm install
npm run dev      # http://localhost:4321
npm run build    # production build to dist/
npm run preview  # serve the build locally
```

## Deploy

This Pages project **has a Git provider attached**, so a push to `main` deploys. That makes it the
exception among these repos — most of the Cloudflare projects here are direct-upload and do not
deploy on push.
