# Total Recall Continuancy Prompt Set

These prompts implement the Total Recall Continuancy loop:

Chat → Extract → Master → Store → Intake → Prove → Clarify → Continue

Use them in order. Do not treat raw chat history, platform memory, or a model summary as current authority. Current state must be human-approved and preserved in user-controlled files.

## Prompt 1 — Old Chat Extraction

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

Include:

1. PROJECT / TOPIC IDENTITY
- Working title
- Purpose
- Scope
- Major lanes or subprojects
- Current profile: BASIC / RESEARCH / PROJECT / ARCHIVAL

2. CURRENT APPROVED STATE
- What is currently approved or operative
- What is provisional
- What is superseded
- What is rejected
- What is held
- What remains UNKNOWN

3. AUTHORITY / GOVERNANCE
- Who approves changes
- What the model was allowed to do
- What the model was not allowed to do
- Any do-not-infer rules

4. DECISIONS AND CORRECTIONS
For each major decision or correction:
- ID
- Date or approximate point in chat if known
- Decision/correction
- Reason
- Status
- What it supersedes or corrects

5. ARTIFACT REGISTER
For each important file, document, image, script, package, source capture, report, or output:
- Exact filename if known
- Role
- Origin
- Current status
- Relationship to other artifacts
- Whether it is current, supporting, superseded, missing, or UNKNOWN

6. SOURCE / EVIDENCE REGISTER
For each meaningful source:
- Source ID
- Title or identity
- URL or local identity if available
- What claim it supports
- Evidence status: established, user thesis, structural inference, speculative, disputed, UNKNOWN, or audit gap
- Limitations

7. CLAIMS LEDGER
For each major claim:
- Claim
- Status
- Basis
- Supporting source/artifact if available
- Boundary or limitation

8. OPEN QUESTIONS
- Unresolved items
- Ambiguities
- Blockers
- Questions that require user review
- Questions that may require bounded historical clarification

9. RESUME POINT
- Exact stopping point
- Next permissible action
- Actions that must not be taken yet

10. FRESH CHAT START-HERE SUMMARY
Write a concise summary that can be pasted into a new chat before the full master.

OUTPUT FORMAT

Use clear Markdown headings.
Preserve exact filenames and names when available.
Use UNKNOWN rather than guessing.
End with:

CONTINUANCY_EXTRACTION_STATUS=
NEXT_SAFE_ACTION=
DO_NOT_INFER=
