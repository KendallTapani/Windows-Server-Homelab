# Windows-Server-Homelab
This is documentation of a fully setup test environment, with Windows Server 2022, 5+ machines, and 1000+ users in Active directory.
This is basically showing the process used to set up this environment, including the network setup and configuration, as well as the scripting practices I regularly implement in the workplace.
This is meant to be a real world example of a typical company environment.
<br/>
<br/>

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
<br/>

### 3. Installed Active Directory DSR
- Installed AD, Promoted server to DC, created new forest ("kendalltapani.com")
<br/>

### 4. Created OUs, and added Admins and Users.
- Created New OU for Admins, Users, and Domain Controllers
- Added My personal admin account, and ran a Powershell script to add 1000+ users into Users account
<picture>
    <img src="https://github.com/user-attachments/assets/11b4e4c0-2ec7-4a32-be0b-c3ad710ae6af" 
         width="450" height="450" alt="image" />
</picture>

<picture>
    <img src="https://github.com/user-attachments/assets/6583434b-850d-437b-b097-3ab45d4111dd" 
         width="450" height="450" alt="image" />
</picture>

### 5. Set up Routing and Remote access
- Installed the remote access role, enabled routing and remote access.
- Configured NAT on the Internet Adapter, allowing internal clients to access the internet.

<picture>
    <img src="https://github.com/user-attachments/assets/29720f4a-dbe3-4a8e-b9ac-6b98ecde3d5d"
        width="300" height="250" alt="image" />
</picture>

### 6. Installed and configured DHCP
- Installed DHCP role on server
- Created 3 new scopes for the internal network
Ranges: 172.16.0.100-200 : 200-300 : 300-400
Subnet Mask: 255.255.255.0
Lease Duration: 8 days
Router/Gateway: 172.16.0.1
DNS server: 172.16.0.1
- Authorized and activated DHCP
<picture>
    <img src="https://github.com/user-attachments/assets/80f78af9-45ad-4d1d-833e-05d1437e58b3"
      width="300" height="300" alt="img" />
</picture>




<br/>
<br/>
<br/>
<picture>
    <img src="https://github.com/user-attachments/assets/d7324353-6ae0-46a0-9f61-127c47db1ced" 
         width="500" height="375" alt="image" />
</picture>
