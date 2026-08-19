# Windows Server Lab – Documentation (Tasks 1–4)

## Task 1 – Local Server Configuration
During this task, the initial configuration of the server was reviewed and adjusted:

- Renamed the server to **SRV-DC-01**
- Configured a static IP address
- Set DNS to the server’s own IP
- Enabled Remote Desktop
- Checked Windows Update settings
- Verified that no roles were installed yet

The server was prepared for role installation and domain deployment.

---

## Task 2 – Installing Active Directory Domain Services (AD DS)
In this task:

- The **Active Directory Domain Services** role was installed via Server Manager.
- The server was promoted to a **Domain Controller**.
- A new forest named **lab.local** was created.
- All AD DS–related services were successfully initialized.

**Result:**  
The server is now functioning as the primary Domain Controller for the lab environment.

---

## Task 3 – Installing DNS Server
During this task:

- The **DNS Server** role was installed (automatically included with AD DS).
- A Forward Lookup Zone for **lab.local** was created.
- Core DNS records (SOA, NS, A records for the DC) were verified.
- DNS functionality was tested using `nslookup`, confirming correct name resolution.

**Result:**  
DNS is fully operational and correctly integrated with the domain.

---

## Task 4 – Installing File Server Role
Steps performed:

### 1. Open Server Manager  
Used **Add Roles and Features** wizard.

### 2. Select Role  
Under **File and Storage Services → File and iSCSI Services**, the **File Server** role was selected.

### 3. Features  
No additional features were selected, as File Server operates fully without extra components.

### 4. Installation  
Clicked **Install** and completed the role installation.

### 5. Verification  
In **Server Manager → File and Storage Services**, the File Server role appeared as **Installed**.

**Result:**  
The server now supports file sharing and storage management capabilities.

---

## Final Status After Task 4
The server **SRV-DC-01.lab.local** now includes:

- Active Directory Domain Services  
- DNS Server  
- File Server  

The environment is fully prepared for Task 5 (Server Manager & Windows Admin Center review).

