# Azure Governance – Task 1: Working Environment & Scope

| Item | Value |
|------|--------|
| **Subscription Name** | Azure for Students |
| **Analysis Scope** | Subscription-level (1 subscription) |
| **Directory** | Default Directory |
| **Management Group** | Tenant Root Group |
| **Permissions** | Likely Owner/Contributor (needs verification via IAM) |
| **Visible Defender Areas** | Will be identified in Task 3 |


<p align="center">
  <img src="https://github.com/samanehsalahi2-hub/Sama/blob/main/AZURE/aufgabe%2021/auf21-1.png" alt="My Image" width="800">
</p>


# Task 2 – Azure Security Services Overview

This table summarizes four key Azure security-related services, their purpose, and how each one connects to Microsoft Defender for Cloud.

| Service | What you use it for in Azure | Connection to Microsoft Defender for Cloud |
|--------|-------------------------------|--------------------------------------------|
| **Microsoft Defender for Cloud** | Centralized security posture management, Secure Score, recommendations, attack path analysis, regulatory compliance | Core platform for security posture; many recommendations are based on Azure Policy; integrates with Sentinel for alert correlation |
| **Microsoft Sentinel** | Cloud-native SIEM/SOAR for log analytics, incident detection, and threat response | Ingests alerts from Defender for Cloud; Defender alerts become Sentinel incidents; enhances threat investigation |
| **Microsoft Entra ID** | Identity and access management (users, groups, roles, MFA, Conditional Access) | Identity configuration affects Secure Score; Defender provides identity-related recommendations (e.g., MFA, privileged access) |
| **Azure Key Vault / Managed HSM** | Secure storage for keys, secrets, and certificates; hardware-backed key protection | Defender evaluates Key Vault security posture (e.g., soft delete, purge protection, firewall, logging) |
| **Azure Policy Insights** | Monitoring and evaluating policy compliance across resources | Defender recommendations are built on Azure Policy; compliance results feed into Secure Score and posture evaluation |

<p align="center">
  <img src="https://github.com/samanehsalahi2-hub/Sama/blob/main/AZURE/aufgabe%2021/auf21-2.png" alt="My Image" width="800">
</p>

<p align="center">
  <img src="https://github.com/samanehsalahi2-hub/Sama/blob/main/AZURE/aufgabe%2021/auf21-3.png" alt="My Image" width="800">
</p>

<p align="center">
  <img src="https://github.com/samanehsalahi2-hub/Sama/blob/main/AZURE/aufgabe%2021/auf21--4.png" alt="My Image" width="800">
</p>

<p align="center">
  <img src="https://github.com/samanehsalahi2-hub/Sama/blob/main/AZURE/aufgabe%2021/auf21-5.png" alt="My Image" width="800">
</p>

<p align="center">
  <img src="https://github.com/samanehsalahi2-hub/Sama/blob/main/AZURE/aufgabe%2021/auf21-6.png" alt="My Image" width="800">
</p>

# Task 3 – Security Posture Snapshot (Microsoft Defender for Cloud)

This snapshot summarizes the current security posture of the Azure environment based on the Defender for Cloud dashboard.

## Security Posture Overview

| Item | Value |
|------|--------|
| **Secure Score** | 100% |
| **Total Recommendations** | 6 (all Not evaluated) |
| **Critical / High / Medium / Low** | 0 / 0 / 0 / 0 |
| **Assessed Resources** | 1 |
| **Attack Paths** | 0 |
| **Security Alerts** | 0 |
| **Regulatory Compliance (MCSB)** | 56 of 63 controls passed |

---

## Observations

### Immediately Understood
- Secure Score is clearly displayed.
- Number of recommendations is visible.
- No attack paths or security alerts.
- Compliance score is easy to interpret.

### Requires Further Understanding
- Why all 6 recommendations are in *Not evaluated* state.
- Why Secure Score shows 100% despite existing recommendations.
- Meaning of “Environment Risk” and how it is calculated.
- How Attack Path Analysis works.
- Why only one resource is being assessed.

