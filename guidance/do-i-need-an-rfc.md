# **Do I Need an RFC?**

RFCs (Requests for Comment) are a tool for **collaboration**, not bureaucracy. They exist to gather input, socialize ideas early, and align teams before decisions are made. But not every change needs an RFC — in fact, many shouldn’t have one.

This guide helps you determine when an RFC is appropriate, when you should go straight to an ADR, and when neither is necessary.

---

# **The Short Answer**
You need an RFC when you want **feedback**, **alignment**, or **discussion** before making a decision.

You do **not** need an RFC when:
- The decision is already made (e.g., management directive)  
- The change is small and isolated  
- You’re simply documenting a decision in an ADR  
- You’re updating an existing Standard  

---

# **Decision Tree**

```
                     ┌──────────────────────────────────┐
                     │ Do you need input or alignment    │
                     │ from multiple teams BEFORE        │
                     │ making a decision?                │
                     └───────────────┬──────────────────┘
                                     │
                            Yes      │       No
                                     │
                                     ▼
            ┌──────────────────────────────────────────────┐
            │ You need an RFC. Use it to gather feedback.   │
            └──────────────────────────────────────────────┘


If “No”:
- If the decision is architectural → create an ADR.
- If the decision updates a Standard → update the Standard.
- If the decision is already made → skip straight to ADR or Standard.
```

---

# **When You *Do* Need an RFC**
Use an RFC when you want to **explore options** or **build consensus**.

### **1. You’re proposing something that affects multiple teams**
- New CI/CD workflow  
- Shared Terraform module design  
- Changes to DNS structure  
- New tagging strategy proposal  

### **2. You want feedback before committing**
- Evaluating multiple observability platforms  
- Considering a new deployment pattern  
- Proposing a new network segmentation model  

### **3. You’re socializing an idea early**
- Early-stage architectural concepts  
- Platform roadmap items  
- Infrastructure modernization proposals  

### **4. You’re unsure whether an ADR is needed**
RFCs are a safe place to think out loud.

---

# **When You *Do Not* Need an RFC**
Skip the RFC when:

### **1. The decision is already made**
Example:  
**Management has decided to move from Terraform Cloud to Spacelift.**

In this case:
- No RFC needed  
- Create an ADR documenting the decision and rationale  
- Update Standards as needed  

RFCs are for discussion — not for rubber‑stamping decisions that are already final.

---

### **2. You’re documenting a decision, not debating it**
If you already know the answer, write an ADR.

### **3. You’re updating a Standard**
Standards are living documents.  
They don’t require an RFC unless the change is controversial or unclear.

### **4. The change is isolated to your team**
- Internal repo structure  
- Team-specific CI jobs  
- Local automation  

No RFC needed.

---

# **Examples**

### **Example 1 — Management Directive**
**“We are moving from Terraform Cloud to Spacelift.”**  
- No RFC  
- Create an ADR documenting the decision  
- Standards Committee updates Terraform Standards  

### **Example 2 — Evaluating Observability Tools**
You’re comparing Datadog, New Relic, and Dynatrace.  
- RFC needed (discussion)  
- ADR created once the decision is made  

### **Example 3 — Updating Tagging Requirements**
Adding a new required tag.  
- No RFC  
- Standard update only  

### **Example 4 — New Network Segmentation Model**
Impacts multiple teams and services.  
- RFC needed  
- ADR follows once consensus is reached  

---

# **Rule of Thumb**
If you need **input**, **alignment**, or **debate**, write an RFC.  
If you already know the answer, skip straight to an ADR or Standard.

RFCs are for thinking.  
ADRs are for deciding.  
Standards are for doing.

---
