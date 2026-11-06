---
status: current
updated: 2026-11-06
purpose: Open questions.
---

# Open questions

### Q1 · Astro version: README says 5, package.json says ^6.3.3
- **Status:** open
- **Context:** `README.md` line 7 vs `package.json`. Code wins; docs here say 6.
- **Options:** fix README (recommended).
- **Owner:** Claude (next docs touch)

### Q2 · Pages build settings and Git provider config are not in the repo
- **Status:** open (partly answered 2026-11-06: Git provider, production branch `main` and preview deploys verified, see RUNBOOK; build command, output dir and Node version still need the dashboard)
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
