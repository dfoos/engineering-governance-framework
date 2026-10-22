# Cloud Operations Architecture Governance Taxonomy

A lightweight, public framework for organizing Architecture Decision Records (ADRs), Standards, and Requests for Comments (RFCs).

The framework uses one shared architecture taxonomy for ADRs and Standards. RFCs remain sequential workflow records and do not require taxonomy classifications.

---

## 1. Core Model

Each document has a permanent identifier:

```text
ADR-0042
STD-0017
RFC-0029
```

The identifier is independent of the taxonomy and does not change when the taxonomy evolves.

```text
Document ID = the individual record
Taxonomy    = where the record belongs in the architecture library
```

Think of it like a library:

```text
Document ID             = the book
Primary classification  = the aisle or section
Reusable classification = the shelf
```

Multiple ADRs and Standards can share the same taxonomy value.

---

## 2. Why the Taxonomy Is Needed

A flat registry works when an organization has only a small number of ADRs and Standards. As the collection grows, sequential document numbers and keyword search alone become less effective. Titles change, authors use different terminology, technologies span multiple platforms, and several records may address different parts of the same architectural concern.

The taxonomy provides a stable architecture structure above individual documents. It separates permanent identity from architectural placement:

```text
ADR-0042   = the permanent decision record
4300.2100  = Cloud Foundations / Naming
```

The document number remains unchanged while the registry can still be browsed, filtered, validated, and reorganized as the architecture practice matures.

### Problems the Taxonomy Solves

#### 1. A growing registry becomes difficult to navigate

Sequential identifiers show when records were created, but they do not show where those records belong. Taxonomy allows users to browse decisions and requirements by architecture area instead of reading the entire registry.

#### 2. Similar records are difficult to discover

Records may address the same concern without using the same title. Grouping ADRs and Standards under a shared classification makes overlap, duplication, and conflict easier to identify.

```text
ADR-0042  Cloud Resource Naming Approach       4300.2100
STD-0017  Cloud Resource Naming Standard       4300.2100
ADR-0061  Subscription Naming Boundaries       4300.2100
```

#### 3. Decisions and requirements become disconnected

An ADR explains why an approach was selected. A Standard defines what implementations must follow. A shared taxonomy connects rationale with governed requirements without combining them into the same document.

#### 4. Vendor and product names become the organizing model

Vendor-based organization does not age well. Products are renamed, replaced, or used across multiple architecture areas. Taxonomy classifies records by durable architecture concern while vendors, products, services, and versions remain metadata.

#### 5. New categories are created inconsistently

Without a shared structure, teams create overlapping categories based on local terminology. Defined primary and reusable classifications encourage consistent placement and make it clearer when a new branch is actually needed.

#### 6. Governance automation lacks dependable structure

An AI agent or validation workflow needs more than free-form titles. A defined taxonomy and structured registries provide reliable inputs for duplicate detection, classification recommendations, relationship checks, registry validation, and document generation.

#### 7. Reorganization can break document references

Embedding classification into a document identifier makes reclassification disruptive. Keeping the ID and taxonomy separate allows the classification model to evolve without renumbering records or breaking links.

### Scaling Principle

The taxonomy is not intended to describe every product, service, or implementation detail. It provides enough durable structure to keep governance understandable as the number of records, authors, teams, and technologies increases.

```text
Use the document ID for identity.
Use the taxonomy for architectural placement.
Use metadata for products and implementation details.
Use relationships to connect RFCs, ADRs, and Standards.
```

The goal is controlled growth, not perfect categorization. Start with broad, durable branches, reuse existing classifications where possible, and add branches only when repeated governance needs demonstrate that the distinction is useful.

---

## 3. Document Types

### Architecture Decision Record

An ADR records a durable architecture decision, including context, alternatives, the decision, and consequences.

```text
ADR-0042: Adopt Workload Identity for CI/CD Deployments
Taxonomy: 3200.2400
Status: Accepted
```

### Standard

A Standard defines a required or strongly governed rule, convention, control, or implementation expectation.

```text
STD-0017: Cloud Resource Naming Standard
Taxonomy: 4300.2100
Status: Active
```

ADRs and Standards use the same taxonomy because both belong to the same architecture landscape. Their document types distinguish a decision from a governed requirement.

### Request for Comments

An RFC is a proposal used to gather feedback before a significant change is approved or implemented.

```text
RFC-0029: Introduce Managed Kubernetes for Shared Services
Status: In Review
```

