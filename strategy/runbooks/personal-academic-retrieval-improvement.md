# Academic Retrieval Improvement

This runbook is governed by [Personal Codex Runbook Execution Contract](personal-codex-execution-contract.md). The shared contract controls unless this scenario is more restrictive.

## Purpose

Coordinate retrieval/search engineering work for ZotSeek or another academic
retrieval layer while separating pipeline engineering, relevance judgment,
data/index quality, implementation, and explicit evaluation modes.

## Use when

Retrieval quality, ranking, chunking, embeddings, metadata filtering,
deduplication, reranking, corpus/index quality, or search relevance is the
central problem.

## Do not use when

- the dominant question is broader system architecture → **Academic Research
  Architecture**;
- the task is ordinary non-retrieval implementation → **Academic Research
  Development**;
- the task is primarily a new provider/tool surface → **New MCP / Callable
  Component**;
- the owner asks specifically for verification/remediation of an existing claim
  rather than retrieval improvement → **Plugin Verification & Remediation**.

## Roster and semantic activation

### Default active

- `engineering-rag-pipeline-engineer` — chunking, embeddings, retrieval stages,
  context assembly, filtering, and reranking architecture.
- `engineering-search-relevance-engineer` — query intent, lexical/semantic
  complementarity, ranking behavior, judgment sets, and task-specific relevance.

### Triggered

- `engineering-ai-data-remediation-engineer` — noisy/corrupt/inconsistent corpus
  or index state.
- `engineering-data-engineer` — ingestion, schema, lineage, or pipeline data
  problems.
- `engineering-multi-agent-systems-architect` — retrieval contracts materially
  alter wider routing/orchestration boundaries.
- `engineering-minimal-change-engineer` — implementation is actually authorized.

### Mode-gated

- `testing-performance-benchmarker` — explicit evaluation/performance mode only.
- `testing-test-results-analyzer` — actual test/evaluation outputs exist and
  their analysis is authorized.

Roster presence does not authorize a benchmark or test run.

## Task sequence

```text
fix retrieval objective / task class
-> define what good retrieval means for this task
-> RAG pipeline analysis || relevance analysis
-> conditional corpus/index/data diagnosis
-> synthesize candidate intervention
-> implement only if authorized
-> benchmark/evaluate only if explicitly authorized
-> stop
```

Do not collapse known-item lookup, topical discovery, related-paper discovery,
rare-term retrieval, and passage retrieval into one generic success metric.

## Safe parallel opportunities

RAG Pipeline Engineer and Search Relevance Engineer may analyze in parallel once
the retrieval objective and frozen input context are shared. Data-quality
inspection may also run independently against the same frozen corpus/index state.

## Serial dependencies

- retrieval objective precedes optimization proposals;
- corpus/index diagnosis precedes remediation when data quality is implicated;
- architecture decision precedes implementation where routing/contracts change;
- benchmark analysis follows actual evaluation outputs and explicit evaluation
  authorization.

## Role-specific I/O expectations

- **RAG Pipeline Engineer:** pipeline diagnosis, likely bottleneck, intervention
  options, technology assumptions explicitly labeled.
- **Search Relevance Engineer:** task intent, relevance/ranking failure mode,
  exact-term/recall risks, judgment/evaluation implications.
- **Data/Remediation roles:** bounded corpus/index findings and audit trail, not
  automatic destructive cleanup.
- **Minimal Change Engineer:** smallest authorized implementation surface.
- **Evaluation roles:** task-specific scorecards and limitations; no autonomous
  promotion decision.

## Mode-gated actions

Benchmark construction/execution, performance measurement, test-result analysis,
reindexing, model/embedding replacement, or autonomous routing changes require
separate authorization appropriate to the active project.

## Explicit exclusions

- retrieval result ≠ evidence authorization;
- no one global retrieval score;
- no mandatory benchmark loop after every implementation;
- no technology-specific donor default elevated into architecture law;
- no autonomous model/config promotion.

## Final synthesis owner

The primary Codex thread synthesizes pipeline, relevance, and data findings and
keeps trade-offs visible. A metric improvement alone does not override other
material regressions.

## Stop condition

Stop after the authorized diagnosis/recommendation or bounded implementation is
complete and limitations are recorded. Evaluation begins only under a separately
permitted evaluation envelope.

## Completion receipt

```text
runbook: Academic Retrieval Improvement
retrieval task/objective
corpus/index/config context
agents invoked/skipped
findings / intervention
changes made if authorized
evaluation performed: yes/no
limitations / next handoff
completion status
```
