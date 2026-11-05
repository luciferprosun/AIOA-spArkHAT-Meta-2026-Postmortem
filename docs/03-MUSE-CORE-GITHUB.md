# Muse, Core, GitHub: architecture versus runtime proof

AIOA spArkHAT is designed around separating a language-model response from permission to perform an effect.

## The intended control path

User on Linux or Android → authenticated Mission Control / mobile gateway → AIOA Core → bounded model call to Meta Muse → verified response/receipt → optional **proposal** → policy + exact owner review → optional bounded tool execution → independent readback and audit record.

The arrow from **proposal to execution is a safety boundary**, not a promise that every tool is enabled.

## Verified model interaction

- A physical Android Muse request and Linux readback passed on **4 November**: see [Android LIVE acceptance](02-ANDROID-MUSE-LIVE.md).
- A separately owner-approved Linux Muse response is documented in [PR #40](https://github.com/luciferprosun/AIOA-spArkHAT/pull/40).
- The Linux interface and browser transport were subsequently improved through [PRs #41–#44](https://github.com/luciferprosun/AIOA-spArkHAT/pulls?q=is%3Apr+41+42+43+44). PR #44 covers bounded owner sessions, stale-read recovery, preservation of partial responses and multi-turn send paths. That code work is **not** evidence that every possible conversation sequence was physically accepted.

## GitHub READ

PR #40 reports a genuinely executed, Core-bound GitHub GET, linked to an exact repository ID/main SHA and signed readback. The model can be given explicitly verified, expiring read context. **READ is not permission to write**, and repository facts not backed by a fresh receipt should be described as assumptions.

## GitHub WRITE — development candidate only

[Draft PR #45](https://github.com/luciferprosun/AIOA-spArkHAT/pull/45) contains the more advanced candidate. Its supported design includes:

- restricted GitHub App installation token, minted per approved operation;
- strict, create-only proposals: new bounded files beneath a demo directory;
- exact review of tree, diff, file contents, owner warrant and expiration;
- creation of a separate branch, Git objects and draft PR; **no direct main write**;
- fresh GitHub GET verification, durable audit record and signed receipt;
- fail-closed status for unknown effects; no automatic risky retry or fake rollback.

**Actual status at submission:** candidate code/CI green; not deployed to production; no live Muse-triggered GitHub WRITE receipt. Missing local scoped App private key/configuration, unresolved historic UNKNOWN reservations, and absent exact owner WRITE authorization prevent activation. CPL LIVE is advisory/unbound and an automatic remote rollback executor is not provided.

## Security decisions

We intentionally retain the human approval boundary, existing Core governor/ledger, short-lived sessions, TLS/host identity, strict mobile status permissions, safe STOP and explicit UNKNOWN states. A generated JSON file-change plan can be useful in the recorded demo **without claiming it was committed**.

## What the demo should say

- “This is a real Muse response” only when a real API result/receipt is shown.
- “This is a proposed change” for the output of the model.
- “This is an owner-approved action” only when a fresh exact warrant was granted.
- “This is a verified GitHub write” **only if** the remote PR/commit and signed independent readback exist. No such live evidence was achieved for the hackathon candidate.
