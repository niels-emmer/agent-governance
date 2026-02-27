# Execution Checklists

## A. Task Start Checklist
- Read `core-principles.md`.
- Read `workflow.md`.
- Confirm if threat modeling is required.
- Log initial scope in `records/decision-log.md`.

## B. Implementation Checklist
- Business logic isolated from I/O.
- External inputs validated at boundaries.
- No secrets introduced in code/config.
- Dependencies pinned and justified if new.
- Error handling explicit; no silent failure paths.

## C. Testing Checklist
- Unit tests added or updated.
- Edge cases covered.
- Security tests run when authn/authz or trust boundaries change.
- Regression tests added for bug fixes.
- Results logged in `records/testing-log.md`.

## D. Documentation Checklist
- `README.md` updated if behavior/setup changed.
- `ARCHITECTURE.md` updated if structure changed.
- `SECURITY.md` updated if security posture changed.
- `THIRD_PARTY.md` updated for dependency changes.
- `DECISIONS.md` updated for design choices.
- Changes logged in `records/documentation-log.md`.

## E. Release Checklist
- CI passing.
- Dependency scan reviewed.
- SBOM generated/updated.
- No critical vulnerabilities, or written risk acceptance.
- Reproducible/verifiable build status noted.
- Results logged in `records/release-log.md`.

