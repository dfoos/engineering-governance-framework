# **Example Governance Flow: Virtual Application Hosting Solution**

This document provides a full end‑to‑end example of how an engineering proposal moves through our governance model using **RFC → ADR → Standard**.  

The example focuses on selecting and implementing a **virtual application hosting solution** for customer‑facing workloads.

This illustrates:
- How an RFC is used to compare options and gather feedback  
- How an ADR documents the architectural decision  
- How a Standard defines the ongoing rules for implementation  

---

# **1. Example RFC — Evaluating Virtual Application Hosting Platforms**

```markdown
# RFC-0001: Evaluation of Virtual Application Hosting Platforms

**Owner:** Infrastructure Architecture  
**Contributors:** Cloud Engineering, EUC Engineering, Security  
**Related To:** Future ADR on Virtual Application Hosting  
**Urgency:** High  
**Date Created:** 2026-03-23  
**Status:** In Review
**Proposed Taxonomy:** `6200.2400` (Application Platforms / Design)

---

# 1. Summary
We need a scalable, multi‑region virtual application hosting platform to support customer‑facing workloads. Two primary options have been identified:

- **Citrix Cloud Virtual Apps**
- **Amazon WorkSpaces Application Manager (WAM)**

This RFC evaluates both options to gather feedback before finalizing an architectural decision.

---

# 2. Scope

### In Scope
- Application virtualization platforms  
- Multi‑region deployment considerations  
- Integration with AWS, Azure, and VMware  
- Operational management and automation capabilities  

### Out of Scope
- Full desktop virtualization (VDI)  
- Licensing procurement  
- Legacy on‑prem Citrix environments  

---

# 3. Details
We require a platform that supports:
- Automated provisioning  
- Multi‑region high availability  
- Strong application lifecycle management  
- Integration with existing identity and security controls  
- Consistent user experience across cloud providers  

---

# 4. Options

## Option 1 — Citrix Cloud Virtual Apps
### Comments
Citrix Cloud provides mature application virtualization capabilities, robust environment management, and automated provisioning via Machine Creation Services (MCS) and WEM.

### Advantages
- Mature, battle‑tested platform  
- Strong multi‑region support  
- Automated provisioning and scaling  
- WEM provides granular performance optimization  
- Broad support across AWS, Azure, and VMware  

### Disadvantages 
- Requires Cloud Connectors in each region  
- More complex initial setup  

---

## Option 2 — Amazon WorkSpaces Application Manager (WAM)
### Comments
AWS WAM provides application streaming capabilities but lacks the maturity and operational tooling of Citrix.

### Advantages
- Native AWS integration    
- Simpler initial deployment  

### Disadvantages
- Limited multi‑cloud support  
- Less mature application lifecycle management  
- No equivalent to WEM for performance tuning  
- Limited automation capabilities  

---

# 5. Conventions
The key words **“MUST”, “SHOULD”, “MAY”** etc. are interpreted as described in RFC 2119.

```

---

# **2. Example ADR — Selection of Citrix Cloud for Virtual Application Hosting**

```markdown
# ADR-0001: Adoption of Citrix Cloud Virtual Apps for Application Hosting

**Date:** 2026-03-30  
**Status:** Accepted  
**Owner(s):** Infrastructure Architecture  
**Contributors:** Cloud Engineering, EUC Engineering  
**Target Audience:** Platform Engineering, EUC, Cloud Teams  
**Linked RFCs:** RFC-0001  
**Taxonomy:** `6200.2400` (Application Platforms / Design)

---

# 1. Summary
After evaluating Citrix Cloud Virtual Apps and Amazon WorkSpaces Application Manager, we have selected **Citrix Cloud** as the standard platform for hosting virtual applications across all customer‑facing regions.

This decision is based on Citrix’s maturity, automation capabilities, multi‑region support, and integration with WEM for performance optimization.

---

# 2. Decision
We will deploy **Citrix Cloud Virtual Apps** using a **highly available pod architecture** in each customer‑facing region.  

We will use:
- **Citrix Cloud Connectors** deployed redundantly  
- **Citrix WEM** for performance and policy management  
- **Machine Creation Services (MCS)** for automated provisioning  
- **VDAs** deployed in AWS, Azure, or VMware depending on customer region  

---

# 3. Scope

### In Scope
- All customer‑facing virtual application workloads  
- All cloud regions where we host customer environments  
- AWS, Azure, and VMware as supported hypervisors  

### Out of Scope
- Full desktop virtualization (VDI)  
- Legacy on‑prem Citrix farms  
- Non‑customer‑facing internal applications  

---

# 4. Consequences

### Positive
- Mature, stable application hosting platform  
- Automated provisioning reduces operational overhead  
- Consistent architecture across all regions  
- WEM improves performance and user experience  

### Negative
- Requires ongoing management of Cloud Connectors  
- More complex initial deployment  

### Neutral
- Requires updates to existing automation pipelines  

---

# 5. Changelog

| When | Who | What |
|------|------|------|
| 2026‑03‑30 | Infrastructure Architecture | Initial ADR created |
| 2026‑04‑02 | EUC Engineering | Added WEM configuration details |

---

# 6. Conventions
The key words **“MUST”, “SHOULD”, “MAY”** etc. are interpreted as described in RFC 2119.

```

