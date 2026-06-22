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

---

### <span style="color:#7B7D7D;">Viel Erfolg!  
Bei Problemen: Fehlermeldung lesen, Portal-Docs nutzen, Mitschüler fragen.  
Azure lernt man am besten durch Ausprobieren.</span>
