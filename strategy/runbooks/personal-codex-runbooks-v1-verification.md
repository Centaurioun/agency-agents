# Personal Codex Runbooks v1 — Targeted Verification Record

**Phase:** Wave 1 targeted Verification & Remediation  
**Branch:** `feature/personal-codex-runbooks-v1`  
**PR:** draft verification PR  
**Scope:** five core Personal Codex runbooks only

## Verification targets

1. `strategy/runbooks.json` remains valid and every roster agent slug resolves.
2. Every new runbook `doc` path resolves.
3. The five core runbook slugs are unique and the optional Statistics & Visualization runbook is absent.
4. Shared execution-contract boundaries are represented consistently across the five runbook docs:
   - primary Codex thread remains coordinator/final synthesizer;
   - one primary runbook per task;
   - roster membership does not authorize activation;
   - testing/remediation/phase advancement require inherited explicit authorization;
   - parallel work is limited to independent/read-only/disjoint surfaces;
   - `agents-orchestrator` is not made the controller of these presets.
5. Existing repository validators remain green.

## Current evidence

Pending fresh pull-request validator runs. Do not infer pass status from implementation commits alone.
