# Queue 3 — Statistics & Visualization Personal Runbook Validation Handoff

**Date:** 2026-08-21  
**Repository:** `Centaurioun/agency-agents`  
**Branch:** `feature/statistics-visualization-personal-runbook-v1`  
**PR:** #2  
**Expected starting head before this handoff commit:** `20658b89b4c1155cae29538c1416bc48fe1fcff0`  
**Mode:** `BOUNDED_VALIDATION_ONLY`

## Candidate scope

The candidate adds exactly one personal runbook:

`statistics-visualization`

Manifest roster:

- core: `academic-statistician`
- core: `engineering-data-visualization-engineer`
- conditional: `engineering-data-engineer`

Runbook doc:

`strategy/runbooks/personal-statistics-visualization.md`

The candidate is personal/general-use only. It does not replace Academic Research / MedSci `analyze-stats` or `make-figures`.

## Required validation

On the exact current branch candidate run only:

```bash
./scripts/check-runbooks.sh
```

Record exact tested SHA, command, exit status, and concise output.

If the validator fails because of a concrete candidate defect, make only the smallest competent correction, rerun only this validator, and record the remediation.

If the failure is environment/tooling-only, record the limitation and stop.

## Do not repeat host/app work

Queue 1 already established a governed Agency Agents host limitation: the installed app's managed catalog is sourced from upstream `msitarzewski/agency-agents`, not `Centaurioun/agency-agents`, and no safe routine path was available to make the app consume the user's fork.

Do not reopen or re-investigate that known host/catalog-source limitation in Queue 3.

## Evidence

Create:

`strategy/runbooks/statistics-visualization-v1-validation.md`

Include:

- starting SHA;
- final SHA;
- local repository path;
- validator command/result;
- candidate defect found YES/NO;
- remediation if any;
- confirmation `statistics-visualization` exists exactly once;
- confirmation all three agent slugs resolve;
- confirmation referenced doc exists;
- confirmation existing five personal runbooks remain unchanged;
- confirmation Academic Research / MedSci were not modified;
- recommendation: `READY_FOR_CANONICAL_MERGE` or `NOT_READY_MATERIAL_DEFECT`.

Commit and push only evidence plus any genuinely necessary minimal defect remediation to this same branch.

## Prohibited

Do not:

- merge PR #2;
- modify `main`;
- add another runbook;
- start Queue 4;
- change Academic Research / MedSci;
- redesign Agency Agents app;
- run broad tests/lint/security/regression suites;
- rewrite Git history.

## Stop condition

Stop after bounded validator evidence is persisted and pushed. Return exact final SHA and recommendation to ChatGPT.
