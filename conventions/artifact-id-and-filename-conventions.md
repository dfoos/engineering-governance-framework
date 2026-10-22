# Artifact ID and Filename Conventions

This document defines the conventions for artifact IDs and filenames across ADRs, RFCs, and Standards. These conventions ensure consistency, discoverability, and traceability of governance artifacts.

---

## Permanent Document IDs

Every document receives a permanent, sequential ID independent of its taxonomy:

- ADR: `ADR-####`
- Standard: `STD-####`
- RFC: `RFC-####`

IDs are never reused, including after rejection, withdrawal, supersession, or retirement. Taxonomy values must not be embedded in IDs or filenames.

## ADR Filename Format

- **Format**: `ADR-####-<short-title>.md`
- **Numbering**: Sequential, starting from the next unused registry ID.
- **Short Title**: A concise, hyphenated summary of the ADR's purpose.
- **Example**: `ADR-0001-terraform-standardization.md`

### Rules:
1. Numbers are zero-padded to four digits (e.g., `0001`, `0002`).
2. Titles must be lowercase, hyphenated, and descriptive.
3. Avoid special characters or spaces in titles.

---

## RFC Filename Format

- **Format**: `RFC-####-<short-title>.md`
- **Numbering**: Sequential, starting from the next unused registry ID.
- **Short Title**: A concise, hyphenated summary of the RFC's purpose.
- **Example**: `RFC-0001-cloud-governance.md`

### Rules:
1. Numbers are zero-padded to four digits (e.g., `0001`, `0002`).
2. Titles must be lowercase, hyphenated, and descriptive.
3. Avoid special characters or spaces in titles.

---

## Standard Filename Format

- **Format**: `STD-####-<short-title>.md`
- **Versioning**: Semantic versioning (`v1.0`, `v2.1`, etc.).
- **Name**: A concise, hyphenated summary of the standard's purpose.
- **Example**: `STD-0001-security-baseline.md`

### Rules:
1. Keep the permanent `STD-####` ID unchanged when the Standard is updated.
   - **Major Version**: Increment the major version (e.g., `v1.0` → `v2.0`) when introducing breaking changes that are not backward compatible.
     - **Example**: A security baseline standard removes support for a deprecated encryption algorithm, requiring teams to update their configurations.
   - **Minor Version**: Increment the minor version (e.g., `v1.0` → `v1.1`) when adding new features or making backward-compatible improvements.
     - **Example**: A security baseline standard adds a new optional control for logging enhancements.
2. Titles must be lowercase, hyphenated, and descriptive.
3. Avoid special characters or spaces in titles.

---

## General File Naming Convention

- **Format**: `<artifact-type>-####-<short-title>.md`
- **Artifact Types**: `adr`, `rfc`, `standard`.
- **Identifier**: The permanent four-digit document ID.
- **Short Title**: A concise, hyphenated summary of the artifact's purpose.
- **Example**: `adr-001-terraform-standardization.md`

### Rules:
1. Use the appropriate artifact type prefix (`adr`, `rfc`, `standard`).
2. Ensure filenames retain the permanent ID and are unique within their category.
3. Avoid special characters, spaces, or uppercase letters.

---

## Change Management

1. **New Artifacts**: Follow the numbering and naming conventions when creating new artifacts.
2. **Updates**: Keep the document ID and taxonomy stable unless governance explicitly changes them; update the Standard version and changelog.
3. **Deprecation**: Record the status and replacement relationship in document metadata.

---

These conventions ensure clarity and consistency across all governance artifacts. Adherence to these rules is mandatory for all contributors.
