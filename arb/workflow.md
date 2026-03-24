# Architecture Review Board (ARB) Workflow

The Architecture Review Board exists to ensure that major architectural decisions are aligned, intentional, and technically sound across the organization. The ARB is not a gatekeeper — it is a mechanism for clarity, consistency, and long‑term stability.

This workflow defines how ADRs are submitted, reviewed, approved, and published.

---

## 1. Purpose of the ARB
The ARB provides:
- A consistent decision‑making process for cross‑domain architecture
- A durable record of architectural decisions (ADRs)
- A forum for resolving architectural conflicts
- A mechanism for ensuring alignment across infrastructure, security, networking, and platform engineering

The ARB does **not** manage day‑to‑day engineering practices. Those are governed by Standards.

---

## 2. What Requires ARB Review
ARB review is required for:
- New architectural patterns or platforms  
- Decisions that impact multiple domains (e.g., networking + cloud + security)  
- Introduction or retirement of major technologies  
- Decisions with long‑term operational or financial impact  
- Deviations from existing Standards  

If the proposal only updates a Standard (not the underlying architecture), it goes to the Standards Committee, not the ARB.

---

## 3. Submission Process
1. Author drafts an ADR using the ADR template  
2. Team performs internal peer review  
3. Author submits ADR via Pull Request to the `/adr` directory  
4. ARB triages the ADR into one of three categories:
   - **A: No ARB Review Needed** (closed with comment)
   - **B: Lightweight Review** (async review)
   - **C: Full Review** (ARB meeting)

---

## 4. Review Categories

### Category A — No ARB Review Needed
Criteria:
- Fully aligns with existing Standards  
- Impacts only a single team  
- No architectural implications  

Outcome:
- ADR closed with comment  
- No further action required  

---

### Category B — Lightweight Review
Criteria:
- Low‑risk architectural change  
- Impacts a single domain  
- Uses existing patterns with minor variation  

Process:
- ARB reviews asynchronously  
- SLA: Refer to the [Lightweight Review SLA](../governance/sla.md#2-adr-lightweight-review-sla)  
- If no objections → **auto‑approved (lazy consensus)**  

Outcome:
- ADR merged and published  

---

### Category C — Full ARB Review
Criteria:
- Cross‑domain impact  
- Security‑sensitive  
- High operational or financial impact  
- Introduces or retires major technology  

Process:
- Added to next ARB meeting agenda  
- SLA: Refer to the [Full Review SLA](../governance/sla.md#3-adr-full-review-sla)  
- Discussion and decision recorded  

Outcome:
- Accepted  
- Rejected  
- Needs Revision  
- Superseded (if replacing an older ADR)

---

## 5. Decision Outcomes

### Accepted
ADR is approved and merged. It becomes an immutable historical record.

### Rejected
ADR is closed with explanation. No further action.

### Needs Revision
Author updates the ADR and resubmits.

### Superseded
ADR replaces a previous ADR. Both documents remain in the repo with cross‑references.

---

## 6. Publishing
Once approved:
- ADR is merged into `/adr`  
- ADR is indexed in the ADR catalog  
- Relevant Standards may be updated by the Standards Committee  

---

## 7. ARB Membership
The ARB consists of senior engineers and architects representing:
- Cloud Infrastructure  
- Networking  
- Security  
- Identity & Access  
- Platform / DevOps  

Members are expected to:
- Review ADRs promptly  
- Provide clear, actionable feedback  
- Represent their domain’s interests without blocking progress  

---

## 8. Operating Principles
- **ARB is a guide, not a gatekeeper**  
- **Time‑boxed decisions** to avoid blocking delivery  
- **Lazy consensus** for low‑risk changes  
- **Transparency** — all decisions are public internally  
- **Standards over tribal knowledge**  

---

## 9. Meeting Cadence
- Weekly 30–60 minute meeting  
- Only Category C ADRs are discussed  
- Agenda published 24 hours in advance  

---

## 10. Contact
For questions or to propose agenda items, open an issue in this repository.
