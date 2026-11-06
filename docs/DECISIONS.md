---
status: current
updated: 2026-11-05
purpose: Decisions. Accepted records are never edited.
---

# Decisions

Backfilled from history; "Why" is inferred and marked as such.

### D-001 · Astro static site on Cloudflare Pages
- **Status:** accepted · 2026-10 (inferred from bdd2a7a)
- **Decision:** Personal site is an Astro static build on Cloudflare Pages, migrated from Wix.
- **Why:** inferred from bdd2a7a ("Initial Astro site migrated from Wix"); alternatives not recorded.
- **Affects:** whole repo

### D-002 · Posts as Markdown in a schema-checked content collection
- **Status:** accepted · 2026-10 (inferred from `src/content.config.ts`)
- **Decision:** Posts are `.md` files validated by Zod at build.
- **Why:** inferred from README ("a missing or mistyped field fails the build rather than shipping a broken card").
- **Affects:** `src/content/blog/`, `src/content.config.ts`

### D-003 · Host the Chief of Staff privacy policy at /privacy
- **Status:** accepted · 2026-11-01
- **Decision:** `timsamson.com/privacy` is the policy URL for the Google OAuth consent screen.
- **Why:** from f4f8115 ("Google's consent screen links to timsamson.com/privacy ... agent-platform D-067").
- **Affects:** `src/pages/privacy.astro`
