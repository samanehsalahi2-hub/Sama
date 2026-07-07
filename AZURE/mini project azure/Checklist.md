# <span style="color:#4A90E2;">CloudStart – Final Project Checklist (A1–A6 )</span>


---

## <span style="color:#4A90E2;">A1 – Network</span>
- [x] Resource Group **rg-cloudstart** created  
- [x] Virtual Network **vnet-cloudstart** created with address space **10.0.0.0/16**  
- [x] Subnets created:  
  - **snet-app** (10.0.1.0/24)  
  - **snet-mgmt** (10.0.2.0/24)  
- [x] Network Security Group **nsg-app** created  
  - RDP rule (Port 3389) added  
  - Assigned to **snet-app**  
- [x] Network Security Group **nsg-mgmt** created  
  - SSH rule (Port 22) added  
  - Assigned to **snet-mgmt**

---

## <span style="color:#27AE60;">A2 – Virtual Machines</span>
- [x] Windows VM **vm-app01** deployed in **snet-app**  
- [x] Successful RDP connection to **vm-app01**  
- [x] Linux VM **vm-mgmt01** deployed in **snet-mgmt**  
- [x] Successful SSH connection to **vm-mgmt01** with `uname -a` output  

---

## <span style="color:#9B59B6;">A3 – Storage</span>
- [x] Storage Account **stcloudstart


- [x] Blob Container **dokumente** created (Private access)  
- [x] Test file uploaded  
- [x] SAS URL generated and successfully opened in browser  

---

## <span style="color:#16A085;">A4 – Entra ID & RBAC</span>
- [x] Three Entra ID users created:  
  - **Anna Maier** – Reader  
  - **Ben Koller** – Developer  
  - **Clara Fuchs** – No Azure access  
- [x] Security Group **grp-entwickler** created  
  - **Ben Koller** added as member  
- [x] RBAC roles assigned on **rg-cloudstart**:  
  - **Anna Maier → Reader**  
  - **grp-entwickler → Virtual Machine Contributor**

---

## <span style="color:#E67E22;">A5 – Monitoring</span>
- [x] CPU metric displayed as a line chart for **vm-app01**  
- [x] Alert Rule **alert-cpu-hoch** created with:  
  - Condition: CPU > 80%  
  - Action Group: **action-email**  
  - Severity: 2  
  - Email notification enabled  

---

## <span style="color:#C0392B;">A6 – Defender for Cloud</span>
- [x] Defender for Cloud opened  
- [x] Secure Score documented  
- [x] Recommendations filtered for **rg-cloudstart**  
- [x] At least one recommendation implemented or justified  

