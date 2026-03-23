# **Do I Need a Standard?**

Standards define **how we operate today** — the required patterns, conventions, and rules that keep our infrastructure consistent and maintainable. Unlike ADRs, Standards are **living documents** that evolve as our tooling, platforms, and best practices evolve.

This guide helps you determine when you should create or update a Standard, when you should write an ADR instead, and when neither is necessary.

---

# **The Short Answer**
You need a Standard when you are defining **repeatable, ongoing engineering practices** that multiple teams must follow.

If you’re making a one‑time architectural decision → you need an **ADR**.  
If you’re exploring options or seeking alignment → you need an **RFC**.  
If you’re defining rules or conventions for day‑to‑day engineering → you need a **Standard**.

---

# **Decision Tree**

```
                     ┌──────────────────────────────────────┐
                     │ Is this guidance something           │
                     │ multiple teams must follow           │
                     │ on an ongoing basis?                 │
                     └──────────────────┬───────────────────┘
                                        │
                            ├── No  → See guidance below
                            └── Yes
                                        │
                                        ▼
            ┌──────────────────────────────────────────────────┐
            │ You need a Standard. This becomes part of        │
            │ the living engineering rules.                    │
            └──────────────────────────────────────────────────┘


If “No”:
- If it's a one-time architectural decision → ADR.
- If you're exploring options → RFC.
- If it's team-specific → no Standard needed.
```

---

# **When You *Do* Need a Standard**
Use a Standard when you are defining **how something should be done consistently across the organization**.

### **1. You’re defining repeatable operational rules**
- Required AWS/Azure tagging  
- DNS naming conventions  
- Firewall request requirements  
- Terraform module structure  
- IAM group naming rules  
- Logging and monitoring requirements  

### **2. You’re documenting best practices that must be enforced**
- Encryption requirements  
- Backup and retention policies  
- CI/CD pipeline expectations  
- Container image hardening rules  

### **3. You’re updating existing guidance**
Standards evolve — they are not frozen like ADRs.

Examples:
- Adding a new required tag  
- Updating naming conventions  
- Changing Terraform backend configuration  
- Updating firewall request expiration rules  

### **4. You’re defining something that will be referenced frequently**
If engineers will ask “What’s the rule for this?” → it belongs in a Standard.

---

# **When You *Do Not* Need a Standard**
Skip the Standard when:

### **1. The change is architectural, not operational**
Example:  
- Choosing Spacelift over Terraform Cloud  
This is an **ADR**, not a Standard.

### **2. The change is team‑specific**
- Internal repo structure  
- Team-specific CI workflows  
- Local automation scripts  

### **3. The change is temporary**
Standards represent long-term guidance.

### **4. You’re still exploring options**
That’s an **RFC**, not a Standard.

---

# **Examples**

### **Example 1 — Terraform**
- Defining how modules must be structured → **Standard**  
- Choosing Terraform over Pulumi → **ADR**  
- Discussing whether to adopt a module registry → **RFC**

### **Example 2 — Tagging**
- Required tags and formats → **Standard**  
- Deciding to adopt mandatory tagging → **ADR**  
- Proposing a new tagging model → **RFC**

### **Example 3 — Networking**
- DNS naming rules → **Standard**  
- Redesigning the DNS architecture → **ADR**  
- Proposing a new segmentation model → **RFC**

### **Example 4 — CI/CD**
- Required pipeline stages → **Standard**  
- Choosing GitHub Actions over Azure DevOps → **ADR**  
- Evaluating pipeline patterns → **RFC**

---

# **Rule of Thumb**
If the guidance will be used **repeatedly**, by **multiple teams**, and needs to be **kept up to date**, you need a Standard.

If the guidance explains **why** a major decision was made, you need an ADR.

If the guidance is still being debated, you need an RFC.

---