---

## Notes
The environment appears small and low‑risk, which explains the limited number of assessed resources and the absence of alerts or attack paths. The Not Evaluated recommendations indicate that Defender for Cloud has not fully assessed the configuration or that additional setup may be required.


# Task 4 – Analysis and Prioritization of Security Recommendations

This task analyzes three real security recommendations from Microsoft Defender for Cloud, explains their impact, and prioritizes them based on the needs of the environment.

---

## 1. Email notification for high severity alerts should be enabled

### Description
High‑severity security alerts must trigger email notifications to ensure immediate awareness of potential threats. Without this configuration, critical incidents may go unnoticed.

### Affected Resources
- Subscription: **Azure for Students**

### Security Impact
- Ensures rapid response to high‑severity alerts  
- Reduces risk of delayed detection  
- Critical for small environments with a single Owner account

### Implementation Type
**Quick Win**

### Prerequisites
- Access to: *Defender for Cloud → Environment settings → Email notifications*  
- Owner permissions (already available)

### Status
**Completed**  
Email notifications are enabled for the Owner and additional email addresses.

---

## 2. Email notification to subscription owner for high severity alerts should be enabled

### Description
Subscription owners must receive high‑severity alert notifications to maintain visibility into critical security events.

### Affected Resources
- Subscription Owner (single user)

### Security Impact
- Ensures the Owner is directly notified of critical threats  
- Essential in environments with only one administrative account

### Implementation Type
**Quick Win**

### Prerequisites
- Same configuration page as Recommendation #1  
- Owner email must be added as a recipient

### Status
**Completed**  
Notifications to the subscription Owner are enabled.

---

## 3. Microsoft Defender for Resource Manager should be enabled

### Description
Defender for Resource Manager monitors Azure Resource Manager operations, detects suspicious activity, and alerts on potential misuse of management APIs.

### Affected Resources
- Azure Resource Manager operations for the subscription

### Security Impact
- Detects malicious or unauthorized resource changes  
- Protects the control plane of the Azure environment  
- Important for preventing privilege misuse

### Implementation Type
**Requires Coordination**  
This plan incurs additional cost.

### Prerequisites
- Navigate to: *Defender for Cloud → Environment settings → Defender plans*  
- Enable **Resource Manager** protection

### Status
**Completed**  
Defender for Resource Manager is turned **On**.

---

## Prioritization

| Priority | Recommendation | Reason |
|---------|----------------|--------|
| **1** | Email notification for high severity alerts | Immediate visibility into critical threats |
| **2** | Email notification to subscription owner | Ensures the only Owner receives alerts |
| **3** | Defender for Resource Manager | Important but cost‑based and less urgent |

---

## Summary

All three selected recommendations have been fully implemented.  
These actions significantly improve alert visibility, strengthen control‑plane security, and ensure timely response to high‑severity incidents.

<p align="center">
  <img src="https://github.com/samanehsalahi2-hub/Sama/blob/main/AZURE/aufgabe%2021/auf21-7.png" alt="My Image" width="800">
</p>
<p align="center">
  <img src="https://github.com/samanehsalahi2-hub/Sama/blob/main/AZURE/aufgabe%2021/auf21-8.png" alt="My Image" width="800">
</p>
<p align="center">
  <img src="https://github.com/samanehsalahi2-hub/Sama/blob/main/AZURE/aufgabe%2021/auf21-9.png" alt="My Image" width="800">
</p>
<p align="center">
  <img src="https://github.com/samanehsalahi2-hub/Sama/blob/main/AZURE/aufgabe%2021/auf21-10.png" alt="My Image" width="800">
</p>
<p align="center">
  <img src="https://github.com/samanehsalahi2-hub/Sama/blob/main/AZURE/aufgabe%2021/auf21-11.png" alt="My Image" width="800">
</p>
<p align="center">
  <img src="https://github.com/samanehsalahi2-hub/Sama/blob/main/AZURE/aufgabe%2021/auf21-12.png" alt="My Image" width="800">
