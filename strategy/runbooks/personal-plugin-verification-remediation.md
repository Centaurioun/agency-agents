# Plugin Verification & Remediation

This runbook is governed by [Personal Codex Runbook Execution Contract](personal-codex-execution-contract.md). The shared contract controls unless this scenario is more restrictive.

## Purpose

Coordinate explicit testing, verification, audit, validation, readiness, or
remediation work without turning QA into an automatic post-stage of ordinary
implementation.

## Use when

The owner explicitly asks to test, verify, audit, review, validate, assess
readiness, benchmark a material performance claim, or remediate validated
findings.

## Do not use when

- the task is ordinary implementation without QA authorization → **Academic
  Research Development**;
- the task is architecture design → **Academic Research Architecture**;
- the task is retrieval optimization without an explicit verification/evaluation
  envelope → **Academic Retrieval Improvement**;
- remediation has not been authorized and the current task is verify-only.

## Roster and semantic activation

### Default active

- `testing-evidence-collector` — gather evidence appropriate to the claim/system
  and record inspected scope. Evidence is not screenshot-only by default.

### Triggered / mode-gated

- `engineering-code-reviewer` — code/source inspection is explicitly in scope.
- `testing-test-results-analyzer` — real test outputs exist and analysis is in
  scope.
- `testing-reality-checker` — an independent acceptance/readiness adjudication is
  requested.
- `testing-performance-benchmarker` — a performance question/claim is explicitly
  in scope.
- `engineering-minimal-change-engineer` — **only** when remediation is explicitly
  authorized and a finding is sufficiently established to act on.

### Excluded by default

- `testing-workflow-optimizer` until repeated real workflow-use evidence makes
  optimization a concrete task;
- implementation specialists unrelated to a validated finding.

## Verify-only path — default

```text
claim / specification
-> define inspected scope and evidence needed
-> collect bounded evidence
-> analyze evidence / existing test outputs
-> optional independent adjudication
-> findings / uncertainty
-> STOP
```

Verify-only does not mutate the product.

## Remediation path — only when authorized

```text
sufficiently established finding
-> define bounded repair scope
-> Minimal Change Engineer performs authorized repair
-> record change receipt and unresolved issues
-> STOP
```

Do not automatically start a retest/fix/retest loop. A further verification
cycle requires the active task to authorize it.

## Safe parallel opportunities

Independent evidence collection or read-only code review can run in parallel
against a stable target. Performance analysis may also be independent when it
uses a frozen workload/configuration.

## Serial dependencies

- scope/claim definition precedes evidence gathering;
- remediation follows a sufficiently established finding;
- a verifier should not inspect a moving target;
- overlapping remediation writes remain serialized under one integration owner.

## Role-specific I/O expectations

- **Evidence Collector:** claim-vs-evidence record, inspected scope, concrete
  artifacts/references, limitations.
- **Code Reviewer:** source-grounded findings limited to the requested review
  surface; no compulsory issue count.
- **Test Results Analyzer:** interpret actual test artifacts; never invent
  unexecuted results.
- **Reality Checker:** independent claim-vs-reality/spec adjudication with neutral
  outcomes, not a default-negative verdict.
- **Performance Benchmarker:** baseline/workload/metrics/trade-offs; no universal
  SLA invented from donor defaults.
- **Minimal Change Engineer:** smallest remediation justified by the authorized
  finding.

## Mode-gated actions

All testing, benchmarking, code review, readiness judgment, remediation, retest,
security review, and release actions remain bounded by the explicit current
authorization.

## Explicit exclusions

- no mandatory number of defects;
- no screenshots as universal source of truth;
- no default `NEEDS WORK`/failure bias;
- no automatic remediation from verify-only;
- no automatic re-test loop;
- no Workflow Optimizer in the initial preset;
- no merge/release decision by a specialist agent.

## Final synthesis owner

The primary Codex thread synthesizes evidence and specialist findings. The owner
retains consequential acceptance, remediation-expansion, merge, and release
decisions.

## Stop condition

Verify-only stops with evidence-backed findings/verdicts and limitations.
Remediation stops when the authorized bounded changes and change receipt are
complete. Continuing into another verification cycle or release stage requires
explicit scope.

## Completion receipt

```text
runbook: Plugin Verification & Remediation
mode: VERIFY_ONLY | REMEDIATE
target claim/scope
agents invoked/skipped
evidence inspected
findings / uncertainty
changes made if remediation authorized
verification-after-change performed: yes/no
limitations
completion status
```
