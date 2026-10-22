# **Engineering Standards Registry**

This is the authoritative registry for all current and historical Standards.
It provides the next available permanent ID and supports duplicate detection,
relationship checks, taxonomy validation, version tracking, and links to the
full documents.

| **ID** | **Title**                          | **Description**                                                                 | **Version** | **Taxonomy** | **Status**   | **Last Updated** |
|--------|------------------------------------|---------------------------------------------------------------------------------|-------------|--------------|--------------|------------------|
| STD-0001 | Tagging Standard | Defines required resource metadata and enforcement mechanisms. | 1.2 | `4300.2200` | Active | 2026-03-01 |
| STD-0002 | Terraform Module Standard | Specifies module structure, backend configuration, and CI/CD patterns. | 1.0 | `9200.2300` | Active | 2026-02-15 |
| STD-0003 | DNS Naming Standard | Details the hierarchical DNS naming schema and allowed characters. | 1.1 | `7100.2100` | Active | 2026-01-20 |
| STD-0004 | Firewall Rules Standard | Outlines least-privilege principles for firewall rules and request requirements. | 2.0 | `7300.2700` | Deprecated | 2025-12-10 |
| STD-0005 | IAM and RBAC Standard | Defines IAM and RBAC models, including roles, permissions, and security baselines. | 1.3 | `3200.2700` | Active | 2026-03-10 |

---

### **Key Fields**
- **ID**: A permanent identifier for the Standard (e.g., STD-0001).
- **Taxonomy**: The shared architecture classification for the Standard.
- **Title**: The name of the standard, linked to the full document.
- **Description**: A short summary of what the standard covers.
- **Version**: The current version of the standard.
- **Status**: Indicates whether the standard is "Active," "Deprecated," or "Draft."
- **Last Updated**: The date the standard was last modified.

---

### **How to Use This Catalog**
1. **Find a Standard**: Use the table above to locate the standard you need.
2. **View Details**: Follow the document link when one is present.
3. **Propose Changes**: To update or deprecate a standard, submit an RFC or ADR.

Add every new Standard to this registry; do not create a separate index.
