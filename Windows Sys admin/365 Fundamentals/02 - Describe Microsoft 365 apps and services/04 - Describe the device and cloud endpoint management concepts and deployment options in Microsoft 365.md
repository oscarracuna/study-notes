

# Introduction
- Describe the endpoint management capabilities of Microsoft 365.
- Describe the differences between Windows 365 and Azure Virtual Desktop.
- Describe the deployment and release models for Windows-as-a-Service.
- Describe the deployment methods and update channels for Microsoft 365 Apps.

---
# Describe the endpoint management capabilities of Microsoft 365
In hybrid environments, many devices can be used to work, from Windows PC, to MacOS, android phones or custom devices. This makes it difficult for IT to manage and secure. *There has to be a balance between security and convenience*.

That's where Microsoft Intune comes in to play. It's a cloud-based unified endpoint management solution.
Intune entails:
- Microsoft Intune service
- Configuration Manager
- Co-management
- Endpoint Analytics
- Windows Autopilot
- Intune admin center

"These solutions support data protection on both company-owned and personal devices using non-intrusive app management."

# Microsoft Intune
It's a cloud-based endpoint management solution that manages user access to organizational resources. It can manage mobile devices, desktop computers and VMs.

- Policy deployment
- Device configuration
- Compliance
- Conditional access
- Can be paired with Microsoft Defender or third-parties

# Configuration Manager
This is an **on-prem** management solution for endpoints (including servers). It automates deploying updates, apps, analytics (for on-site and online), compliance and overseeing endpoints.

# Co-management
Tool to migrate existing Configuration Manager settings to the cloud. It allows for Conditional Access implementation as well (since that's something you'd want when moving from on-prem to cloud).

# Tenant-attach
Same as co-management, but for device records.

# Endpoint Analytics
Provides metrics and recommendations on the health and performance of Windows clients.

# Windows Autopilot
Cloud-native service to set up and pre-configure new devices. It can also be used to reset/re-image devices. It can also automatically join endpoints to Microsoft Entra ID (Azure AD), enroll in Intune and automate custom out-of-the-box experience (custom image with specific apps and stuff like that).

# Windows Autopatch
Service to automate updates for Windows, M365 apps, MS Edge and Teams.

# Intune admin center
Web interface for Intune. Similar to Microsoft Admin Portal.

---
# Compare the differences of Windows 365 and Azure Virtual Desktop
Both are virtual desktop solutions (Desktop-as-a-Service). They allow you to experience Windows OS.

### Windows 365
It creates a type of Windows VM know as Cloud PC. These are dedicated to a single user. Automatically provisioned via licenses. Azure computing and storage are manage by Microsoft with a fixed cost.

### Azure Virtual Desktop
Same as Windows 365 but can be used by multiple users (FSLogix) and set up multi-sessions. Consumption-based costs.

---
# Describe the deployment and release models for Windows-as-a-Service (WaaS)
