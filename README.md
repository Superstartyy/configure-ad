<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>On-premises Active Directory Deployed in the Cloud (Azure)</h1>
This tutorial outlines the implementation of on-premises Active Directory within Azure Virtual Machines.<br />




<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services
- PowerShell

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)

<h2>High-Level Deployment and Configuration Steps</h2>

1. Create the Domain Controller VM (Windows Server 2022) named “DC-1”
Take note of the Resource Group and Virtual Network (Vnet) that get created at this time

2. Ensure Connectivity between the client and Domain Controller

3 .Create an Admin and Normal User Account in AD

4 .Create a bunch of additional users and attempt to log into client-1 with one of the users

<h2>Deployment and Configuration Steps</h2>



![image](https://github.com/Superstartyy/configure-ad/assets/159973263/22515919-222e-45b6-b24f-522ae52245e9)


</p>
<p>
Establish the virtual machine, in order to do a remote desktop connection. By creating DC-1 and Client-1 you are able to create the Azure Active Directory function that enables systems to work more effectively and efficently when computing resrouces on a main stream. 
</p>
<br />


![image](https://github.com/Superstartyy/configure-ad/assets/159973263/97a6efae-8e43-4674-838a-6bf9916d89f0)

</p>
<p>
In Active Directory Users and Computers (ADUC), establish two Organizational Units (OUs) named "_EMPLOYEES" and "_ADMINS." Within the "_EMPLOYEES" OU, create a new employee account named "Jane Doe" with the username "jane_admin" and the same password. Subsequently, add "jane_admin" to the "Domain Admins" Security Group. Logout or close the Remote Desktop connection to DC-1, then log back in using the credentials "mydomain.com\jane_admin." Moving forward, utilize the user account "jane_admin" as your administrative account.
</p>
<br />

![image](https://github.com/Superstartyy/configure-ad/assets/159973263/12ae4f61-4d04-4460-911b-9541b4853064)

</p>
<p>
From the Azure Portal, configure Client-1's DNS settings to use the DC's Private IP address. Subsequently, initiate a restart for Client-1 through the Azure Portal. Following the restart, log in to Client-1 via Remote Desktop using the original local admin credentials (labuser) and proceed to join it to the domain (the computer will undergo a restart during this process). Afterward, access the Domain Controller via Remote Desktop and confirm in Active Directory Users and Computers (ADUC) that Client-1 is visible within the "Computers" container located on the root of the domain. To organize, establish a new Organizational Unit (OU) named "_CLIENTS" and move Client-1 into this OU.
</p>
<br />
