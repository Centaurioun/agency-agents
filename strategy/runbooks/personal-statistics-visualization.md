# Statistics & Visualization

This runbook is governed by [Personal Codex Runbook Execution Contract](personal-codex-execution-contract.md). The shared contract controls unless this scenario is more restrictive.

## Purpose

Coordinate a small personal Codex team for tasks where statistical interpretation and visual representation are both central, while keeping statistical claims and chart design under separate specialist ownership.

This runbook is personal/general-purpose. It does not replace Academic Research or MedSci scientific procedure owners such as `analyze-stats` or `make-figures`.

## Use when

- interpreting already available statistical results and deciding how to communicate them visually;
- choosing a chart, figure, or compact visual summary from an existing analysis context;
- reviewing whether a proposed visualization accurately represents the stated statistical result;
- preparing a visualization plan where the analysis question and result structure are already sufficiently defined;
- resolving a bounded input-shape or data-structure issue that blocks interpretation/visualization and justifies the conditional Data Engineer.

## Do not use when

- the dominant task is biomedical or scientific statistical analysis owned by Academic Research / MedSci `analyze-stats`;
- the dominant task is scientific figure generation owned by Academic Research / MedSci `make-figures`;
- the task requires a new study design, statistical model selection from raw scientific data, causal analysis, or domain-specific scientific inference that belongs to another scientific owner;
- the problem is primarily data engineering, retrieval, architecture, or plugin development;
- the user has not authorized analysis or representation of the available data/results.

When another specialized workflow is the real owner, use that workflow rather than treating this personal runbook as a replacement scientific engine.

## Specificity / switching relationship

Use this runbook when the combined question is specifically:

```text
What do these statistical results mean?
+
What is the most truthful and useful way to show them?
```

If the task becomes primarily new computation or scientific inference, hand off to the appropriate statistical/scientific owner. If it becomes primarily implementation of a visualization system, dashboard, or custom data-visualization product, switch to the relevant engineering workflow instead of expanding this roster.

## Roster and semantic activation map

### Default active

- `academic-statistician` — interprets the supplied analysis/results, checks whether the proposed statistical language is supported, identifies important uncertainty/assumption limits, and prevents visual design from strengthening the claim beyond the analysis.
- `engineering-data-visualization-engineer` — selects and designs the visual representation using perceptually honest encodings, accessibility-aware choices, and chart forms appropriate to the question and data structure.

### Triggered

- `engineering-data-engineer` — only when a concrete input-shape, schema, tabular transformation, aggregation, or data-flow issue materially blocks the statistical/visual task.

### Excluded by default

- testing and benchmarking agents;
- generic software architects;
- Workflow Optimizer;
- retrieval specialists;
- MCP specialists;
- autonomous orchestration roles;
- additional scientific/domain specialists merely because they are available.

Roster membership does not widen task authority.

## Task sequence

```text
establish the analysis question and supplied result context
-> Statistician interprets result, uncertainty, and claim limits
-> Visualization Engineer maps those supported results to an honest visual form
-> Data Engineer only if a concrete input/shape blocker exists
-> reconcile statistical meaning with visual encoding
-> primary Codex thread produces final interpretation/visualization recommendation
-> stop
```

Visualization must never invent a statistical conclusion that is absent from the supplied analysis.

## Safe parallel opportunities

After a stable result/context brief exists, the Statistician and Data Visualization Engineer may work in parallel on independent read-only surfaces:

- Statistician: estimand/result meaning, uncertainty, assumptions, unsupported claim promotion;
- Visualization Engineer: chart type, visual encoding, scale/axis choices, accessibility, annotation strategy.

Their outputs must be reconciled before final synthesis so that a visually compelling chart cannot overstate the statistical evidence.

## Serial dependencies

- unclear or incomplete result context must be resolved before confident interpretation;
- statistical meaning/claim limits control what the visual may imply;
- data restructuring that changes denominators, aggregation, units, or analytic meaning must be understood before the chart is finalized;
- overlapping data transformations remain serialized under one integration owner.

## Role-specific I/O expectations

### Academic Statistician

Input:
- analysis question;
- available results, estimates, intervals, p-values/effect measures, model summaries, or other supplied statistical output;
- relevant user-stated context and constraints.

Output:
- concise interpretation;
- uncertainty and assumption notes;
- claim-force ceiling;
- warnings where the supplied evidence cannot support a stronger conclusion;
- variables/quantities that a visualization may legitimately encode.

### Data Visualization Engineer

Input:
- analysis question;
- Statistician-supported quantities and claim limits;
- audience/output context where supplied.

Output:
- recommended chart/figure type;
- encoding and scale choices;
- annotation/legend guidance;
- accessibility/perceptual considerations;
- explicit note if a requested visual form would mislead or distort the supported result.

### Data Engineer — conditional

Input:
- the concrete shape/schema/transformation blocker only.

Output:
- smallest transformation or data-shape recommendation needed to unblock the task;
- any semantic risks introduced by aggregation, reshaping, joins, filtering, or denominator changes.

## Mode-gated actions

The following require explicit task authorization and are not implied merely by selecting this runbook:

- running new statistical analyses on user data;
- modifying datasets;
- implementing production dashboards or visualization applications;
- benchmarking visualization performance;
- testing/remediation loops;
- scientific manuscript modification;
- release or deployment work.

## Explicit exclusions

- no replacement for MedSci `analyze-stats`;
- no replacement for MedSci `make-figures`;
- no automatic model selection or causal inference from raw data;
- no invention of missing results or uncertainty;
- no visual embellishment that changes the apparent magnitude, precision, or direction of an effect;
- no misleading axes, scales, denominators, aggregation, or dual-axis constructions;
- no automatic transition into data engineering, implementation, testing, or another runbook;
- no autonomous multi-agent controller.

## Final synthesis owner

The primary Codex thread remains the final synthesizer. It reconciles statistical interpretation with visual representation and must preserve any disagreement or limitation that materially affects the final result.

Neither specialist may convert an unsupported statistical inference into a visual conclusion.

## Stop condition

Stop when the bounded statistical interpretation and visualization recommendation/output requested by the user has been completed, material limitations are recorded, and any required handoff to a different scientific or engineering owner is explicit.

Do not continue into new computation, implementation, testing, or optimization without separate authorization.

## Completion receipt

Record, proportionally to task size:

```text
runbook: Statistics & Visualization
analysis question / result context
agents invoked / skipped
statistical interpretation delivered
visualization recommendation or artifact delivered
data transformation used, if any
claim / uncertainty limitations
known issues / handoff
completion status
```
