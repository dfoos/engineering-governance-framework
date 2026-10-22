# Cross-Linking Rules

This document defines the rules for cross-linking governance artifacts to ensure clarity, traceability, and consistency across the repository.

---

## Linking RFCs to ADRs

- RFCs must include references to any ADRs that influenced their creation or implementation.
- Use the following format for links:
  - **Example**: "This RFC builds upon [ADR 001: Terraform Standardization](../adr/adr-001-terraform-standardization.md)."
- Place the links in the "Related Artifacts" section of the RFC.
- RFCs MAY include `proposed-taxonomy`, but that value classifies only a resulting ADR or Standard.

---

## Linking ADRs to Standards

- ADRs must reference any Standards that they establish or modify.
- Use the following format for links:
  - **Example**: "This ADR defines the [Security Baseline Standard v1.0](../standards/standard-security-baseline-v1.0.md)."
- Place the links in the "Decision Details" or "References" section of the ADR.
- ADRs MUST include the shared taxonomy and may share a value with other ADRs or Standards.

---

## Referencing Superseded Artifacts

- Superseded artifacts must include a reference to their replacement.
- Use the following format for links:
  - **Example**: "This artifact has been superseded by [ADR 002: Updated Terraform Practices](../adr/adr-002-updated-terraform-practices.md)."
- Place the reference at the top of the artifact, clearly marked as "Superseded."

---

## Citing Governing ADRs in Standards

- Standards must cite the ADRs that govern their creation or updates.
- Use the following format for links:
  - **Example**: "This Standard is governed by [ADR 003: Security Baseline Definition](../adr/adr-003-security-baseline-definition.md)."
- Place the citation in the "Governance" or "References" section of the Standard.
- Standards MUST include the shared taxonomy and should link the ADR that provides the governing rationale when one exists.

---

Adherence to these cross-linking rules ensures that governance artifacts remain interconnected and traceable throughout their lifecycle.
