# Personal Codex Runbooks v1 — Wave 1B Implementation Handoff

**Repository:** `Centaurioun/agency-agents`  
**Branch:** `feature/personal-codex-runbooks-v1`  
**Base revision:** `ebe9c99acb5c96f9468de368d8bead775387d1a7` (`main` at branch creation/current implementation start)  
**Planning record:** `Centaurioun/academic-research-plugin`, `planning/agency-agents-and-runbooks-vnext`  
**Implementation mode:** implementation-first  
**Testing / validation:** not run / not authorized in this wave

## Scope

Implemented the five core Personal Codex runbooks only:

1. Academic Research Development
2. Academic Research Architecture
3. Academic Retrieval Improvement
4. New MCP / Callable Component
5. Plugin Verification & Remediation

`Statistics & Visualization` remains optional/personal-only and was not added.

## Files created

- `strategy/runbooks/personal-codex-execution-contract.md`
- `strategy/runbooks/personal-academic-research-development.md`
- `strategy/runbooks/personal-academic-research-architecture.md`
- `strategy/runbooks/personal-academic-retrieval-improvement.md`
- `strategy/runbooks/personal-new-mcp-callable-component.md`
- `strategy/runbooks/personal-plugin-verification-remediation.md`

## File modified

- `strategy/runbooks.json`

The existing upstream scenario entries were preserved and five new personal
entries were appended using the established manifest fields only:

```text
slug
title
mode
duration
summary
doc
roster[].group
roster[].activation
roster[].agents[]
```

No custom executable runbook schema was introduced.

## Shared execution model

The new shared contract establishes:

- primary Codex thread = coordinator/state owner/final synthesizer;
- one primary runbook per task;
- prefer the most-specific applicable runbook;
- explicit handoff/switch instead of automatic nesting;
- roster membership != automatic activation;
- `DEFAULT_ACTIVE`, `TRIGGERED`, `MODE_GATED`, and `EXCLUDED_BY_DEFAULT` semantics;
- inherited task/project authorization; the runbook cannot widen it;
- bounded specialist briefs and inspectable handoffs without private chain-of-thought;
- parallel work only for independent/read-only/disjoint surfaces;
- serial execution for dependencies and overlapping writes;
- contradiction preservation, failure localization, and bounded retries;
- no automatic testing, remediation, release, or phase advancement.

## Important activation boundary

The `activation` strings in `strategy/runbooks.json` are deployment/presentation
metadata. They are not treated as an executable policy engine. The Markdown
contract and current owner/project authorization govern actual activation.

This is particularly important for:

- `testing-performance-benchmarker` and `testing-test-results-analyzer` in the
  Retrieval runbook: explicit evaluation mode only;
- QA/remediation roles in Plugin Verification & Remediation: only under the
  corresponding explicit authorization;
- `engineering-minimal-change-engineer` in verify/remediation context: presence
  in the deployed roster never authorizes remediation by itself.

## Roster boundaries retained

- `agents-orchestrator` is not a controller or roster member of the new personal
  presets.
- `testing-workflow-optimizer` is not included in v1.
- Rapid Prototyper remains a direct agent rather than a runbook.
- Statistics & Visualization remains separately optional.

## Verification state

No `scripts/check-runbooks.sh`, tests, linting, UI/manual validation, installation,
or host execution was performed. The exact roster slugs used for the new entries
were selected from the current repository catalog during implementation, but
that source inspection is not a substitute for later validator/host testing.

## Known limitations

- The Agency Agents app's display treatment of the new free-text activation
  labels was not manually verified.
- The manifest describes deployable rosters; it does not enforce the Markdown
  execution contract.
- No automated runbook switching or authorization engine is added.

## Status

```text
WAVE_1B_CORE_FIVE: IMPLEMENTED — UNTESTED
OPTIONAL_STATISTICS_VISUALIZATION: DEFERRED / NOT_AUTHORIZED
```

Stop at the Wave 1 boundary. Do not start optional runbooks, QA, or another
implementation wave without explicit owner authorization.
