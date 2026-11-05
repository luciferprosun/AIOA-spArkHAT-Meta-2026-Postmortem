# Open engineering and security gates

These gaps are listed to make future integration decisions explicit, while preserving the verified prototype achievements.

| Gate | Why it matters | Status at 5 November 2026 |
| --- | --- | --- |
| Muse-authorized remote GitHub WRITE | Proposal is not execution | **BLOCKED_EXTERNAL**: development [PR #45](https://github.com/luciferprosun/AIOA-spArkHAT/pull/45) passed required CI; no live authorized commit/PR |
| Narrow GitHub App credentials | Protect production from broad developer credentials | Local App key/config and verified restricted installation token not configured for the live Core |
| Old UNKNOWN remote/financial effects | An ambiguous response is not proof of no effect | Historical Core records retained; reconciliation requires original provider evidence |
| Owner approval / safe deployment | Green unit tests do not grant permission | Need real local owner session, exact reviewed warrant and controlled release |
| Critical Prompt Loop LIVE / native worker | Agent execution needs separate evidence | Advisory/unbound, not certified as a complete autonomous tool loop |
| Remote mutation rollback | No blind replay/undo after partial effects | Read-only recovery exists in candidate; automatic rollback not implemented |
| Most recent Android UI release | A Compose source branch is not a signed APK | Real Cosmic 4.1.0 Android → Muse acceptance existed for a bounded profile; later UI changes still need complete build and physical-device checks |
| Stress-test history | One exact revision may fail what a later revision passes | 130-reconnect stress in [PR #39](https://github.com/luciferprosun/AIOA-spArkHAT/pull/39) timed out; a later 128-reconnect regression was reported passing; neither changes the earlier result |
| Historical-branch consolidation | Merge conflicts, duplicate functionality and policy divergence | Inventory exists; audited integration and branch retirement remain unfinished |
| iOS client | Future cross-device access | Planned API-backed companion, not a released iOS application |

## Evidence discipline

Every claimed PASS should identify the source revision, environment, test, actual permissions and receipt type. A real Android-initiated Muse reply is **not** a live GitHub WRITE. An offline fixture is **not** physical-device proof. A successful CI build of an experimental branch is **not** deployment.

## Decisions required before advancing

1. Preserve all owner-controlled secrets, SQLite history, device identity and old UNKNOWN records.
2. Choose a reviewed consolidation branch instead of force-merging all histories.
3. Complete any missing qualified builds, regression gates and real-device tests.
4. Add narrowly scoped GitHub App authentication, reconcile UNKNOWN evidence and obtain an exact owner warrant before the first real WRITE.
5. Keep the proposed iOS work behind stable existing Core contracts.

No statement in this postmortem authorizes an external GitHub mutation in the canonical product.
