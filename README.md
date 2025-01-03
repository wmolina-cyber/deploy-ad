# Active Directory Lab: Part 2 - Configuring and Deploying AD and Joining a Client
![image](https://github.com/user-attachments/assets/7fadf434-2b70-4f76-a0f7-1f9513fec347)

## Overview
In this part of the lab, I expanded the Active Directory setup by creating Organizational Units (OUs), managing domain users, and joining the client machine to the domain.

---

## Steps Performed

### 1. Create Organizational Units (OUs)
- I logged into **DC-1** as `mydomain.com\labuser` and opened **Active Directory Users and Computers (ADUC)**.  
- Created the following Organizational Units (OUs):
  - `_EMPLOYEES`
  - `_ADMINS`
- These OUs will help organize users and groups logically.  
![33](https://github.com/user-attachments/assets/03d48808-3582-4d38-ac86-175b1baf70a0)

### 2. Add a Domain Admin User
- Within the `_ADMINS` OU, I created a new user:
  - **Name**: Jane Doe  
  - **Username**: `jane_admin`  
  - **Password**: `Cyberlab123!`  
- Assigned the `jane_admin` account to the **Domain Admins** security group.
![41](https://github.com/user-attachments/assets/56c54912-3d6c-44ea-a4de-5b801809b3cc)
- Logged out of **DC-1** and logged back in as `mydomain.com\jane_admin` to verify the account's administrative privileges.  

### 3. Join Client-1 to the Domain
- I set **Client-1**'s DNS settings to the private IP address of **DC-1** (already done in Part 1).
- Restarted **Client-1** from the Azure Portal to ensure the DNS settings applied.
- Logged into **Client-1** as the local administrator (`labuser`) and joined it to the `mydomain.com` domain:
  - Went to **System Properties** > **Computer Name** > **Change** and entered the domain name `mydomain.com`.
  - Provided domain credentials (`jane_admin`) when prompted.  
  - Restarted **Client-1** to apply the changes.
![51](https://github.com/user-attachments/assets/3eab3da6-5891-45a3-98d6-686011da70b2)
- Verified in ADUC that **Client-1** appeared under **Computers**.
- Moved **Client-1** to the `_CLIENTS` OU for better organization.  
![57](https://github.com/user-attachments/assets/9ed71695-57c5-405f-87cb-3de9df5d746a)

---

## Observations
- The Organizational Units (_EMPLOYEES, _ADMINS, and _CLIENTS) were successfully created and logically structure the domain.  
- **Client-1** was successfully joined to the `mydomain.com` domain and appears in the correct OU in ADUC.  
- The `jane_admin` account has full domain administrative privileges and functions as expected.

---

## Notes
- Ensuring the correct DNS settings is critical for domain connectivity.
- In production, consider using Group Policies to automate tasks like moving domain computers to the appropriate OUs.

---

## What's Next?
In **Part 3**, I will:
1. Configure Remote Desktop access for non-administrative users.  
2. Use PowerShell to create multiple user accounts in bulk.  
3. Test domain authentication using newly created accounts.  

Stay tuned for the next part as I enhance and test domain functionalities!

---
