# Active Directory Lab: Part 2 - Deploying Active Directory

## Overview
In this part of the lab, I set up an Active Directory (AD) infrastructure in Azure by deploying a domain controller, creating a forest, and preparing the environment for domain administration.

---

## Steps Performed

### 1. Install Active Directory Domain Services
- I logged into **DC-1** and installed the **Active Directory Domain Services** (AD DS) role through the Server Manager.  
  ![Screenshot: AD DS Installation](path-to-screenshot/ad-ds-installation.png)

### 2. Promote DC-1 to a Domain Controller
- I promoted **DC-1** to a domain controller and created a new forest named `mydomain.com`.  
  - Selected "Add a new forest" option during configuration.
  - Specified the domain name as `mydomain.com`.
- After completing the setup, the VM restarted automatically.  
  ![Screenshot: Promote DC to Domain Controller](path-to-screenshot/promote-dc.png)

### 3. Login to the Domain
- I logged back into **DC-1** using the credentials: `mydomain.com\labuser` and confirmed the domain controller was properly configured.  
  ![Screenshot: Login as Domain Admin](path-to-screenshot/domain-login.png)

### 4. Disable the Windows Firewall (Testing Purposes)
- I disabled the Windows Firewall on **DC-1** temporarily to facilitate connectivity testing between machines.  
  ![Screenshot: Firewall Disabled](path-to-screenshot/firewall-disabled.png)

---

## Observations
- The domain `mydomain.com` was successfully created, and the domain controller is operational.  
- The AD DS role is installed, and the domain is ready for additional configurations.  

---

## Notes
- Disabling the firewall was only for testing purposes. In production environments, it's essential to configure security rules instead of disabling the firewall entirely.

---

## What's Next?
In **Part 3**, I will:
1. Create and configure Organizational Units (OUs) in Active Directory.
2. Add a domain administrator user and additional accounts.
3. Join **Client-1** to the domain and verify connectivity between the machines.
Stay tuned as we build out the AD environment further!

---
