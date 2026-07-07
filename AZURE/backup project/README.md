**Lab-Setup Anleitung** 

*Hybrid Cloud Basis-Server – Vorbereitung für Azure Arc, Backup & Migrate* 

| Für wen?  | Alle Teilnehmer:innen des Azure-Moduls, unabhängig vom Windows Server-Vorwissen |
| :---- | :---- |
| **Dauer**  | Ca. 45 – 60 Minuten |
| **Ziel**  | Eine einzelne Windows-Server-2025-VM, bereit für Azure Arc, Azure  Backup und Azure Migrate |
| **Vorkenntnisse**  | Keine zwingend nötig – alle Schritte werden erklärt |

**Überblick – Was bauen wir heute auf?** 

Wir brauchen nur eine einzige Windows-Server-VM. Diese VM ist unsere „on-prem“-Maschine, die wir  später an Azure anbinden (Arc-Agent), sichern (Azure Backup) und/oder migrieren (Azure Migrate). 

| Komponente  | Wozu wir es brauchen |
| :---- | :---- |
| VMware Workstation  | Bereits installiert – unsere virtuelle Laborumgebung  |
| Windows Server 2025 VM  | Unser simulierter „on-prem“-Server |
| Internetverbindung (NAT)  | Pflicht\! Arc-Agent, Backup und Migrate müssen zu Azure telefonieren |
| Grundkonfiguration  | Name, IP, Zeitzone, Updates – saubere Basis für alle folgenden Übungen |

**Voraussetzung** 

• VMware Workstation ist installiert und startet fehlerfrei. 

• Mindestens 8 GB RAM und 60 GB freier Speicherplatz auf dem Host-PC. 

• Virtualisierung (Intel VT-x / AMD-V) ist im BIOS aktiviert. 

**ℹ HINWEIS** 

Falls VMware Workstation noch nicht installiert ist oder Virtualisierung im BIOS fehlt: **Bitte melden.** Das wiederholen wir hier nicht. 

**Schritt 1 – Windows Server 2025 ISO beschaffen** 

• Microsoft Evaluation Center öffnen: https://www.microsoft.com/en-us/evalcenter/evaluate-windows server-2025 

• Formular ausfüllen (beliebige Angaben möglich) → 64-bit ISO herunterladen 

❓ **WARUM?** 

Die Evaluierungsversion ist 180 Tage voll funktionsfähig und kostenlos – perfekt für unser Lab. 

**Schritt 2 – Virtuelle Maschine in VMware erstellen** 

Datei → Neue Virtuelle Maschine → „Custom (advanced)“ → Weiter

| Einstellung  | Wert |
| :---- | :---- |
| Hardware compatibility  | Workstation 17.x |
| Installationsmedium  | Die heruntergeladene ISO-Datei   auswählen |
| Gastbetriebssystem  | Microsoft Windows → Windows Server  2025 |
| VM-Name  | SRV-HYBRID01 |
| Prozessoren  | 1 Prozessor, 2 Kerne |
| Arbeitsspeicher  | 2048 MB (8 GB Host-RAM) bis 4096 MB  (16 GB Host-RAM) |
| Netzwerkverbindung  | NAT: Used to share the host's IP address |
| Festplatte  | 60 GB, Store virtual disk as a single file |

❓ **WARUM?** 

Warum NAT? Die VM teilt sich die Internetverbindung des Host   
PCs und bekommt eine eigene IP im 192.168.x.x-Bereich. Damit    
kommt sie ins Internet – das ist Pflicht für Arc, Backup und    
Migrate. 

**Schritt 3 – Windows Server 2025 installieren** 

• VM starten → sofort eine Taste drücken bei „Press any key to boot from CD or DVD“ • Sprache: Deutsch (Deutschland) → Weiter 

• „Jetzt installieren“ klicken 

• Edition: Windows Server 2025 Standard Evaluation (Desktop Experience) auswählen – NICHT die  Core-Version 

• Installationstyp: „Benutzerdefiniert: Nur Windows installieren“ 

• Festplatte: „Laufwerk 0 – nicht zugewiesener Speicherplatz“ auswählen → Weiter 

• Installation abwarten (5–20 Minuten, mehrere Neustarts sind normal) 

• Administrator-Kennwort setzen, z. B. Pa$$w0rd2025 

⚠ **Problem: Der Bildschirm bleibt nach einem Neustart schwarz.** 

→ Lösung: 2–3 Minuten warten. Falls nach 5 Minuten nichts passiert: VM-Menü → Power → Power  Off, dann neu starten. 

**Schritt 4 – Grundkonfiguration (in der WS Server VM\!)** 

**4.1 Computername setzen** 

• Server Manager → Lokaler Server → Computername (blauer Link) → Ändern 

• Name eingeben: SRV-HYBRID01 → OK → Jetzt neu starten 

**4.2 Netzwerk konfigurieren** 

Server Manager → Ethernet-Link → Adaptereigenschaften → Internetprotokoll Version 4 (TCP/IPv4):

