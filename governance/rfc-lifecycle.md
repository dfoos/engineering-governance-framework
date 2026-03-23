# RFC Lifecycle

This document outlines the lifecycle stages of a Request for Comments (RFC) artifact, from proposal to archival. The lifecycle ensures clarity and consistency in the governance process.

---

## Lifecycle Stages

1. **Proposed**
   - The RFC is under discussion and has not yet been approved.
   - Contributors can provide feedback and suggest changes.
   - The RFC must include the `proposed` lifecycle tag.

2. **Approved**
   - The RFC has been reviewed and accepted by the Standards Committee.
   - The RFC is now considered an official governance artifact.
   - The RFC must include the `active` lifecycle tag.

3. **Superseded**
   - The RFC has been replaced by a newer decision or artifact.
   - The RFC must include the `superseded` lifecycle tag and reference the new artifact.

4. **Deprecated**
   - The RFC is scheduled for removal or is no longer recommended for use.
   - The RFC must include the `deprecated` lifecycle tag.

5. **Archived**
   - The RFC is no longer active but is retained for historical reference.
   - The RFC must include the `archived` lifecycle tag.

---

## Change Management

- **Superseding RFCs**: When an RFC is superseded, update its metadata to include the `superseded` tag and add a reference to the new RFC.
- **Deprecating RFCs**: When an RFC is deprecated, communicate the deprecation to all stakeholders and provide a transition plan.
- **Archiving RFCs**: When an RFC is archived, ensure it is marked with the `archived` tag and moved to the `archive/` directory.

---

Adherence to this lifecycle ensures that RFCs remain clear, actionable, and traceable throughout their existence.