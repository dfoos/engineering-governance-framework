# Archive Conventions

This document outlines the conventions for archiving governance artifacts. Archiving ensures that deprecated or inactive artifacts are retained for historical reference while remaining clearly marked as no longer active.

---

## Archiving Artifacts

Artifacts are archived when they are no longer active but need to be retained for historical or reference purposes.

### Process:
1. **Mark the Artifact as Archived**:
   - Set the document `status` to `archived`.
   - Include a justification for archiving the artifact.

2. **Move the Artifact to the Archive Directory**:
   - Place the artifact in the appropriate `archive/` subdirectory based on its type:
     - ADRs: `adr/archive/`
     - RFCs: `rfc/archive/`
     - Standards: `standards/archive/`

3. **Update Registries**:
   - Mark the artifact archived in its type registry.
   - Keep the historical entry available with its archive location.

---

## Archive Directory Structure

The archive directory structure mirrors the main repository structure:

```
adr/
  archive/
    adr-001-example.md
rfc/
  archive/
    rfc-001-example.md
standards/
  archive/
    standard-example-v1.0.md
```

---

Adherence to these conventions ensures that archived artifacts remain accessible and clearly distinguished from active artifacts.
