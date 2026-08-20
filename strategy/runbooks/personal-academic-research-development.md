# Academic Research Development

This runbook is governed by [Personal Codex Runbook Execution Contract](personal-codex-execution-contract.md). The shared contract controls unless this scenario is more restrictive.

## Purpose

Coordinate ordinary implementation work on Academic Research Plugin or closely
related components when no more specific personal runbook dominates.

## Use when

- implementing a bounded feature or repository change;
- modifying existing behavior without a major architecture decision;
- updating a prompt/tool contract as part of implementation;
- handling a focused data/schema change that does not become a dedicated
  retrieval or architecture project.

## Do not use when

Switch instead when the dominant problem is:

- architecture/authority/component boundaries → **Academic Research Architecture**;
- retrieval/index/search quality → **Academic Retrieval Improvement**;
- a new callable/MCP component → **New MCP / Callable Component**;
- testing, audit, validation, or remediation → **Plugin Verification & Remediation**.

Do not use this runbook to create mandatory QA after implementation.

## Roster and semantic activation

### Default active

- `engineering-minimal-change-engineer` — bounded implementation/change owner.
- `engineering-codebase-onboarding-engineer` — reconstructs repository context
  when the current thread does not already have a reliable source-grounded map.

### Triggered

- `engineering-software-architect` — small architecture clarification that does
  not justify switching runbooks.
- `engineering-data-engineer` — schema, ingestion, data-flow, or lineage work.
- `engineering-prompt-engineer` — prompt/tool behavioral contract changes.
- `engineering-technical-writer` — durable documentation or handoff is
  materially required.

### Excluded by default

Testing/review/performance agents, Workflow Optimizer, retrieval specialists,
and MCP specialists. Switch to the specific runbook instead of accumulating a
giant roster.

## Task sequence

```text
reconstruct current context if needed
-> define bounded implementation scope
-> identify triggered specialists
-> implement the smallest authorized change
-> record local issues / limitations
-> persist a concise handoff when useful
-> stop
```

Implementation authority comes from the current task/project, not from this
runbook.

## Safe parallel opportunities

After a stable repository/state brief exists, independent read-only analysis may
run in parallel, for example a data-flow assessment alongside a prompt-contract
assessment when neither depends on the other.

## Serial dependencies

- context reconstruction precedes edits when current state is uncertain;
- architecture clarification precedes affected implementation;
- implementation writes to overlapping files stay serialized under one
  integration owner.

## Role-specific I/O expectations

- **Codebase Onboarding Engineer:** source-grounded map, relevant entry points,
  inspected/uninspected boundaries.
- **Minimal Change Engineer:** bounded edit set, files changed, known follow-ups.
- **Triggered specialist:** recommendation limited to its declared concern, with
  file/source references and explicit assumptions.

## Mode-gated actions

Testing, verification, security review, performance benchmarking, remediation,
release/readiness work, or broader refactoring occur only if separately
included in the authorization envelope.

## Explicit exclusions

- no automatic test/fix/test loop;
- no repository-wide cleanup merely because nearby debt is discovered;
- no second orchestrator;
- no automatic transition to a different runbook or project phase.

## Final synthesis owner

The primary Codex thread integrates specialist outputs and records unresolved
issues. No specialist self-promotes its recommendation into the final decision.

## Stop condition

Stop when the authorized implementation/handoff for the bounded scope has been
attempted and material issues are recorded. If further work requires another
runbook, testing mode, remediation mode, or owner decision, stop and hand off.

## Completion receipt

Record, proportionally to task size:

```text
runbook: Academic Research Development
scope
agents invoked/skipped
files or artifacts changed
known issues / limitations
persistence status
completion status
next handoff if any
```
