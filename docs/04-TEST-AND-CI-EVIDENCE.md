# Test evidence: measured snapshots, no inflated totals

**Date:** 5 November 2026. These numbers are sourced from individual merged PR descriptions, CI runs, and the audited local report for the 5 November GitHub WRITE candidate. They represent **different source revisions and test suites**. They must **not be added together** and described as one combined test run.

| Revision / work | Reported measured result | Evidence |
| --- | --- | --- |
| ONE AIOA local integration, 1 Nov | 2,488 Python tests total: **2,483 pass + 5 optional skips**, 0 fail; plus Native 42/42, Node 15/15, packaging 2/2 (separate suites) | [PR #27](https://github.com/luciferprosun/AIOA-spArkHAT/pull/27) |
| Android QR/core, 3 Nov | 2,609 Core tests **per Python 3.11 and 3.12** with 5 allowed optional skips per run; 105 native authority tests; hosted browser/packaging checks | [PR #35](https://github.com/luciferprosun/AIOA-spArkHAT/pull/35), [CI](https://github.com/luciferprosun/AIOA-spArkHAT/actions/runs/41575188754) |
| Android/Linux Cosmic UI, 3–4 Nov | 166 Python baseline/build-handoff + 39 Native security + 29 JS + 66 JVM tests **reported PASS**; isolated browser PASS; **130-reconnect long test TIMEOUT/NOT_PASS in that revision** | [PR #39](https://github.com/luciferprosun/AIOA-spArkHAT/pull/39) |
| Unified main Muse advisory + GitHub READ | **10/10 required CI jobs PASS**; 2,740 Core tests per Python interpreter, 5 allowed skips per run; 105 NonZero regressions per interpreter | [PR #40](https://github.com/luciferprosun/AIOA-spArkHAT/pull/40), [Core CI](https://github.com/luciferprosun/AIOA-spArkHAT/actions/runs/41809858882) |
| CDP/Chrome repair | **10/10 required CI jobs PASS**; 2,795 tests per Python interpreter, 5 optional skips each; 105 additional tests | [PR #42](https://github.com/luciferprosun/AIOA-spArkHAT/pull/42) |
| Muse direct owner sessions | 142 targeted Python tests and 41 JavaScript tests reported PASS; four Core/packaging CI jobs PASS on the reviewed head | [PR #44](https://github.com/luciferprosun/AIOA-spArkHAT/pull/44), [CI](https://github.com/luciferprosun/AIOA-spArkHAT/actions/runs/41962468545) |
| Muse → GitHub WRITE development candidate (final revision ff38e17a, 5 Nov) | **6/6 required CI jobs PASS**; 2,856 tests **per Python 3.11 and 3.12**, 0 failures, **5 allowed optional skips per run**; 105 NonZero regressions per interpreter; 43 JavaScript tests; 52 focused integration/security tests; 96 broader Native tests | [PR #45](https://github.com/luciferprosun/AIOA-spArkHAT/pull/45), [Core CI](https://github.com/luciferprosun/AIOA-spArkHAT/actions/runs/41975197032), [MCP CI](https://github.com/luciferprosun/AIOA-spArkHAT/actions/runs/41975197031) |

## Key interpretation

- The **2,856** figure is the complete reported suite **for each interpreter**, not 2,856 independent features. The 5 permitted skips are part of the 2,856 total, not hidden successes. We therefore do not advertise 5,712 distinct tests.
- The **105 NonZero** tests and targeted suites are mentioned separately as they appear in the engineering reports; overlapping assertions may exist.
- A **PASS in synthetic/local tests** does **not** establish live model use, a real phone pairing, a paid operation or a remote GitHub mutation. Each live action needs separate evidence.
- **CodeQL SKIPPED** is not called PASS when the relevant policy gate did not run. Earlier merged snapshots have individual CodeQL results and historical Kotlin-build issues; see their exact PRs.
- Earlier failing CI runs and timeouts remain part of the record. For example, a legacy issue-proposal state bug failed one #45 development run before being fixed. The final exact revision ff38e17a passed its required CI.

## Measured real execution is separate

- **Physical Android → Muse Spark 1.3:** one successful approved API call; 530 tokens, signed Linux readback. See [02](02-ANDROID-MUSE-LIVE.md).
- **Linux → Muse Spark 1.3:** one separately approved real response reported in [PR #40](https://github.com/luciferprosun/AIOA-spArkHAT/pull/40), 361 tokens, with proof of repository READ separately.
- **GitHub WRITE by Muse:** zero verified live acceptance operations at the submission snapshot; development CI is not a substitute.

The goal is inspectable engineering confidence, not the largest possible marketing test count.