---

# **3. Example Standard — Citrix Cloud Naming & Sizing Standard**

```markdown
# Citrix Cloud Virtual Apps Standard

**Version:** 1.0  
**Owner(s):** EUC Engineering  
**Contributors:** Cloud Engineering, Infrastructure Architecture  
**Last Updated:** 2026-04-05  
**Related ADRs:** ADR-0001  
**Related RFCs:** RFC-0001  
**Taxonomy:** `6200.2400` (Application Platforms / Design)

---

# 1. Purpose
This Standard defines naming conventions, sizing requirements, and catalog structures for Citrix Cloud Virtual Apps deployments across AWS, Azure, and VMware.

---

# 2. Scope

### In Scope
- Cloud Connectors  
- VDAs  
- Machine Catalogs  
- Delivery Groups  
- Published Applications  

### Out of Scope
- Citrix VDI  
- On‑prem Citrix environments  

---

# 3. Requirements

### Cloud Connector Naming
- MUST follow: `CTX-CC-<region>-<seq>`  
  - Example: `CTX-CC-us-east-01`

### VDA Naming
- MUST follow: `CTX-VDA-<region>-<catalog>-<seq>`  
  - Example: `CTX-VDA-us-west-apps-03`

### Machine Catalog Naming
- MUST follow: `MC-<region>-<workload>`  
  - Example: `MC-eu-central-finance`

### Delivery Group Naming
- MUST follow: `DG-<region>-<workload>`  
  - Example: `DG-us-east-hr`

### Published Application Naming
- MUST match the application’s official product name  
  - Example: `Adobe Acrobat Pro`

### Sizing Requirements
- **AWS:**  
  - Standard VDA: `m6i.large`  
  - High‑performance VDA: `m6i.xlarge`  
- **Azure:**  
  - Standard VDA: `D4s_v5`  
  - High‑performance VDA: `D8s_v5`  
- **VMware:**  
  - Standard VDA: 2 vCPU / 8 GB RAM  
  - High‑performance VDA: 4 vCPU / 16 GB RAM  

---

# 4. Implementation Guidance
- Machine Catalogs SHOULD group workloads by region and application type  
- Delivery Groups SHOULD align with customer‑facing business units  
- WEM policies SHOULD be applied consistently across all regions  

---

# 5. Examples

### Example Machine Catalog
`MC-us-east-analytics`

### Example Delivery Group
`DG-eu-west-operations`

### Example VDA
`CTX-VDA-us-east-analytics-07`

---

# 6. Exceptions
Exceptions MUST be approved by EUC Engineering and Infrastructure Architecture.  
Temporary exceptions MUST include an expiration date.

---

# 7. Version History

| Version | Date | Author | Description |
|---------|------|--------|-------------|
| 1.0 | 2026‑04‑05 | EUC Engineering | Initial release |

---

# 8. Conventions
The key words **“MUST”, “SHOULD”, “MAY”** etc. are interpreted as described in RFC 2119.

```

---

# **Summary of the Example**

This example demonstrates the full lifecycle of a technical decision:

### **1. RFC — Exploration**
We compared Citrix Cloud vs. Amazon WorkSpaces Application Manager.  
Citrix was preferred due to maturity, automation, and multi‑region capabilities.

### **2. ADR — Decision**
We formally decided to adopt Citrix Cloud Virtual Apps with WEM and a highly available pod architecture.

### **3. Standard — Implementation Rules**
We defined naming conventions, sizing requirements, and catalog structures to ensure consistent deployments across AWS, Azure, and VMware.

This is exactly how the governance model is intended to work:  
**RFC → ADR → Standard → Implementation**

---
