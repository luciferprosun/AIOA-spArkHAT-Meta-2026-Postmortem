# One AIOA: post-hackathon consolidation and Muse roadmap

**The single canonical product repository is [luciferprosun/AIOA-spArkHAT](https://github.com/luciferprosun/AIOA-spArkHAT).** This postmortem repo contains only documentation. The plan below is **proposed work**, not a declaration that all code has been merged.

## Phase 0 — protect current working evidence

- Inventory the real main SHA, live Native source, installed Android build identities, active worktrees, open PRs, preserved logs, owner identity, TLS keys and SQLite.
- Create reversible backups and read-only integrity checks, without overwriting/rewriting historic receipts.
- Protect active Muse/Android work; preserve existing \`UNKNOWN\` operations and any funds reservations. No silent clean/reset/force-push, no blanket branch deletion.

## Phase 1 — one architecture, not 75 blind merges

The remote branch inventory in early November had **75 names including main**. PR #40 documented an earlier post-merge inventory of **74 remote heads, 40 already in main, 34 with distinct histories**. These are time-specific snapshots, not contradictory totals for one instant.

- Build a feature provenance inventory by branch, PR, unique commits, files, safety contracts, and active dependents.
- Distinguish already merged changes, duplicate implementations, true new features, dead code, and long-lived experiments.
- Reconcile GitHub READ, GitHub WRITE draft, Muse chat/session, Core/CPL, MCP, device identity, Android gateway, Mission Control and policy ledger.
- Prefer selective forward integration into the **same Core**. Use an isolated short-lived integration branch/worktree or protected PR only as needed; no separate permanent product repo. No direct unreviewed mutations to protected \`main\`.
- For each completed integration: test, prove behavior, review security, document final commit, and only then update canonical \`main\`. Delete redundant historical branches **only after explicit owner approval** and verified reachability of their unique content.

**Relevant unmerged development PRs as observed 5 Nov:** [#44 direct chat session](https://github.com/luciferprosun/AIOA-spArkHAT/pull/44) and [#45 reviewed GitHub WRITE](https://github.com/luciferprosun/AIOA-spArkHAT/pull/45). Check current status again before modifying them.

## Phase 2 — improve conversational agent reliability

- Fix any remaining Send/recovery lifecycle bugs without weakening the single Core journal.
- Prove three consecutive actual Muse responses using one owner-admitted session and genuine provider receipts.
- Maintain context bounded by token/time budgets; preserve full content safely for display, distinguish truncated/partial replies and mark model content as untrusted proposals.
- Preserve and use verified GitHub READ as tool context, with provenance and expiry. Ensure UI indicates freshness and avoids synthetic evidence.
- No automatic paid retries after timeout or uncertain response.

## Phase 3 — activate controlled GitHub READ and WRITE

The goal is **functional execution**, but only after real controls and acceptance:
1. Install **a user-owned GitHub App restricted to a designated test repository**. Grant only Contents and Pull Requests read/write plus Metadata read. Keep its private key local in a root/user-protected state directory, not in logs or git. Issue fresh short-lived installation tokens and independently verify scope.
2. Resolve or safely reconcile earlier \`UNKNOWN\` provider reservations through documented original evidence; never assume no effect or reset ledger. If irrecoverable, require separate owner-approved risk disposition preserving the historical unknown.
3. Verify the draft PR #45 design, its dependency on PR #44, source and CI. Deploy only after signed owner admission and controlled release safeguards.
4. Real workflow: **verified repository READ → real Muse proposal → Core schema/policy review → exact owner approval → new branch/files/commit/draft PR → independent GitHub GET → signed receipt**.
5. Test denial and incident cases: expired approval, mismatched repo/tree, private-key absent, 401/403/429, duplicate request, lost response, expired worker, stop, process restart, partially completed remote actions.
6. Only after successful test-repo acceptance should scope expand to carefully selected canonical repo workflows. Broad "can do everything" means an **extensible reviewed toolbox**, not bypassing code review or arbitrary destructive administration.
7. Preserve default **READ-ONLY**; require independent approval for each WRITE or higher-risk operation. No agent-issued permission escalation, no autonomous deletion/force push/main merge.

## Phase 4 — restore Android ↔ Linux and eventually Muse

- Start from host-verified Android Cosmic build and signed pairing evidence, not a screenshot.
- Reconfirm actual app source and installed signature, private Tailscale transport, current signed status/reconnect, revocation and freshness.
- Perform a separately budgeted, real owner-approved Android → Core → Muse conversational turn; capture provider receipt and signed readback.
- Expose reviewed GitHub proposals on Android without exposing installation credentials to the handset. Sensitive writes continue to require Core owner approval.
- Revalidate on physical phone and under restart/network loss.

## Phase 5 — explore iOS and startup readiness

Investigate a **thin iOS client** that speaks to the existing AIOA Native Core and authorized hosted Muse API; preserve one authority system and one audited execution path. Security architecture, Apple developer tooling/build/signing, pairing, model terms, and real-device acceptance need independent analysis. No claim of an existing iOS app or of native on-device Muse execution.

After stable end-to-end operation, pursue a reproducible demo/release profile, public technical documentation, operator runbook, minimal-privilege security review, and startup/prototype-fund readiness.

## Acceptance criteria for saying "agent works"

- Actual model output with receipt and state; no prerecorded fixture substituted for LIVE.
- Evidence-bound GitHub READ with repo/main SHA.
- Exact owner consent to one proposed bounded WRITE.
- New test-repo commit and draft PR independently verified by GitHub GET.
- Durable signed receipt, error/UNKNOWN recovery, no hidden retries.
- CI and security review on exact deployed source, plus real operator/UI proof.
- Separate Android/iOS claims only after end-to-end physical tests.

[Overview](../README.md) · [Evidence matrix](01_STATUS_AND_EVIDENCE.md)
