Scenario 1
“An existing web application that requires special server configuration and Administrator access to the operating system.”

✔ Choice:
Virtual Machine

✔ Reasons:
Requires full access to the operating system for custom configurations

Allows installation of custom software that App Service does not support

Provides full control over networking, firewall, services, and file system

✔ Pre-Go-Live Checks:
Security and Network Security Group configuration

OS patching and updates

Backup and snapshot strategy

VM size selection and cost estimation

Scenario 2
“A public company website with minimal operational overhead.”

✔ Choice:
App Service

✔ Reasons:
OS and runtime are fully managed by Azure

Requires minimal maintenance

Easy and automatic scaling without server management

Lower cost compared to a VM for simple websites

✔ Pre-Go-Live Checks:
Select the appropriate App Service Plan (Free / Basic / Standard)

Configure Custom Domain and SSL

Review logging and availability settings

Understand limitations of the selected tier

Scenario 3
“A test system for a self‑managed application requiring full access to network, OS, and installed components.”

✔ Choice:
Virtual Machine

✔ Reasons:
Requires full control over OS and networking

Allows installation of specific components needed for testing

Enables realistic simulation of a production environment

✔ Pre-Go-Live Checks:
VM size and cost

Snapshot creation for quick rollback

Network isolation

Monitoring and logging configuration

| Scenario | Choice | Main Reason |
| --- | --- | --- |
| 1 | **VM** | Full control and custom configuration |
| 2 | **App Service** | Minimal management for public website |
| 3 | **VM** | Full access for self‑managed test environment |
