# Queue 1 — Personal Codex Runbooks v1 Host/Validator Handoff

**Date:** 2026-08-21  
**Repository:** `Centaurioun/agency-agents`  
**Active branch:** `feature/personal-codex-runbooks-v1`  
**Expected starting head:** `35a9762c131719c7599592ead8a74ba8121e2968`  
**PR:** #1  
**Queue item:** Agency Agents — five core Personal Codex runbooks  
**Mode:** BOUNDED_VALIDATION_AND_HOST_ACCEPTANCE_ONLY

## Why Codex is needed

ChatGPT completed the repository-side inspection and attempted to obtain repository-native validator evidence through GitHub. The PR workflow is configured to run `./scripts/check-runbooks.sh` on `pull_request`, but no workflow run was observed for either a fresh `synchronize` commit or a close/reopen `reopened` event.

Do not continue trying to repair GitHub Actions in this task. The remaining useful evidence is local/host-only.

## Frozen candidate scope

Validate only the existing five core Personal Codex runbooks:

1. `academic-research-development`
2. `academic-research-architecture`
3. `academic-retrieval-improvement`
4. `new-mcp-callable-component`
5. `plugin-verification-remediation`

Shared contract:

`strategy/runbooks/personal-codex-execution-contract.md`

Optional `Statistics & Visualization` is explicitly OUT OF SCOPE.

## Required local validator

On the exact active branch candidate:

```bash
./scripts/check-runbooks.sh
```

Run only the repository-native validator needed for this queue item. Do not initiate unrelated test/lint/security/regression work.

Record the exact command, exit status, concise output, repository path, branch, and tested SHA.

If it fails because of an actual core-five candidate defect, apply only the smallest correction needed, rerun only this validator, and record the defect/remediation. If it fails because of environment/tooling, record the limitation and do not widen scope.

## Bounded host/app acceptance

If the local Agency Agents application/deployment mechanism is already available on the machine, perform the smallest non-destructive acceptance sufficient to determine whether the five runbooks are discoverable/loadable/displayable from the normal host path.

Do not redesign or broadly test the app. Do not create the optional Statistics & Visualization runbook. Do not modify unrelated upstream Agency Agents behavior.

Useful evidence, where available:

- normal host/deployment command or mechanism used;
- whether all five runbooks are visible/discoverable;
- whether referenced docs resolve/load;
- whether roster agent slugs load without a missing-agent error;
- whether free-text activation labels create an obvious host/UI breakage.

If the host/app is not installed or acceptance is not possible from the current local environment, record exactly that limitation. A missing host capability is not permission to install or redesign unrelated infrastructure unless a pre-existing documented install/deploy path makes the action routine and reversible.

## Evidence persistence

Create/update one concise evidence record on this same branch:

`strategy/runbooks/personal-codex-runbooks-v1-host-validation.md`

It must contain:

- starting SHA;
- final SHA;
- local repository path;
- validator command/result;
- any remediation performed;
- host/app acceptance attempted? YES/NO;
- host/app result or limitation;
- confirmation core-five scope unchanged;
- confirmation Statistics & Visualization not started;
- recommendation: `READY_FOR_CANONICAL_MERGE` or `NOT_READY_MATERIAL_DEFECT`.

Commit and push only the evidence and any genuinely necessary minimal defect remediation to `feature/personal-codex-runbooks-v1`.

## Prohibited

Do NOT:

- merge PR #1 or `main`;
- start Statistics & Visualization;
- add new runbooks;
- broaden the runbook schema;
- add an autonomous orchestration engine;
- start Queue 2;
- run broad tests merely for extra confidence;
- modify `Centaurioun/academic-research-plugin`;
- rewrite Git history.

## Stop condition

Stop after the local validator and bounded host acceptance (or explicit host limitation) are persisted and pushed. Return the exact final SHA and recommendation to ChatGPT for coordinator adjudication and merge decision.
