# Windows-Server-Homelab
This is documentation of a fully setup test environment, with Windows Server 2022, 5+ machines, and 1000+ users in Active directory.
This is basically showing the process used to set up this environment, including the network setup and configuration, as well as the scripting practices I regularly implement in the workplace.
This is meant to be a real world example of a typical company environment.
<br/>
<br/>
<picture>
    <img src="https://github.com/user-attachments/assets/d7324353-6ae0-46a0-9f61-127c47db1ced" 
         width="500" height="375" alt="image" />
</picture>

### 1. Created Server and Client Machines
- Windows server 2022 with an internal and external network adapter.
- Windows 10 pro client machines, with only an internal network adapter.
<div>
<picture>
    <img src="https://github.com/user-attachments/assets/830a0b0d-c786-4a66-b84d-0b3114c89728" 
         width="250" height="400" alt="image" />
</picture>
<picture>
    <img src="https://github.com/user-attachments/assets/52f8da6e-5163-40f3-9016-2f04f8f136d6" 
         width="250" height="400" alt="image" />
</picture>
</div>
<br/>

### 2. Configured Network Adapters
- First adapter configured for NAT, renamed "Internet"
- Second Adapter configured statically, IP: 172.16.0.1/24, DNS set to loopback address

### 3. Installed Active Directory DSR
- Installed AD, Promoted server, created new forest ("kendalltapani.com")

### 4. Created OUs, and added Admins and Users.
- Created New OU for Admins, Users, and Domain Controllers
- Added My personal admin account, and ran a Powershell script to add 1000+ users into Users account
<picture>
    <img src="https://github.com/user-attachments/assets/250c7378-3d43-42e0-a8bb-15c99053ca54" 
         width="400" height="450" alt="image" />
</picture>
<picture>
    <img src="https://github.com/user-attachments/assets/6583434b-850d-437b-b097-3ab45d4111dd" 
         width="400" height="450" alt="image" />
</picture>
