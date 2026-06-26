# Azure Compliance & Governance – Final Report  
## Tasks 1–5 (Complete Submission)

---

# ✅ Task 1 – Overview of Azure Compliance Areas

## Main Areas Reviewed
1. Microsoft Defender for Cloud → Regulatory Compliance  
2. Azure Policy → Assignments / Definitions  
3. Azure Policy → Compliance  

---

## Summary Table

| Area | Purpose | Visible Metrics | Use in Operations |
|------|---------|----------------|-------------------|
| Microsoft Defender for Cloud → Regulatory Compliance | View compliance posture and standards | Passed/Failed controls, compliance percentage | Assess overall security and compliance |
| Regulatory Compliance → Control Domains | View status of each security domain | Passed/Failed per domain | Identify weak areas needing action |
| Azure Policy | Define and enforce governance rules | Policies, Initiatives, Effects | Control resource behavior |
| Azure Policy → Compliance | Evaluate policy compliance | Compliance %, non-compliant resources | Detect governance issues |

---

# ✅ Task 2 – Subscription Compliance Status

## Framework Active
- Microsoft Cloud Security Benchmark (MCSB)

## Overall Status
- 57 of 63 controls passed (~90%)

## Observations
1. Logging & Threat Detection has several non-compliant controls.  
2. Governance & Strategy shows failed or unevaluated controls.  
3. Backup & Recovery is not enabled or not evaluated.

## Priority Actions
- Enable diagnostic logs  
- Introduce standardized tags  
- Review and enable backup for critical resources  

---

# ✅ Task 3 – From Rule to Evidence

## Requirement
PA‑1 — Separate and limit highly privileged/administrative users

## Assessments
- More than one owner should be assigned → ❌ Failed  
- Max 3 owners → ✔ Passed  
- Guest owners removed → ✔ Passed  
- Disabled owners removed → ✔ Passed  

## Affected Resource
- Subscription (1 resource affected)

## Severity / Status
- Non‑compliant (1 failed assessment)

## Summary
Azure converts a high-level requirement such as PA‑1 into measurable automated assessments.  
These assessments scan real resources and report Passed/Failed status.  
Azure links each failed control to the specific affected resource, producing auditable evidence.  
This evidence appears in both Azure Policy Compliance and Defender for Cloud regulatory dashboards.

---

# ✅ Task 4 – Governance via Azure Policy

## Policy / Initiative Name
ASC Default (Microsoft Defender for Cloud default initiative)

## Scope
Subscription — Azure for Students

## Effect
Mixed (Audit, AuditIfNotExists, DeployIfNotExists)

## Compliance Status
- Non‑compliant  
- 0% resource compliance  
- 1 non‑compliant resource  
- 12 non‑compliant policies  
- 223 total policies

## Controlled Behavior
This initiative audits and enforces secure configurations across incident response, logging, identity, network, and data protection domains.  
In this subscription, IR‑3 and IR‑5 show the highest number of failures.

## Compliance Link
The initiative provides direct evidence for Microsoft Cloud Security Benchmark controls.  
Any failed configuration appears as non‑compliant in both Azure Policy and Defender for Cloud, enabling traceable and auditable compliance reporting.

---

# ✅ Task 5 – Simple Governance Measure (Variant B)

## Measure
Introduce a mandatory tagging standard using the built‑in policy  
**“Require a tag and its value”**

## Goal
Enforce consistent tagging across all resources to improve governance and auditability.

## Scope
Subscription — Azure for Students

## Policy Type
Built‑in Azure Policy (Audit or Deny)

## Expected Benefit
- Improved governance  
- Better visibility and classification of resources  
- Stronger compliance alignment  
- Enhanced cost and ownership tracking  

## Evidence
- Azure Policy → Compliance  
- Defender for Cloud → Regulatory Compliance  