RFCs do not require taxonomy. They are workflow records and can reference the ADRs or Standards produced by the review.

---

## 4. Shared Architecture Taxonomy

### Classification Format

```text
DDDD.SSSS
│    │
│    └──── Optional reusable classification
└───────── Primary architecture classification
```

Examples:

```text
4300.2400 = Cloud Foundations / Design
8100.2100 = Storage Platforms / Naming
9200.2600 = Infrastructure as Code / Testing and Validation
```

The reusable classification is optional. A record may use only its primary classification:

```text
3200
4300
7200
```

### Primary Architecture Classifications

```text
1000 Architecture Governance
├── 1100 Architecture Practice
├── 1200 Decision Management
├── 1300 Technology Lifecycle
├── 1400 Risk and Compliance
└── 1500 Portfolio and Roadmap Governance

3000 Identity and Security
├── 3100 Identity Services
├── 3200 Authorization and RBAC
├── 3300 Privileged Access
├── 3400 PKI and Certificates
└── 3500 Security Operations

4000 Infrastructure
├── 4100 Physical Infrastructure
├── 4200 Virtualization
├── 4300 Cloud Foundations
├── 4400 Shared Infrastructure Services
└── 4500 Infrastructure Management

5000 Compute and Hosting
├── 5100 Compute Infrastructure
├── 5200 Workload Platforms
├── 5300 Image Management
├── 5400 Containers and Orchestration
└── 5500 Serverless Computing

6000 Application and Delivery Platforms
├── 6100 Workforce Computing
├── 6200 Application Platforms
├── 6300 Integration Platforms
├── 6400 Management Platforms
└── 6500 Application Delivery Platforms

7000 Networking and Connectivity
├── 7100 DNS and Name Resolution
├── 7200 Connectivity and Routing
├── 7300 Network Security
├── 7400 Segmentation and Load Balancing
└── 7500 Access and Service Connectivity

8000 Data and Storage
├── 8100 Storage Platforms
├── 8200 Data Platforms
├── 8300 Backup and Recovery
├── 8400 Data Lifecycle
└── 8500 Data Integration and Movement

9000 Automation and Operations
├── 9100 Automation and CI/CD
├── 9200 Infrastructure as Code
├── 9300 Observability
├── 9400 Operations
└── 9500 Resilience and Continuity
```

### Reusable Classifications

```text
2000 Reusable Classifications
├── 2100 Naming
├── 2200 Tagging and Metadata
├── 2300 Configuration
├── 2400 Design
├── 2500 Operations
├── 2600 Testing and Validation
├── 2700 Security
└── 2800 Lifecycle Management
```

Examples:

```text
4300.2200 = Cloud Foundations / Tagging and Metadata
5400.2300 = Containers and Orchestration / Configuration
6500.2400 = Application Delivery Platforms / Design
8100.2100 = Storage Platforms / Naming
9200.2600 = Infrastructure as Code / Testing and Validation
```

Not every primary classification needs every reusable classification.

### When to Use 2000 Directly

Use `2000.xxxx` when a decision or Standard intentionally applies across multiple architecture areas.

```text
Enterprise-wide resource tagging approach
→ 2000.2200
```

Use `xxxx.2xxx` when that concern is scoped to one architecture area.

```text
Cloud resource tagging       → 4300.2200
Storage naming               → 8100.2100
Infrastructure as Code tests → 9200.2600
```

Simple rule:

```text
Global concern  → 2000.xxxx
Scoped concern  → xxxx.2xxx
No useful shelf → xxxx
```

---

## 5. Relationships Between Records

An ADR and a Standard may share a taxonomy while serving different purposes.

```text
ADR-0042
Taxonomy: 4300.2100
Decision: Establish a common naming approach for cloud resources

STD-0017
Taxonomy: 4300.2100
Requirement: Define the required cloud resource naming format
```

The ADR explains why the approach was selected. The Standard defines what implementations must follow.

```text
RFC-0048
   │
   ├── proposes a naming approach
   ├── results in ──────> ADR-0042  4300.2100
   └── may create/update -> STD-0017 4300.2100
```

---

## 6. Examples

### ADRs

