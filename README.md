# agent-governance

## Purpose
This repository defines a governance baseline for engineering work and a simple operational memory system for human and agent collaboration.

It is designed to ensure that day-to-day implementation follows explicit principles for security, provenance, architecture, testing, documentation, and release readiness.

## Repository Contents
- `GOVERNANCE.md`: canonical policy charter and engineering principles.
- `AGENTS.md`: operational contract for agents, including startup routine and memory update protocol.
- `docs/README.md`: docs index.
- `docs/memory/`: simple memory system used during delivery.
- `docs/memory/core-principles.md`: distilled governance rules for implementation.
- `docs/memory/workflow.md`: idea-to-deployment execution flow.
- `docs/memory/checklists.md`: task, testing, documentation, and release checklists.
- `docs/memory/records/`: durable evidence logs (`decision`, `testing`, `documentation`, `release`).

## How It Works
1. `GOVERNANCE.md` is the policy source of truth.
2. Governance rules are transferred into `docs/memory/` for operational use.
3. Agents execute work using memory docs and keep evidence logs current.
4. If governance and memory diverge, memory is updated first and the sync is logged.

## Current Scope
This repository currently contains governance and process scaffolding only. It does not include application/runtime code.

