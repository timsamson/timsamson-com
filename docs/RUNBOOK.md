---
status: draft
updated: 2026-11-06
purpose: How to deploy, operate and fix it.
---

# Runbook

## Deploy
- Push to `main` deploys via Cloudflare Pages project `timsamson-com` (README.md). Use a branch and PR; merge only with Tim's yes.
- Verified 2026-11-06 (`wrangler pages project list` and `pages deployment list --project-name timsamson-com`): Git provider attached; production branch is `main`; merging PR #2 (4188f73) produced a Production deployment ~39 min before the check; PR branches get Preview deployments (`docs/bootstrap-agents-md`, f5be16a). Domains: `timsamson-com.pages.dev`, `timsamson.com`.
- Dashboard settings (Pages > timsamson-com > Settings, read 2026-11-06 from screenshots): build command `npm run build`; output `dist`; root directory empty; build system version 3; build cache disabled; watch paths `*`; production branch `main`, automatic deployments on; no deploy hooks; no variables or secrets (so Node version is the build system v3 default, not pinned); compatibility date `2026-05-15`, no flags; preview deployments are public (no Cloudflare Access).
- `wrangler.toml` says compatibility date `2024-01-01`; the dashboard says `2026-05-15` (Q5).
- Local check before PR: `npm ci && npm run build`.

## Rollback
- Not recorded. Revert the commit on `main`, or redeploy a prior deployment in the Cloudflare Pages dashboard (unverified; Q2). Deployments list via `npx wrangler pages deployment list --project-name timsamson-com`.

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