| ADR | Title | Taxonomy |
|---|---|---:|
| ADR-0001 | Adopt a Multi-Account Cloud Landing Zone | `4300.2400` |
| ADR-0002 | Use Role-Based Access for Cloud Administration | `3200.2400` |
| ADR-0003 | Standardize Immutable Machine Images | `5300.2300` |
| ADR-0004 | Use Managed Kubernetes for Shared Workloads | `5400.2400` |
| ADR-0005 | Adopt Private Connectivity for Managed Services | `7500.2400` |
| ADR-0006 | Standardize Infrastructure as Code Testing | `9200.2600` |
| ADR-0007 | Establish an Enterprise Resource Tagging Model | `2000.2200` |
| ADR-0008 | Centralize Platform Observability | `9300.2400` |

### Standards

| Standard | Title | Taxonomy |
|---|---|---:|
| STD-0001 | Cloud Resource Naming Standard | `4300.2100` |
| STD-0002 | Required Cloud Resource Metadata | `4300.2200` |
| STD-0003 | Privileged Access Standard | `3300.2700` |
| STD-0004 | Infrastructure as Code Repository Standard | `9200.2300` |
| STD-0005 | Machine Image Baseline Standard | `5300.2300` |
| STD-0006 | Platform Logging Standard | `9300.2500` |
| STD-0007 | Architecture Documentation Standard | `1000.2300` |

---

## 7. RFC Organization

RFCs use sequential identifiers without taxonomy:

```text
RFC-0001
RFC-0002
RFC-0003
```

Use metadata for discovery and workflow:

```yaml
id: RFC-0029
title: Introduce Managed Kubernetes for Shared Services
status: in-review
owners:
  - platform-engineering
created: 2026-10-22
proposed-taxonomy: 5400.2400
resulting-adrs: []
resulting-standards: []
labels:
  - kubernetes
  - containers
  - platform
```

`proposed-taxonomy` is optional guidance for resulting ADRs or Standards. It does not classify the RFC itself.

Recommended statuses:

```text
Draft
In Review
Approved
Rejected
Withdrawn
Superseded
Implemented
```

---

## 8. Registries

Maintain a registry for each document type. Registries are the source for the next available ID and the primary index for duplicate detection.

### ADR Registry

| ADR | Title | Taxonomy | Status | Supersedes |
|---|---|---:|---|---|
| ADR-0001 | Adopt a Multi-Account Cloud Landing Zone | `4300.2400` | Accepted | |
| ADR-0002 | Use Role-Based Access for Cloud Administration | `3200.2400` | Accepted | |

### Standards Registry

| Standard | Title | Taxonomy | Status | Supersedes |
|---|---|---:|---|---|
| STD-0001 | Cloud Resource Naming Standard | `4300.2100` | Active | |
| STD-0002 | Required Cloud Resource Metadata | `4300.2200` | Draft | |

### RFC Registry

| RFC | Title | Status | Resulting Records |
|---|---|---|---|
| RFC-0001 | Introduce Managed Kubernetes | Implemented | ADR-0004, STD-0005 |
| RFC-0002 | Centralize Platform Logging | In Review | Pending |

Never reuse an ID, including after a record is rejected, withdrawn, superseded, or retired.

---

## 9. Recommended Repository Structure

```text
architecture-governance/
├── README.md
├── taxonomy.md
├── agent-instructions.md
├── adr/
│   ├── registry.md
│   ├── template.md
│   └── ADR-0001-multi-account-cloud-landing-zone.md
├── standards/
│   ├── registry.md
│   ├── template.md
│   └── STD-0001-cloud-resource-naming.md
└── rfc/
    ├── registry.md
    ├── template.md
    └── RFC-0001-managed-kubernetes.md
```

---

## 10. Recommended Metadata

### ADR

```yaml
id: ADR-0042
title: Adopt Workload Identity for CI/CD Deployments
status: accepted
taxonomy: 3200.2400
primary-classification: Authorization and RBAC
reusable-classification: Design
owners: [cloud-platform]
related-rfcs: [RFC-0027]
related-standards: [STD-0014]
supersedes: null
superseded-by: null
```

### Standard

```yaml
id: STD-0017
title: Cloud Resource Naming Standard
status: active
taxonomy: 4300.2100
primary-classification: Cloud Foundations
reusable-classification: Naming
owners: [architecture]
related-rfcs: [RFC-0048]
related-adrs: [ADR-0042]
supersedes: null
superseded-by: null
```

### RFC

```yaml
id: RFC-0029
title: Introduce Managed Kubernetes for Shared Services
status: in-review
owners: [platform-engineering]
proposed-taxonomy: 5400.2400
resulting-adrs: []
resulting-standards: []
labels: [kubernetes, platform]
```

---

## 11. Rules

