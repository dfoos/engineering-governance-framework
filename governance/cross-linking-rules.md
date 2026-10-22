# Cross-Linking Rules

This document defines the rules for cross-linking governance artifacts to ensure clarity, traceability, and consistency across the repository.

---

## Linking RFCs to ADRs

- RFCs must include references to any ADRs that influenced their creation or implementation.
- Use the following format for links:
  - **Example**: "This RFC builds upon ADR-0001: Terraform Standardization."
- Place the links in the "Related Artifacts" section of the RFC.
- RFCs MAY include `proposed-taxonomy`, but that value classifies only a resulting ADR or Standard.

---

## Linking ADRs to Standards

- ADRs must reference any Standards that they establish or modify.
- Use the following format for links:
  - **Example**: "This ADR defines STD-0001: Security Baseline Standard v1.0."
- Place the links in the "Decision Details" or "References" section of the ADR.
- ADRs MUST include the shared taxonomy and may share a value with other ADRs or Standards.

---

## Referencing Superseded Artifacts

- Superseded artifacts must include a reference to their replacement.
- Use the following format for links:
  - **Example**: "This artifact has been superseded by ADR-0002: Updated Terraform Practices."
- Place the reference at the top of the artifact, clearly marked as "Superseded."

---

## Citing Governing ADRs in Standards

- Standards must cite the ADRs that govern their creation or updates.
- Use the following format for links:
  - **Example**: "This Standard is governed by ADR-0003: Security Baseline Definition."
- Place the citation in the "Governance" or "References" section of the Standard.
- Standards MUST include the shared taxonomy and should link the ADR that provides the governing rationale when one exists.

---

Adherence to these cross-linking rules ensures that governance artifacts remain interconnected and traceable throughout their lifecycle.
