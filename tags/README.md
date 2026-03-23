# **Tagging System**

This directory defines the tagging system for RFCs, ADRs, and Standards. Tags improve discoverability, cross-referencing, and governance of engineering decisions across the organization.

---

## **What Are Tags?**

Tags are short, lowercase labels applied to every RFC, ADR, and Standard to categorize and relate artifacts across technology, domain, impact, and lifecycle.

Tags enable:

- **Quick Discovery**: Find all decisions related to a technology, domain, or impact level
- **Cross-Referencing**: Understand how decisions in different domains connect
- **Impact Visibility**: Track which decisions affect which teams and systems
- **Governance Reporting**: Analyze trends in decision-making and identify gaps
- **Navigation**: Engineers know instantly which artifacts are relevant to their work

---

## **Five Tag Categories**

Tags are organized into five categories:

### **1. Technology Tags**
Identify platforms, languages, frameworks, and tools: `kubernetes`, `terraform`, `aws`, `azure`, `cicd`, etc.

**Use when**: The artifact directly concerns a specific technology.

### **2. Domain Tags**
Identify organizational or technical domains: `platform`, `devops`, `security`, `networking`, `identity`, `operations`, etc.

**Use when**: The artifact affects a specific domain; typically one per artifact.

### **3. Category Tags**
Describe the nature of the decision: `pattern`, `policy`, `operational`, `migration`, `tool-selection`, `naming-convention`, `security-baseline`, etc.

**Use when**: Every artifact needs exactly one category tag.

### **4. Impact Tags**
Describe scope and significance: `breaking-change`, `high-impact`, `low-impact`, `org-wide`, `team-local`, `strategic`, etc.

**Use when**: You want to quickly assess the blast radius of a decision.

### **5. Lifecycle Tags**
Indicate the current state: `active`, `proposed`, `superseded`, `deprecated`, `archived`, `on-hold`.

**Use when**: Every artifact needs exactly one lifecycle tag.

---

## **How to Tag Artifacts**

### **Quick Start**

Add a `tags:` field to the top of your RFC, ADR, or Standard file:

```yaml
---
tags: [category-tag, lifecycle-tag, domain-tag, impact-tag, technology-tag]
---

# Title of Your Artifact
```

### **Rules**

- **All lowercase**: Hyphens for multi-word tags (e.g., `tool-selection`, not `toolSelection`)
- **Minimum five tags**: One from each category (Category, Lifecycle, Domain, Impact, and optionally Technology)
- **Maximum reasonable**: Use as many tags as needed for clarity, but avoid over-tagging
- **Only approved tags**: See [tags.md](tags.md) for the complete list
- **No duplicates**: Do not use the same tag twice in one artifact

### **Examples**

**RFC: Tool Evaluation**
```yaml
---
tags: [tool-selection, proposed, platform, high-impact, kubernetes]
---
```

**ADR: Infrastructure Pattern**
```yaml
---
tags: [pattern, active, platform, org-wide, terraform, aws]
---
```

**Standard: Naming Convention**
```yaml
---
tags: [naming-convention, active, networking]
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
- ✅ Include at least one tag from each required category
- ✅ Update tags if an artifact's status changes (e.g., `proposed` → `active`)
- ✅ Use technology tags to identify cross-cuts (e.g., all Kubernetes decisions)
- ✅ Review and update tags during artifact reviews

### **Don't**
- ❌ Invent new tags; use only approved tags from [tags.md](tags.md)
- ❌ Over-tag with redundant tags (e.g., both `aws` and `cloud`)
- ❌ Forget to update tags when an artifact changes status or scope
- ❌ Tag team-specific decisions as `org-wide`
- ❌ Leave an artifact untagged

---

## **Contact and Questions**

If you have questions about tagging:

- Review [tags.md](tags.md) for approved tags and examples
- Review [standard.md](standard.md) for tagging rules and requirements
- Propose new tags or changes to the Standards Committee
- Tag the Standards Committee in a GitHub discussion or email for guidance

---

## **Next Steps**

All new artifacts must be tagged immediately. Existing artifacts will be tagged during the next review cycle.

**Start tagging today** — it takes 30 seconds and makes decisions much easier to find.

---
