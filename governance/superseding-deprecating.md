# Superseding and Deprecating Artifacts

This document outlines the process for superseding and deprecating governance artifacts, ensuring clarity and consistency in the governance process.

---

## Superseding Artifacts

Superseding occurs when an artifact is replaced by a newer version or a different artifact. The superseded artifact remains in the repository for historical reference.

### Process:
1. **Create the New Artifact**:
   - Draft and approve the new artifact following the appropriate lifecycle process.
   - Ensure the new artifact references the artifact it is superseding.

2. **Update the Superseded Artifact**:
   - Set the document `status` to `superseded` and populate `superseded-by`.
   - Include a reference to the new artifact in the superseded artifact.

3. **Communicate the Change**:
   - Notify all stakeholders about the supersession.
   - Provide guidance on transitioning to the new artifact.

---

## Deprecating Artifacts

Deprecating occurs when an artifact is no longer recommended for use and is scheduled for removal.

### Process:
1. **Mark the Artifact as Deprecated**:
   - Set the document `status` to `deprecated` and document any replacement.
   - Include a justification for the deprecation and any replacement artifacts.

2. **Communicate the Deprecation**:
   - Notify all stakeholders about the deprecation.
   - Provide a transition plan and timeline for removal.

3. **Remove the Artifact**:
   - After the transition period, set the document `status` to `archived` and move it to the appropriate archive directory when applicable.

---

Adherence to these processes ensures that governance artifacts remain clear, actionable, and traceable throughout their lifecycle.
