# Queue 1 — Post-Merge Host Refresh Handoff

**Date:** 2026-08-21  
**Repository:** `Centaurioun/agency-agents`  
**Canonical main merge:** `389eab64cd602364f42b805cdb1f9a0fb570e987`  
**Queue item:** Agency Agents — five core Personal Codex runbooks  
**Mode:** POST_MERGE_HOST_REFRESH_ONLY

## Current state

The five core Personal Codex runbooks and shared execution contract were merged to canonical `main` through PR #1.

The repository-native validator passed locally before merge:

```text
./scripts/check-runbooks.sh
PASS
PASSED: 9 runbooks, 97 agent slug references — all resolve to real agent files.
```

The pre-merge host check found `/Applications/Agency Agents.app` version `0.3.0`, but its managed catalog at `/Users/yusuf/.agency-agents` was still on `github:main@2026-08-20` and did not consume the feature branch.

Now that the candidate is canonical `main`, perform only the smallest normal refresh/update action available to make the installed app/catalog consume current main.

## Required work

1. Inspect the existing app/catalog update mechanism already present on the machine.
2. If a routine, documented, non-destructive refresh/update path exists, use it.
3. Do not replace the app, redesign configuration, or create a custom branch-consumption path.
4. After refresh, inspect whether the five canonical runbooks are discoverable/visible/loadable from the normal Agency Agents host path.
5. Record whether the managed catalog revision/source moved to current canonical main or otherwise demonstrably incorporated the five runbooks.
6. Do not start Statistics & Visualization or any later queue item.

## Five expected runbooks

- `academic-research-development`
- `academic-research-architecture`
- `academic-retrieval-improvement`
- `new-mcp-callable-component`
- `plugin-verification-remediation`

## Failure/limitation policy

If no routine safe refresh/update path is available, do not invent one. Record:

`HOST_REFRESH_NOT_AVAILABLE_WITH_EXISTING_ROUTINE_PATH`

If refresh succeeds but the app still does not surface the canonical runbooks, record the exact observed state as a host limitation; do not redesign the app in this task.

## Evidence

Create:

`strategy/runbooks/personal-codex-runbooks-v1-postmerge-host-refresh.md`

Record:

- local repo path;
- canonical main SHA observed;
- app version;
- managed catalog pre-state;
- refresh/update mechanism attempted;
- command/action used;
- post-state;
- whether all five runbooks are visible/discoverable/loadable;
- any limitation;
- recommendation: `HOST_USABLE_CONFIRMED` or `HOST_LIMITATION_RECORDED`.

Do not modify product/runbook content unless a truly blocking canonicalization defect is directly demonstrated. Do not merge or start another queue item.
