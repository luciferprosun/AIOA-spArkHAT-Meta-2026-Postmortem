# What consumed the hackathon: engineering challenges and lessons

## The original ambition

We wanted to integrate Muse as an effective agent provider into an existing AIOA Core, with a polished Linux White Hole Mission Control, an Android companion, GitHub READ/WRITE, and future iOS access. Rather than ship only a small web chat, we tried to connect identity, persistent authority, signed device transport, a model API and tool execution.

## Sources of delay

### 1. Android packaging and signer compatibility

The app had multiple Android/JDK/SDK/build variants. Gradle/Compose, pinned toolchain requirements, signing-fingerprint continuity and CodeQL for Kotlin demanded targeted repair and verification. A successful dependency download is not an Android build; a JVM unit test is not proof that a signed APK installed on a physical phone. We ultimately achieved a physical, in-place update for a bounded Xiaomi profile, but not every later Android UI branch achieved new build-and-install acceptance.

### 2. Pairing, identity and private transport

A reliable Android → Linux connection requires genuine owner admission, TLS/host identity, signed invite and reconnect, replay protection, revocation and device Keystore preservation. Rebuilding this as a quick permissive API would have undermined the point of the platform. The owner-tested signed profile was retained; it did not automatically authorize tasks or repository writes.

### 3. Browser and model-conversation faults

Chrome/CDP deadlines, network and host-session lifetimes, failed background reads, stale response UI and incomplete send routing caused real friction. The Linux chat and session recovery work was patched/tested in [PRs #41–#44](https://github.com/luciferprosun/AIOA-spArkHAT/pulls). A genuine model response from Android and a separate Linux owner-approved response were achieved, but we did not claim an unrestricted autonomous tool loop.

### 4. The cumulative cost of regression and security checks

Changing a shared Core requires proving the owner authority, governor, UNKNOWN records, device bindings and signed receipts are not damaged. Larger CI runs reached thousands of tests for each Python interpreter. Keeping previous failures visible and fixing them is slower than relabeling a blocked capability as ready.

### 5. GitHub WRITE was a separate authorization challenge

The design implemented a limited App token and exact proposal-to-approval-to-readback path in [draft PR #45](https://github.com/luciferprosun/AIOA-spArkHAT/pull/45). However, local App key setup, historic uncertain operations, deployment and exact user sign-off had not been completed. Existing broad GitHub CLI credentials were intentionally not substituted for a scoped runtime token.

### 6. Scope management and branching

Working in parallel on Android, Meta Muse, Nebius/NVIDIA leftovers, security modules, Linux UI and integration branches created duplicate implementations and expensive merge review. Our 5 November audit found **75 branch names including main**; a different post-merge snapshot in PR #40 reported **74 remote heads**. These are point-in-time inventories, not contradictory universal totals. We need one canonical product and fewer ongoing tracks.

## What we learned

1. Define one measurable acceptance path at the start: owner → model → proposal → optional approved action → independent evidence.
2. Freeze optional mobile/UI work before a contest deadline; prioritize the one demo path.
3. Use small CI and simulation locally, then require separate physical and LIVE gates for the relevant release.
4. Preserve old state, credentials and UNKNOWN liabilities rather than resetting for convenience.
5. Make proposals and executed changes visibly different to the user and judges.
6. Reduce branch entropy by auditing actual functionality before merges and deletions.

We see the hackathon result as a meaningful prototype milestone and a candid scheduling failure against the full agent ambitions. We are continuing development, not describing unfinished features as production-ready.
