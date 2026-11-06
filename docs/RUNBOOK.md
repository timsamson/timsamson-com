---
status: draft
updated: 2026-11-05
purpose: How to deploy, operate and fix it.
---

# Runbook

## Deploy
- Push to `main` deploys via Cloudflare Pages project `timsamson-com` (README.md). Use a branch and PR; merge only with Tim's yes.
- Local check before PR: `npm ci && npm run build`.

## Rollback
- Not recorded. Revert the commit on `main`, or redeploy a prior deployment in the Cloudflare Pages dashboard (unverified; Q2).

## Scheduled jobs
- None in the repo.

## Monitoring
- None in the repo.

## Common failures
| Symptom | Cause | Fix |
|---|---|---|
| Build fails on a post | Front matter violates `src/content.config.ts` | Fix the field; `readTime` must be a number |
| Post has no filter chip | Category not in `src/pages/index.astro:9` | Add the category there |

## Credentials and external dependencies
- This repo holds no secrets. Deploys use the Cloudflare account's Git integration (credential lives in Cloudflare/GitHub, not here).
- Google OAuth consent screen for Chief of Staff links to `/privacy`. App verification status and any consent expiry are tracked in agent-platform, not here (Q4).

## Expiring credentials
| What | Expires | Renew by |
|---|---|---|
| None known in this repo | n/a | n/a |
