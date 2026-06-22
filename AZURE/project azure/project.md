MINI-PROJEKT 

**Azure – CloudStart GmbH** 

| Thema  | Azure Grundlagen – VMs, Netzwerk, IAM, Storage |
| :---- | :---- |
| **Bearbeitungszeit**  | 1–2 Stunden (ein Nachmittagsblock) |
| **Abgabe**  | Screenshots \+ kurze Dokumentation |
| **Voraussetzung**  | Azure-Subscription mit aktivem Credit (Demo-Umgebung) |

**1 Das Szenario** 

Du bist der neue Cloud-Administrator der **CloudStart GmbH** – ein kleines Startup in Wien, das seine IT komplett in die Cloud verlagert. Bisher lief alles lokal, jetzt soll eine saubere Azure-Umgebung aufgebaut werden: mit Netzwerk, einer virtuellen Maschine, einem Speicherkonto, richtigen Zugriffsrechten und einem kurzen Blick auf das Monitoring. 

| Firma  | CloudStart GmbH |
| :---- | :---- |
| **Standort**  | Wien, Österreich |
| **Azure Region**  | Frei wählbar (z.B. West Europe oder North Europe) |
| **Resource Group**  | rg-cloudstart |

**Die drei Mitarbeiter:** 

| Anzeigename  | Rolle  | UPN |
| :---- | :---- | :---- |
| Anna Maier  | Geschäftsführerin – braucht Lesezugriff auf alles | a.maier@\[deine-domain\] |
| Ben Koller  | Entwickler – braucht Zugriff auf die VM  | b.koller@\[deine-domain\] |
| Clara Fuchs  | Praktikantin – kein Azure-Zugriff (nur Entra-User) | c.fuchs@\[deine-domain\] |

**2 Wichtige Hinweise** 

| Tipp: Wähle immer die günstigste VM-Größe (B1s) und verwende Standard- statt Premium-Dienste. Am Ende des Projekts werden alle Ressourcen gemeinsam gelöscht. |
| :---- |

**3 Aufgaben**  
Achtung: Lies jede Aufgabe vollständig durch, bevor du beginnst. Verwende durchgehend dieselbe Region und Resource Group. 

**A1 Ressourcengruppe & Netzwerk aufbauen** 

Thema: Resource Group, VNet, Subnets, NSG 

Bevor wir VMs oder Dienste erstellen, brauchen wir eine saubere Netzwerkstruktur. Aufgabe: 

• Erstelle eine **Resource Group** mit dem Namen **rg-cloudstart** in einer **Region deiner Wahl** • Erstelle ein **Virtual Network** namens **vnet-cloudstart** mit dem Adressraum **10.0.0.0/16** • Füge zwei **Subnetze** hinzu:   
– **snet-app**: 10.0.1.0/24 

– **snet-mgmt**: 10.0.2.0/24 

• Erstelle eine **Network Security Group (NSG)** namens **nsg-app** 

• Weise die NSG dem Subnetz **snet-app** zu 

• Füge eine **Inbound-Regel** hinzu, die **RDP (Port 3389\)** erlaubt (Priorität 100\) • Erstelle eine zweite **Network Security Group** namens **nsg-mgmt** 

• Weise sie dem Subnetz **snet-mgmt** zu 

• Füge eine **Inbound-Regel** hinzu, die **SSH (Port 22\)** erlaubt (Priorität 100\) 

Screenshot-Pflicht: VNet mit beiden Subnetzen sichtbar \+ beide NSGs mit ihren Inbound-Regeln (RDP bzw. SSH). 

**A2 Virtuelle Maschinen erstellen** 

Thema: Azure VM, Windows & Linux, Subnetz-Platzierung, Verbindung 

Du erstellst zwei VMs – eine Windows-VM im App-Subnetz und eine Linux-VM im Management-Subnetz. So simulierst du eine typische Umgebung mit getrennten Netzbereichen. 

**VM 1 – Windows Server (snet-app)** 

• Erstelle eine **Windows Server 2022 VM**: 

– Name: **vm-app01** 

– Größe: **B1s** 

