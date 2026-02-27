# Core Principles

Source: distilled from `GOVERNANCE.md` (sync date 2026-02-27)

## 1. Security by Design
- Threat model when adding interfaces, auth/secrets handling, untrusted input, or persistence.
- Treat all external input as untrusted and validate at boundaries.
- Reject by default and use allowlists where practical.
- Use only standards-backed cryptography from standard libraries.
- Store keys/secrets in managed stores, never in source control.
- Pin dependencies, commit lockfiles, scan for CVEs, generate SBOMs.

## 2. Provenance and Trust
- Prefer authoritative sources: RFCs, vendor docs, NIST, ISO, language specs.
- Treat blogs, forums, and AI outputs as non-authoritative unless verified.
- Pin third-party code by version/hash and verify licenses.
- Treat generated code as untrusted until reviewed and tested.

## 3. Architecture and Determinism
- Isolate business logic from I/O.
- Keep boundaries explicit and interfaces clear.
- Prefer pure functions and minimize shared mutable state.
- Use structured logs and explicit error handling.
- Keep environment configuration outside code; no secrets in config files.

## 4. Complexity and Efficiency
- Choose simplicity first: standard library, fewer dependencies, minimal abstraction.
- Avoid premature optimization.
- Justify high-complexity algorithms and benchmark before optimizing.
- Avoid unbounded memory growth and clean up resources explicitly.

## 5. Testing and Verification
- Unit tests for business logic and edge conditions.
- Security tests for authn/authz paths.
- Deterministic tests: no uncontrolled clock or network dependencies.
- Add regression tests for fixed defects.

## 6. Documentation and Change Control
- Keep `README.md`, `ARCHITECTURE.md`, `SECURITY.md`, `THIRD_PARTY.md`, and `DECISIONS.md` current.
- Document risky changes: new dependencies, interfaces, crypto, data model, concurrency/distribution.
- Include risk, alternatives, and simpler rejected option.

## 7. Release Gates
- CI passing.
- Dependency scan clean or risk accepted in writing.
- Documentation updated.
- SBOM updated.
- No critical open vulnerabilities.
- Build artifacts reproducible/verifiable.

