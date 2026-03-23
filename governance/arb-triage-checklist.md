# ARB Triage Checklist

**Version:** 1.0  
**Owner:** Architecture Review Board (ARB)  
**Last Updated:** 2026-03-23  
**Related Documents:** ADR Lifecycle, ARB Workflow, ADR Template  

---

# Purpose
This checklist ensures consistent, predictable triage of all incoming ADRs.  
ARB reviewers use this document to determine the correct review path, identify missing information, and ensure ADRs meet minimum quality standards before entering the review pipeline.

---

# 1. Pre‑Triage Validation

Before assigning a category, confirm the ADR meets baseline requirements.

### 1.1 Metadata Check
- [ ] Title is clear and descriptive  
- [ ] Status is set to **Proposed**  
- [ ] Owner(s) identified  
- [ ] Contributors listed (if applicable)  
- [ ] Tags applied and valid per `tags.md`  
- [ ] Linked RFCs included (if applicable)  
- [ ] Supporting documentation links provided  

### 1.2 Template Completeness
- [ ] Summary section is complete and value‑neutral  
- [ ] Decision is clearly stated in active voice  
- [ ] Scope includes both **in scope** and **out of scope**  
- [ ] Consequences include positive, negative, and neutral impacts  
- [ ] Changelog initialized  
- [ ] Conventions section intact  

If any of the above are missing or incomplete:  
→ **Return to author for revision** (do not proceed to categorization)

---

# 2. Categorization Decision

Determine whether the ADR requires ARB involvement and at what level.

### 2.1 Category A — No ARB Review Needed
Assign **Category A** if ALL are true:
- [ ] Fully aligns with existing Standards  
- [ ] Impacts only a single team or domain  
- [ ] No architectural implications  
- [ ] No cross‑region or cross‑platform impact  
- [ ] No security or compliance concerns  

**Outcome:**  
→ Close ADR or redirect to Standards Committee

---

### 2.2 Category B — Lightweight Review (Async)
Assign **Category B** if ANY are true:
- [ ] Low‑risk architectural change  
- [ ] Impacts a single domain  
- [ ] Minor variation on existing patterns  
- [ ] No major financial or operational impact  
- [ ] No new technology being introduced  

**Outcome:**  
→ Async review with **5‑day SLA** and **lazy consensus**

---

### 2.3 Category C — Full ARB Review (Meeting)
Assign **Category C** if ANY are true:
- [ ] Cross‑domain impact (cloud + networking + security, etc.)  
- [ ] Introduces or retires major technology  
- [ ] High operational or financial impact  
- [ ] Security‑sensitive decision  
- [ ] Multi‑region or global architecture implications  
- [ ] Requires alignment across multiple engineering groups  

**Outcome:**  
→ Add to next ARB meeting agenda  
→ **10‑day SLA**

---

# 3. Quality & Clarity Checks

Before finalizing the category, confirm the ADR is understandable and actionable.

### 3.1 Clarity
- [ ] Decision is unambiguous  
- [ ] Scope is clearly defined  
- [ ] Consequences are realistic and complete  
- [ ] No major unanswered questions  

### 3.2 Technical Soundness
- [ ] Decision aligns with architectural principles  
- [ ] No obvious conflicts with existing ADRs  
- [ ] No contradictions with current Standards  
- [ ] Risks are acknowledged  

If clarity or technical soundness is insufficient:  
→ **Return to author for revision**

---

# 4. Routing & Communication

### 4.1 If Category A
- [ ] Close ADR with explanation  
- [ ] Redirect to Standards Committee if appropriate  

### 4.2 If Category B
- [ ] Label ADR as `category-b`  
- [ ] Notify ARB members for async review  
- [ ] Set 5‑day lazy consensus window  

### 4.3 If Category C
- [ ] Label ADR as `category-c`  
- [ ] Add to next ARB meeting agenda  
- [ ] Notify ARB members and ADR owner  

---

# 5. Documentation & Tracking

- [ ] Update ADR index (if maintained manually)  
- [ ] Ensure tags reflect categorization  
- [ ] Ensure ADR status remains **Proposed** until approved  
- [ ] Confirm linked Standards are flagged for potential updates  

---

# 6. Version History

| Version | Date | Author | Description |
|---------|------|--------|-------------|
| 1.0 | 2026‑03‑23 | Architecture Governance | Initial release |
