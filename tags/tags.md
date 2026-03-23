# **Approved Tags**

This document defines all approved tags for RFCs, ADRs, and Standards. Tags are lowercase, short, and consistently applied to improve discoverability and cross-referencing across governance artifacts.

Tags are organized into five categories: **Technology**, **Domain**, **Category**, **Impact**, and **Lifecycle**.

---

## **Technology Tags**

Technology tags identify the platforms, languages, frameworks, and tools involved in a decision.

| Tag | Description |
|-----|-------------|
| `kubernetes` | Kubernetes container orchestration |
| `terraform` | Terraform infrastructure as code |
| `aws` | Amazon Web Services |
| `azure` | Microsoft Azure |
| `gcp` | Google Cloud Platform |
| `cicd` | Continuous integration / continuous deployment |
| `github` | GitHub version control and automation |
| `docker` | Docker containerization |
| `helm` | Helm package manager |
| `monitoring` | Monitoring, observability, and alerting |
| `logging` | Logging and log aggregation |
| `security-tools` | Security tooling and controls |
| `networking-tools` | Network infrastructure and connectivity |
| `storage` | Data storage and persistence |
| `database` | Database systems |
| `messaging` | Message queues and event streaming |
| `api` | API design and management |

---

## **Domain Tags**

Domain tags identify the organizational or technical domain affected by the decision.

| Tag | Description |
|-----|-------------|
| `platform` | Platform engineering and infrastructure |
| `devops` | DevOps practices and tooling |
| `security` | Security and compliance (organizational domain) |
| `networking` | Networking and connectivity (organizational domain) |
| `identity` | Identity and access management (IAM) |
| `operations` | Operational procedures and runbooks |
| `applications` | Application development and deployment |
| `data` | Data engineering and analytics |
| `cloud` | Cloud infrastructure and services |
| `governance` | Governance structure and processes |

---

## **Category Tags**

Category tags describe the nature or type of the artifact or decision.

| Tag | Description |
|-----|-------------|
| `pattern` | Architectural or design pattern |
| `policy` | Policy or enforcement rule |
| `operational` | Operational guidance or procedure |
| `migration` | Migration strategy or plan |
| `deprecation` | Deprecation or decommissioning |
| `tool-selection` | Tool or platform selection |
| `standards-update` | Update to existing standards |
| `infrastructure` | Infrastructure architecture or design |
| `process` | Process or workflow change |
| `naming-convention` | Naming or tagging scheme |
| `security-baseline` | Security requirements or baseline |

---

## **Impact Tags**

Impact tags describe the scope and significance of the decision.

| Tag | Description |
|-----|-------------|
| `breaking-change` | Breaks backward compatibility or requires migration |
| `high-impact` | Affects multiple teams or systems significantly |
| `low-impact` | Affects a single team or system with minimal risk |
| `org-wide` | Applies to the entire organization |
| `team-local` | Applies to a single team only |
| `experimental` | Experimental or time-limited decision |
| `strategic` | Long-term strategic decision |

---

## **Lifecycle Tags**

Lifecycle tags indicate the current state of an artifact or decision.

| Tag | Description |
|-----|-------------|
| `active` | Currently active and in use |
| `proposed` | Under consideration or in discussion |
| `superseded` | Replaced by a newer decision |
| `deprecated` | Scheduled for removal or replacement |
| `archived` | No longer active, kept for historical reference |
| `on-hold` | Intentionally paused or deferred |

---

## **Tag Usage Rules**

1. **Minimum Tags**: Every artifact must have at least one tag from **Category** and one from **Lifecycle**.
2. **Technology Tags**: Add technology tags only if the artifact discusses or affects a specific technology.
3. **Domain Tags**: Add domain tags to indicate the primary domain affected.
4. **Impact Tags**: RFCs and ADRs should include impact tags; Standards should include them if relevant.
5. **Multiple Tags**: Artifacts may have multiple tags from any category; use as many as needed for clarity.
6. **No Redundancy**: Avoid tagging with both a parent and child concept (e.g., `azure` and `cloud` together is redundant; use `azure`).

---

## **Adding New Tags**

New tags are proposed through the following process:

1. **Propose** the tag in an RFC or discussion with the Standards Committee.
2. **Justify** why the tag is needed and how it improves discoverability.
3. **Approve** the tag through Standards Committee consensus.
4. **Document** the new tag in this file and notify all teams.

Proposed tags should follow these rules:
- Lowercase, hyphenated, no spaces  
- Short (2–3 words max)  
- Distinct from existing tags  
- Applicable to multiple artifacts  

---

## **Deprecating Tags**

Tags are deprecated when they are no longer useful or have been superseded.

1. Mark the tag as `deprecated` in this file.
2. Communicate the deprecation to all teams with a 30-day notice.
3. Update existing artifacts to use replacement tags.
4. Remove the tag after the transition period.

---
