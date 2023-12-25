<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket -Tickets an Ticket LifeCycle </h1>
This outlines the lifecycle of a ticket in the help desk ticketing system osTicket.<br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)
  
<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>
Prerequisites:

- Server Setup-Ensure a web server.
- Database Preparation-Verify PHP and Composer are installed.

<h2>Active Directory Configuration </h2>

<p>

</p>

1. Create Domain Controller VM (DC-1)

Create a Windows Server 2022 VM named "DC-1" in Azure.
Note the Resource Group and Virtual Network (Vnet) created for DC-1.
Set the Domain Controller's NIC Private IP address to be static.


2. Create Client VM (Client-1)

Create a Windows 10 VM named "Client-1" using the same Resource Group and Vnet as DC-1.
Ensure that both VMs are in the same Vnet.





3. Connectivity Setup

Ensure connectivity between the client and Domain Controller.
Login to Client-1 with Remote Desktop and ping DC-1’s private IP address.
Enable ICMPv4 in the local Windows Firewall on DC-1 to allow ping.

4. Install Active Directory on DC-1

Install Active Directory Domain Services on DC-1.
Promote DC-1 as a domain controller and set up a new forest (e.g., mydomain.com).
Restart DC-1 and log back in as user: mydomain.com\labuser.

5. Create Admin and Normal User Accounts in AD

In Active Directory Users and Computers (ADUC), create an Organizational Unit (OU) called "_EMPLOYEES" and another OU named "_ADMINS".
Create a new employee named "Jane Doe" with the username "jane_admin" and add her to the "Domain Admins" Security Group.
Logout and log back into DC-1 as "mydomain.com\jane_admin".


6. Join Client-1 to the Domain

Set Client-1's DNS settings to the DC's Private IP address from the Azure Portal.
Restart Client-1 from the Azure Portal.
Login to Client-1 using Remote Desktop as the original local admin (labuser) and join it to the domain.
Verify Client-1 shows up in Active Directory Users and Computers (ADUC) inside the "Computers" container on the root of the domain.

</p>
<br />

<p>

</p>
<p>

</p>
<br />

<p>
