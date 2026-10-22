# **Optional Metadata Labels**

This directory defines optional metadata labels for RFCs, ADRs, and Standards. Labels improve discoverability and cross-referencing; they do not replace the shared architecture taxonomy.

The authoritative taxonomy is [governance/taxonomy.md](../governance/taxonomy.md). ADRs and Standards MUST use that taxonomy. RFCs do not receive taxonomy, but MAY include `proposed-taxonomy` metadata for resulting ADRs or Standards.

---

## **What Are Tags?**

Labels are short, lowercase metadata values used when they add discovery value, for example technology, team, lifecycle, or impact.

Labels enable:

- **Quick Discovery**: Find all decisions related to a technology, domain, or impact level
- **Cross-Referencing**: Understand how decisions in different domains connect
- **Impact Visibility**: Track which decisions affect which teams and systems
- **Governance Reporting**: Analyze trends in decision-making and identify gaps
- **Navigation**: Engineers know instantly which artifacts are relevant to their work

Labels are deliberately secondary metadata. Classification should follow this
order:

```text
if artifact is an ADR or Standard:
    assign taxonomy from governance/taxonomy.md
if artifact is an RFC:
    do not assign taxonomy
    optionally assign proposed-taxonomy for resulting records
if a product, technology, team, or lifecycle value improves search:
    add it as an optional label
```

Do not create a label to compensate for a missing taxonomy branch. Propose a
taxonomy change when the architectural structure is insufficient; use a label
for implementation or discovery details.

---

## **Label Categories**

Labels may describe:

### **1. Technology Tags**
Identify platforms, languages, frameworks, and tools: `kubernetes`, `terraform`, `aws`, `azure`, `cicd`, etc.

**Use when**: The artifact directly concerns a specific technology.

### **2. Domain Tags**
Identify organizational or technical domains: `platform`, `devops`, `security`, `networking`, `identity`, `operations`, etc.

**Use when**: The artifact affects a specific domain; typically one per artifact.

### **3. Category Labels**
Describe the nature of the decision: `pattern`, `policy`, `operational`, `migration`, `tool-selection`, `naming-convention`, `security-baseline`, etc.

**Use when**: The label adds useful discovery context.

### **4. Impact Tags**
Describe scope and significance: `breaking-change`, `high-impact`, `low-impact`, `org-wide`, `team-local`, `strategic`, etc.

**Use when**: You want to quickly assess the blast radius of a decision.

### **5. Lifecycle Labels**
Indicate the current state: `active`, `proposed`, `superseded`, `deprecated`, `archived`, `on-hold`.

**Use when**: A workflow tool or report needs a searchable status label. The document `status` field remains authoritative.

---

## **How to Tag Artifacts**

### **Quick Start**

Add an optional `labels:` field to the top of a document:

```yaml
---
labels: [kubernetes, platform]
---

# Title of Your Artifact
```

### **Rules**

- **All lowercase**: Hyphens for multi-word tags (e.g., `tool-selection`, not `toolSelection`)
- **No minimum**: Use labels only when they improve discovery
- **Maximum reasonable**: Use as many labels as needed for clarity, but avoid over-labeling
- **Only approved tags**: See [tags.md](tags.md) for the complete list
- **No duplicates**: Do not use the same tag twice in one artifact

### **Examples**

**RFC: Tool Evaluation**
```yaml
---
labels: [kubernetes, platform]
---
```

**ADR: Infrastructure Pattern**
```yaml
---
labels: [terraform, aws, platform]
---
```

**Standard: Naming Convention**
```yaml
---
labels: [naming-convention, networking]
---
```

---

## **How Tags Support Governance**

### **For Engineers**
- Search for all decisions affecting your domain or technology
- Understand the impact level before diving into a decision
- See the current status of a decision (active, deprecated, etc.)
- Navigate related artifacts quickly through consistent tagging

### **For the ARB**
- Report on decision frequency and trends by technology or domain
- Identify gaps in governance (e.g., "We have no standards for X")
- Triage RFCs and ADRs by impact level
- Assess backward compatibility impact of `breaking-change` tags

### **For the Standards Committee**
- Track which standards are active vs. deprecated
- Identify standards that need updates based on technology tags
- Report on domain coverage and consistency

### **For Leadership**
- Understand organizational investment in specific technologies
- Track progress on strategic initiatives tagged `strategic`
- Identify areas of high volatility or change (`proposed` lifecycle)

---

## **Tag Reference**

For the complete list of approved tags with descriptions, see:

- [tags.md](tags.md) — All approved tags organized by category

For tagging rules and requirements, see:

- [standard.md](standard.md) — Formal tagging standard and requirements

---

## **Proposing New Tags**

If an approved tag doesn't fit your artifact, propose a new tag:

1. **Check existing tags** in [tags.md](tags.md) to avoid duplication
2. **Write an RFC or Standards Committee discussion** proposing the tag
3. **Justify** why the tag improves discoverability or governance
4. **Get approval** through Standards Committee consensus
5. **Update** [tags.md](tags.md) once approved

New tags should be:
- Lowercase and hyphenated
- Short (2–3 words max)
- Distinct from existing tags
- Applicable to multiple artifacts

---

## **Tagging Best Practices**

### **Do**
- ✅ Use tags consistently to improve searchability
- ✅ Use labels only when they improve discovery
- ✅ Update tags if an artifact's status changes (e.g., `proposed` → `active`)
- ✅ Use technology tags to identify cross-cuts (e.g., all Kubernetes decisions)
- ✅ Review and update tags during artifact reviews

### **Don't**
- ❌ Invent new tags; use only approved tags from [tags.md](tags.md)
- ❌ Over-tag with redundant tags (e.g., both `aws` and `cloud`)
- ❌ Forget to update tags when an artifact changes status or scope
- ❌ Tag team-specific decisions as `org-wide`
- ❌ Use labels as a substitute for taxonomy or document status

---

## **Contact and Questions**

If you have questions about tagging:

- Review [tags.md](tags.md) for approved tags and examples
- Review [standard.md](standard.md) for tagging rules and requirements
- Propose new tags or changes to the Standards Committee
- Tag the Standards Committee in a GitHub discussion or email for guidance

---

## **Next Steps**

New artifacts MAY include labels immediately. Existing labels should be migrated only when they provide useful discovery metadata.

**Start tagging today** — it takes 30 seconds and makes decisions much easier to find.

---
