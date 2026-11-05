# Android + Linux: what really worked and what remained

**Scope:** Android companion / Cosmic UI, Linux Native Core, signed device enrollment/status, private transport, and future model actions. This page is not a claim of an Android production release.

## Engineering outcome

The Android work was substantial. We built and integrated source for a companion app, Linux device console, private host pairing and signed status flows. Mainline integration was done through [PR #27](https://github.com/luciferprosun/AIOA-spArkHAT/pull/27), [#34](https://github.com/luciferprosun/AIOA-spArkHAT/pull/34), [#35](https://github.com/luciferprosun/AIOA-spArkHAT/pull/35), [#39](https://github.com/luciferprosun/AIOA-spArkHAT/pull/39), and [#40](https://github.com/luciferprosun/AIOA-spArkHAT/pull/40). These changes use the existing Native Core rather than a separate mobile authority service.

Implemented mechanisms include:
- Device enrollment and status-only profile, native local PolicyKit admission, SQLite records, one-use enrollment codes and replay/revocation checks.
- Signed QR invitation and host/SAS confirmation, device trust records, fresh signed status/reconnect, and explicit unavailable-action indicators.
- Android Cosmic UI / Linux device controls with shared design tokens and source-checked read-only mission surfaces.
- Transport work using existing private Tailscale connectivity and TLS, without claiming public network availability.
- Explicit disabled status for unsupported Android model execution, spending, GitHub writes or autonomous task mutation.

## Build evidence

An inspected Android 4.0.0 Cosmic **DEBUG** APK build associated with GitHub Actions [run 41688400577](https://github.com/luciferprosun/AIOA-spArkHAT/actions/runs/41688400577) recorded:

| Check | Recorded result |
| --- | --- |
| Source checkout | \`6e018c877d518c2ab3f16c312cccecc80ac69080\` |
| Profile | \`DEBUG_UBUNTU22_V1\` |
| Android package | \`eu.sparkhat.aioa.companion.cosmic4\` |
| Version | \`4.0.0-cosmic\` / versionCode 400 |
| Android JVM tests | **76 PASS, zero failures** |
| Android lint | **0 errors** |
| Assemble | **PASS** |
| APK bytes | 12,113,711 |
| Artifact upload | **NOT_RUN** in the saved build-evidence snapshot |
| Release signing / independent phone E2E | **NOT VERIFIED** by the build report |

Debug build dependencies and runner inventory had documented verification limitations; this is **host-built**, not a reproducible production/release certification.

## Actual pairing evidence on 3 November

A private source- and device-bound readback recorded at **2026-11-03 18:29 UTC** reported:

- \`installed_byte_identity_verified = true\`
- \`pairing = COMPLETED_CORE_AND_APP_MATCH\`
- existing and newly recorded trusted device entries preserved and not revoked
- \`status_readback = EXPIRED_OR_NOT_CURRENT\`
- \`model_calls = 0\` in that pairing evidence

The claim supported by this record is **the Core-and-app pairing was completed and matched at the recorded point**, **not** that the phone maintained a fresh active session indefinitely. An independently observed historical status was fresh at an earlier moment; the later readback expired.

The [PR #39](https://github.com/luciferprosun/AIOA-spArkHAT/pull/39) snapshot had earlier shown a real Linux Core/UI device registry with one trusted device and zero current sessions, while Xiaomi's fresh remote status was still pending. Later snapshots mention two retained trusted-device records. Different timestamps and source versions should not be silently merged into one single live test.

## What consumed days

The original schedule underestimated:
1. Android SDK/JDK/Gradle and hosted runner-image pinning.
2. APK signature, package and permission validation (including scanner dependency permissions).
3. Distinguishing built source, downloadable APK, user-installed APK and verified phone outcome.
4. Device network availability, signed pairing, native desktop admission and reconnect.
5. Concurrent Android, Linux, provider and frontend worktrees with strict no-regression boundaries.
6. Full test and CI execution for each repair before it could be considered safe.

Examples of specific fixes and proof: [PR #36](https://github.com/luciferprosun/AIOA-spArkHAT/pull/36) (build and source fingerprint), [PR #38](https://github.com/luciferprosun/AIOA-spArkHAT/pull/38) (explicit QR scanner network permission), [PR #39](https://github.com/luciferprosun/AIOA-spArkHAT/pull/39) (Cosmic UI and honest acceptance gates).

This was **an integration/scope management failure**, not evidence that all Android work was wasted. The correct next step is a narrow real-device acceptance run with fresh signed status, followed by separately approved Muse inference, and only later mobile execution features.

## Explicit limits

**Not claimed:** production-signed Android release; iOS binary; continuous Xiaomi connectivity; live Android → Linux → Muse response receipt; native GitHub WRITE via phone; unconstrained autonomous execution. These need independent tests. Their absence does not negate the completed build and pairing milestones, but it matters for a hackathon description.

[Back to overview](../README.md) · [Test evidence](03_TESTS_AND_CI.md)
