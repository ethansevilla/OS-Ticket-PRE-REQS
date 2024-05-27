# OS-Ticket-Pre-Reqs 
<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />



<h2>Environments and Technologies Used</h2>

- Microsoft Azure Virtual Machine
- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)


<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2> List of Prerequisites </h2> 

-   PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi) (https://www.iis.net/downloads/community/2018/05/php-manager-150-for-iis-10)
-   Rewrite Module (rewrite_amd64_en-US.msi)(https://www.iis.net/downloads/microsoft/url-rewrite)
-   PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip)
-   VC_redist.x86.exe (https://learn.microsoft.com/en-us/cpp/windows/latest-supported-vc-redist?view=msvc-170)
-    MySQL 5.5.62 (mysql-5.5.62-win32.msi) (https://downloads.mysql.com/archives/community/)
-    HeidiSQL (https://www.heidisql.com/download.php) 

<h2> Installation Steps </h2>  

<h2> (Step 1)Create Virtual Machines on Azure </h2>  

<br />
<p>
	Create a Resource Group
</p>
<p>
	  

https://github.com/ethansevilla/OS-Ticket-Pre-Reqs/assets/170621372/567e07cf-0f82-4dbb-9b00-0b2681888fdb


  
</p>
<p>
	Create a Windows 10 Virtual Machine (VM) with 2-4 Virtual CPUs
	When creating the VM, allow it to create a new Virtual Network (Vnet):
</p>
<p>
	<img src="https://i.imgur.com/dEF1c7h.png" height="75%" width="100%" alt="Windows Virutal Machine"/>
</p>



</p>
<br />

