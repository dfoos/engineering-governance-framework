# **Engineering Governance Overview**

This document provides a high‑level view of how **RFCs**, **ADRs**, and **Standards** work together to support consistent, scalable engineering practices across the organization.

The goal is simple:  
**Make it obvious which artifact to use, when to use it, and how decisions flow through the system.**

---

# **Governance Flow Diagram**

```markdown
                           ┌──────────────────────────┐
                           │        Idea / Need        │
                           └──────────────┬───────────┘
                                          │
                                          ▼
                     ┌────────────────────────────────────┐
                     │ Do we need discussion, alignment,   │
                     │ or exploration before deciding?     │
                     └──────────────┬──────────────────────┘
                                    │
                           Yes      │       No
                                    │
                                    ▼
                     ┌──────────────────────────┐
                     │           RFC             │
                     │  (Request for Comment)    │
                     └──────────────┬───────────┘
                                    │
                                    ▼
                     ┌──────────────────────────┐
                     │   Decision Reached?       │
                     └──────────────┬───────────┘
                                    │
                           Yes      │       No
                                    │
                                    ▼
                     ┌──────────────────────────┐
                     │           ADR             │
                     │ (Architecture Decision)   │
                     └──────────────┬───────────┘
                                    │
                                    ▼
                     ┌──────────────────────────┐
                     │ Does this decision        │
                     │ define ongoing rules?     │
                     └──────────────┬───────────┘
                                    │
                           Yes      │       No
                                    │
                                    ▼
                     ┌──────────────────────────┐
                     │        Standard           │
                     │ (Living Engineering Rule) │
                     └──────────────────────────┘
```

---

# **Artifact Roles**

## **RFC — Request for Comment**
**Purpose:** Explore ideas, gather feedback, build alignment.  
**Used when:**  
- Multiple options exist  
- Cross‑team input is needed  
- You’re socializing a proposal  
- You’re not ready to commit  

**Outcome:**  
- Leads to an ADR, a Standard update, or is closed with no action.

---

## **ADR — Architecture Decision Record**
**Purpose:** Document a long‑term architectural decision.  
**Used when:**  
- A major decision is being made  
- The decision impacts multiple teams or systems  
- The decision will matter years from now  
- You need a durable historical record  

**Outcome:**  
- Immutable record of *why* the decision was made  
- May trigger updates to Standards  

---

## **Standard — Living Engineering Rule**
**Purpose:** Define how we operate today.  
**Used when:**  
- Establishing repeatable rules or conventions  
- Documenting required patterns  
- Updating operational guidance  
- Ensuring consistency across teams  

**Outcome:**  
- Versioned, maintained, and updated as technology evolves  
- Does not require a new ADR unless architecture changes  

---

# **How They Interact**

```markdown
RFC → ADR → Standard
```

### **RFC → ADR**
When discussion leads to a clear architectural choice.

### **ADR → Standard**
When the architectural decision requires ongoing rules or conventions.

### **Standard (alone)**
When updating operational guidance without changing architecture.

### **ADR (alone)**
When the decision is already made or does not require debate.

### **RFC (alone)**
When exploring ideas without committing to a decision.

---

# **Examples**

### **Example 1 — Terraform Platform Change**
- Management decides to move from Terraform Cloud to Spacelift  
  → **ADR only**  
  → Standards updated afterward  

### **Example 2 — New Tagging Model**
- Team proposes new tagging strategy  
  → **RFC**  
  → Decision made  
  → **ADR**  
  → Tagging Standard updated  

### **Example 3 — Adding a Required Tag**
- No architectural change  
  → **Standard update only**  

### **Example 4 — Evaluating Observability Tools**
- Need discussion  
  → **RFC**  
- Decision made  
  → **ADR**  
- Implementation rules  
  → **Standard**  

---

# **Summary**

| Artifact | Purpose | When to Use | Outcome |
|---------|----------|--------------|---------|
| **RFC** | Explore ideas, gather feedback | When you need alignment or discussion | May lead to ADR or Standard |
| **ADR** | Record architectural decisions | When making long‑term, cross‑team decisions | Immutable decision record |
| **Standard** | Define ongoing rules | When documenting required practices | Living, versioned guidance |

---
