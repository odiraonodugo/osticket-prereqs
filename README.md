<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>




<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Item 1
- Item 2
- Item 3
- Item 4
- Item 5

<h2>Installation Steps</h2>


<p>
<h2>Part 1 (Create Virtual Machine in Azure)</h2>
Create a Resource Group
Create a Windows 10 Virtual Machine (VM) with 2-4 Virtual CPUs
When creating the VM, allow it to create a new Virtual Network (Vnet)


![Screenshot 2023-04-03 182435](https://user-images.githubusercontent.com/129751851/229794868-25b37f9d-be9b-4033-b57a-c7be9aa3500a.png)

</p>
<p>
<h2>Part 2 (Installation)</h2>
Create an Azure Virtual Machine Windows 10, 4 vCPUs
Name: Vm-osticket
Username: labuser (for example/whatever you chose)
Password: osTicketPassword1! (for example/whatever you chose)

Open this: Installation Files
We will use these files to install osTicket and some of the dependencies. 

Install / Enable IIS in Windows WITH CGI
World Wide Web Services -> Application Development Features -> [X] CGI

From the Installation Files, download and   
<a href="https://drive.google.com/file/d/1RHsNd4eWIOwaNpj3JW4vzzmzNUH86wY_/view">install PHP Manager</a>☺</h1>  for IIS (PHPManagerForIIS_V1.5.0.msi)

From the Installation Files, 
download and install the <a href="https://drive.google.com/file/d/1tIK9GZBKj1JyUP87eewxgdNqn9pZmVmY/view">Rewrite Module</a>☺</h1> (rewrite_amd64_en-US.msi)

Create the directory C:\PHP

From the Installation Files, download <a href="https://drive.google.com/file/d/1snNMtLdCOpMtkCyD4mvl9yOOmvVIp9fP/view">PHP 7.3.8</a>☺</h1>  (php-7.3.8-nts-Win32-VC15-x86.zip)
and unzip the contents into C:\PHP

From the Installation Files, download and install <a href="https://drive.google.com/file/d/1s1OsGF3-ioO0_9LYizPRiVuIkb3lFJgH/view">  VC_redist.x86.exe.</a>☺</h1>

From the Installation Files, download and install <a href="https://drive.google.com/file/d/1_OWh9p7VQLcrB0q_V7qT8yHl0xo5gv7z/view"> MySQL 5.5.62</a>☺</h1> (mysql-5.5.62-win32.msi)
Typical Setup ->
Launch Configuration Wizard (after install) ->
Standard Configuration ->
Password1

Open IIS as an Admin

Register PHP from within IIS

Reload IIS (Open IIS, Stop and Start the server)

Install osTicket v1.15.8
Download osTicket from the Installation Files Folder
Extract and copy “upload” folder to c:\inetpub\wwwroot
Within c:\inetpub\wwwroot, Rename “upload” to “osTicket”

Reload IIS (Open IIS, Stop and Start the server)

Go to sites -> Default -> osTicket
On the right, click “Browse *:80”

Note that some extensions are not enabled
Go back to IIS, sites -> Default -> osTicket
Double-click PHP Manager
Click “Enable or disable an extension”
Enable: php_imap.dll
Enable: php_intl.dll
Enable: php_opcache.dll
Refresh the osTicket site in your browse, observe the changes

Rename: ost-config.php
From: C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php
To: C:\inetpub\wwwroot\osTicket\include\ost-config.php

Assign Permissions: ost-config.php
Disable inheritance -> Remove All
New Permissions -> Everyone -> All

Continue Setting up osTicket in the browser (click Continue)
Name Helpdesk
Default email (receives email from customers)

From the Installation Files, download and install <a href="https://docs.google.com/document/d/1WovrX2DaS9xkfaSr4LXyB4YnnWpXIgPCMMbbfgHmGVw/edit"> HeidiSQL</a>☺</h1>.
Open Heidi SQL

</p>
<br />
