---
status: current
updated: 2026-11-06
purpose: Step log, 2026-11-06.
---

# 2026-11-06 · Pages deploy facts

### 17:00 · Record verified Pages deploy facts (Q2)
- **Goal:** answer Q2 from the live Cloudflare Pages project.
- **Done:** PR #2 merged (squash, 4188f73). Queried the project with wrangler; recorded Git provider, production branch, preview deploys and domains in docs/RUNBOOK.md; updated Q2, BUILD-PLAN and AGENTS.md current step.
- **Verified:** `wrangler pages project list` and `wrangler pages deployment list --project-name timsamson-com` show Production deploy of 4188f73 from `main` after the merge. Build command, output dir and Node version are not exposed by the CLI: not verified.
- **Decisions:** none
- **Open questions:** Q2 partly answered; Q3 still open (Tim).

### 17:20 · Dashboard settings recorded (Q2 closed)
- **Goal:** finish Q2 with the values the CLI could not read.
- **Done:** Tim shared dashboard screenshots; recorded build command, output, build system version, branch control, runtime and preview access in docs/RUNBOOK.md; closed Q2; raised Q5 (compat date mismatch); BUILD-PLAN and AGENTS.md now point at Q3.
- **Verified:** read from Tim's screenshots, not from the API. Node version is not set anywhere (no variables), so the default applies.
- **Decisions:** none
- **Open questions:** Q2 answered; Q5 raised; Q3 open.
- **Next:** Tim lists roadmap steps for Q3.
- **Branch / PR:** `docs/runbook-pages-deploy-facts`

### 20:20 · Fix README Astro version (Q1 closed)
- **Goal:** make README match `package.json` (`^6.3.3`).
- **Done:** README.md line 7 now says Astro 6; Q1 marked answered; removed the stale trap line from AGENTS.md.
- **Verified:** diff reviewed; docs and README only, build not run.
- **Decisions:** none
- **Open questions:** Q1 answered; Q3, Q5 still open.
- **Next:** Tim lists roadmap steps for Q3.
