<p align="center">

![image](https://github.com/Chas101/AD-EX/assets/153942150/cb2458d6-290b-4ae6-b081-7dc4b3d4fcfb)


</p>

<h1>Active Directory </h1>
This outlines steps in Active Directory deploment and creating users. .<br />

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

![image](https://github.com/Chas101/AD-EX/assets/153942150/83f1c37a-45c3-4c8b-9be4-c7ba9d0c7546)

![image](https://github.com/Chas101/AD-EX/assets/153942150/e604233d-cf0d-498e-b354-abcf9487bdd4)


2. Create Client VM (Client-1)

Create a Windows 10 VM named "Client-1" using the same Resource Group and Vnet as DC-1.
Ensure that both VMs are in the same Vnet.

![image](https://github.com/Chas101/AD-EX/assets/153942150/ff619994-e624-4d9b-a6c2-ca4ab7f7de8f)

![image](https://github.com/Chas101/AD-EX/assets/153942150/4ee232ef-b5d3-408b-8e60-b2c9eb9d9da6)


3. Connectivity Setup

Ensure connectivity between the client and Domain Controller.
Login to Client-1 with Remote Desktop and ping DC-1’s private IP address.
Enable ICMPv4 in the local Windows Firewall on DC-1 to allow ping.

![image](https://github.com/Chas101/AD-EX/assets/153942150/5354f76c-0301-4970-a603-aeb5163e0a0f)

![image](https://github.com/Chas101/AD-EX/assets/153942150/78bce6fc-7195-47a2-9b21-7418d20e500c)



4. Install Active Directory on DC-1

Install Active Directory Domain Services on DC-1.
Promote DC-1 as a domain controller and set up a new forest (e.g., mydomain.com).
Restart DC-1 and log back in as user: mydomain.com\labuser.

![image](https://github.com/Chas101/AD-EX/assets/153942150/fc9d98f3-50ba-47ac-bac7-d33b703e05e3)

![image](https://github.com/Chas101/AD-EX/assets/153942150/9ff5d3a6-d9bb-403c-abd2-4c88e6b9f381)

![REDO](https://github.com/Chas101/AD-EX/assets/153942150/959658aa-25d3-48b8-9d9a-387dac391c3a)


5. Create Admin and Normal User Accounts in AD

In Active Directory Users and Computers (ADUC), create an Organizational Unit (OU) called "_EMPLOYEES" and another OU named "_ADMINS".
Create a new employee named "Jane Doe" with the username "jane_admin" and add her to the "Domain Admins" Security Group.
Logout and log back into DC-1 as "mydomain.com\jane_admin".

![image](https://github.com/Chas101/AD-EX/assets/153942150/9befa9f4-601e-410e-bc68-3fce93446a84)

![image](https://github.com/Chas101/AD-EX/assets/153942150/a8911232-f11b-451e-9c0c-726edde9b483)

![image](https://github.com/Chas101/AD-EX/assets/153942150/e99e4678-fd5f-4af1-986f-b226489fb8d4)

6. Join Client-1 to the Domain

Set Client-1's DNS settings to the DC's Private IP address from the Azure Portal.
Restart Client-1 from the Azure Portal.
Login to Client-1 using Remote Desktop as the original local admin (labuser) and join it to the domain.
Verify Client-1 shows up in Active Directory Users and Computers (ADUC) inside the "Computers" container on the root of the domain.

![image](https://github.com/Chas101/AD-EX/assets/153942150/2215b5c6-00ca-40ba-84d0-93a495b650a8)

![image](https://github.com/Chas101/AD-EX/assets/153942150/9453e640-0c39-46ff-9033-e93b1252c6d8)

![image](https://github.com/Chas101/AD-EX/assets/153942150/e6f07078-ceca-455d-8aee-a76deb764767)

![1st picture](https://github.com/Chas101/AD-EX/assets/153942150/ffc2aa21-8644-4b88-bf06-00956d354a13)

![2nd picture](https://github.com/Chas101/AD-EX/assets/153942150/53412076-8959-4174-9044-468297f89b5e)








</p>
<br />

<p>

</p>
<p>

</p>
<br />

<p>
