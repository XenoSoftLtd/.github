# XenoSoftLtd/.github

Org-wide defaults for the product repos.

## How work is tracked
All product work lives on [Project 10](https://github.com/orgs/XenoSoftLtd/projects/10).

1. **Feature**: open it in `MarketDataUsageAnalysis` with the Feature form.
2. **Tasks**: on the Feature, *Create sub-issue* once per PR-sized slice, in the repo whose PR will close it
   (Task form). Group several related Features under an **Epic** when needed.
3. **Pull requests**: put `Closes XenoSoftLtd/<repo>#<task>` in the body.
4. When every Task is closed, the Feature shows 100% sub-issue progress. Close it.

## Automation
Project 10's built-in workflows do all of it (Project → ⋯ → Workflows). There is no bot, App or secret.
- **Auto-add**: one rule per repo (MarketDataUsageAnalysis, MarketDataUsageAnalysis-UI, CLARE, client-manager,
  rate-card-manager), filter `is:issue,pr is:open`. The Team plan allows 5 rules, so a 6th repo needs an
  App-backed `actions/add-to-project` workflow instead.
- **Status**:
  - added or reopened → Todo
  - PR linked → In Progress
  - PR merged or item closed → Done
  - sub-issues are auto-added
- `.github/ISSUE_TEMPLATE/` holds the default Feature, Task and Bug forms for every repo without its own forms.
  This repo must stay **public** for those defaults to apply.
