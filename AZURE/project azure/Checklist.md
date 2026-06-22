# <span style="color:#4A90E2;">CloudStart – Project Submission Checklist (A1–A6)</span>


---

## <span style="color:#4A90E2;">A1 – Netzwerk</span>
- [x] Resource Group **rg-cloudstart** erstellt  
- [x] VNet **vnet-cloudstart** mit zwei Subnetzen (**snet-app**, **snet-mgmt**)  
- [x] **nsg-app** mit RDP-Regel → **snet-app** zugewiesen  
- [x] **nsg-mgmt** mit SSH-Regel → **snet-mgmt** zugewiesen  

---

## <span style="color:#27AE60;">A2 – VMs</span>
- [x] **vm-app01 (Windows)** läuft in **snet-app**, RDP-Verbindung erfolgreich  
- [x] **vm-mgmt01 (Linux)** läuft in **snet-mgmt**, SSH-Verbindung mit `uname`-Output  

---

## <span style="color:#9B59B6;">A3 – Storage</span>
- [x] Storage Account erstellt  
- [x] Blob Container **dokumente** mit hochgeladener Datei  
- [x] SAS-URL im Browser geöffnet  

---

## <span style="color:#16A085;">A4 – Entra ID & RBAC</span>
- [x] 3 Entra-Benutzer angelegt  
- [x] Gruppe **grp-entwickler** mit *Ben Koller*  
- [x] RBAC-Rollen auf **rg-cloudstart** gesetzt:  
  - Reader  
  - VM Contributor  

---

## <span style="color:#E67E22;">A5 – Monitoring</span>
- [x] CPU-Metrik als Liniendiagramm sichtbar  
- [x] Alert Rule **alert-cpu-hoch** konfiguriert  

---

## <span style="color:#C0392B;">A6 – Defender for Cloud</span>
- [x] Defender for Cloud geöffnet, Secure Score notiert  
- [x] Empfehlungen für **rg-cloudstart** gefiltert  
- [x] Mindestens eine Empfehlung umgesetzt oder schriftlich begründet  

----------------------
# <span style="color:#4A90E2;">CloudStart – Final Project Submission Checklist (A1–A6 + Bonus)</span>
### <span style="color:#7B7D7D;">Completed by: Samaneh</span>

---

## <span style="color:#4A90E2;">A1 – Network</span>
- [x] Resource Group **rg-cloudstart** created  
- [x] Virtual Network **vnet-cloudstart** with two subnets:  
  - **snet-app**  
  - **snet-mgmt**  
- [x] Network Security Group **nsg-app** created with RDP rule and assigned to **snet-app**  
- [x] Network Security Group **nsg-mgmt** created with SSH rule and assigned to **snet-mgmt**

---

## <span style="color:#27AE60;">A2 – Virtual Machines</span>
- [x] **vm-app01 (Windows)** deployed in **snet-app**, RDP connection successful  
- [x] **vm-mgmt01 (Linux)** deployed in **snet-mgmt**, SSH connection successful with `uname` output  

---

## <span style="color:#9B59B6;">A3 – Storage</span>
- [x] Storage Account created  
- [x] Blob Container **dokumente** created  
- [x] File uploaded to the container  
- [x] SAS URL generated and successfully opened in browser  

---

## <span style="color:#16A085;">A4 – Entra ID & RBAC</span>
- [x] Three Entra ID users created  
- [x] Group **grp-entwickler** created and *Ben Koller* added  
- [x] RBAC roles assigned on **rg-cloudstart**:  
  - Reader  
  - Virtual Machine Contributor  

---

## <span style="color:#E67E22;">A5 – Monitoring</span>
- [x] CPU metric displayed as a line chart for **vm-app01**  
- [x] Alert Rule **alert-cpu-hoch** configured with:  
  - Valid signal  
  - Threshold set  
  - Evaluation settings corrected  
  - Action Group linked  
  - Rule enabled  

---

## <span style="color:#C0392B;">A6 – Defender for Cloud</span>
- [x] Defender for Cloud opened  
- [x] Secure Score documented  
- [x] Recommendations filtered for **rg-cloudstart**  
- [x] At least one recommendation implemented or justified  

---

## <span style="color:#F1C40F;">★ Bonus – App Service</span>
- [x] Web App deployed and running  
- [x] Application Setting **UMGEBUNG = Test** configured  
- [x] Web App URL opened in browser  


