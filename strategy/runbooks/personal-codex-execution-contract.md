# Personal Codex Runbook Execution Contract

This contract governs the owner's personal Codex runbooks in this repository.
It complements the machine-readable deployment roster in `strategy/runbooks.json`.

A personal runbook is:

```text
TEAM PRESET
+
WORKFLOW CONTRACT
+
ACTIVATION POLICY
```

It is **not** an autonomous orchestrator and does not create new authority.

## Coordinator and decision authority

The primary Codex thread is the coordinator, task-state owner, activation
decider, handoff integrator, and final synthesizer. Specialist agents are bounded
contributors. The user/owner retains consequential decision authority.

`agents-orchestrator` is not the default controller for these personal runbooks.

## One primary runbook per task

Use one dominant runbook at a time and prefer the most specific applicable
runbook. Do not automatically nest runbooks.

Preferred specificity:

```text
architecture problem        -> Academic Research Architecture
retrieval/search problem    -> Academic Retrieval Improvement
new callable/MCP component  -> New MCP / Callable Component
verification/remediation    -> Plugin Verification & Remediation
otherwise implementation    -> Academic Research Development
```

If the dominant task changes, the primary Codex thread performs an explicit
handoff/switch.

## Authorization envelope

A runbook inherits the current user, project, repository, and task constraints.
It cannot expand them.

Roster membership never automatically authorizes:

- implementation or repository writes;
- testing, verification, audit, or review;
- remediation;
- security assessment;
- web research;
- release/readiness work;
- branch/merge operations;
- phase transitions.

The same runbook may therefore operate under implementation-first, read-only,
verify-only, remediation-authorized, no-web, or other bounded modes.

## Roster membership is not activation

Interpret roster groups semantically as follows. The current Agency Agents
manifest/app may display activation labels, but those labels are not an
execution engine.

### `DEFAULT_ACTIVE`

Normally useful for the runbook. The coordinator may skip the role when trusted
current context already satisfies that responsibility.

### `TRIGGERED`

Use only when the documented condition is present, such as a data/schema issue,
a multi-agent boundary, or agent-facing tool-contract work.

### `MODE_GATED`

Use only when the current authorization envelope permits the relevant mode.
Typical examples are test analysis, performance benchmarking, independent QA,
or remediation.

### `EXCLUDED_BY_DEFAULT`

Do not invoke merely because an agent exists. Add only if a new explicit task
reason makes the role relevant.

## Shared input brief

Provide each activated specialist the smallest sufficient shared brief:

```text
task_id
primary_runbook
authorization_envelope
objective
scope
explicit_non_goals
current_state_or_revision
relevant_files_or_sources
known_constraints
known_decisions
deliverable_expected
```

Do not transfer private chain-of-thought or dump unnecessary conversation
history when a bounded brief is sufficient.

## Specialist handoff

Material specialist contributions should return an inspectable handoff:

```text
role
runbook
task_id
scope_received
inputs_inspected
output_summary
evidence_or_file_refs
recommendations_or_decisions
assumptions_or_inferences
uncertainties
changes_made_if_authorized
out_of_scope_findings
recommended_next_handoff
status
```

Suggested statuses:

```text
COMPLETE
PARTIAL
BLOCKED
CANNOT_DETERMINE
NOT_APPLICABLE
```

No hidden-reasoning field is required.

## Serial and parallel execution

Parallel work is appropriate only when responsibilities are independent, inputs
are stable, neither worker depends on the other's result, and writes are absent
or clearly disjoint.

Serial execution is required when:

- one result is an input to another role;
- architecture must precede implementation/interface work;
- remediation depends on a validated finding;
- a verifier would otherwise inspect a moving target;
- two roles would edit the same file/shared state.

Do not fan out overlapping parallel writes by default. If multiple writers are
used, assign disjoint surfaces and retain one integration owner.

## Contradictions

When specialists disagree:

1. preserve the competing claims and evidence;
2. identify whether the conflict is factual, methodological, architectural, or
   scope-related;
3. prefer repository/source evidence over role prestige;
4. do not settle by majority vote;
5. use targeted follow-up only when material;
6. allow `CANNOT_DETERMINE` when evidence cannot adjudicate the conflict.

## Failure localization and retries

One failed specialist does not automatically fail the whole runbook.

```text
component failure
-> record limitation
-> continue independent work
-> use the smallest justified workaround
-> escalate only if the missing result is a true prerequisite
```

Retries must be bounded and justified by a plausible correction. Do not create
infinite agent loops or substitute a broader-authority agent merely to force an
answer.

## Completion receipt

For substantial work, the coordinator should be able to summarize:

```text
runbook
objective
authorization_envelope
agents_invoked
material_agents_skipped_and_reason
artifacts_or_decisions_produced
changes_made
unresolved_items
limitations
persistence_status
next_recommended_step
completion_status
```

This is a practical continuation/handoff receipt, not ceremonial logging for
every trivial task.

## Universal stop condition

Stop when the deliverable allowed by the current authorization is complete or as
complete as available capability permits, specialist outputs are synthesized,
material uncertainty is recorded, and continuing would require a new mode,
runbook, phase, or owner authorization.

A runbook never automatically continues into testing, remediation, release,
planning, or another runbook.
