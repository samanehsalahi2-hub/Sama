# Task 1
## 1. Comparison Table

| Model | Location of Resources | Operation Responsibility | Scalability | Security & Compliance | Cost Characteristics | Typical Use Cases |
|-------|------------------------|---------------------------|-------------|------------------------|-----------------------|-------------------|
| **Private Cloud** | On-premises datacenter | Internal IT team | Limited by hardware | Full control, suitable for sensitive data | High CAPEX (hardware, maintenance) | Banks, hospitals, regulated industries |
| **Public Cloud** | Cloud provider datacenter (e.g., Azure) | Cloud provider | Very high, elastic | Shared responsibility, global standards | OPEX, pay-as-you-go | Web apps, global services, rapid development |
| **Hybrid Cloud** | Combination of on-premises + cloud | Shared between company and provider | Flexible, gradual expansion | Mixed model, requires coordination | Mix of CAPEX + OPEX | Gradual migration, DR, remote work, file sync |

---

## 2. Practical Company Examples

### **Private Cloud**
A pharmaceutical company keeps its critical systems inside its own datacenter due to strict medical data regulations. This setup gives them full control over security and compliance while maintaining predictable internal operations.

### **Public Cloud**
An e-commerce startup deploys its website and databases in Azure to scale quickly without investing in hardware. The pay-as-you-go model helps them manage costs efficiently while supporting rapid growth.

### **Hybrid Cloud**
A manufacturing company keeps its ERP system and AD on-premises but uses Azure for backup, file synchronization, and remote access. This hybrid approach allows them to modernize gradually without disrupting critical internal systems.

# Task 2 — Hybrid Scenario Analysis

## 1. Reasons Why a Hybrid Solution Makes Sense

1. **ERP cannot migrate yet**  
   The ERP system has strong dependencies on the on-premises environment, making immediate migration risky.  
   **Perspective:** Migration

2. **Existing on-premises Active Directory**  
   The company relies on its local AD, requiring identity integration with cloud services.  
   **Perspective:** Operations

3. **Need for secure remote access**  
   Remote locations and employees require secure access to both on-premises and cloud resources.  
   **Perspective:** Availability

4. **Need for reliable backup and disaster recovery**  
   The on-premises datacenter has limitations, and the company needs robust backup and DR capabilities.  
   **Perspective:** Security/Compliance

5. **High availability without hardware investment**  
   The company wants to improve availability without purchasing new on-premises hardware.  
   **Perspective:** Costs

---

## 2. Categorization of Reasons

| Reason | Perspective |
|--------|-------------|
| ERP must remain on-premises | Migration |
| Local Active Directory exists | Operations |
| Need for remote access | Availability |
| Need for backup/DR | Security/Compliance |
| Improve availability without hardware | Costs |

---

## 3. Requirements for Azure Connectivity

### Requirement 1 — Secure and stable network connection
A secure tunnel is needed between the on-premises datacenter and Azure.  
**Solution:** Site-to-Site VPN or ExpressRoute

### Requirement 2 — Identity integration
Users should authenticate to cloud services using their existing on-premises AD accounts.  
**Solution:** Microsoft Entra Connect

### Requirement 3 — File synchronization between on-premises and Azure
Remote locations and users need access to files without full dependency on the on-premises file server.  
**Solution:** Azure File Sync

# Task 3 — Connections Between On-Premises and Azure

## 1. Overview of Hybrid Connection Areas

The company scenario requires typical hybrid connections in these areas:

- **Network connection**
- **Identity integration**
- **Data and file synchronization**
- **Management and monitoring**
- **Backup and recovery**

---

## 2. Assignment Table: Requirement → Connection → Azure Service → Purpose

