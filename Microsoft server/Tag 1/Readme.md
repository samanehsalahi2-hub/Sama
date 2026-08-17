(17 August)

# ILP – Day 1 Assignment 
# Windows Server 2025 – Introduction, Installation & Windows Admin Center

---

## 🖥️ Task 1: Introduction to Windows Server 2025 – First Overview

### 🎯 Task 1.1 – Core Features of Windows Server 2025

**Key new and improved features:**

- **Hybrid Cloud Integration** — Deep Azure Arc integration, Azure Update Manager, Azure Monitor; essential for hybrid infrastructures.
- **Enhanced Zero Trust Security** — Improved Credential Guard, Secure Boot, stronger identity protection.
- **Advanced Containerization** — Better Windows Containers performance and Kubernetes compatibility.
- **Edge Computing Optimization** — Designed for low‑resource and distributed environments.
- **Performance Improvements** — Faster I/O, improved memory management, optimized Hyper‑V.
- **SMB over QUIC** — Secure file transfer without VPN; ideal for remote work.
- **Hotpatching** — Install updates without rebooting; reduces downtime.

---

### 🎯 Task 1.2 – Evolution Compared to Previous Versions

**Major differences from Windows Server 2022 / 2019:**

1. **Hotpatching Expansion**  
   - Previously limited; now widely available.  
   - Reduces downtime for critical servers.

2. **SMB over QUIC Enhancements**  
   - Fully integrated in 2025.  
   - Enables secure remote file access without VPN.

3. **Improved Hybrid Cloud Management**  
   - Stronger Azure Arc and cloud tool integration.  
   - Simplifies hybrid operations.

4. **Container Networking Improvements**  
   - Better performance and Kubernetes compatibility.

5. **Security Hardening**  
   - Stronger identity protection and secure boot mechanisms.

---

## ⚙️ Task 2: Installation of Windows Server – Foundation of Your Environment

### 🎯 Task 2.1 – Planning Phase (Checklist)

**Checklist before installation:**

- **Hardware Requirements**  
  - CPU: Minimum 2 cores  
  - RAM: Minimum 4 GB (recommended 8 GB)  
  - Storage: Minimum 60 GB  

- **Network Planning**  
  - Static IP address  
  - Gateway  
  - DNS server  

- **Edition Selection**  
  - Standard Edition  
  - Datacenter Edition  

- **Installation Media**  
  - Windows Server 2025 ISO file  

- **Licensing**  
  - Product key or evaluation license  

- **VM Configuration**  
  - CPU, RAM, Disk, Network adapter  

---

### 🎯 Task 2.2 – Simulated Virtual Installation Steps

**Step‑by‑step installation:**

1. Boot from the ISO file.  
2. Select language, time, and keyboard layout.  
3. Click **Install now**.  
4. Choose edition (Standard or Datacenter).  
5. Select installation type: Server Core or Desktop Experience.  
6. Accept license terms.  
7. Choose **Custom installation**.  
8. Create partition and select disk.  
9. Begin installation.  
10. System restarts.  
11. Set Administrator password.  
12. Log in.  
13. Configure static IP.  
14. Rename server.  
15. Install updates.

---

## 🖥️ Task 3: Windows Admin Center (WAC)

### 🎯 Task 3.1 – What is WAC? Why and How?

**Definition:**  
Windows Admin Center is a modern, browser‑based management tool for Windows Servers, clusters, and clients.

**Advantages over RSAT or RDP:**

- Centralized management  
- More secure than RDP  
- Modern and fast interface  
- No full remote desktop session required  
- Integrated dashboards and monitoring  

**Installation Location:**  
- A separate workstation or management server  

**Requirements:**  
- Windows 10/11 or Windows Server  
- Microsoft Edge browser  
- Network access to the server  
- WinRM enabled  

---

### 🎯 Task 3.2 – Installation and First Steps in WAC

**Steps to install WAC:**

1. Download Windows Admin Center installer.  
2. Run installer.  
3. Choose port (default: 443).  
4. Generate or import certificate.  
5. Open WAC in browser.  
6. Add Windows Server 2025.  
7. Enter hostname or IP.  
7. Provide credentials.  
9. Access dashboard.

**First areas to explore:**

- Dashboard  
- Roles & Features  
- Event Logs  
- Updates  
- Performance Monitor  
- Firewall  

---

## 🧠 Self‑Reflection

- **New concepts learned:** Hotpatching, SMB over QUIC, hybrid cloud integration.  
- **Challenges:** Understanding hybrid cloud and security enhancements.  
- **Open questions:** Kubernetes integration in enterprise environments.  
- **Real‑world application:** Deploying domain controllers, managing servers via WAC, connecting servers to Azure Arc.

