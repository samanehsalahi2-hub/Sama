# Task 3 – Synchronization Scope Design between Active Directory and Microsoft Entra ID

---

## OU Decision Table

| OU | Synchronize? | Reason |
|----|--------------|--------|
| OU=Sales | Yes | Sales users need access to cloud services. |
| OU=IT | Yes | IT administrators and technical users must be visible in the cloud. |
| OU=External | No | External users should not be synchronized to the organization’s cloud environment. |
| OU=ServiceAccounts | No | Service accounts are used internally and do not need cloud synchronization. |
| OU=Devices | Yes | Devices must be synchronized for cloud management (e.g., Intune). |

---

## Expected Object Types
- Users  
- Groups  
- Devices  

---

## Synchronization Tool
Synchronization is performed using one of the following tools:
- **Microsoft Entra Connect Sync**
- **Microsoft Entra Cloud Sync**

---

## Logical Connection
The logical connection is established between:
- **On-premises Active Directory**
- **Microsoft Entra ID**

This connection is managed by the synchronization tool.

---

# Task 4 – Workflow: Creating a New User and Signing in to a Cloud Service

---

## 1. Creating the User in On-Premises Active Directory
The IT administrator creates a new employee named **Mia Müller** in the company’s on-premises Active Directory.
This step happens only inside the local company network.

---

## 2. Synchronization Tool Detects the Change
The synchronization tool (Microsoft Entra Connect or Cloud Sync) detects that a new user has been created.
This step occurs between the on-premises environment and the cloud.

---

## 3. User Is Synchronized to Microsoft Entra ID
The synchronization tool transfers the new user’s information from Active Directory 
to Microsoft Entra ID.
This step ensures that the user also exists in the cloud.

---

## 4. User Becomes Visible in the Cloud
The user **Mia Müller** is now visible in the **Users** section of Microsoft Entra ID.
This step happens entirely in the cloud.

---

## 5. User Attempts to Sign In to a Cloud Service
Mia tries to sign in to a cloud service such as **Microsoft Teams** or **Outlook**.
This step takes place in the cloud.

---

## 6. Authentication Process
During authentication, the cloud checks:
- whether the password is correct,
- whether the user is valid,
- whether any security policies apply.

If everything is correct, authentication succeeds.

---

## 7. Token Issuance and Successful Sign-In
The cloud issues an **authentication token** (permission to access the service),
and Mia successfully signs in to the cloud application.

---

## Checkpoints

### 1. Verify User Exists in Entra ID
- Path: Microsoft Entra ID → Users  
- If the user is not visible, synchronization has not completed.

### 2. Check Synchronization Errors
- Path: Microsoft Entra Connect → Synchronization Errors  
- If errors exist, the synchronization process needs troubleshooting.

---
# Task 5 – Site-to-Site VPN Connection Design between On-Premises Network and Azure

---

## Network Information

### On-Premises Network
- 192.168.10.0/24

### Azure Network
- VNet: 10.20.0.0/16
- Workload Subnet: 10.20.1.0/24
- GatewaySubnet: 10.20.255.0/27

---

## Azure Resource Naming

| Item | Suggested Name |
|------|----------------|
| Resource Group | RG-HybridNetwork |
| Virtual Network | VNet-Hybrid |
| VPN Gateway | VNG-Hybrid |
| Local Network Gateway | LNG-OnPrem |
| Connection Name | Conn-Hybrid-S2S |
| Shared Key | YourSharedKey123 |

---

## Required Information from On-Premises Side
- **Public IP of the on-premises VPN device**  
This IP is required to establish the Site-to-Site tunnel.



