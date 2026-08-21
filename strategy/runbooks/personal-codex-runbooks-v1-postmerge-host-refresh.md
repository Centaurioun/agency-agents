# Queue 1 — Personal Codex Runbooks v1 Post-Merge Host Refresh

**Date:** 2026-08-21
**Repository:** `Centaurioun/agency-agents`
**Validation branch:** `validation/personal-codex-runbooks-v1-postmerge-host-refresh`
**Starting SHA:** `65c2a64dce17cc7dcced01b6b6f421eff241d528`
**Final SHA:** `57b7d1fe24e0f003b14323fcb387d5bde509586f`
**Local repository path:** `/Users/yusuf/Repos/agency-agents`
**Canonical main SHA observed:** `65c2a64dce17cc7dcced01b6b6f421eff241d528`
**Canonical merge commit:** `389eab64cd602364f42b805cdb1f9a0fb570e987`

## Host state

- **Agency Agents app:** `/Applications/Agency Agents.app`
- **App version:** `0.3.0`
- **Managed catalog:** `/Users/yusuf/.agency-agents`
- **Pre-refresh catalog state:** app state reported `github:main@2026-08-20`;
  the catalog is a Git checkout on `main` at
  `ebe9c99acb5c96f9468de368d8bead775387d1a7`.
- **Managed catalog remote:**
  `https://github.com/msitarzewski/agency-agents.git`
- **Pre-refresh manifest:** four scenario runbooks; none of the five canonical
  Personal Codex runbooks were present.

## Existing refresh path investigation

- **Refresh/update path found:** NO safe path capable of consuming the current
  `Centaurioun/agency-agents` canonical `main` was available in the current
  host environment.
- **Mechanisms investigated:** the installed app's native catalog operations
  exposed in its local runtime (`catalog_check_updates`, `catalog_pull`,
  `catalog_source_set`, and `runbooks_list`), the app's configured catalog
  state, and the managed catalog's existing Git remote/branch.
- **Refresh attempted:** NO.
- **Reason:** the installed app is configured for a read-only managed clone
  whose remote is the upstream `msitarzewski/agency-agents` repository, not the
  canonical `Centaurioun/agency-agents` repository. Running its normal pull
  would refresh the wrong source and could not make the canonical five
  runbooks available. The app did not expose an accessible UI/API path in this
  session to select the canonical repository, and no documented repository
  update command for changing this managed source was available.
- **Required limitation:**
  `HOST_REFRESH_NOT_AVAILABLE_WITH_EXISTING_ROUTINE_PATH`
- **Post-refresh catalog state:** unchanged; still managed `main` at
  `ebe9c99acb5c96f9468de368d8bead775387d1a7`, with app metadata still
  `github:main@2026-08-20`.

## Bounded host acceptance

Because the canonical-main refresh could not be performed through an existing
safe routine path, the five-runbook host acceptance could not be established.
The managed catalog manifest was inspected directly and the following were
not discoverable there:

- `academic-research-development`
- `academic-research-architecture`
- `academic-retrieval-improvement`
- `new-mcp-callable-component`
- `plugin-verification-remediation`

Document loading, roster resolution, and activation-label behavior for these
five runbooks were therefore not observable through the normal host path. No
claim is made that they are available in the installed app.

The canonical repository itself was not altered: the five runbooks and shared
contract were already present on observed `main`; no product/runbook content
was changed during this task.

`Statistics & Visualization` was not started or added. No unrelated runbooks,
app behavior, or other repositories were modified.

## Final classification

`HOST_LIMITATION_RECORDED`
