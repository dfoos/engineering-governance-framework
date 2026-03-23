# **Engineering Governance Framework**

This repository defines how we manage architectural decisions, engineering standards, and cross‑team technical proposals. It exists to bring clarity, consistency, and velocity to how we design, build, and operate infrastructure across the organization.

Over time, this repo will become the single source of truth for:
- **RFCs** (Requests for Comment)  
- **ADRs** (Architecture Decision Records)  
- **Engineering Standards**  
- **ARB workflows**  
- **Standards Committee workflows**  
- **Templates, examples, and governance guidance**

The goal is simple:  
**Make it easy for teams to understand how decisions are made, what standards they must follow, and how to propose changes without navigating a maze of Confluence pages and tribal knowledge.**

---

# **Why This Repository Exists**
Our current process relies heavily on Confluence and has grown organically over time. The result is predictable:  
- Hundreds of RFCs and ADRs scattered across spaces  
- Slow ARB approvals  
- Duplicate or conflicting decisions  
- No authoritative standards catalog  
- Teams reinventing the wheel or re‑proposing decisions that were already made  

This repo consolidates everything into a version‑controlled, transparent, and reviewable workflow.

---

# **How RFCs, ADRs, and Standards Fit Together**
These three artifacts serve different purposes. Treating them as interchangeable is what created the sprawl we’re cleaning up.

## **RFC — Request for Comment**
RFCs are **proposals**.  
They are used when a team wants feedback, alignment, or early visibility before committing to a direction.

Use an RFC when:
- You’re exploring options  
- You want cross‑team input  
- You’re proposing something that *might* become an ADR or Standard  
- You want to socialize an idea before investing heavily  

RFCs are **temporary**.  
Once resolved, they either:
- Become an ADR  
- Update a Standard  
- Or are closed with no further action  

---

## **ADR — Architecture Decision Record**
ADRs are **immutable records of architectural decisions**.

An ADR captures:
- The problem  
- The options considered  
- The decision  
- The reasoning  
- The consequences  

ADRs explain **why** we made a decision at a point in time.  
They do **not** define ongoing rules or operational guidance.

Once accepted, an ADR is frozen.  
If the decision changes, a new ADR supersedes the old one.

Use an ADR when:
- You’re making a long‑term architectural choice  
- The decision impacts multiple teams  
- The decision introduces or retires a major pattern, platform, or technology  
- You need a durable historical record  

---

## **Standards — Living Engineering Rules**
Standards are **living documents** that define how we operate today.

They represent:
- Current best practices  
- Required patterns  
- Naming conventions  
- Tagging rules  
- Terraform module requirements  
- Networking and DNS rules  
- IAM and RBAC models  
- Security baselines  

Standards evolve as technology and practices evolve.  
They are versioned, curated, and updated without requiring a new ADR unless the underlying architecture changes.

Use a Standard when:
- You’re defining “how we do things here”  
- You’re documenting rules teams must follow  
- You’re updating guidance as tools or platforms evolve  

---

# **How They Work Together (Examples)**

### **Tagging**
- **ADR:** “We will adopt a mandatory tagging strategy for all cloud resources.”  
- **Standard:** Defines the exact required tags, formats, and enforcement mechanisms.

### **Terraform**
- **ADR:** “All infrastructure provisioning will standardize on Terraform.”  
- **Standard:** Defines module structure, backend configuration, naming rules, and required CI/CD patterns.

### **DNS**
- **ADR:** “We will use a hierarchical DNS naming model across all environments.”  
- **Standard:** Defines the exact naming schema, allowed characters, and examples.

### **Firewall Access**
- **ADR:** “Firewall rules must follow least‑privilege principles.”  
- **Standard:** Defines request requirements, allowed ports, expiration rules, and automation.

The ADR sets the direction.  
The Standard defines the implementation.

---

# **Repository Structure**

- [/README.md](README.md) — This landing page  
- [/adr/](adr) — Architecture Decision Records  
    - [/adr/template.md](adr/template.md)  
    - [/adr/index.md](adr/index.md)  
- [/arb/](arb) — Architecture Review Board workflows & roles  
    - [/arb/workflow.md](arb/workflow.md)  
- [/examples/](examples) — Example governance documents  
    - [/examples/virtual-app-hosting-example.md](examples/virtual-app-hosting-example.md)  
- [/governance/](governance) — Governance overview docs  
    - [/governance/overview.md](governance/overview.md)  
    - [/governance/adr-lifecycle.md](governance/adr-lifecycle.md)  
    - [/governance/arb-membership.md](governance/arb-membership.md)  
    - [/governance/standards-committee-membership.md](governance/standards-committee-membership.md)  
    - [/governance/cross-linking-rules.md](governance/cross-linking-rules.md)  
    - [/governance/superseding-deprecating.md](governance/superseding-deprecating.md)  
    - [/governance/archive-conventions.md](governance/archive-conventions.md)  
- [/guidance/](guidance) — Decision guidance  
    - [/guidance/do-i-need-a-rfc.md](guidance/do-i-need-a-rfc.md)  
    - [/guidance/do-i-need-a-standard.md](guidance/do-i-need-a-standard.md)  
    - [/guidance/do-i-need-an-adr.md](guidance/do-i-need-an-adr.md)  
- [/rfc/](rfc) — Requests for Comment  
    - [/rfc/template.md](rfc/template.md)  
    - [/rfc/index.md](rfc/index.md)  
- [/standards/](standards) — Engineering Standards (living documents)  
    - [/standards/template.md](standards/template.md)  
    - [/standards/index.md](standards/index.md)  
- [/standards-committee/](standards-committee) — Standards Committee workflows & roles  
    - [/standards-committee/workflow.md](standards-committee/workflow.md)  
- [/tags/](tags) — Tagging system for artifacts  
    - [/tags/README.md](tags/README.md)  
    - [/tags/tags.md](tags/tags.md)  
    - [/tags/standard.md](tags/standard.md)  

This structure will evolve as we migrate content from Confluence and formalize our governance model.

---

# **ARB and Standards Committees**
Two bodies govern this repository:

### **Architecture Review Board (ARB)**
Responsible for:
- Reviewing ADRs  
- Approving major architectural decisions  
- Ensuring cross‑domain alignment  

### **Standards Committee**
Responsible for:
- Maintaining and updating Standards  
- Ensuring consistency across domains  
- Reviewing proposed changes to Standards  

Both groups will have:
- Clear membership  
- Defined responsibilities  
- Time‑boxed review SLAs  
- Lightweight workflows  

Templates and workflows will be added under their respective directories.

---
