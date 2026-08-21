# Academic Research Architecture

This runbook is governed by [Personal Codex Runbook Execution Contract](personal-codex-execution-contract.md). The shared contract controls unless this scenario is more restrictive.

## Purpose

Coordinate architecture decisions for Academic Research Plugin and related
components without turning architecture review into automatic implementation or
QA.

## Use when

- component or provider boundaries may change;
- responsibility/authority ownership is unclear;
- orchestration topology, context handoff, failure behavior, or integration
  contracts are materially affected;
- a callable/interface decision has architecture consequences but is not yet an
  implementation task.

## Do not use when

- the architecture is already settled and the task is ordinary bounded
  implementation → **Academic Research Development**;
- retrieval/search design is the dominant concern → **Academic Retrieval
  Improvement**;
- the primary deliverable is a new callable/MCP surface → **New MCP / Callable
  Component**;
- the task is testing/audit/remediation → **Plugin Verification & Remediation**.

## Roster and semantic activation

### Default active

- `engineering-software-architect` — component/dependency/interface architecture.
- `engineering-codebase-onboarding-engineer` — current-state reconstruction when
  the source-grounded map is not already reliable.

### Triggered

- `engineering-multi-agent-systems-architect` — worker/provider topology,
  delegation, context, handoff, retry, or multi-agent ownership concerns.
- `specialized-mcp-builder` — callable tool/resource/schema implications.
- `engineering-prompt-engineer` — agent-facing behavioral contract implications.
- `engineering-technical-writer` — durable ADR/design/handoff documentation.

### Excluded by default

`agents-orchestrator`, implementation specialists acting before the architecture
is settled, and QA agents acting as automatic architecture gates.

## Task sequence

```text
source-grounded current-state map
-> define architecture question and non-goals
-> Software Architect analysis
-> optional independent Multi-Agent Systems analysis
-> triggered interface/prompt analysis
-> preserve competing options/trade-offs
-> primary Codex synthesis / decision record
-> stop
```

## Safe parallel opportunities

After the factual current-state map is stable, Software Architect and Multi-Agent
Systems Architect may analyze different architecture dimensions in parallel.
Interface and prompt specialists may also work in parallel if their scopes are
independent and read-only.

## Serial dependencies

- factual repository mapping precedes architecture conclusions when state is
  uncertain;
- responsibility/authority placement precedes callable implementation;
- architecture decision precedes production edits unless the task is explicitly
  re-authorized and handed off.

## Role-specific I/O expectations

- **Codebase Onboarding Engineer:** current components, entry points, authority
  surfaces, inspected/uninspected areas.
- **Software Architect:** alternatives, dependencies, trade-offs, recommended
  boundary placement.
- **Multi-Agent Systems Architect:** explicit I/O/non-responsibility contracts,
  context/handoff/failure implications without inventing a second orchestrator.
- **MCP Builder / Prompt Engineer:** bounded interface or behavior-contract
  consequences only.

## Mode-gated actions

Implementation, testing, remediation, security review, migration, and release
work require separate authority. Architecture discussion alone never grants
those modes.

## Explicit exclusions

- no `agents-orchestrator` as controller;
- no second Academic Research orchestrator;
- no provider/agent proliferation merely because a responsibility is important;
- no production coding while the architecture decision itself remains the
  active deliverable.

## Final synthesis owner

The primary Codex thread owns final synthesis and records the selected option,
trade-offs, unresolved questions, and any required handoff.

## Stop condition

Stop once the architecture decision surface is sufficiently documented for the
current task. If implementation is desired, hand off explicitly to the relevant
runbook under the current/new authorization envelope.

## Completion receipt

```text
runbook: Academic Research Architecture
architecture question
sources/files inspected
agents invoked/skipped
options considered
current decision / unresolved questions
handoff target if any
completion status
```
