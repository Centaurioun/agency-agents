# New MCP / Callable Component

This runbook is governed by [Personal Codex Runbook Execution Contract](personal-codex-execution-contract.md). The shared contract controls unless this scenario is more restrictive.

## Purpose

Coordinate creation or substantial redesign of one callable provider/component,
MCP tool/resource surface, or equivalent agent-facing interface without losing
responsibility, authority, schema, error, or least-privilege boundaries.

## Use when

- adding a new MCP/provider component;
- adding a substantial callable tool/resource family;
- redesigning a callable contract where ownership and agent-facing semantics are
  central;
- exposing an existing owner through a new bounded callable surface.

## Do not use when

- the dominant question is system architecture rather than the callable itself
  → **Academic Research Architecture**;
- the task is ordinary implementation inside an established callable contract
  → **Academic Research Development**;
- retrieval/search is the dominant problem → **Academic Retrieval Improvement**;
- the task is verification/remediation → **Plugin Verification & Remediation**.

## Roster and semantic activation

### Default active

- `engineering-codebase-onboarding-engineer` — current component/context map when
  not already reliable.
- `engineering-software-architect` — responsibility and component placement.
- `specialized-mcp-builder` — bounded tool/resource/schema/error contract.

### Triggered

- `engineering-multi-agent-systems-architect` — orchestration, delegation,
  context, or authority implications.
- `engineering-prompt-engineer` — agent-facing tool names/descriptions or prompt
  behavior materially affect correct selection/use.
- `engineering-minimal-change-engineer` — implementation is authorized.
- `engineering-technical-writer` — durable API/tool/handoff documentation.

### Excluded by default

Testing/benchmarking/reality-checking agents unless separately authorized, and
`agents-orchestrator` as a controller.

## Task sequence

```text
map current system
-> define one component responsibility and non-responsibilities
-> place authority / data / side-effect boundaries
-> define callable contract
-> define typed inputs/outputs and structured errors
-> refine agent-facing names/descriptions when needed
-> implement only if authorized
-> document/handoff
-> stop
```

## Callable-contract rules

Prefer:

- verb-noun or otherwise unambiguous tool names;
- descriptions that explain **when to use** the tool;
- bounded typed inputs and outputs;
- explicit validation and structured error states;
- one clear responsibility per tool;
- stateless behavior where practical;
- least-privilege access and explicit side effects;
- provenance/identity fields when downstream systems need them.

Do not make a tool broader merely to reduce tool count if doing so blurs
responsibility or authorization.

## Safe parallel opportunities

After responsibility/authority placement is stable, MCP Builder and Prompt
Engineer may independently refine schema/tool semantics and agent-facing
selection guidance. Read-only architecture analysis may also run in parallel if
scopes are disjoint.

## Serial dependencies

- current-state mapping precedes placement when context is uncertain;
- responsibility/authority placement precedes schema implementation;
- contract design precedes implementation;
- overlapping file writes stay serialized under one integration owner.

## Role-specific I/O expectations

- **Codebase Onboarding Engineer:** actual entry points, adjacent components,
  inspected/uninspected surfaces.
- **Software Architect:** component owner, dependencies, boundaries, alternatives.
- **MCP Builder:** tool/resource contract, schemas, validations, structured errors,
  side effects, statelessness assumptions.
- **Prompt Engineer:** agent-facing selection/use language only when needed.
- **Minimal Change Engineer:** smallest authorized source edits.

## Mode-gated actions

Implementation, live service deployment, testing, security assessment,
performance measurement, remediation, and release work depend on the current
authorization envelope and are never implied by the runbook.

## Explicit exclusions

- no second orchestrator merely because a component is callable;
- no tool surface before responsibility/authority is sufficiently clear;
- no arbitrary secret or filesystem access;
- no custom runbook execution engine;
- no automatic QA stage.

## Final synthesis owner

The primary Codex thread integrates architecture/interface contributions and
owns the final contract/handoff for the active task.

## Stop condition

Stop at the authorized level: design-only if implementation is not authorized,
or after the bounded callable implementation/documentation/handoff when it is.
Do not automatically proceed to QA, deployment, or another phase.

## Completion receipt

```text
runbook: New MCP / Callable Component
component responsibility
non-responsibilities / authority boundaries
agents invoked/skipped
contract artifacts
changes made if authorized
known limitations
next handoff
completion status
```
