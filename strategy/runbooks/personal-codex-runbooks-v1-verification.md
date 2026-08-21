# Personal Codex Runbooks v1 — Targeted Verification Record

**Phase:** Wave 1 targeted Verification & Remediation  
**Branch:** `feature/personal-codex-runbooks-v1`  
**PR:** #1, draft verification PR; do not merge from this record alone  
**Scope:** five core Personal Codex runbooks only

## Verification targets

1. `strategy/runbooks.json` remains structurally consistent with the repository's established runbook manifest contract.
2. Every new runbook `doc` path resolves.
3. The five core personal runbook slugs are unique and the optional Statistics & Visualization runbook is absent.
4. Every roster agent slug used by the five new entries resolves to a real catalog agent file.
5. Shared execution-contract boundaries are represented consistently across the five runbook docs:
   - primary Codex thread remains coordinator/final synthesizer;
   - one primary runbook per task;
   - roster membership does not authorize activation;
   - testing/remediation/phase advancement require inherited explicit authorization;
   - parallel work is limited to independent/read-only/disjoint surfaces;
   - `agents-orchestrator` is not made the controller of these presets.
6. Repository-native validator evidence is preferred when the host actually runs it.

## Repository-native validator contract inspected

`scripts/check-runbooks.sh` was inspected from this repository. Its relevant checks are:

- `strategy/runbooks.json` parses and required fields exist;
- every `roster[].agents[]` slug resolves to a tracked agent Markdown filename stem;
- every `doc` path exists;
- runbook slugs are unique.

The repository's `check-runbooks.yml` is configured for pull-request execution.

## Fresh host-run evidence

A draft PR was opened and the branch was subsequently updated. Repeated GitHub workflow-run queries for the current verification commit returned **no workflow runs**.

Classification:

```text
HOST_VALIDATOR_RUN: NOT_OBSERVED
CAUSE: CANNOT_DETERMINE_FROM_CURRENT_EVIDENCE
```

Do not describe `scripts/check-runbooks.sh` as executed in this phase. A normal local `git clone`/validator fallback was also unavailable in the current execution environment because the local shell environment could not resolve GitHub. This host limitation does not convert static inspection into an executed validator result.

## Repository-static verification

### Manifest scope

`strategy/runbooks.json` contains exactly these five new personal runbook slugs:

1. `academic-research-development`
2. `academic-research-architecture`
3. `academic-retrieval-improvement`
4. `new-mcp-callable-component`
5. `plugin-verification-remediation`

No Statistics & Visualization personal runbook entry is present.

The five slugs are distinct from one another and from the pre-existing scenario runbook slugs visible in the same manifest.

### Document resolution

The branch directory `strategy/runbooks/` contains all five manifest-target docs plus the shared execution contract:

- `personal-academic-research-development.md`
- `personal-academic-research-architecture.md`
- `personal-academic-retrieval-improvement.md`
- `personal-new-mcp-callable-component.md`
- `personal-plugin-verification-remediation.md`
- `personal-codex-execution-contract.md`

### Roster slug resolution

The engineering and testing catalog directories were inspected, and the specialized MCP Builder was read directly. Every slug referenced by the five new personal manifest entries was observed as a repository agent filename stem:

```text
engineering-minimal-change-engineer
engineering-codebase-onboarding-engineer
engineering-software-architect
engineering-data-engineer
engineering-prompt-engineer
engineering-technical-writer
engineering-multi-agent-systems-architect
engineering-rag-pipeline-engineer
engineering-search-relevance-engineer
engineering-ai-data-remediation-engineer
engineering-code-reviewer
specialized-mcp-builder
testing-performance-benchmarker
testing-test-results-analyzer
testing-evidence-collector
testing-reality-checker
```

`agents-orchestrator` is not present in any of the five new personal rosters. `testing-workflow-optimizer` is also absent.

### Shared execution-contract semantics

`personal-codex-execution-contract.md` explicitly establishes:

- primary Codex thread as coordinator, task-state owner, activation decider, handoff integrator, and final synthesizer;
- one primary runbook at a time and no automatic nesting;
- inherited authorization that a runbook cannot widen;
- roster membership != activation;
- mode-gated testing/remediation/benchmarking;
- parallelism only for independent, stable, read-only/disjoint work;
- serialized dependencies and overlapping writes;
- bounded specialist handoffs without private chain-of-thought;
- failure localization and bounded retries;
- no automatic transition into testing, remediation, release, planning, or another runbook.

Each of the five runbook documents links to this shared contract and adds a narrower purpose, roster/activation delta, sequence, exclusions, final synthesis owner, and stop condition. No contradictory authority expansion was found in the inspected docs.

## Findings

No manifest/doc/roster or execution-contract contradiction was found by repository-static inspection.

No product remediation was justified from the evidence available in this phase.

## Verification classification

```text
WAVE_1B_CORE_FIVE:
  REPOSITORY_STATIC_VERIFIED
  HOST_VALIDATOR_NOT_EXECUTED
  HOST_UI_INSTALLATION_NOT_VERIFIED
```

This is stronger than the prior `IMPLEMENTED — UNTESTED` state but intentionally weaker than an executed repository-validator + host/UI acceptance result.

## Remaining limitations

- `scripts/check-runbooks.sh` did not produce a fresh executed result in the current PR context.
- Agency Agents app display/deployment behavior for the free-text activation labels was not manually exercised.
- No Codex host installation/deployment of these runbooks was performed.
- The manifest remains deployment metadata; it does not enforce the Markdown authorization contract at runtime.

## Scope boundary

Statistics & Visualization remains optional and out of scope. Do not start another runbook wave, merge, or release from this record without separate owner authorization.
