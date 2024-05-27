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

<p>
   - Install osTicket v1.15.8

</p> 
<p>
	<img src="https://i.imgur.com/Fw4m4fZ.png" height="75%" width="100%" alt="Enable IIS in Windows"/>
</p>
<p>
  Open after installation:
</p>
<p>
	<img src="https://i.imgur.com/X0GcGff.png" height="75%" width="100%" alt="MySQL 5.5"/>
</p>
<br />
<p>
  Add MySQL 5.5 (it will ask for credentials to be created later).
</p>
<p>
  Name: root
</p>
<o>
  Password: Password1:
</p>
<p>
	<img src="https://i.imgur.com/zdhWXNx.png" height="75%" width="100%" alt="Credentials"/>
</p>
<p>
  Add All simple versions of x86 PHP up until 7.3:
</p>
<p>
	<img src="https://i.imgur.com/0npbiTj.png" height="75%" width="100%" alt="PHP"/>
</p>
<p>
  Fix any failures if required. 
</p>
<p>
  Install PHP Version 7.3.8 (or any other version if necessary, archives).
</p>
<p>
  Install Microsoft Visual C++ 2009 Redistributable Package (if necessary).
</p>
<p>
  Install PHP Manager 1.5.0 for IIS 10:
</p>
<p>
	<img src="https://i.imgur.com/LcD8jGJ.png" height="75%" width="100%" alt="PHP Manager"/>
</p>
<br />
<br />
<h3 align="center">Install osTicket v1.15.8</h3>
<br />
<p>
  Download osTicket (download from within lab files: link).
</p>
<p>
	Extract and copy the “upload” folder INTO c:\inetpub\wwwroot:
</p>
	<img src="https://i.imgur.com/0MUJLMU.png" height="75%" width="100%" alt="PHP Manager"/>
	<img src="https://i.imgur.com/1h9goM8.png" height="75%" width="100%" alt="PHP Manager"/>
<p>
	Within c:\inetpub\wwwroot, Rename “upload” to “osTicket”:
</p>
<p>
	<img src="https://i.imgur.com/pDikkgq.png" height="75%" width="100%" alt="rename to osTicket"/>
</p>
<br />
<br />
<h3 align="center">Reload IIS (Open IIS, Stop and Start the server)</h3>
<br />
<p>
	Go to sites -> Default -> osTicket:
</p>
<p>
	<img src="https://i.imgur.com/QeWNlG3.png" height="75%" width="100%" alt="default osTicket"/>
</p>
<p>
	On the right, click “Browse *:80”:
</p>
<p>
	<img src="https://i.imgur.com/3iXhNbi.png" height="75%" width="100%" alt="port 80"/>
</p>
<br />
<br />
<h3 align="center">Enable Extensions in IIS: Note that some extensions are not enabled</h3>
<br />
<p>
	Go back to IIS, sites -> Default -> osTicket.
</p>
<p>
	Double-click PHP Manager:
</p>
<p>
	<img src="https://i.imgur.com/LFKo5Hs.png" height="75%" width="100%" alt="PHP Manager"/>
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
	<img src="https://imgur.com/a/nrQo0kz" height="75%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<br />
<br />
<h3 align="center">Refresh the osTicket site in your browser, observe the changes</h3>
<br />
<p>
	<img src="https://i.imgur.com/6iSNd4H.png" height="75%" width="100%" alt="osTicket change"/>
</p>
<br />
<br />
<h3 align="center">Rename</h3>
<br />
<p>
	From: C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php.
</p>
<p>
	To: C:\inetpub\wwwroot\osTicket\include\ost-config.php:
</p>
<p>
	<img src="https://i.imgur.com/TEw71SD.png" height="75%" width="100%" alt="ost-config"/>
</p>
<br />
<br />
<h3 align="center">Assign Permissions: ost-config.php</h3>
<br />
<p>
	Disable inheritance -> Remove All:
</p>
<p>
	<img src="https://i.imgur.com/1QtRWEF.png" height="75%" width="100%" alt="disable inheritance"/>
</p>
<p>
	New Permissions -> Everyone -> All:
</p>
<p>
	<img src="https://i.imgur.com/YzsMXNX.png" height="75%" width="100%" alt="new permissions"/>
</p>
<p>
	<img src="https://i.imgur.com/k7x9yGR.png" height="75%" width="100%" alt="new permissions - all"/>
</p>
<br />
<br />
<h3 align="center">Continue Setting up osTicket in the browser (click Continue)</h3>
<br />
<p>
	Name Helpdesk.
</p>
<p>
	Default email (receives email from customers):
</p>
<p>
	<img src="https://i.imgur.com/rvMvlNC.png" height="75%" width="100%" alt="continue osTicket setup"/>
	<img src="https://i.imgur.com/YszhIpl.png" height="75%" width="100%" alt="osTicket settings"/>
</p>
<br />
<br />
<h3 align="center">Download and Install HeidiSQL</h3>
<br />
<p>
	<img src="https://i.imgur.com/AEg0b2P.png" height="75%" width="100%" alt="download HeidiSQL"/>
</p>
<p>
	Create a new session, root/Password1.
</p>
<p>
	Connect to the session:
</p>
<p>
	<img src="https://i.imgur.com/9t51ApR.png" height="75%" width="100%" alt="create sessions"/>
</p>
<p>
	Create a database called “osTicket”:
</p>
<p>
	<img src="https://i.imgur.com/vXzmQqg.png" height="75%" width="100%" alt="create database"/>
</p>
<br />
<br />
<h3 align="center">Continue Setting up osTicket in the browser</h3>
<br />
<p>MySQL Database: osTicket</p>
<p>
	MySQL Username: root
</p>
<p>
	MySQL Password: Password1:
</p>
<p>
	<img src="https://i.imgur.com/akDyber.png" height="75%" width="100%" alt="setting up osTicket cont'd"/>
</p>
<p>Click “Install Now!”</p>
<p>Congratulations, hopefully it is installed with no errors!</hp>
<p>
	<img src="https://i.imgur.com/J5omRoE.png" height="75%" width="100%" alt="installation complete"/>
</p>
<br />
<br />
<h3 align="center">Clean up</h3>
<br />
<p>
	Delete: C:\inetpub\wwwroot\osTicket\setup:
</p>
<p>
	<img src="https://i.imgur.com/eg0ZPG3.png" height="75%" width="100%" alt="clean up"/>
</p>
<p>
	Set Permissions to “Read” only: C:\inetpub\wwwroot\osTicket\include\ost-config.php:
</p>
<p>
	<img src="https://i.imgur.com/n6k46XL.png" height="75%" width="100%" alt="permissions"/>
</p>
<br />
<br />
<h3 align="center">Login to the osTicket Admin Panel (http://localhost/osTicket/scp/login.php)</h3>
<br />
<p>
	<img src="https://i.imgur.com/zklvv8K.png" height="75%" width="100%" alt="admin panel"/>
</p>
<br />
<br />
<p>
	And there you have it! I hope this tutorial helped you with installing osTicket.
</p>
<p>
	And now you can practice having your own mock help desk locally to prepare you for a postion in a help desk or IT support position.
</p>



