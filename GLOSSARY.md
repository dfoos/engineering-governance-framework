# **Glossary of Terms**

This glossary defines key terms used throughout the Engineering Governance Framework. It ensures consistent understanding and usage of terminology across teams.

### **Key Terms**

- **ADR (Architecture Decision Record)**: An immutable record of an architectural decision made at a specific point in time. Captures the context, options considered, and reasoning behind the decision.

- **RFC (Request for Comment)**: A proposal used to gather feedback, alignment, and early visibility before committing to a direction. RFCs are temporary and may lead to ADRs or updates to Standards.

- **Standard**: A living document that defines current best practices, required patterns, and operational rules. Standards evolve over time and are versioned.

- **Taxonomy**: The shared architecture classification used by ADRs and Standards to describe where a record belongs. Taxonomy values are not identifiers and are not required to be unique.

- **Primary classification**: The durable architecture area that owns an ADR or Standard, such as Cloud Foundations or Data Platforms.

- **Reusable classification**: An optional cross-cutting concern, such as Naming, Design, Security, or Testing and Validation, appended to a primary classification.

- **Proposed taxonomy**: Optional RFC metadata suggesting the classification for an ADR or Standard that may result from the RFC. It does not classify the RFC.

- **Registry**: The authoritative structured index for one document type. Registries provide the next available ID and support duplicate, relationship, and taxonomy validation.

- **ARB (Architecture Review Board)**: A governance body responsible for reviewing and approving ADRs to ensure cross-domain alignment and architectural consistency.

- **Standards Committee**: A governance body responsible for maintaining and updating Standards to ensure consistency and alignment across the organization.

- **Lifecycle**: The stages an artifact (e.g., RFC, ADR, Standard) goes through, from creation to archival or supersession.

- **Supersede**: The process of replacing an existing artifact with a new one that reflects updated decisions or practices.

- **Deprecate**: The process of marking an artifact as outdated or no longer recommended for use, often as a precursor to archival.

- **Archive**: The process of retiring an artifact, removing it from active use while preserving it for historical reference.

- **Template**: A predefined structure or format used to create new artifacts (e.g., RFC Template, ADR Template).

- **Catalog**: A structured index of artifacts (e.g., Standards Catalog, ADR Catalog) that provides metadata and links to the full documents.

- **Label**: Optional metadata used for discovery, such as a technology or team name. Labels do not replace the taxonomy and are not a required classification system.

---

### **How to Use This Glossary**
1. **Understand Terms**: Refer to this glossary whenever you encounter unfamiliar terms.
2. **Ensure Consistency**: Use these definitions when creating or updating artifacts.
3. **Propose Additions**: Submit an RFC to propose new terms or updates to existing definitions.
