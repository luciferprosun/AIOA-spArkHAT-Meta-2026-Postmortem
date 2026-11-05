# Quantified tests, CI and verification

**Evidence date:** 2026-11-05. These numbers belong to **different source revisions**. Do not sum them into one unique test count or mistake CI for proof of production acceptance.

## GitHub WRITE development candidate

Source **ff38e17a**, [draft PR #45](https://github.com/luciferprosun/AIOA-spArkHAT/pull/45):

| Check | Result | Evidence |
| --- | --- | --- |
| Core suite — Python 3.11 | 2,856 collected, 0 failures, 5 permitted skips | [CI run 41975197032](https://github.com/luciferprosun/AIOA-spArkHAT/actions/runs/41975197032) |
| Core suite — Python 3.12 | 2,856 collected, 0 failures, 5 permitted skips | Same |
| NonZero regressions | 105 in each Python interpreter | Same |
| Installed packaging | 2/2 PASS | Same |
| Core certification | 2/2 PASS | Same |
| MCP contract | 2/2 PASS | [CI run 41975197031](https://github.com/luciferprosun/AIOA-spArkHAT/actions/runs/41975197031) |
| Required hosted jobs, combined | **6/6 PASS** | Both runs |
| Isolated browser gate | PASS on 3.11 and 3.12 | Both certify jobs |
| CodeQL | **SKIPPED**, not a pass | Existing owner-controlled policy |
| Targeted remote integration/security | 52 PASS | Private local CI evidence |
| JavaScript chat/console | 43 PASS | Private local CI evidence |
| Broader Native/source/HTTP | 96 PASS | Private local CI evidence; includes 128 reconnects |
| \`test_core_remote_git\` | 4 PASS | Included in the 52 tests |
| Expired worker recovery | 20 PASS | Local regression evidence |
| Legacy proposal status fix | 15 PASS | Local regression evidence |

The draft PR's **LIVE GitHub WRITE remains BLOCKED_EXTERNAL**: the scoped GitHub App key was not available to the Native runtime, historical Meta UNKNOWN reservations persisted, and exact owner approval was absent. No demo commit/PR was created by live Muse execution. A local fixture and a GitHub development PR are not equivalent to an agent-created live PR.

## Earlier Linux Muse + GitHub READ mainline

[PR #40](https://github.com/luciferprosun/AIOA-spArkHAT/pull/40) merged an earlier version into \`main\` with:
- **10/10 required CI jobs PASS**: [Core/packaging 4/4](https://github.com/luciferprosun/AIOA-spArkHAT/actions/runs/41809858882), [MCP 2/2](https://github.com/luciferprosun/AIOA-spArkHAT/actions/runs/41809858921), [default CodeQL 4/4](https://github.com/luciferprosun/AIOA-spArkHAT/actions/runs/41809859449).
- **2,740 Core tests on each of Python 3.11 and 3.12**, with 5 permitted optional skips per interpreter.
- **105 NonZero tests** per interpreter, and local transport / authority / JavaScript / isolated browser checks.
- A separately authorized **real Meta Muse API response**, plus an independently verified **GitHub READ** receipt.

Those mainline CodeQL results do not imply CodeQL ran for the later PR #45.

## Android milestones

| Version / scope | Evidence | Limitation |
| --- | --- | --- |
| Native status pairing [PR #34](https://github.com/luciferprosun/AIOA-spArkHAT/pull/34) | 88 targeted tests and 19 subtests, zero failures | Local OS auth partly mocked in tests |
| QR/Cosmic source [PR #35](https://github.com/luciferprosun/AIOA-spArkHAT/pull/35) | 2,609 hosted Core tests per interpreter; 5 allowed optional skips; separate 105 Native checks; isolated browser PASS | At that PR stage Kotlin build/physical test pending |
| Builder repair [PR #36](https://github.com/luciferprosun/AIOA-spArkHAT/pull/36) | 119 Android regressions PASS | Did not itself build a phone-ready release |
| QR manifest repair [PR #38](https://github.com/luciferprosun/AIOA-spArkHAT/pull/38) | 122 Android regressions PASS | Actual installed merged manifest was checked later |
| Cosmic UI [PR #39](https://github.com/luciferprosun/AIOA-spArkHAT/pull/39) | Local 166 Python, 39 Native security, 29 JS, 66 JVM PASS | A 130-reconnect experimental run timed out; not PASS |
| Cosmic 4.0.0 DEBUG APK, source \`6e018c8\` | **76 JVM tests PASS**, **0 lint errors**, **ASSEMBLE PASS**, 12.1 MB host-verified APK | [Actions run 41688400577](https://github.com/luciferprosun/AIOA-spArkHAT/actions/runs/41688400577); not release-signed or accepted physical Android → Muse E2E |
| 3 Nov signed pairing evidence | \`COMPLETED_CORE_AND_APP_MATCH\`, installed bytes match | Fresh subsequent status \`EXPIRED_OR_NOT_CURRENT\` |

## Lessons about test reporting

**Do not claim:** millions of proven behaviors; all-code green CI; 2,856 distinct features; security certification from tests alone; successful mobile-to-Muse inference because separate Android pairing and Linux model checks exist. Always keep source SHA, runner, date and caveats beside each number.

[Overview](../README.md) · [Android details](02_ANDROID_LINUX.md) · [Roadmap](05_CONSOLIDATION_AND_IOS_ROADMAP.md)
