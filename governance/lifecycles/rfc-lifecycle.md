# RFC Lifecycle

This document outlines the lifecycle stages of a Request for Comments (RFC) artifact, from proposal to archival. The lifecycle ensures clarity and consistency in the governance process.

---

## Lifecycle Stages

1. **Proposed**
   - The RFC is under discussion and has not yet been approved.
   - Contributors can provide feedback and suggest changes.
   - The RFC status is `draft` or `in-review`.

2. **Approved**
   - The RFC has completed review and its proposal is approved for implementation or conversion into resulting records.

3. **Superseded**
   - The RFC has been replaced by a newer decision or artifact.
   - Set status to `superseded` and reference the replacement or resulting records.

4. **Deprecated**
   - The RFC is scheduled for removal or is no longer recommended for use.
   - Set status to `deprecated` and provide a transition plan.

5. **Archived**
   - The RFC is no longer active but is retained for historical reference.
   - Set status to `archived` and move it to the `archive/` directory when applicable.

---

## Change Management

- **Superseding RFCs**: When an RFC is superseded, update its status and add a reference to the replacement or resulting record.
- **Deprecating RFCs**: When an RFC is deprecated, communicate the deprecation to all stakeholders and provide a transition plan.
- **Archiving RFCs**: When an RFC is archived, set its status to `archived` and move it to the `archive/` directory when applicable.

---

Adherence to this lifecycle ensures that RFCs remain clear, actionable, and traceable throughout their existence.
