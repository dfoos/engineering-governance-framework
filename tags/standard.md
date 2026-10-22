# **Optional Metadata Labels**

Labels are optional metadata for improving searchability and cross-referencing. They are not a required classification system. The shared architecture taxonomy in [governance/taxonomy.md](../governance/taxonomy.md) is authoritative for ADR and Standard organization.

---

## **Why Tagging Matters**

Tags serve critical functions:

- **Discoverability**: Engineers find related artifacts quickly across domains and technologies.
- **Cross-Reference**: Tags reveal dependencies and relationships between decisions.
- **Consistency**: Standardized tags prevent ambiguity and duplicate categorization.
- **Governance**: Tags support reporting, impact analysis, and trend identification.
- **Navigation**: Teams understand which decisions affect their domain or technology.

---

## **Tag Structure and Syntax**

### **Format**
Labels MAY be applied in a `labels:` field using YAML front matter:

```yaml
---
labels: [kubernetes, platform]
---

# Title of the artifact
```

### **Rules**
- All tags are **lowercase**
- Tags are **hyphenated** with no spaces
- Tags are short, typically 1–3 words
- Multiple tags are comma-separated in a single list
- No duplicate tags in one artifact
- Prefer approved labels (see [tags.md](tags.md)); labels must not conflict with the document's status or taxonomy.

### **Example**

```yaml
---
labels: [kubernetes, platform]
---

# RFC: Kubernetes Platform Migration
```

---

## **Taxonomy by Artifact Type**

### **RFCs (Requests for Comment)**
RFCs use their permanent sequential ID and workflow `status`. They do not receive taxonomy. An RFC MAY include `proposed-taxonomy` to guide resulting ADRs or Standards, plus optional labels.

**Example RFC tags**:
```yaml
labels: [kubernetes, platform]
labels: [aws, kubernetes]
labels: [security]
```

---

### **ADRs (Architecture Decision Records)**
ADRs MUST include a valid `taxonomy`, `primary-classification`, and optional `reusable-classification` from [governance/taxonomy.md](../governance/taxonomy.md). Labels are optional.

**Example ADR tags**:
```yaml
labels: [kubernetes, terraform]
labels: [github, devops]
labels: [aws, deprecation]
```

---

### **Standards**
Standards MUST include a valid `taxonomy`, `primary-classification`, and optional `reusable-classification` from [governance/taxonomy.md](../governance/taxonomy.md). Labels are optional.

**Example Standard tags**:
```yaml
labels: [platform, naming-convention]
labels: [security, operational]
labels: [identity, security-baseline]
```

---

## **Tag Application Guidelines**

### **Technology Tags**
- Use only if the artifact directly concerns that technology
- Example: An ADR about Kubernetes does NOT need the `aws` tag unless AWS is integral to the decision
- Example: A tagging standard for all clouds should use neither `aws` nor `azure` (use `cloud` instead)

### **Domain Tags**
- Use the *primary* domain affected
- Example: A decision about IAM naming belongs to `identity`, not `platform`
- Example: A decision about CI/CD infrastructure can be `devops` or `platform` (pick the most relevant)

### **Category Tags**
- Labels are optional and should not be used to encode taxonomy or status
- Example: Do not use both `tool-selection` and `process` for one artifact; create separate RFCs/ADRs

### **Impact Tags**
- Use to quickly identify scope and blast radius
- Example: `org-wide` means all teams must understand and comply
- Example: `team-local` means only one team is affected
- Example: Use `high-impact` for decisions affecting many systems, `low-impact` for isolated changes

### **Lifecycle Tags**
- Use to indicate the current state of the artifact
- Example: An `active` ADR is the current decision; a `superseded` ADR is replaced by a newer one
- Example: A `deprecated` standard is scheduled for removal; update it to `deprecated` as soon as the decision is made

---

## **Versioning and Tag Maintenance**

### **Updating Tags**
If an artifact's content or status changes, update its labels when they are no longer accurate:

- An ADR moving from `proposed` to `active` when approved by the ARB
- A Standard updated from `active` to `deprecated` when scheduled for removal
- A RFC with new technology tags if the scope expands

All tag updates should be committed with a clear message explaining the change.

### **Searching by Tags**
Engineers can search for tags in multiple ways:

- GitHub issue/PR search: `tag:kubernetes` (if using labels)
- File grep: `grep "labels:.*kubernetes" *.md`
- Repository documentation: Link to tagged collections in governance READMEs

---

## **Governance of Optional Labels**

### **Adding New Tags**
New tags are proposed and approved through the Standards Committee:

1. Propose a new tag with justification in an RFC or Standards Committee discussion
2. Explain why the tag improves discoverability or governance
3. Standards Committee must approve by consensus
4. Add the tag to [tags.md](tags.md) once approved
5. Communicate the new tag to all teams

### **Deprecating Tags**
Deprecated tags are phased out over time:

1. Mark the tag as `deprecated` in [tags.md](tags.md)
2. Notify all teams with a 30-day transition period
3. Update all artifacts using the deprecated tag to use replacement tags
4. Remove the tag from [tags.md](tags.md) after the transition period

---

## **Examples**

### **RFC: Kubernetes Adoption**
```yaml
---
labels: [kubernetes, platform]
---

# RFC: Kubernetes as the Platform for Container Orchestration
```

### **ADR: Terraform Standardization**
```yaml
---
labels: [terraform, platform]
---

# ADR: All Infrastructure Provisioning Must Use Terraform
```

### **Standard: DNS Naming Conventions**
```yaml
---
labels: [networking, naming-convention]
---

# Standard: DNS Naming Conventions
```

### **Deprecated ADR: Legacy Docker Swarm**
```yaml
---
labels: [docker, platform]
---

# ADR: Docker Swarm for Container Orchestration
(Superseded by Kubernetes ADR)
```

---

## **Enforcement**

Starting immediately:

- Labels are optional for all RFCs, ADRs, and Standards
- Existing artifacts need not be retrofitted with labels
- The Standards Committee will audit tags quarterly and report trends
- Missing or incorrect tags will be flagged during ARB/Standards Committee review

---
