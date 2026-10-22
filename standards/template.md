# Engineering Standard

---
id: STD-####
title:
status: draft
version: 1.0
taxonomy: DDDD.SSSS
primary-classification:
reusable-classification:
owners: []
related-adrs: []
related-rfcs: []
supersedes: null
superseded-by: null
---

**Standard Name:**  
**Version:**  
**Owner(s):**  
**Contributor(s):**  
**Last Updated:**  
**Related ADRs:**  
**Related RFCs:**  
**Related Jira Items / Documentation:**  
**Taxonomy:** `DDDD.SSSS`
**Primary Classification:**
**Reusable Classification:** Optional

---

# Table of Contents
1. Purpose  
2. Scope  
3. Requirements  
4. Implementation Guidance  
5. Examples  
6. Exceptions  
7. Version History  
8. Conventions  

---

# 1. Purpose
Explain *why* this Standard exists and what problem it solves.

Examples:
- Ensure consistent tagging across all cloud resources  
- Define required Terraform module structure  
- Establish DNS naming conventions  
- Standardize firewall request requirements  

This section should be concise and focused on the operational need.

---

# 2. Scope

### In Scope
List the systems, teams, platforms, or environments where this Standard applies.

Examples:
- All AWS accounts  
- All production and non‑production environments  
- All Terraform-managed infrastructure  

### Out of Scope
List anything explicitly not covered by this Standard.

Examples:
- Legacy systems pending migration  
- Vendor-managed SaaS platforms  

---

# 3. Requirements
This is the authoritative list of rules engineers **MUST** follow.

Use RFC 2119 language (MUST, SHOULD, MAY, etc.).

Examples:
- All AWS resources **MUST** include the following tags: `Owner`, `CostCenter`, `Environment`.  
- Terraform modules **SHOULD** be sourced from the internal registry.  
- DNS names **MUST** follow the pattern `<env>.<region>.<service>.company.com`.  
- Firewall requests **MUST** include justification and expiration.  

Keep this section crisp and unambiguous.

---

# 4. Implementation Guidance
Provide practical guidance to help teams apply the Standard.

Examples:
- How to structure Terraform modules  
- How to apply required tags in IaC  
- How to request firewall rules  
- How to configure IAM roles  

This section is **informational**, not normative.

---

# 5. Examples
Include examples that clarify the Standard.

Examples:
- Correct and incorrect tagging  
- Sample Terraform module layout  
- DNS naming examples  
- Example firewall request  

Engineers should be able to follow the Standard without guesswork.

---

# 6. Exceptions
Describe how teams can request exceptions and under what circumstances they may be granted.

Include:
- Required justification  
- Approval process  
- Expiration requirements  
- Documentation expectations  

Standards should be firm, but not inflexible.

---

# 7. Version History

| Version | Date | Author | Description |
|---------|------|--------|-------------|
| v1.0 | YYYY‑MM‑DD | Name | Initial release |
| v1.1 | YYYY‑MM‑DD | Name | Updated required tags |
| v1.2 | YYYY‑MM‑DD | Name | Added examples |

Standards are living documents — versioning is critical.

---

# 8. Conventions
The key words **“MUST”, “MUST NOT”, “REQUIRED”, “SHALL”, “SHALL NOT”, “SHOULD”, “SHOULD NOT”, “RECOMMENDED”, “MAY”,** and **“OPTIONAL”** in this document are to be interpreted as described in [RFC 2119](https://www.rfc-editor.org/rfc/rfc2119).
