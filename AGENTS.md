# AGENTS.md

## 1. Purpose
This repository uses a simple file-based memory system for human and agent collaboration.

`GOVERNANCE.md` is the canonical policy source.
`docs/memory/` is the operational memory that agents should use during delivery.

Rule: transfer governance knowledge into `docs/memory/` and work from that memory.
Treat `GOVERNANCE.md` as a temporary reconciliation source when memory is missing, stale, or ambiguous.

## 2. Required Startup Routine
Before doing implementation work, agents must:

1. Read `docs/memory/core-principles.md`.
2. Read `docs/memory/workflow.md`.
3. Read `docs/memory/checklists.md`.
4. Read the latest relevant entries in `docs/memory/records/`.

## 3. Memory Model
- Stable memory: `docs/memory/core-principles.md`
- Process memory: `docs/memory/workflow.md` and `docs/memory/checklists.md`
- Evidence memory: `docs/memory/records/*.md`

## 4. Update Protocol
When a task is executed:

1. Record important choices in `docs/memory/records/decision-log.md`.
2. Record verification outcomes in `docs/memory/records/testing-log.md`.
3. Record documentation changes in `docs/memory/records/documentation-log.md`.
4. For release-ready changes, record gate status in `docs/memory/records/release-log.md`.

If `GOVERNANCE.md` introduces a rule not represented in memory:

1. Update the relevant file in `docs/memory/` first.
2. Add a synchronization note in `decision-log.md`.
3. Continue implementation using the updated memory files.

## 5. Guardrails
Agents must preserve these constraints while coding:

- Security by design for all external interfaces and untrusted input.
- No custom cryptography and no secrets in source control.
- Pinned dependencies and documented third-party usage.
- Clear module boundaries and explicit error handling.
- Deterministic testing with regression coverage for bugs.
- Required documentation updates for architecture, security, decisions, and dependencies.

## 6. Definition of Done
A task is not done until:

1. Code changes are complete.
2. Tests are executed and logged.
3. Documentation updates are logged.
4. Release gates are checked or explicitly marked as not applicable with reason.

