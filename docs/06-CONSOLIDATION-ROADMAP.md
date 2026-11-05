# One AIOA spArkHAT: branch consolidation and future roadmap

**Canonical implementation repository:** https://github.com/luciferprosun/AIOA-spArkHAT

**This repository is documentation only.** Do not duplicate the codebase here; do not move secrets, state databases or raw device receipts into this public archive.

## Starting inventory and priorities

- During a 5 November branch enumeration, **75 names** were observed, including **main**; do not assume all contain unique unmerged features.
- Post-merge [PR #40](https://github.com/luciferprosun/AIOA-spArkHAT/pull/40) separately reported 74 remote heads, 40 already in main and 34 unique histories. The underlying branch set can evolve as PRs merge.
- Existing merged slices already integrate local Core/workspace/mobile and Muse READ. Do not remerge them blindly.
- Retain active development sources, notably [Muse chat #44](https://github.com/luciferprosun/AIOA-spArkHAT/pull/44) and [GitHub WRITE #45](https://github.com/luciferprosun/AIOA-spArkHAT/pull/45), until their dependencies, tests and effect safety are reviewed.

## Phase A — freeze and inventory

Snapshot main, local/remote refs, PRs, active worktrees, uncommitted data and exact source SHA. Identify owners and active jobs. Prepare recovery branches and reversible backups without resetting any live service.

## Phase B — functionality matrix

Classify each branch's contribution and map it into one canonical module group:

- AIOA Core: authority, policy, budget/governor, intent/outbox, receipt, Critical Prompt Loop.
- Provider routing: Meta Muse, existing other model integrations.
- Native Linux Mission Control: chat, status, security UX, desktop startup.
- Android companion: build/signing, pairing, mobile chat/status and session flow.
- GitHub: verified READ, proposal schema, scoped App WRITE candidate.
- MCP and authorized external tool adapters.
- Documentation, tests, security and CI.

For each module record: merged? duplicated? tests? LIVE evidence? missing dependencies? approved to ship?

## Phase C — integration without unsafe shortcuts

Create a temporary integration branch from up-to-date main. Apply the smallest independently reviewed slices in dependency order; resolve **functional** duplication instead of wholesale copying. Preserve canonical state/identity/TLS, historical receipts, UNKNOWN barriers and owner-controlled actions. Maintain the live Muse/Linux environment separately until tested.

## Phase D — evidence gates

Require targeted and full regression checks, packaging tests, current CI on the exact integration SHA, static security review and the narrowest relevant end-to-end demonstrations. Distinguish OFFLINE, DEVICE, LIVE MODEL, REMOTE READ and REMOTE WRITE. No unexplained skips or mock results represented as production PASS.

## Phase E — controlled promotion

Open a reviewable PR to main; owner approval precedes merge/deployment. Verify exact tree SHA, rollback plan, source compatibility and persisted Core state. Only after independent post-merge readback should redundant branches be nominated for deletion, with explicit owner approval.

## Phase F — advance the product

1. Complete stable Muse multi-turn conversation UX and receipts.
2. Reconcile old UNKNOWN external-operation records from original provider evidence, never by silent deletion.
3. Configure a repo-scoped GitHub App and execute one owner-approved, independently verified demo write on a separate test branch.
4. Complete physical-device acceptance for updated Android UI/mission capabilities and audited APK delivery.
5. Explore an **iOS companion** as an API-backed client after stable Core contracts; there is no iOS release at this time.
6. Broaden MCP/adapters only behind the same policy, provenance and operator controls.

**Goal:** one AIOA spArkHAT mainline and auditable product, not dozens of separate hackathon forks.
