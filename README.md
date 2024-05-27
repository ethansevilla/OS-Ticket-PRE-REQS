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

<h2> Create Virtual Machines on Azure </h2>  

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
         <img src="https://github.com/ethansevilla/OS-Ticket-Pre-Reqs/assets/170621372/5f750521-21f7-40af-a2fe-f747d40272a3"/>

</p>

<br /> 
<br />
<h3> Connect to your Virtual Machine with Remote Desktop</h3>
<br />
<p>
	-If using PC, use Remote Desktop Connection
        
</p>
<p> 
      -If using Mac, use Microsoft Remote Deskop
</p> 

<p>  
      -Use the VM public IP address to connect, along with username and password that you used when VM was created.
</p>
	
<p>
	<img src="https://github.com/ethansevilla/OS-Ticket-Pre-Reqs/assets/170621372/318d1ba2-8130-47f6-b56a-19d18dee3d06"/>
</p>
<br />
<br />
<h3>  Install and Enable IIS in Windows </h3>
<br />
<p>
      -Within the VM Windows Machine, go to Control Panel and Programs 
      
</p>	

<p>
	-When in the Programs, go to Turn Windows features on or off 

</p> 
    
<p>
    - World Wide Web Services -> Application Development Features ->  [X] CGI
    [X] Common HTTP Features


</p> 

<p>    -   -> Internet Information Services -> Web Management Tools -> IIS Management Console
	[X] IIS Management Console

</p> 
<p>
	
	
https://github.com/ethansevilla/OS-Ticket-Pre-Reqs/assets/170621372/03ae682d-9c67-4c7c-9f4c-6f629807ef7f

</p>
<br />
<br />
<h3>Install Dependencies</h3>
<br />

<p>
     -Download PHP manager for IIS 
</p>
<p>
     -Download Rewrite Module
</p> 

<p> 
   -Create the directory C:\PHP
</p> 	
<p>
   - Download PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) and unzip the contents into C:\PHP

</p>

<p> 
    -Download and install VC_redist.x86.exe.

</p> 
<p> 
    -Download and install MySQL 5.5.62 (mysql-5.5.62-win32.msi)


</p> 

<p>
	-Add MySQL 5.5 

Name: root

Password: Password1:
</p>
<p>
    - Open IIS as an Admin, Reload IIS (Open IIS, Stop and Start the server)


</p> 
<p>
	<img src="https://github.com/ethansevilla/OS-Ticket-Pre-Reqs/assets/170621372/06ec3624-c223-42d1-8155-03fe8ed46fdc"/>

	
</p>
<br />
<br />
<h3>Install osTicket v1.15.8</h3>
<br />

<p>
	-Download osTicket 
</p>
<p>
       -Extract and copy the “upload” folder to c:\inetpub\wwwroot

</p> 
<p>
	<img src="https://github.com/ethansevilla/OS-Ticket-Pre-Reqs/assets/170621372/28222cd0-273f-4ed9-a0f2-6514e9d0b44e"/>

</p>
<p>
     - Within c:\inetpub\wwwroot, Rename “upload” to “osTicket”
</p>
<p>
	<img src="https://github.com/ethansevilla/OS-Ticket-Pre-Reqs/assets/170621372/f21e9869-8cc7-41d2-8ae9-f89e10900c34"/>
</p>

<br />
<br />
<h3>Reload IIS (Open IIS, Stop and Start the server)</h3>
<br />
<p>
 Go to sites -> Default -> osTicket:
</p>
<p>
	<img src="https://github.com/ethansevilla/OS-Ticket-Pre-Reqs/assets/170621372/1f0fad17-d033-4455-b669-9f30c4dc9bb3"/>

	
</p>
<p>
	On the right, click “Browse *:80”:
</p> 

<p>
	

https://github.com/ethansevilla/OS-Ticket-Pre-Reqs/assets/170621372/48374172-ef6d-4409-bc35-bffa97e430a8

</p>
<br />
<br /> 
<h3>Enable Extensions in IIS: Note that some extensions are not enabled</h3>
<br />
<p>
	Go back to IIS, sites -> Default -> osTicket.
</p>

<p>
	Double-click PHP Manager:
</p>

<p>
	Click “Enable or disable an extension”.
</p>
<p>
	Enable: php_imap.dll.
</p>
<p>
	Enable: php_intl.dll.
</p>
<p>
	Enable: php_opcache.dll:
</p>
<p>
	<img src="https://github.com/ethansevilla/OS-Ticket-Pre-Reqs/assets/170621372/3ad0691a-87f8-4ab0-9211-1e657811c603"/>

</p>

