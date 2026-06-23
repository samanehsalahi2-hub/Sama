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
  <img src="https://github.com/samanehsalahi2-hub/Sama/blob/main/AZURE/aufgabe%2021/auf21-1.png" alt="My Image" width="800">
</p>

<p align="center">
  <img src="https://github.com/samanehsalahi2-hub/Sama/blob/main/AZURE/aufgabe%2021/auf21-1.png" alt="My Image" width="800">
</p>

<p align="center">
  <img src="https://github.com/samanehsalahi2-hub/Sama/blob/main/AZURE/aufgabe%2021/auf21-1.png" alt="My Image" width="800">
</p>

<p align="center">
  <img src="https://github.com/samanehsalahi2-hub/Sama/blob/main/AZURE/aufgabe%2021/auf21-1.png" alt="My Image" width="800">
</p>

<p align="center">
  <img src="https://github.com/samanehsalahi2-hub/Sama/blob/main/AZURE/aufgabe%2021/auf21-1.png" alt="My Image" width="800">
</p>
