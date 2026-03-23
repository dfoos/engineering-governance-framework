# Standard Lifecycle

This document outlines the lifecycle stages of a Standard artifact, from creation to archival. The lifecycle ensures clarity and consistency in the governance process.

---

## Lifecycle Stages

1. **Draft**
   - The Standard is under development and has not yet been approved.
   - Contributors can provide feedback and suggest changes.
   - The Standard must include the `proposed` lifecycle tag.

2. **Active**
   - The Standard has been reviewed and approved by the Standards Committee.
   - The Standard is now considered an official governance artifact.
   - The Standard must include the `active` lifecycle tag.

3. **Updated**
   - The Standard has been revised to include new information or improvements.
   - The version number must be incremented following semantic versioning.

4. **Superseded**
   - The Standard has been replaced by a newer version or a different Standard.
   - The Standard must include the `superseded` lifecycle tag and reference the new Standard.

5. **Deprecated**
   - The Standard is scheduled for removal or is no longer recommended for use.
   - The Standard must include the `deprecated` lifecycle tag.

6. **Archived**
   - The Standard is no longer active but is retained for historical reference.
   - The Standard must include the `archived` lifecycle tag.

---

## Change Management

- **Updating Standards**: Increment the version number and update the metadata to reflect the changes.
- **Superseding Standards**: When a Standard is superseded, update its metadata to include the `superseded` tag and add a reference to the new Standard.
- **Deprecating Standards**: When a Standard is deprecated, communicate the deprecation to all stakeholders and provide a transition plan.
- **Archiving Standards**: When a Standard is archived, ensure it is marked with the `archived` tag and moved to the `archive/` directory.

---

Adherence to this lifecycle ensures that Standards remain clear, actionable, and traceable throughout their existence.