– Resource Group: rg-cloudstart, gleiche Region 

• Subnetz: **snet-app** | NSG: **nsg-app** 

• Öffentliche IP: **aktiviert** | Admin-Zugangsdaten notieren 

• Verbinde dich per **RDP** mit der VM – öffne den Server-Manager als Nachweis **VM 2 – Linux Ubuntu (snet-mgmt)**   
• Erstelle eine **Ubuntu Server 22.04 VM**: 

– Name: **vm-mgmt01** 

– Größe: **B1s** 

– Resource Group: rg-cloudstart, gleiche Region 

• Subnetz: **snet-mgmt** | NSG: **nsg-mgmt** 

• Öffentliche IP: **aktiviert** | Authentifizierung: **Passwort** (einfacher für den Einstieg)  
• Verbinde dich per **SSH** mit der VM – z.B. über die Azure Cloud Shell oder einen SSH-Client: **ssh adminuser@\<öffentliche-IP\>** 

• Führe **uname \-a** aus – der Output bestätigt, dass du auf der Linux-VM bist 

Screenshot-Pflicht: Beide VMs laufen (Status: Running) \+ RDP-Verbindung zu vm-app01 \+ SSH-Session auf vm-mgmt01 mit uname-Output. 

**A3 Storage Account & Blob Container** 

Thema: Azure Storage, Blob, Zugriffsebene 

Aufgabe: 

• Erstelle einen **Storage Account** namens **stcloudstart\[deine-initialen\]** 

(Name muss global eindeutig sein – füge deine Initialen an) 

• Performance: **Standard**, Redundanz: **LRS** 

• Erstelle einen **Blob Container** namens **dokumente** 

– Zugriffsebene: **Private** 

• Lade eine beliebige Testdatei (z.B. eine .txt-Datei) in den Container hoch 

• Generiere eine **SAS-URL** (Shared Access Signature) für die Datei mit einer Gültigkeit von 1 Stunde und öffne sie im Browser 

Screenshot-Pflicht: Blob Container mit hochgeladener Datei \+ SAS-URL im Browser geöffnet. 

**A4 Entra ID – Benutzer, Gruppe & RBAC** 

Thema: Microsoft Entra ID (ehem. Azure AD), Benutzer, Gruppen, RBAC-Rollen 

Aufgabe: 

• Gehe zu **Microsoft Entra ID** im Azure Portal 

• Erstelle die **drei Benutzer** aus dem Szenario (Anna Maier, Ben Koller, Clara Fuchs) • Erstelle eine **Sicherheitsgruppe** namens **grp-entwickler**   
– Füge Ben Koller als Mitglied hinzu 

• Weise auf der **Resource Group rg-cloudstart** folgende RBAC-Rollen zu: – Anna Maier → **Reader** 

– grp-entwickler → **Virtual Machine Contributor** 

• Überprüfe unter **Access Control (IAM)** der Resource Group, ob die Zuweisungen korrekt sind Screenshot-Pflicht: Entra ID Benutzer \+ Gruppe sichtbar \+ IAM-Rollenzuweisungen auf der Resource Group. 

**A5 Monitoring – Metriken & Alert** 

Thema: Azure Monitor, Metriken, Alert Rules 

Aufgabe: 

• Gehe zur VM **vm-app01** → **Metrics** (Metriken) 

• Zeige die **CPU-Auslastung** der letzten Stunde als Liniendiagramm an 

• Erstelle eine **Alert Rule** auf der VM: 

– Bedingung: CPU-Auslastung \> 80 % 

– Name der Regel: **alert-cpu-hoch** 

– Aktion: E-Mail-Benachrichtigung an deine eigene Adresse 

– Severity: 2  
Screenshot-Pflicht: Metrik-Diagramm mit CPU \+ Alert Rule konfiguriert (Bedingung und E-Mail-Aktion sichtbar). 

**A6 Defender for Cloud – Sicherheitsempfehlungen** 

Thema: Microsoft Defender for Cloud, Secure Score, Empfehlungen 

