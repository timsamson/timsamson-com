---
status: current
updated: 2026-11-06
purpose: Open questions.
---

# Open questions

### Q1 · Astro version: README says 5, package.json says ^6.3.3
- **Status:** answered 2026-11-06 (README now says Astro 6; no decision needed)
- **Context:** `README.md` line 7 vs `package.json`. Code wins; docs here say 6.
- **Options:** fix README (recommended).
- **Owner:** Claude (next docs touch)

### Q2 · Pages build settings and Git provider config are not in the repo
- **Status:** answered 2026-11-06 (no decision needed; settings recorded in RUNBOOK "Deploy")
- **Context:** Build command, output dir, production branch and Node version live in the Cloudflare dashboard; `wrangler.toml` has name and compatibility date only. Could not be verified from code.
- **Options:** record them in RUNBOOK after checking the dashboard.
- **Owner:** Tim

### Q3 · What is the roadmap for the site?
- **Status:** open
- **Context:** No plan, issues or TODOs found in the repo or history; BUILD-PLAN has no later phases.
- **Options:** Tim lists next steps; add as BUILD-PLAN phases.
- **Owner:** Tim

### Q4 · Who keeps /privacy in sync with agent-platform scopes?
- **Status:** open
- **Context:** The page names `gmail.readonly` and `calendar.readonly` and a date (Updated November 1, 2026). If agent-platform's scopes change, the page and the consent screen must change together.
- **Options:** add a check to agent-platform's release steps (recommended).
- **Owner:** Tim

### Q5 · Compatibility date differs between wrangler.toml and the Pages dashboard
- **Status:** open
- **Context:** `wrangler.toml` has `compatibility_date = "2024-01-01"`; the dashboard Runtime setting is `2026-05-15`. The site is static with no Functions, so it likely has no effect; which one Pages honours is not verified.
- **Options:** delete the unused `wrangler.toml` keys or align them (recommended once confirmed harmless).
- **Owner:** Claude (next code touch)
