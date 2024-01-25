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
<h3>Phase One</h3>
  
![Configuring Active Directory Phase 1 - Imgur](https://github.com/PhillisEssel/configure-ad/assets/156061642/20a12556-8005-426c-afe8-96e1c91ff74a)

<p><a href="https://imgur.com/a/5ZE6blF">More</a></p>

</p>
<p>
Set Up Rescouces in Azure cloud. Creat Domain Controller, name it "DC-1," then set DC's NIC Private IP address to be static. Next create the Client VM, name it "Client-1," use the same resouce group and vnet that was created for VM 1 (DC). check topology with Network Watcher. Next insure connectivity for both VMs. Login to Client-1 Remote Desktop and ping DC-1'S Private IP address (perpetual ping). Login to DC and enable ICMPV4 in the local windows Firewall then check back into Client-1 and make sure the ping is successful. Next you are going to install Active Directory. Login to DC-1 and instal Active Directory Domain Services. Promote as a DC: Set Up a new forest with any domain name (example: mydomain.com). Restart and then log back into DC-1 as user mydomain.com\labuser.
</p>
<br />

<p>
<h3>Phase Two</h3>
  
![Configuring Active Directory Phase 2 - Imgur](https://github.com/PhillisEssel/configure-ad/assets/156061642/1d4bcfc3-deee-490d-a35c-6eaf605e0818)

<p><a href="https://imgur.com/a/6cO46ET">More</a></p>
  
</p>
<p>
Then create an Admin and Normal user acccount. Create an Organizational Unit called "_EMPLOYEES" Create another OU name called "_ADMINS" Create a new emyployee(ex:Jane Doe) and a username(ex:jane_admin). add the user to "Domain Admins" Security Group. Log out/close Remote Desktop connection to DC-1 and log back in as "mydomain.com\jane_admin" or whatever username you did. the user is an admin account from now on. Next you join Client-1 to your domain. Go to the azure portal and set Client-1's DNS settings to the DC's Private IP address and proceed to restart Client-1 from the Azure Portal. Login to Client-1 as the original local admin (labuser) and join it to the domain (computer will automatically restart). 
</p>
<br />

<p>
<h3>Phase Three</h3>

![Configuring Active Directory Phase 3 - Imgur](https://github.com/PhillisEssel/configure-ad/assets/156061642/4340a86f-e2a9-4ad8-abfe-8bd1f42b41df)

<p><a href="https://imgur.com/a/6cO46ET)">More</a></p>
  
</p>
<p>
Next Login to DC and verify Client-1 shows up in Active Directory Users and Computers (ADUC) under "Computers" container on root of the domain. Set up remote desktop for non-admin users on Client-1. log in as the domain admin and open system properties, click "remote desktop" and allow "domain users" access to it so you can log in as a normal non-admin user. Next create a bunch of additional users and attempt to log into Client-1 as one of them (good for businesses that have thousands of employees or schools that have thousands of students). Login to DC-1 as admin, open Powershell_ise as an administrator, create a new file and paste the contents of the script into it. Run the script and observe the accounts being created. After, open ADUC and observe the accounts in OU and attempt to login as one on Client-1. 
</p>
<br />
