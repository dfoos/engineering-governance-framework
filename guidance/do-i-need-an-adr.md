# **Do I Need an ADR?**

Architectural Decision Records (ADRs) are powerful, but they’re not meant for every change. Overusing ADRs slows teams down, clutters the decision history, and forces the ARB to review work that doesn’t require architectural oversight.

This guide exists to help engineers quickly determine whether a proposal needs an ADR, a Standard update, or simply an RFC for discussion.

---

# **The Short Answer**
You need an ADR when you are making a **long‑term architectural decision** that affects **multiple teams**, **multiple systems**, or **core infrastructure patterns**.

If you’re not changing architecture, you probably don’t need an ADR.

---

# **Decision Tree**

```
                          ┌────────────────────────────────┐
                          │ Are you making a decision      │
                          │ that changes architecture?     │
                          └──────────────────┬─────────────┘
                                             │
                                 ├── No  → See guidance below
                                 └── Yes
                                             │
                                             ▼
                     ┌────────────────────────────────┐
                     │ Does the decision impact       │
                     │ multiple teams or domains?     │
                     └──────────────────┬─────────────┘
                                        │
                            ├── No  → See guidance below
                            └── Yes
                                        │
                                        ▼
            ┌──────────────────────────────────────────────────┐
            │ You need an ADR. This goes to the ARB.           │
            └──────────────────────────────────────────────────┘


If “No” at either step:
- Update a Standard, OR
- Submit an RFC for discussion, OR
- Just implement the change within your team.
```

---

# **When You *Do* Need an ADR**
Use an ADR when the decision:

### **1. Introduces a new architectural pattern**
- Moving from VMs to Kubernetes  
- Adopting event‑driven architecture  
- Introducing a new identity provider  

### **2. Retires or replaces a major platform**
- Decommissioning VMware clusters  
- Migrating from Azure DevOps to GitHub Actions  
- Replacing a legacy DNS system  

### **3. Impacts multiple domains**
- Networking + Cloud + Security  
- IAM + Application Architecture  
- Terraform + CI/CD + Governance  

### **4. Has long‑term operational impact**
- Selecting a new secrets management platform  
- Standardizing on a new logging/observability stack  

### **5. Deviates from an existing Standard**
If you need to break a Standard, you need an ADR explaining why.

---

# **When You *Do Not* Need an ADR**
Skip the ADR if the change is:

### **1. A refinement of an existing Standard**
- Adding a new required tag  
- Updating naming conventions  
- Adjusting Terraform module structure  

This belongs in the **Standards Committee**, not the ARB.

### **2. A team‑level decision**
- Internal refactoring  
- Changing how your team structures repos  
- Updating CI/CD steps that don’t affect other teams  

### **3. A tooling or configuration change with no architectural impact**
- Updating firewall automation scripts  
- Changing monitoring thresholds  
- Modifying IAM roles within an existing pattern  

### **4. A proposal that needs discussion, not a decision**
This is an **RFC**, not an ADR.

---

# **Examples**

### **Example 1 — Tagging**
- Adding a new required tag → **Standard update**  
- Changing the entire tagging model → **ADR**

### **Example 2 — Terraform**
- Updating backend configuration → **Standard update**  
- Moving from Terraform to Pulumi → **ADR**

### **Example 3 — Networking**
- Adding a new subnet → **No ADR**  
- Redesigning the IP allocation model → **ADR**

### **Example 4 — Identity**
- Adding a new AD group → **No ADR**  
- Moving from AD‑based auth to Azure AD → **ADR**

---

# **Rule of Thumb**
If the decision will still matter **three years from now**,  
and engineers will ask **“Why did we do this?”**,  
you need an ADR.

If the decision will change again in six months,  
you probably need a **Standard update**, not an ADR.

---

# **Still Not Sure?**
If you’re on the fence:
1. Open an RFC  
2. Tag the ARB  
3. Let the ARB triage whether an ADR is required  

This keeps the process lightweight and avoids unnecessary churn.

For an ADR, classify the architecture concern using the shared taxonomy. Select
the owning primary classification and add a reusable classification only when
it improves discovery. The taxonomy is not part of the permanent ADR ID.

---
