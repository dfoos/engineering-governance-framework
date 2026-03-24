# ADR Lifecycle & Review Cadence

**Version:** 1.0  
**Owner:** Architecture Review Board (ARB)  
**Last Updated:** 2026-03-23  
**Related Documents:** ADR Template, ARB Workflow, Standards Committee Workflow  

---

# 1. Purpose
This document defines the lifecycle and review cadence for Architecture Decision Records (ADRs).  
The goal is to ensure architectural decisions are reviewed consistently, approved quickly, and documented in a way that scales with the organization.

This lifecycle prevents ADR backlog, eliminates ambiguity around review timelines, and ensures the ARB focuses on decisions that truly require architectural oversight.

---

# 2. ADR Lifecycle Overview

The ADR lifecycle consists of the following stages:

1. **Draft**  
2. **ARB Triage**  
3. **ARB Review** (Async or Meeting)  
4. **Revision Cycle** (if required)  
5. **Approval & Publication**  
6. **Standards Update** (if applicable)  
7. **Periodic Review** (optional but recommended)

Each stage is described in detail below.

---

# 3. Lifecycle Stages

## 3.1 Draft Stage
**Owner:** Authoring team  
**Duration:** As needed  

The author drafts the ADR using the approved template.  
Activities include:
- Internal team peer review  
- Ensuring the ADR is necessary (per “Do I Need an ADR?”)  
- Adding tags  
- Linking RFCs or supporting documentation  

**Exit Criteria:**  
ADR is complete, internally reviewed, and ready for ARB triage.

---

## 3.2 ARB Triage
**Owner:** ARB Facilitator or designated reviewer  
**Duration:** 1–2 business days  

Every ADR is categorized into one of three review paths:

### Category A — No ARB Review Needed
- Fully aligns with existing Standards  
- Impacts only one team  
- No architectural implications  

**Outcome:**  
Closed or redirected to Standards Committee.

### Category B — Lightweight Review
- Low-risk architectural change  
- Single-domain impact  
- Minor variation on existing patterns  

**Outcome:**  
Async review with **5 business-day SLA** and **lazy consensus**.

### Category C — Full ARB Review
- Cross-domain impact  
- Security-sensitive  
- High operational or financial impact  
- Introduces or retires major technology  

**Outcome:**  
Added to next ARB meeting with **10 business-day SLA**.

---

## 3.3 ARB Review
**Owner:** ARB  
**Cadence:** Weekly meeting (30–60 minutes)  

Only **Category C** ADRs are discussed in the meeting.  
Category B ADRs are reviewed asynchronously.

ARB decisions:
- **Accepted**  
- **Rejected**  
- **Needs Revision**  
- **Superseded**  

ARB MUST provide clear, actionable feedback.

---

## 3.4 Revision Cycle
**Owner:** Author  
**Duration:** As needed  

If ARB requests changes:
- Author updates ADR  
- Resubmits for triage  
- Typically re-enters as Category B unless major changes were made  

---

## 3.5 Approval & Publication
**Owner:** ARB + Author  
**Duration:** Immediate upon approval  

Once approved:
- ADR is merged into `/adr`  
- Status updated to **Accepted**  
- Tags validated  
- ADR added to the ADR index  
- Linked Standards flagged for update (if required)

The ADR becomes an immutable historical record.

---

## 3.6 Standards Update (If Applicable)
**Owner:** Standards Committee  
**Cadence:** Bi-weekly  

If the ADR requires operational rules:
- Standards Committee updates or creates a Standard  
- Version history updated  
- ADR linked in the Standard  

This ensures ADRs capture **why**, and Standards capture **how**.

---

## 3.7 Periodic Review (Recommended)
**Owner:** ARB + Standards Committee  
**Cadence:** Quarterly  

Purpose:
- Identify outdated ADRs  
- Mark ADRs as **Superseded**  
- Ensure Standards reflect current reality  
- Clean up stale or unused documents  

This prevents governance drift and documentation rot.

---

# 4. Review Cadence Summary

| Activity | Owner | Cadence | SLA |
|---------|--------|---------|-----|
| ADR Triage | ARB | Daily or every other day | 1–2 days |
| Category B Review | ARB | Async | 5 days |
| Category C Review | ARB | Weekly meeting | 10 days |
| Standards Updates | Standards Committee | Bi-weekly | N/A |
| Governance Cleanup | ARB + Standards Committee | Quarterly | N/A |

---

# 5. Operating Principles

- **ARB is a guide, not a gatekeeper**  
- **Time-boxed decisions** prevent backlog  
- **Lazy consensus** accelerates low-risk changes  
- **Transparency** ensures trust and clarity  
- **Standards over tribal knowledge**  
- **ADRs capture “why,” Standards capture “how”**  

---

# 6. Version History

| Version | Date | Author | Description |
|---------|------|--------|-------------|
| 1.0 | 2026‑03‑23 | Architecture Governance | Initial release |
