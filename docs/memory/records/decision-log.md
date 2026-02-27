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

