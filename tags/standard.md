# **Tagging Standard**

All RFCs, ADRs, and Standards must be tagged to improve searchability, discoverability, and cross-referencing. This standard defines the tagging rules, requirements, and governance.

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
Tags are applied in a `tags:` field at the top of every RFC, ADR, and Standard file using YAML front matter:

```yaml
---
tags: [tag1, tag2, tag3, tag4]
---

# Title of the artifact
```

### **Rules**
- All tags are **lowercase**
- Tags are **hyphenated** with no spaces
- Tags are short, typically 1–3 words
- Multiple tags are comma-separated in a single list
- No duplicate tags in one artifact
- Only approved tags (see [tags.md](tags.md)) may be used

### **Example**

```yaml
---
tags: [kubernetes, platform, tool-selection, high-impact, active]
---

# RFC: Kubernetes Platform Migration
```

---

## **Required Tags by Artifact Type**

### **RFCs (Requests for Comment)**
Minimum tags required:

- **One Category tag** (e.g., `tool-selection`, `pattern`, `migration`)
- **One Lifecycle tag** (typically `proposed`)
- **One Domain tag** (e.g., `platform`, `security`, `applications`)
- **One Impact tag** (e.g., `high-impact`, `low-impact`)

Optional tags:

- Zero or more **Technology tags** (if the RFC discusses specific tech)

**Example RFC tags**:
```yaml
tags: [tool-selection, proposed, platform, high-impact]
tags: [migration, proposed, cloud, org-wide, aws, kubernetes]
tags: [policy, proposed, security, org-wide]
```

---

### **ADRs (Architecture Decision Records)**
Minimum tags required:

- **One Category tag** (e.g., `pattern`, `tool-selection`, `infrastructure`)
- **One Lifecycle tag** (typically `active`, `superseded`, or `deprecated`)
- **One Domain tag** (e.g., `platform`, `devops`, `networking`)
- **One Impact tag** (e.g., `high-impact`, `org-wide`)

Optional tags:

- Zero or more **Technology tags** (if the ADR involves specific technologies)

**Example ADR tags**:
```yaml
tags: [pattern, active, platform, org-wide, kubernetes, terraform]
tags: [tool-selection, active, devops, high-impact, github]
tags: [deprecation, deprecated, cloud, aws]
```

---

### **Standards**
Minimum tags required:

- **One Category tag** (e.g., `operational`, `naming-convention`, `security-baseline`)
- **One Lifecycle tag** (typically `active` unless the standard is deprecated)
- **One Domain tag** (e.g., `platform`, `identity`, `networking`)

Optional tags:

- **Impact tags** (use if the standard is org-wide or team-local)
- **Technology tags** (if the standard is specific to a technology)

**Example Standard tags**:
```yaml
tags: [naming-convention, active, platform]
tags: [operational, active, security, org-wide]
tags: [security-baseline, active, identity, org-wide]
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
- Every artifact must have exactly one category tag (or split artifacts if they span multiple categories)
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
If an artifact's content or status changes, update its tags:

- An ADR moving from `proposed` to `active` when approved by the ARB
- A Standard updated from `active` to `deprecated` when scheduled for removal
- A RFC with new technology tags if the scope expands

All tag updates should be committed with a clear message explaining the change.

### **Searching by Tags**
Engineers can search for tags in multiple ways:

- GitHub issue/PR search: `tag:kubernetes` (if using labels)
- File grep: `grep "tags:.*kubernetes" *.md`
- Repository documentation: Link to tagged collections in governance READMEs

---

## **Governance of Tags**

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
tags: [tool-selection, proposed, platform, org-wide, kubernetes, high-impact]
---

# RFC: Kubernetes as the Platform for Container Orchestration
```

### **ADR: Terraform Standardization**
```yaml
---
tags: [pattern, active, platform, org-wide, terraform, infrastructure]
---

# ADR: All Infrastructure Provisioning Must Use Terraform
```

### **Standard: DNS Naming Conventions**
```yaml
---
tags: [naming-convention, active, networking]
---

# Standard: DNS Naming Conventions
```

### **Deprecated ADR: Legacy Docker Swarm**
```yaml
---
tags: [tool-selection, superseded, platform, docker]
---

# ADR: Docker Swarm for Container Orchestration
(Superseded by Kubernetes ADR)
```

---

## **Enforcement**

Starting immediately:

- All new RFCs, ADRs, and Standards must include tags
- Existing artifacts should be tagged during the next review cycle
- The Standards Committee will audit tags quarterly and report trends
- Missing or incorrect tags will be flagged during ARB/Standards Committee review

---
