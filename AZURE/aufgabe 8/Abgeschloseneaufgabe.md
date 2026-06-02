# Task 2
# Task 2 – VM or App Service? (English Version)

## Scenario 1  
**“An existing web application that requires special server configuration and Administrator access to the operating system.”**

### ✔ Choice  
Virtual Machine

### ✔ Reasons  
- Requires full access to the operating system for custom configurations  
- Allows installation of custom software not supported by App Service  
- Provides full control over networking, firewall, services, and file system  

### ✔ Pre-Go-Live Checks  
- Security and Network Security Group  
- OS patching and updates  
- Backup and snapshot strategy  
- VM size and cost estimation  


---

## Scenario 2  
**“A public company website with minimal operational overhead.”**

### ✔ Choice  
App Service

### ✔ Reasons  
- OS and runtime are fully managed by Azure  
- Minimal maintenance required  
- Easy scaling without server management  
- Lower cost for simple websites  

### ✔ Pre-Go-Live Checks  
- Select appropriate App Service Plan (Free / Basic / Standard)  
- Configure Custom Domain and SSL  
- Review logging and availability  
- Understand tier limitations  


---

## Scenario 3  
**“A test system for a self‑managed application requiring full access to network, OS, and installed components.”**

### ✔ Choice  
Virtual Machine

### ✔ Reasons  
- Full control over OS and networking  
- Ability to install specific components for testing  
- Realistic simulation of a production environment  

### ✔ Pre-Go-Live Checks  
- VM size and cost  
- Snapshot for rollback  
- Network isolation  
- Monitoring and logging  


---

## Summary Table

| Scenario | Choice | Main Reason |
|---------|--------|-------------|
| 1 | VM | Full control and custom configuration |
| 2 | App Service | Minimal management for public website |
| 3 | VM | Full access for self‑managed test environment |



---

# Task 3 – Deploying a Web App in Azure App Service (Updated)

## Goal
Deploy a functional Web App in Azure App Service and document the actual configuration used in the deployment.

---

## 1. Resource Group Creation
A new Resource Group was created:

- **Resource Group:** `rg-08-ilp`
- **Region:** Germany West Central

---

## 2. Creating the Web App
A Web App was created in the Azure Portal.

### Configuration:
- **Name:** `08-ilp-WebApp`
- **Publish:** Code
- **Runtime Stack:** .NET v10.0
- **Operating System:** Windows
- **Region:** Germany West Central

---

## 3. App Service Plan
A new App Service Plan was used:

- **App Service Plan:** `NewILPService`
- **Tier:** Free (F1)
- **Operating System:** Windows
- **Instance Count:** 0 (shared infrastructure)

---

## 4. Deployment
The Web App was successfully deployed.  
Azure automatically provisioned:

- Hosting environment  
- Default domain  
- Runtime environment  

---

## 5. Testing the Web App
The deployed Web App was opened using the default Azure domain:

- **App URL:**  
  `https://08-ilp-webapp-dwh6ewddd9cqgnhz.germanywestcentral-01.azurewebsites.net`

The default Azure App Service page loaded successfully (after bypassing the browser security warning due to Free tier SSL limitations).

---

## Summary Table

| Item | Value |
|------|--------|
| **Resource Group** | `rg-08-ilp` |
| **Region** | Germany West Central |
| **Operating System** | Windows |
| **Runtime** | .NET v10.0 |
| **App Service Plan** | `NewILPService` |
| **Tier** | Free (F1) |
| **App URL** | `https://08-ilp-webapp-dwh6ewddd9cqgnhz.germanywestcentral-01.azurewebsites.net` |

