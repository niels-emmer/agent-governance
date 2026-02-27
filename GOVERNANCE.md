
# **0. Purpose**

This charter defines mandatory engineering principles for repositories developed with human and agentic assistance.

Objectives:

- Secure by design
- Verifiable provenance
- Architectural integrity
- Operational efficiency
- Simplicity over sophistication
- Reproducibility and auditability
    
This charter is normative. Deviations require documented justification.

---

# **1. Security by Design**

Aligned with:

- NIST SP 800-218 (SSDF)    
- OWASP ASVS
- SLSA framework
    
## **1.1 Threat Modeling**

Required when:

- Exposing network interfaces    
- Handling authentication or secrets
- Processing untrusted input
- Persisting data
    
Threat models must identify:

- Assets
- Trust boundaries
- Entry points
- Abuse cases
- Mitigations
    
STRIDE is recommended.

## **1.2 Input Handling**

- All external input is untrusted.    
- Validation occurs at boundaries.
- Reject by default.
- Use allowlists where feasible.
    
## **1.3 Cryptography**

- No custom cryptographic algorithms.
- Use only standard libraries.
- Algorithms must be standards-backed (NIST or RFC).
- Keys must be stored in a secrets manager or OS keystore.
- No secrets in source control.
    
## **1.4 Dependency Security**

- Dependencies pinned to exact versions.
- Lockfiles committed.
- Automated CVE scanning in CI.
- SBOM generated per build.
- High severity vulnerabilities block release unless risk-accepted in writing.


## **1.5 Build Integrity**

- Builds must be reproducible or verifiable.    
- Provenance metadata generated where feasible.
- Align with SLSA Level 2 minimum.
    

---

# **2. Provenance and Attribution**

  

Aligned with:

- SLSA
- IEEE Software Engineering Code of Ethics
- Reproducible Builds
    

  

## **2.1 Source Authority**

  

Permitted normative references:

- RFCs
- Official vendor documentation
- NIST publications
- ISO standards
- Language specifications
    

  

Non-authoritative sources:

- Blogs
- Forums
- AI outputs
    

  

These require independent verification.

  

## **2.2 Third-Party Code**

- Pinned by commit hash or exact version.
- License verified and compatible.
- Documented in THIRD_PARTY.md.
- Modifications clearly marked.
    

  

## **2.3 LLM-Generated Code**

- Treated as untrusted until reviewed.
- Security-relevant logic must cite authoritative source.
- No unverifiable cryptographic or protocol logic.
    

---

# **3. Architecture Principles**

  

Aligned with:

- ISO/IEC/IEEE 42010
- ISO 25010 quality model
- Clean Architecture
- Twelve-Factor (if service-based)
    

## **3.1 Separation of Concerns**

- Business logic isolated from I/O.    
- Clear module boundaries.
- Explicit interfaces.
    

  

## **3.2 Determinism**

- Prefer pure functions.
- Minimize shared mutable state.
- Avoid hidden side effects.
    

  

## **3.3 Observability**

- Structured logging.
- Explicit error handling.
- No silent failures.
    

  

## **3.4 Configuration**

- Environment-based configuration.
- No environment-specific code branches.
- No secrets in configuration files.
    

---

# **4. Efficiency and Complexity Discipline**

  

## **4.1 Simplicity First**

- Prefer standard library.
- Prefer fewer dependencies.
- Avoid abstraction without demonstrated need.
- Avoid premature optimization.
    

  

## **4.2 Complexity Control**

- Cyclomatic complexity kept low.
- Large functions refactored.
- O(n²) algorithms require justification.
- Benchmark before optimizing.
    

  

## **4.3 Resource Discipline**

- Memory proportional to problem size.
- No unbounded growth structures.
- Explicit cleanup of resources.
    

---

# **5. Rule of Least Power**

  

Aligned with W3C TAG principle.

- Use the least powerful language/tool sufficient.
- Prefer declarative over imperative where viable.
- Prefer configuration over code when safe.
- Avoid introducing distributed systems unnecessarily.
    

---

# **6. Testing and Verification**

  

## **6.1 Required Tests**

- Unit tests for business logic.
- Edge-case validation tests.
- Security tests for authentication/authorization paths.
    

  

## **6.2 Deterministic Tests**

- No dependency on wall clock unless controlled.
- No external network dependency in unit tests.
- Use mocks at system boundaries.
    

  

## **6.3 Regression Safety**

- Bugs must be accompanied by regression tests.
- Public interfaces require contract tests.
    

---

# **7. Documentation Requirements**

  

Each repository must contain:

- README.md
- ARCHITECTURE.md
- SECURITY.md
- THIRD_PARTY.md
- DECISIONS.md (architecture decision records)
    

  

Security-sensitive design decisions must cite authoritative references.

---

# **8. Change Control**

  

Changes that require written justification:

- New dependency
- New external interface
- Cryptography changes
- Data model changes
- Introduction of concurrency or distribution
    

  

Justification must include:

- Risk assessment
- Alternatives considered
- Simpler rejected option and reason
    

---

# **9. Prohibited Practices**

- Hardcoded secrets
- Custom cryptography
- Implicit global state
- Silent exception suppression
- Unpinned dependencies
- Security by obscurity
    

---

# **10. Release Gate Criteria**

  

Release requires:

- Passing CI
- Dependency scan clean or risk accepted
- Updated documentation
- Updated SBOM
- No critical open vulnerabilities
- Reproducible build artifacts
    

---

# **11. Guiding Principles Summary**

1. Secure by design.
2. Cite authoritative sources.
3. Prefer simplicity over sophistication.
4. Make state and boundaries explicit.
5. Optimize only with evidence.
6. Make builds reproducible.
7. Treat generated code as untrusted until verified.
    

---

# **References**


NIST SP 800-218 (SSDF): https://csrc.nist.gov/publications/detail/sp/800-218/final
  

OWASP ASVS: https://owasp.org/www-project-application-security-verification-standard/

  

SLSA Framework: https://slsa.dev

  

ISO 25010 Overview: https://iso25000.com/index.php/en/iso-25000-standards/iso-25010

  

W3C Rule of Least Power: https://www.w3.org/2001/tag/doc/leastPower.html

  

IEEE Software Engineering Code of Ethics: https://www.computer.org/education/code-of-ethics
