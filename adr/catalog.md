# **Architecture Decision Records (ADR) Registry**

This is the authoritative registry for all current and historical ADRs. It
provides the next available permanent ID and supports duplicate detection,
relationship checks, taxonomy validation, and links to the full documents.

| **ID** | **Title**                          | **Description**                                                                 | **Taxonomy** | **Status**   | **Last Updated** |
|--------|------------------------------------|---------------------------------------------------------------------------------|--------------|--------------|------------------|
| ADR-0001 | Adopt Terraform | Decision to standardize on Terraform for infrastructure provisioning. | `9200.2400` | Accepted | 2026-03-01 |
| ADR-0002 | Use REST APIs | Decision to use REST APIs for inter-service communication. | `6300.2400` | Superseded | 2025-12-15 |

---

### **Key Fields**
- **ID**: A permanent identifier for the ADR (e.g., ADR-0001).
- **Taxonomy**: The shared architecture classification for the ADR.
- **Title**: The name of the ADR, linked to the full document.
- **Description**: A short summary of what the ADR covers.
- **Status**: Indicates whether the ADR is "Accepted," "Rejected," "Draft," or "Superseded."
- **Last Updated**: The date the ADR was last modified.

---

### **How to Use This Catalog**
1. **Find an ADR**: Use the table above to locate the ADR you need.
2. **View Details**: Follow the document link when one is present.
3. **Propose Changes**: To update or supersede an ADR, submit a new ADR or RFC.

Add every new ADR to this registry; do not create a separate index.
