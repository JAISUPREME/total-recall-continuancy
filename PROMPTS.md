# Total Recall Continuancy Prompt Set

These prompts implement the Total Recall Continuancy loop:

Chat → Extract → Master → Store → Intake → Prove → Clarify → Continue

Use them in order. Do not treat raw chat history, platform memory, or a model summary as current authority. Current state must be human-approved and preserved in user-controlled files.

## Individual prompt files

- `prompts/01-old-chat-extraction.md`
- `prompts/02-master-builder.md`
- `prompts/03-fresh-chat-intake.md`
- `prompts/04-bounded-historical-clarification.md`
- `prompts/05-acceptance-failure-recorder.md`

## Minimal public workflow

1. Run Prompt 1 in the old chat.
2. Use Prompt 2 to make the master.
3. Save the master in user-controlled files.
4. Start a fresh chat with Prompt 3.
5. Continue only after PASS.
6. Use Prompt 4 only for one bounded historical ambiguity.
7. Use Prompt 5 if intake fails.

## Core rule

Preserve the source. Preserve the artifact. Preserve the relationship. Preserve the correction. Prove re-entry. Then continue.

# Prompt 1 — Old Chat Extraction

Use this prompt at the end of an old chat or inside a chat that contains important project/research history.

```text
You are creating a Total Recall Continuancy extraction from this chat.

Do not continue the project.
Do not invent missing facts.
Do not rewrite history to make it cleaner.
Do not silently resolve contradictions.
Use UNKNOWN where information is missing.
Distinguish current state from superseded, provisional, rejected, or historical-only material.

TASK

Extract the durable continuity state of this chat into a structured handoff package.

Include project/topic identity, current approved state, authority/governance, decisions and corrections, artifact register, source/evidence register, claims ledger, open questions, resume point, and fresh chat START HERE summary.

OUTPUT FORMAT

Use clear Markdown headings.
Preserve exact filenames and names when available.
Use UNKNOWN rather than guessing.
End with:

CONTINUANCY_EXTRACTION_STATUS=
NEXT_SAFE_ACTION=
DO_NOT_INFER=
```

# Prompt 2 — Master Builder

Use this prompt after Prompt 1 has produced an extraction. This turns the extraction into a human-readable continuity master.

```text
You are building a Total Recall Continuancy master document from the extraction provided below.

Do not continue the underlying project.
Do not add new claims that are not supported by the extraction.
Do not silently resolve contradictions.
Do not overwrite historical material.
Use UNKNOWN where needed.
Preserve current/provisional/superseded/rejected/held distinctions.

TASK

Create a master continuity document that a future chat/model can use to re-enter the work accurately.

The master must include START HERE, governing laws, current state matrix, artifact register, source register, claims ledger, decisions/corrections, relationship map, open questions/UNKNOWN items, Continuation Acceptance Test, and exact continuation point.

OUTPUT FORMAT

Write in Markdown.
Make it readable as a standalone file.
Do not include private or irrelevant chat color unless it is necessary for continuity.
End with:

MASTER_STATUS=
CURRENT_STOPPING_POINT=
NEXT_VALIDATION_GATE=
DO_NOT_INFER=
```

# Prompt 3 — Fresh Chat Intake

Use this prompt at the start of a new chat with the START HERE summary and master document.

```text
You are receiving a Total Recall Continuancy handoff.

Do not continue the project yet.
Do not invent missing history.
Do not rely on platform memory.
Do not promote raw history or model memory into current truth.
Use only the provided master/state/provenance/resume package.
Use UNKNOWN where information is missing.
Respect current/provisional/superseded/rejected/held distinctions.

TASK

Read the provided START HERE and master continuity package.

Before doing any substantive work, answer the Continuation Acceptance Test:

Q1 — Current state
Q2 — Authority
Q3 — Active artifacts
Q4 — Evidence boundaries
Q5 — Do-not-infer
Q6 — Resume point
Q7 — Ambiguity test

OUTPUT FORMAT

ACCEPTANCE_TEST_RESULT=PASS / FAIL / CLARIFICATION_NEEDED
CURRENT_STATE_UNDERSTOOD=YES / NO
AUTHORITY_UNDERSTOOD=YES / NO
ACTIVE_ARTIFACTS_UNDERSTOOD=YES / NO
EVIDENCE_BOUNDARIES_UNDERSTOOD=YES / NO
DO_NOT_INFER_UNDERSTOOD=YES / NO
RESUME_POINT_UNDERSTOOD=YES / NO
BLOCKING_AMBIGUITY=NONE / [describe one]
NEXT_SAFE_ACTION=
```

# Prompt 4 — Bounded Historical Clarification

Use this only when the fresh chat finds one genuine ambiguity that cannot be resolved from the current approved master but may be answerable by an older chat or preserved source.

```text
You are acting only as a bounded historical witness.

Do not continue the project.
Do not update current state.
Do not verify new present-tense events.
Do not provide a full history dump.
Do not infer beyond what this chat/source could actually see.
Use UNKNOWN if the answer is not established in your available context.

CURRENT QUESTION

[Paste one narrow ambiguity here.]

TASK

Answer only this bounded historical question from the context available to you.

Include direct answer if known, evidence/basis, what remains UNKNOWN, and whether the answer is directly established, inferred, uncertain, or not answerable.

Do not promote your answer into current authority.

OUTPUT FORMAT

HISTORICAL_CLARIFICATION_RESULT=
ANSWER=
BASIS=
UNKNOWN=
STATUS=
DO_NOT_PROMOTE_TO_CURRENT_STATE_WITHOUT_REVIEW=YES
```

# Prompt 5 — Acceptance Failure Recorder

Use this when a fresh chat fails the acceptance test.

```text
You are recording a Total Recall Continuancy acceptance failure.

Do not continue the project.
Do not patch the master silently.
Do not overwrite historical artifacts.
Do not invent a corrected state.
Use UNKNOWN where needed.

TASK

Record the failure mode clearly.

Include intended handoff package, acceptance question that failed, exact failure, why it matters, failure class, required recovery action, and whether bounded historical clarification is justified.

OUTPUT FORMAT

ACCEPTANCE_FAILURE_RECORDED=YES
FAILURE_CLASS=
FAILED_QUESTION=
MATERIALITY=
RECOVERY_ACTION=
CLARIFICATION_ALLOWED=YES / NO
NEXT_SAFE_ACTION=
```