Defender for Cloud analysiert automatisch deine Azure-Ressourcen und gibt dir konkrete Hinweise, was du verbessern kannst. Das ist einer der wichtigsten Einstiegspunkte für Cloud-Sicherheit. Aufgabe: 

• Suche im Azure Portal nach **Microsoft Defender for Cloud** und öffne es 

• Schau dir den **Secure Score** an – wie hoch ist dein aktueller Wert? 

• Gehe zu **Recommendations** (Empfehlungen) und filtere nach deiner Resource Group **rg-cloudstart** 

• Lies mindestens **3 Empfehlungen** durch – was wird bemängelt, warum ist das ein Risiko? • Suche eine Empfehlung, die du schnell umsetzen kannst, z.B.:   
– Just-in-time VM access should be applied → JIT-Zugriff für vm-app01 aktivieren – MFA should be enabled on accounts → notieren und begründen warum das wichtig ist – Management ports should be closed → RDP-Regel in der NSG auf eine konkrete IP einschränken 

• Setze die gewählte Empfehlung um **oder** dokumentiere schriftlich, was du tun würdest und warum 

Screenshot-Pflicht: Defender for Cloud mit Secure Score \+ Empfehlungsliste für rg-cloudstart \+ eine Empfehlung geöffnet. 

★ **BONUS – Azure App Service** 

Thema: PaaS, App Service Plan, Web App 

Aufgabe: 

• Erstelle einen **App Service Plan** namens **asp-cloudstart** 

– Betriebssystem: Windows, Pricing Tier: **F1 (Free)** 

• Erstelle eine **Web App** namens **app-cloudstart-\[deine-initialen\]** auf diesem Plan • Öffne die Standard-URL der Web App im Browser   
– Du siehst eine Azure-Standardseite 

• Gehe zu **Configuration** → **Application Settings** und füge eine neue App-Einstellung hinzu: – Key: **UMGEBUNG**, Value: **Test** 

Screenshot-Pflicht: Web App läuft (URL im Browser offen) \+ App Setting sichtbar. 

**4 Aufräumen – Ressourcen löschen** 

| Wichtig\! Lösche am Ende alle Ressourcen um Credit zu sparen. Am einfachsten: rg-cloudstart im Portal öffnen → Delete resource group. Damit werden alle Ressourcen darin auf einmal gelöscht. |
| :---- |

**5 Abgabe-Checkliste**  
**A1 – Netzwerk** 

■ Resource Group rg-cloudstart erstellt 

■ VNet vnet-cloudstart mit zwei Subnetzen (snet-app, snet-mgmt) 

■ nsg-app mit RDP-Regel → snet-app zugewiesen 

■ nsg-mgmt mit SSH-Regel → snet-mgmt zugewiesen 

**A2 – VMs** 

■ vm-app01 (Windows) läuft in snet-app, RDP-Verbindung erfolgreich 

■ vm-mgmt01 (Linux) läuft in snet-mgmt, SSH-Verbindung mit uname-Output 

**A3 – Storage** 

■ Storage Account erstellt 

■ Blob Container dokumente mit hochgeladener Datei 

■ SAS-URL im Browser geöffnet 

**A4 – Entra ID & RBAC** 

■ 3 Entra-Benutzer angelegt 

■ Gruppe grp-entwickler mit Ben Koller 

■ RBAC-Rollen auf rg-cloudstart gesetzt (Reader \+ VM Contributor) 

**A5 – Monitoring** 

■ CPU-Metrik als Liniendiagramm sichtbar 

■ Alert Rule alert-cpu-hoch konfiguriert 

**A6 – Defender for Cloud** 

■ Defender for Cloud geöffnet, Secure Score notiert 

■ Empfehlungen für rg-cloudstart gefiltert 

■ Mindestens eine Empfehlung umgesetzt oder schriftlich begründet 

★ **Bonus – App Service** 

■ Web App läuft, URL im Browser offen 

■ App Setting UMGEBUNG=Test gesetzt 

Viel Erfolg\! Bei Problemen: Fehlermeldung lesen, Portal-Docs nutzen, Mitschüler fragen. Azure ist am besten durch Ausprobieren zu lernen.