1. Document identifiers are permanent and independent of taxonomy.
2. Taxonomy values are classifications, not unique identifiers.
3. ADRs and Standards use the same architecture taxonomy.
4. Multiple ADRs and Standards may share a taxonomy value.
5. ADRs describe durable decisions.
6. Standards define governed expectations.
7. RFCs propose changes and do not receive taxonomy by default.
8. Classify by architectural concern, not merely by vendor or product.
9. Keep vendors, products, versions, and environments as metadata.
10. Reusable classifications are optional.
11. Add branches only for durable, repeated governance needs.
12. Preserve unused numbering space for growth.
13. Never reuse document identifiers.
14. Link related RFCs, ADRs, and Standards.
15. Search current and historical records before creating a new one.
16. Supersede an existing record when a decision or requirement is replaced.

---

## 12. Quick Classification Guide

### ADR or Standard

```text
What architecture area owns the decision or requirement?
→ Select the primary classification.

Does Naming, Tagging, Configuration, Design, Operations,
Testing, Security, or Lifecycle add useful meaning?
→ Add the optional reusable classification.

Everything else
→ Record as metadata.
```

### RFC

```text
Assign the next RFC number.
Use status, labels, owners, and relationships for discovery.
Optionally recommend taxonomy for resulting ADRs or Standards.
Do not classify the RFC itself.
```

---

## 13. AI Agent Prompt

Use the following as starting system instructions for an AI agent that works with the repository.

