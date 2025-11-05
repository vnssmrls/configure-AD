<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>On-premises Active Directory Deployed in the Cloud (Azure)</h1>
This tutorial outlines the implementation of on-premises Active Directory within Azure Virtual Machines.<br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop/Windows App
- Active Directory Domain Services
- PowerShell

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)

<h2>High-Level Deployment and Configuration Steps</h2>

- Create 2 Virtual Machines in Azure. 
- Ensure communication between the Domain Controller and the Client machine.
- Install and configure Active Directory on the Domain Controller.
- Create Domain Admin within domain
- Organize users and Security Groups
- Join Client-1 to your Domain (mydomain.com) and verify connectivity
- Create thousands of users in bulk using a PowerShell script
- Test the setup by logging into the Client-1 as one of the created users

<h2>Deployment and Configuration Steps</h2>
<h3>Setup</h3>
<p>In Azure you will create 2 Virtual Machines.</br>
- DC-1 for a Domain Controller (Windows Server 2022)</br>
- Client-1 for a Client machine (Windows 10)</br>
</p>
<p>
<img src="https://i.imgur.com/v1Y3v7m.png" height="80%" width="80%" alt="Create VM"/>
</p>

<p>
After VMs are created </br>
- Access VMs using Remote Desktop/ Windows App</br>
- Set Domain Controller’s NIC Private IP address to be static</br>
- Log into DC-1 VM and disable the Windows Firewall (for testing connectivity)</br>
- In Client-1, open Powershell and you can successfuly ping DC-1's private IP address
</p>

<p>
<img src="https://i.imgur.com/O0Lel0M.png" height="80%" width="80%" alt="Ping"/>
</p>

<h3>Install Active Directory</h3>

<p>
Install Active Directory Domain Services</br>
- Log into DC-1, open Server Manager and install Active Directory Domain Services
</p>

<p>
<img src="https://i.imgur.com/3ivZEEL.png" height="80%" width="80%" alt="AD domain svcs"/>
</p>
<p>
Promote as a Domain Controller</br>
- Configure as DC and setup a new forest as mydomain.com</br>
- DC-1 now requires login context mydomain.com\vnssmrls </br>
- In Active Directory create admin user within domain</br>
- Add admin to "Domain Admins" Security Group</br>
</p>

<p>
<img src="https://i.imgur.com/jC11cP5.png" height="80%" width="80%" alt="admin user"/>
</p>
<h3>Join Client-1 to your domain</h3>
- In Azure set Client-1’s DNS settings to DC-1’s Private IP address</br>
- Log into Client-1 VM -> Start -> System -> Rename This PC -> Change -> Member of Domain</br>
- Log into DC-1 to verify Client-1 shows up on AD Users and Computers
</p>

<p>
<img src="https://i.imgur.com/Y0Rh8lo.png" height="80%" width="80%" alt="join domain"/>
</p>

<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>

<p>
<img src="" height="80%" width="80%" alt="join domain"/>
</p>

<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>

<p>
<img src="" height="80%" width="80%" alt="join domain"/>
</p>

