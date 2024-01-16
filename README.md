<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>On-premises Active Directory Deployed in the Cloud (Azure)</h1>
This tutorial outlines the implementation of on-premises Active Directory within Azure Virtual Machines.<br />


<h2>Video Demonstration</h2>

- ### [YouTube: How to Deploy on-premises Active Directory within Azure Compute](https://www.youtube.com)

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services
- PowerShell

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (22H2)

<h2>High-Level Deployment and Configuration Steps</h2>

- Creating a Domain Controller VM
- Creating Client-1 WM, connect to DC Domain
- Install Active Directory on DC
- Creating Users on AD

<h2>Deployment and Configuration Steps</h2>

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Set Up Rescouces in Azure cloud. Creat Domain Controller, name it "DC-1," then set DC's NIC Private IP address to be static. Next create the Client VM, name it "Client-1," use the same resouce group and vnet that was created for VM 1 (DC). check topology with Network Watcher. Next insure connectivity for both VMs. Login to Client-1 Remote Desktop and ping DC-1'S Private IP address (perpetual ping). Login to DC and enable ICMPV4 in the local windows Firewall then check back into Client-1 and make sure the ping is successful.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Nest you are going to install Active Directory. Login to DC-1 and instal Active Directory Domain Services. Promote as a DC: Set Up a new forest with any domain name (example: mydomain.com). Restart and then log back into DC-1 as user mydomain.com\labuser. Then create an Admin and Normal user acccount. Create an Organizational Unit called "_EMPLOYEES" Create another OU name called "_ADMINS" Create a new emyployee(ex:Jane Doe) and a username(ex:jane_admin). add the user to "Domain Admins" Security Group. Log out/close Remote Desktop connection to DC-1 and log back in as "mydomain.com\jane_admin" or whatever username you did. the user is an admin account from now on.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />
