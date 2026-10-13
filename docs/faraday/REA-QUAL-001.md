# REA-QUAL-001 — Review before build

Date: 2026-10-13
Repository: https://github.com/tomrivera-dev/rea
Review branch baseline: 4758ba30b6852c49b9539a2e815af22b3f822341
Status: PASS WITH FINDINGS (source-level), RUNTIME/INTEGRATION BLOCKED

## Verified
- Fork is public, default branch main; review branch pinned to the referenced commit.
- package.json identifies rea-agents v6.4.0; package-lock.json v3 exists.
- SECURITY.md expressly states its provider bridging is **not a sandbox**.
- docs/mcp-contracts.md documents Evidence identities, normalized results, coverage, limitations, retained bundles.
- CI YAML includes two daily cron patterns that collectively cover hourly intervals. Whether fork Actions are *enabled* is unverified; GitHub often disables scheduled workflows on new forks.
- THIRD_PARTY_NOTICES.md identifies third-party and separately licensed engines.
- GitHub Issues are disabled on this repository (issue creation returned 410).

## KEEP / CHANGE / ADD / DEFER
- KEEP: upstream fork, CLI/MCP as an evaluation target, evidence contract, licensing notices.
- CHANGE: no direct REA production registration; require isolated and authorized execution.
- ADD: independent branch-head/upstream pin verification; confirm fork Actions schedules/settings; dependency and native-artifact security scan; harmless authorized fixture; data retention and network policy; evidence normalization.
- DEFER: production integration, agent autonomy, code generation, Studio/Foundry and Orbit connections.

## Remaining gates
1. **A — Repo provenance/CI.** Verify exact main HEAD against upstream baseline; inspect Actions settings, workflows, schedules and billing. Proposed disabling inherited high-frequency schedules *if active* after explicit authorization. No workflow changes made.
2. **B — Supply chain.** Run npm audit with verified locked dependencies inside isolated environment; examine preinstall/install/postinstall scripts and native binary provenance; classify high/critical exposures.
3. **C — Isolated fixture.** Provision throwaway non-production environment, no secrets, no mounted credentials, constrained network, authorized non-sensitive fixture; reproducible test outputs.
4. **D — Reality Agent adapter review.** Read-only import of evidence_id, provenance, digests, coverage.scope/status, unknowns, limitations; independent verification; never promote a hypothesis to fact.
5. **E — Founder review.** Approve or reject bounded implementation separately.

## Architecture
REA = investigation/evidence generator. Reality Agent = independent verifier. FounderPM = sequencing. Shield = action governance. Orbit = prospective authorized entry point. ARC is FACP-specific, not a shared platform brain.

## Review safeguards
No installation, REA runtime execution, production secrets, deploy, merge, or product integration authorized by this record. This is documentation only.
