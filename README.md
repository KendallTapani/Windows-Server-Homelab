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
<picture>
<img src="https://github.com/user-attachments/assets/34e7f238-1feb-4c83-9ae2-fd469dabac4d"
    width="700" height="200" alt="image" />
</picture>
<br/>
<br/>

### 3. Installed Active Directory DSR
- Installed AD, Promoted server to DC, created new forest ("kendalltapani.com")

### 4. Created OUs, and added Admins and Users.
- Created New OU for Admins, Users, and Domain Controllers
- Added My personal admin account, and ran a Powershell script to add 1000+ users into _Users
<picture>
    <img src="https://github.com/user-attachments/assets/11b4e4c0-2ec7-4a32-be0b-c3ad710ae6af" 
         width="450" height="400" alt="image" />
</picture>

<picture>
    <img src="https://github.com/user-attachments/assets/6583434b-850d-437b-b097-3ab45d4111dd" 
         width="450" height="400" alt="image" />
</picture>

### 5. Set up Routing and Remote access
- Installed the remote access role, enabled routing and remote access.
- Configured NAT on the Internet Adapter, allowing internal clients to access the internet.

<picture>
    <img src="https://github.com/user-attachments/assets/29720f4a-dbe3-4a8e-b9ac-6b98ecde3d5d"
        width="450" height="310" alt="image" />
</picture>

### 6. Installed and configured DHCP
- Installed DHCP role on server
- Created 3 new scopes for the internal network
Ranges: 172.16.0.100-200 : .1.100-200 : .2.100-200
Subnet Mask: 255.255.255.0
Router/Gateway: 172.16.0.1
DNS server: 172.16.0.1
<picture>
    <img src="https://github.com/user-attachments/assets/80f78af9-45ad-4d1d-833e-05d1437e58b3"
      width="450" height="325" alt="img" />
</picture>

### 7. Configured Client computers
- Renamed client computers and joined domain.
- Verified connectivity to DC with ping.

<picture>
    <img src="https://github.com/user-attachments/assets/3e336a6c-1a17-4f74-9033-d6255a351f67"
        width="500" height="225" alt="img" />
</picture>


### 8. Confirmed Client computers were fully setup
- Made sure DHCP assigned IP addresses properly.
- Checked AD to confirm client joined the domain
- Logged into client using domain credentials.

<picture>
    <img src="https://github.com/user-attachments/assets/f64a84fe-802a-43ec-9069-e09351eb4052"
        width="450" height="325" alt="img" />
</picture>
<picture>
    <img src="https://github.com/user-attachments/assets/921a41cd-bd3c-4e78-a06c-727468059eda"
        width="525" height="325" alt="img" />
</picture>
<br/>
<br/>
<br/>
<br/>
<br/>

## Check out Scripting and automation repo for AD scripts in powershell
<div style="background-color: #f6f8fa; padding: 20px; border-radius: 6px; margin: 20px 0;">
    <h4 style="margin-top: 0;">
        <a href="https://github.com/KendallTapani/Scripting-and-Automation/tree/main" style="text-decoration: none; color: #0366d6;">
            🤖 Scripting & Automation Repository
        </a>
    </h4>
</div>