</p>
<p align="center">
  <img src="https://github.com/samanehsalahi2-hub/Sama/blob/main/AZURE/aufgabe%2021/auf21-13.png" alt="My Image" width="800">
</p>


# Task 5 – Root Cause, Impact, Fix, Evidence, and Final State

This task provides a detailed analysis of the three selected security recommendations from Microsoft Defender for Cloud.  
Each recommendation includes:  
- Root Cause  
- Impact  
- How it was fixed  
- Evidence  
- Final State  

---

## 1. Email notification for high severity alerts should be enabled

### Root Cause
High‑severity alert notifications were disabled.  
This meant that critical security alerts would not be delivered to administrators.

### Impact
- High‑severity alerts could go unnoticed.  
- Delayed response to security incidents.  
- Increased risk of data loss or compromise.  

### Fix (How it was resolved)
- Navigated to: **Defender for Cloud → Environment settings → Email notifications**  
- Enabled notifications for **High severity alerts**  
- Added the Owner and an additional email address as recipients  
- Saved configuration  

### Evidence
- Screenshot of Email Notifications page showing:  
  - Recipient = Owner  
  - Additional email added  
  - Severity = High  

### Final State
**Completed / Healthy**

---

## 2. Email notification to subscription owner for high severity alerts should be enabled

### Root Cause
The subscription Owner was not explicitly configured to receive high‑severity alert notifications.

### Impact
- The only administrative account (Owner)

- # Task 6 – Final Security Posture Evaluation

This task provides a final evaluation of the Azure environment after completing all previous recommendations and remediation steps. It summarizes the current security posture, improvements made, remaining risks, and overall readiness.

---

## 1. Current Security Posture Summary

After completing the selected recommendations in Task 4 and Task 5, the environment shows the following characteristics:

- **Secure Score:** 100%  
- **Total Recommendations:** 6 (all resolved or not applicable)  
- **Critical / High / Medium / Low:** 0 / 0 / 0 / 0  
- **Attack Paths:** 0  
- **Security Alerts:** 0  
- **Assessed Resources:** 1  
- **Compliance:** 56 of 63 controls passed (Microsoft Cloud Security Benchmark)

The environment is small, low‑risk, and fully monitored.

---

## 2. Improvements Achieved

### ✔ Email Notifications Enabled
High‑severity alerts now notify both the subscription Owner and additional email addresses.  
This ensures rapid awareness of critical incidents.

### ✔ Defender for Resource Manager Enabled
Control‑plane operations are now monitored for suspicious activity.  
This significantly improves protection against unauthorized resource changes.

### ✔ Governance and Visibility Improved
- Alerting is configured  
- Control‑plane protection is active  
- No misconfigurations remain in the selected recommendations  

---

## 3. Remaining Risks and Considerations

Even though the environment is currently healthy, the following considerations remain:

### • Single Owner Account
There is only one administrative account.  
Best practice recommends creating a second Owner or Privileged Role Administrator for redundancy.

### • No Key Vault or Storage Resources
Since the environment is minimal, some security controls (e.g., Key Vault hardening, Storage protection) are not applicable yet.

### • No Log Analytics Workspace
Diagnostic logging is not configured because no resources require it yet.  
This should be added when new services are deployed.

---

## 4. Overall Assessment

The environment is:

- **Secure**  
- **Fully monitored**  
- **Low‑risk**  
- **Compliant with baseline recommendations**  

All selected recommendations have been implemented successfully, and the environment is in a **Healthy** state.

---

## 5. Final Status

| Area | Status |
|------|--------|
| High‑severity alert notifications | Enabled |
| Owner alert notifications | Enabled |
| Defender for Resource Manager | Enabled |
| Attack paths | None |
| Security alerts | None |
| Secure Score | 100% |
| Compliance | 56/63 controls passed |

---

## 6. Conclusion

The Azure environment is now properly configured for alerting, monitoring, and control‑plane protection.  
Future improvements will depend on deploying additional resources such as Key Vault, Storage Accounts, or Virtual Machines.

