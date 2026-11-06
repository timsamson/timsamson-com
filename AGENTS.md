---
status: current
updated: 2026-11-06
purpose: Agent entry point. Read this first.
---

# AGENTS.md — timsamson-com

## What this is
- Tim Samson's personal site and blog, "Coasters and Cupcakes": https://timsamson.com (Astro static site, Cloudflare Pages project `timsamson-com`).
- Also hosts `/privacy`, the policy linked from the Chief of Staff (agent-platform) Google OAuth consent screen (`src/pages/privacy.astro`, commit f4f8115).
- Personal repo (`timsamson/timsamson-com`): docs live in this repo. Not RocketRez infra; reads no production data (README.md).

## Read in this order
1. docs/README.md (index)
2. docs/ARCHITECTURE.md
3. docs/BUILD-PLAN.md ("Now" first)
4. docs/DECISIONS.md, docs/OPEN-QUESTIONS.md (grep ids only)

## Build / test / run
```bash
npm install && npm run dev      # http://localhost:4321
npm run build                   # static output to dist/; fails on bad post front matter
```
- No test or typecheck script exists (package.json). The build is the only check.

## Reading budget
Don't read DECISIONS, OPEN-QUESTIONS or log/ whole. Read BUILD-PLAN "Now", then grep the D-/Q- ids and the log file it links.

## Hard rules and traps
- A push to `main` deploys (Pages has a Git provider, README.md). Work on a branch and PR; never push to main without Tim's yes.
- Post front matter is Zod-enforced (`src/content.config.ts:4-14`); a bad field fails the build.
- Filter chips are a fixed list in `src/pages/index.astro:9`; a new category needs a chip added there.
- `/privacy` is a public OAuth-consent dependency: keep the URL and its scopes text accurate (see RUNBOOK).
- Never write secret values; none are needed in this repo.

## Current step
Q5 (optional): align or remove the `wrangler.toml` compatibility date on the next code touch. Nothing else planned (D-004). Log: docs/log/2026-11-06-pages-deploy-facts.md