```text
You are an Architecture Governance Registry Agent.

Your job is to help users discover, classify, draft, and maintain Architecture Decision Records (ADRs), Requests for Comments (RFCs), and Standards stored in this repository.

The taxonomy exists to keep governance discoverable and consistent as the number of records, contributors, teams, and technologies grows. Preserve the separation between permanent document identity, architectural classification, implementation metadata, and record relationships.

AUTHORITATIVE SOURCES

Before making a recommendation, read:
1. taxonomy.md
2. adr/registry.md
3. standards/registry.md
4. rfc/registry.md
5. Relevant ADR, Standard, and RFC files
6. The applicable template

Use the repository as the source of truth. Do not assume a record does not exist based only on its title. Search titles, summaries, context, decisions, requirements, taxonomy values, labels, aliases, technologies, and relationships.

DOCUMENT MODEL

- ADR-#### records a durable architecture decision.
- STD-#### defines a governed rule, convention, control, or requirement.
- RFC-#### proposes a change and gathers feedback.
- ADRs and Standards use the shared DDDD.SSSS architecture taxonomy.
- RFCs do not receive taxonomy by default.
- An RFC may recommend taxonomy for records it produces.
- IDs are sequential, permanent, and never reused.
- Taxonomy values are classifications, not unique identifiers.
- Multiple ADRs and Standards may share a taxonomy value.

CORE CAPABILITIES

1. Duplicate and overlap detection
   - Search active, draft, proposed, superseded, rejected, withdrawn, and retired records.
   - Identify exact duplicates, strong overlaps, partial overlaps, related records, and conflicts.
   - Explain why each result is relevant.
   - Do not claim no record exists until all registries and relevant files are searched.

2. Taxonomy recommendations
   - Classify by the architecture concern that owns the decision or requirement.
   - Add a reusable classification only when it improves discovery.
   - Do not classify solely by vendor, product, version, or technology.
   - Provide a primary recommendation, rationale, and up to two alternatives.

3. Propose an ADR from an RFC
   - Read the complete RFC and linked or overlapping records.
   - Extract the durable decision, context, drivers, options, consequences, risks, dependencies, and open questions.
   - Do not treat discussion or unapproved proposals as accepted decisions.
   - Use adr/template.md.
   - Recommend the next ADR ID without reserving it unless authorized.
   - Link the RFC and related records.

4. Propose a Standard from an ADR
   - Read the complete ADR and linked records.
   - Extract only requirements supported by the accepted decision.
   - Separate mandatory requirements from recommendations and examples.
   - Define scope, requirements, exceptions, validation, ownership, and lifecycle.
   - Use standards/template.md.
   - Recommend the next Standard ID without reserving it unless authorized.

5. Propose an RFC
   - Search existing ADRs, Standards, and RFCs first.
   - Describe the problem, motivation, scope, proposal, alternatives, impact, risks, migration, and open questions.
   - Use rfc/template.md.
   - Recommend the next RFC ID without reserving it unless authorized.

6. Registry maintenance
   - Validate unique and sequential IDs.
   - Validate taxonomy values against taxonomy.md.
   - Validate relationships and flag broken references.
   - Flag missing files, duplicate IDs, invalid statuses, malformed metadata, and registry/file mismatches.
   - Never silently alter an accepted ADR or active Standard.
   - Propose a change set before writing changes.

REQUIRED SEARCH PROCESS

For every creation or classification request:
1. Normalize the concept into architecture terms and synonyms.
2. Search all three registries.
3. Search full document content.
4. Search relevant taxonomy branches.
5. Search related-rfcs, related-adrs, related-standards, supersedes, and superseded-by.
6. Compare the requested scope with existing records.
7. Report findings before recommending a new record.

DUPLICATE ASSESSMENT

Use one of these classifications:
- Exact match: the same decision, proposal, or requirement exists.
- Strong overlap: most of the scope is already covered.
- Partial overlap: part is covered and may need an amendment or additional record.
- Related: relevant context exists, but the purpose is distinct.
- Conflict: an existing record makes an incompatible decision or requirement.
- No material match: no meaningful overlap was found after the required searches.

Never use title similarity alone.

TAXONOMY DECISION PROCESS

Ask:
1. What architecture area owns the decision or requirement?
2. Is the concern global or scoped to one area?
3. Does a reusable classification add useful meaning?
4. Is the classification based on a durable concern rather than a vendor or product?
5. Does an existing branch fit without creating a new branch?

Use:
- 2000.xxxx for a global reusable concern.
- xxxx.2xxx for a concern scoped to one architecture area.
- xxxx when no reusable classification adds useful meaning.

OUTPUT FOR DISCOVERY

Request summary:
<one sentence>

Existing records:
- <ID, title, status, taxonomy if applicable, and relevance>

Assessment:
<Exact match | Strong overlap | Partial overlap | Related | Conflict | No material match>

Recommendation:
<Create | Update | Supersede | Link | No action>

OUTPUT FOR TAXONOMY

Recommended taxonomy: <DDDD.SSSS or DDDD>
Primary classification: <name>
Reusable classification: <name or None>
Rationale: <brief explanation>
Alternatives:
- <classification and tradeoff>
Confidence: <High | Medium | Low>

OUTPUT FOR A PROPOSED DOCUMENT

Preflight findings:
- Existing related records
- Duplicate or conflict assessment
- Recommended next ID
- Recommended taxonomy for an ADR or Standard

Draft:
<complete document using the repository template>

Registry changes:
<exact rows and relationship updates required>

VALIDATION RULES

- Never invent repository content.
- Distinguish repository facts from recommendations.
- Reference supporting record IDs.
- Do not create a taxonomy branch when an existing one fits.
- Do not assign taxonomy to an RFC.
- Do not confuse an RFC proposal with an accepted ADR decision.
- Do not turn every ADR statement into a mandatory requirement.
- Do not reuse IDs.
- Do not modify accepted or active records outside the change process.
- If evidence is insufficient, state what is missing and provide a provisional recommendation.

EXAMPLE USER REQUESTS

- Check whether we already have an ADR for centralized platform logging.
- Does a Standard already cover required resource tags?
- Recommend taxonomy for an ADR about private endpoints for managed databases.
- Turn RFC-0029 into a proposed ADR.
- Propose a Standard from ADR-0042.
- Identify records that overlap with this proposal.
- Validate registry entries against repository files.
- Find invalid or missing taxonomy values.
- Recommend whether this should be an RFC, ADR, Standard, or combination.
```

### Example Agent Request

```text
Review the following proposal against the ADR, RFC, and Standards registries.

Proposal:
All production cloud resources must include owner, environment,
data-classification, and cost-center metadata.

Perform the following:
1. Check whether an ADR, RFC, or Standard already covers this requirement.
2. Identify exact matches, overlaps, related records, and conflicts.
3. Recommend a new RFC, ADR, Standard, or update to an existing record.
4. If an ADR or Standard is appropriate, recommend taxonomy.
5. Provide the likely next ID without reserving it.
6. Draft the recommended document using the repository template.
7. List required registry and relationship changes.
```

---

## 14. Bottom Line

Use three independent document sequences:

```text
ADR-#### = durable architecture decisions
STD-#### = governed Standards
RFC-#### = proposals and review workflow
```

Use one shared architecture taxonomy:

```text
DDDD.SSSS = architecture classification for ADRs and Standards
```

RFCs remain sequential and rely on metadata plus links to the ADRs and Standards they produce.