| Requirement | Connection Type | Azure Service | Purpose |
|-------------|------------------|---------------|---------|
| Secure communication between on-premises and Azure | Network | **Azure VPN Gateway** | Creates an encrypted IPsec tunnel between the datacenter and Azure. |
| Unified identity for users across on-premises and cloud | Identity | **Microsoft Entra Connect** | Synchronizes on-premises AD identities with Microsoft Entra ID for SSO and MFA. |
| File access for remote locations and cloud workloads | Data / Files | **Azure File Sync** | Syncs on-premises file server with Azure Files and enables cloud tiering. |
| Centralized management of on-premises servers | Management | **Azure Arc** | Extends Azure management, policies, and monitoring to on-premises Windows/Linux servers. |
| Reliable backup and protection of critical systems | Backup / Recovery | **Azure Backup** | Provides cloud-based backup for on-premises servers without local tape or hardware. |

---

## 3. Short Descriptions of Each Assignment

### **Azure VPN Gateway**
Creates a secure, persistent network tunnel between the company’s datacenter and Azure, enabling hybrid communication.

### **Microsoft Entra Connect**
Synchronizes users, groups, and passwords from on-premises Active Directory to Microsoft Entra ID, enabling unified identity and cloud authentication.

### **Azure File Sync**
Allows the on-premises file server to sync with Azure Files, enabling remote access, cloud tiering, and centralized file management.

### **Azure Arc**
Brings on-premises servers into Azure management, enabling monitoring, policy enforcement, tagging, and inventory from a single control plane.

### **Azure Backup**
Provides secure, offsite backup storage in Azure, reducing dependency on local backup hardware and improving recovery capabilities.

# Task 4 — Overview of Important Hybrid Azure Services

## 1. Hybrid Azure Services Overview

Below are six key Azure services commonly used in hybrid cloud environments.  
Each entry includes: Description, Benefit, Scenario Component, and Prerequisites.

---

## Azure Arc
- **Description:** Extends Azure management to on-premises and multi-cloud servers.  
- **Benefit:** Centralized management, policy enforcement, monitoring, and tagging across hybrid environments.  
- **Scenario Component:** On-premises Windows/Linux servers in the manufacturing company.  
- **Prerequisites:** Arc agent installed on each server.

---

## Azure File Sync
- **Description:** Synchronizes on-premises file servers with Azure Files.  
- **Benefit:** Enables cloud tiering, remote access, and centralized file storage without replacing the local file server.  
- **Scenario Component:** Local file server used by remote locations.  
- **Prerequisites:** Storage account + File Sync agent.

---

## Azure Backup
- **Description:** Cloud-based backup solution for on-premises and Azure workloads.  
- **Benefit:** Eliminates dependency on local backup hardware and improves recovery reliability.  
- **Scenario Component:** Backup of on-premises VMs and critical data.  
- **Prerequisites:** Recovery Services Vault.

---

## Azure Site Recovery
- **Description:** Disaster Recovery (DR) service enabling replication and failover of on-premises VMs to Azure.  
- **Benefit:** Ensures business continuity with fast failover in case of datacenter outages.  
- **Scenario Component:** ERP system and critical servers requiring DR.  
- **Prerequisites:** ASR agent + network connectivity.

---

## Azure VPN Gateway
- **Description:** Provides secure IPsec tunnels between on-premises networks and Azure.  
- **Benefit:** Enables hybrid connectivity for remote locations and internal systems.  
- **Scenario Component:** Network connection between datacenter and Azure.  
- **Prerequisites:** Public IP + Gateway Subnet.

---

## Microsoft Entra ID (Azure AD)
- **Description:** Cloud identity platform providing authentication, SSO, MFA, and Conditional Access.  
- **Benefit:** Unified identity across on-premises AD and cloud services.  
- **Scenario Component:** Users in remote locations accessing cloud and internal systems.  
- **Prerequisites:** Microsoft Entra Connect for synchronization.

---

# 2. Three Most Important Services for the Scenario

### ⭐ Microsoft Entra ID  
Identity is the foundation of hybrid access. Without unified identity, remote access, security policies, and cloud integration cannot function properly.

### ⭐ Azure VPN Gateway  
The company requires secure connectivity between its datacenter, Azure, and remote locations. VPN Gateway is essential for establishing the hybrid network.

### ⭐ Azure File Sync  
The company has multiple remote locations and a local file server. File Sync solves file distribution, access, and storage challenges without replacing existing infrastructure.

