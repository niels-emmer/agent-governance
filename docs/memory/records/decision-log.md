# Decision Log

Use this file for decisions that affect scope, architecture, security, or delivery.

Template:

## YYYY-MM-DD - Decision Title
Context:
Decision:
Alternatives considered:
Risk and mitigation:
Evidence/links:
Follow-up:

---

## 2026-02-27 - Establish simple memory system
Context:
Repository had governance policy but no operational memory workflow.
Decision:
Add `AGENTS.md` and `docs/memory/` as a lightweight, file-based memory system.
Alternatives considered:
Continue using only `GOVERNANCE.md` as source of truth during every task.
Risk and mitigation:
Risk: drift between governance and memory docs. Mitigation: explicit sync protocol in `AGENTS.md`.
Evidence/links:
`GOVERNANCE.md`, `AGENTS.md`, `docs/memory/*`.
Follow-up:
Keep memory files synchronized whenever governance policy changes.

---

## 2026-02-28 - Document alignment with agents.md standard
Context:
`docs/memory/README.md` described the local memory system but did not explicitly reference the external `agents.md` standard.
Decision:
Add an "Alignment with `agents.md`" section with a link to https://agents.md/ and a short mapping to local files.
Alternatives considered:
Leave alignment implicit via existing `AGENTS.md` usage.
Risk and mitigation:
Risk: external standard reference may drift. Mitigation: keep wording high-level and maintain link validity during docs reviews.
Evidence/links:
`docs/memory/README.md`, https://agents.md/
Follow-up:
None.