| Feld  | Wert |
| :---- | :---- |
| IP-Adresse  | 192.168.100.10 |
| Subnetzmaske  | 255.255.255.0 |
| Standardgateway  | 192.168.100.2 (VMware-NAT  Gateway) |
| Bevorzugter DNS-Server  | 8.8.8.8 (öffentlicher DNS – wir haben  noch keinen eigenen DNS-Server) |

❓ **WARUM?** 

Eine feste IP sorgt dafür, dass der Server unter derselben Adresse    
erreichbar bleibt – wichtig, sobald wir ihn später z. B. per Azure Arc    
registrieren. DNS zeigt vorerst auf 8.8.8.8, weil dieser Server (noch)    
kein eigener DNS-Server ist. 

**4.3 Verbindung testen** 

• Eingabeaufforderung als Administrator öffnen → ping 8.8.8.8 eingeben 

✅ **SO SIEHT ERFOLG AUS** 

ping 8.8.8.8 liefert Antworten 

Der Server hat Internetzugang über NAT 

**4.4 Zeitzone & Updates** 

• Zeitzone: (UTC+01:00) Amsterdam, Berlin, Bern, Rom, Stockholm, Wien 

• Einstellungen → Windows Update → Nach Updates suchen → alle installieren 

**Schritt 5 – VMware Tools installieren** 

• VMware-Fenster → Menü „VM“ → „Install VMware Tools“ 

• Im Autorun-Dialog: setup64.exe ausführen → Typical → Install → Finish → Neustart 

❓ **WARUM?** 

Ohne VMware Tools ruckelt die Maus, die Auflösung ist niedrig und Copy-Paste zwischen VM und  PC funktioniert nicht. 

**Schritt 6 – Snapshot erstellen** 

• VM-Menü → Snapshot → Take Snapshot 

• Name: „Basis fertig – bereit für Arc/Backup/Migrate“ 

❓ **WARUM?** 

Ab jetzt experimentieren wir mit Azure-Diensten auf diesem Server. Geht dabei etwas kaputt, kommen  wir mit einem Klick zu diesem sauberen Zustand zurück.  
**Abschluss-Checkliste** 

☐ VM „SRV-HYBRID01“ ist erstellt und Windows Server 2025 installiert 

☐ Computername lautet SRV-HYBRID01 

☐ IP-Adresse 192.168.100.10 ist gesetzt, ping 8.8.8.8 funktioniert 

☐ Zeitzone korrekt, Windows Updates installiert 

☐ VMware Tools installiert 

☐ Snapshot „Basis fertig“ ist vorhanden 

**Bonus: Domain Controller einrichten (Vorbereitung für Entra  Connect Cloud Sync)** 

Dieser Teil ist optional und nur nötig, wenn wir später Microsoft Entra Connect Cloud Sync ausprobieren  wollen. Für Azure Arc, Backup und Migrate ist er NICHT erforderlich. 

**A – AD DS Rolle installieren** 

• Server Manager → Verwalten → Rollen und Features hinzufügen 

• Rollenbasierte Installation → Lokalen Server auswählen 

• Serverrolle: Active Directory-Domänendienste (AD DS) aktivieren → Features hinzufügen bestätigen • Weiter → Weiter → Installieren (ca. 2–3 Minuten) 

**B – Server zum Domänencontroller heraufstufen** 

• Warnflagge im Server Manager anklicken → „Diesen Server zu einem Domänencontroller  heraufstufen“ 

• „Neue Gesamtstruktur hinzufügen“ auswählen 

• Stammdomänenname eingeben, z. B. hybridlab.local 

• Funktionsebene: Windows Server 2016 oder höher, DNS-Server-Häkchen lassen • DSRM-Kennwort setzen, z. B. Dsrm@2025\! 

• Weiter durchklicken → Installieren → Server startet automatisch neu 

❓ **WARUM?** 

Bei der Heraufstufung wird automatisch die DNS-Rolle mitinstalliert – Active Directory braucht  zwingend einen eigenen DNS-Server. 

**C – DNS der Netzwerkkarte anpassen** 

• Nach dem Neustart: Netzwerkadapter-Eigenschaften → TCP/IPv4 → Bevorzugter DNS-Server auf  192.168.100.10 (sich selbst) ändern 

• Alternativer DNS-Server: leer lassen oder 8.8.8.8 als Fallback 

**D – Ein bis zwei Testbenutzer anlegen** 

• Server Manager → Tools → Active Directory-Benutzer und \-Computer 

• Rechtsklick auf die Domäne → Neu → Benutzer, z. B. Anna Test / a.test 

• Kennwort setzen, „Benutzer muss Kennwort bei nächster Anmeldung ändern“ aktivieren 

✅ **SO SIEHT ERFOLG AUS** 

Anmeldung als HYBRIDLAB\\Administrator funktioniert 

nslookup hybridlab.local liefert 192.168.100.10  
Mindestens ein Testbenutzer ist im Active Directory sichtbar 

**Neuen Snapshot erstellen** 

• VM-Menü → Snapshot → Take Snapshot → Name: „DC fertig – bereit für Entra Connect“
