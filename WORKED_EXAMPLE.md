# Worked Example — Three-Chat Continuancy Lineage

This example shows how Total Recall Continuancy carries a project from one chat to another without depending on platform memory.

The point is not to load every old message into every new chat.

The point is to preserve approved state, provenance, corrections, artifacts, and the resume point.

## Scenario

A researcher is using AI to investigate Topic X across multiple long chats.

The work includes sources, claims, decisions, corrections, and a final written report.

The first chat is getting too long, so the user needs to move the project into a fresh chat without losing continuity.

## Chat A — Original research chat

Chat A creates the first research branch.

It produces Sources S01-S12, Research Packet A, Decision D01, Master A, Artifact Register A, Claims Ledger A, and Open Questions A.

At closeout, the user runs Prompt 1 — Old Chat Extraction.

The extraction records what was established, what was inferred, what was the user’s thesis, what remained UNKNOWN, which files were created, which decisions were current, which claims were provisional, and where the work stopped.

Then the user runs Prompt 2 — Master Builder.

The result is `MASTER_A.md`.

Commander/user review approves Master A.

Master A becomes the current continuity spine.

## Chat B — First fresh continuation

Chat B receives `START_HERE_A.md`, `MASTER_A.md`, and `ARTIFACT_REGISTER_A.md`.

Before continuing, Chat B must answer the Continuation Acceptance Test.

If Chat B passes, it may continue one bounded task.

During continuation, Chat B discovers that Claim C04 from Chat A was overstated.

Chat B does not silently rewrite Chat A.

Instead, it creates Correction D02, Research Packet B, and Master B.

Master B BUILDS_ON Master A, CORRECTS Claim C04, and PRESERVES Master A as a historical ancestor.

The correction changes current state, but it does not erase the earlier record.

## Chat C — Second fresh continuation

Chat C receives `START_HERE_B.md` and `MASTER_B.md`.

Chat C does not need all of Chat A loaded wholesale.

If Chat C needs Source S03, it follows the lineage:

Master B → Research Packet A → Source Register A → Source S03

Chat C then validates only the needed evidence branch.

## Bounded historical clarification

Chat C encounters one unresolved question: why was Decision D01 originally chosen?

Master B does not contain the rationale.

If Chat A still exists and uniquely retains that context, Chat C may generate one bounded clarification request using Prompt 4 — Bounded Historical Clarification.

The old chat answers only from what it could see.

The answer is not automatically current truth.

The user reviews it.

If accepted, Chat C creates Clarification Artifact C01.

C01 is related to D01 and incorporated through a new state transition.

## If the old chat is unavailable

If Chat A no longer exists, Chat C does not invent the rationale.

It records D01_RATIONALE = UNKNOWN.

The project may continue only if that UNKNOWN item does not block the current task.

## Resulting lineage

Chat A → Master A → Chat B → Correction D02 → Master B → Chat C → Clarification Artifact C01 → Master C

## What this proves

This example demonstrates that raw chat history is evidence, a master carries approved state forward, corrections preserve lineage, fresh chats must prove handoff understanding, old chats may serve as bounded witnesses, missing information remains UNKNOWN, and the user-controlled repository remains authoritative even if old chats disappear.

## Core rule

A prior chat is a witness, not a ruler.

A new chat is a receiver, not an owner.

The user-controlled master governs continuation.
