# Workflow: Idea to Deployment

## Phase 1: Intake and Framing
Inputs:
- Problem statement
- Expected user impact
- Constraints and assumptions

Actions:
1. Define scope and non-goals.
2. Identify whether threat modeling is required.
3. Identify documentation and testing implications.

Outputs:
- Short task statement in `records/decision-log.md`.

## Phase 2: Design and Planning
Actions:
1. Define module boundaries and interfaces.
2. Evaluate dependency and data model impact.
3. Identify risks and alternatives.

Outputs:
- Design decision entries in `records/decision-log.md`.
- If architecture-level, update `DECISIONS.md` and `ARCHITECTURE.md`.

## Phase 3: Implementation
Actions:
1. Implement smallest viable change first.
2. Keep business logic separate from I/O.
3. Maintain explicit error paths and deterministic behavior.

Outputs:
- Incremental code changes tied to logged decisions.

## Phase 4: Verification
Actions:
1. Run unit and edge-case tests.
2. Run security-related tests for authn/authz or boundary validation.
3. Add regression tests for fixed bugs.

Outputs:
- Test evidence in `records/testing-log.md`.

## Phase 5: Documentation
Actions:
1. Update repository docs affected by the change.
2. Update third-party references and decision records.
3. Capture operational notes needed for maintainers.

Outputs:
- Documentation evidence in `records/documentation-log.md`.

## Phase 6: Release Readiness
Actions:
1. Confirm release gates (CI, vulnerabilities, SBOM, docs, reproducibility).
2. Document risk acceptance if any gate is excepted.
3. Record final readiness status.

Outputs:
- Release evidence in `records/release-log.md`.

