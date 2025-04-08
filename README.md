<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />


<h2>Video Demonstration</h2>

- ### [YouTube: How To Install osTicket with Prerequisites](https://www.youtube.com)

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Repository and VM Creation
- osTicket File Installation
- Install / Enable IIS 
- PHP Registration and Configuration
- MySQL Configuration 

<h2>Installation Steps</h2>

<p>
Repository and VM Creation <br />
  
<img src="https://i.imgur.com/5Km8Lld.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

  <br /> <br />
  <img src="https://i.imgur.com/eLbrFBw.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Create an Azure Virtual Machine Windows 10, 4 vCPUs 
  
 - Name: WindowVM
 - Username: labuser
 - Password: osTicketPassword1!

Log into the VM with Remote Desktop
<p>
  <br />
</p>

osTicket File Installation:

Within the VM (WindowVM), download the osTicket-Installation-Files.zip and unzip it onto your desktop. The folder should be called “osTicket-Installation-Files”

- We will use the files in this folder to install osTicket and some of the dependencies.

</p>
<br />

<p>

Install / Enable IIS in Windows WITH CGI

World Wide Web Services -> Application Development Features -> [X] CGI
  
<img src="https://i.imgur.com/obPFPTw.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>


</p>
<br />

<p>
Dependency Files:

From the “osTicket-Installation-Files” folder, install PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi)
  
<img src="https://i.imgur.com/1SGtzXR.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

<br /> 

From the “osTicket-Installation-Files” folder install the Rewrite Module (rewrite_amd64_en-US.msi)

<img src="https://i.imgur.com/DtAJJp9.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

<br />

Create the directory C:\PHP

- File Explorer -> 'C' Drive -> New Folder

From the “osTicket-Installation-Files” folder, unzip PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) into the “C:\PHP” folder

<br />

From the “osTicket-Installation-Files” folder, install VC_redist.x86.exe.

(Downloaded mine from doing lab prior.)

<img src="https://i.imgur.com/jUKTyEu.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>


</p>
<br />


<p>
PHP Regristration and Configuration 

From the “osTicket-Installation-Files” folder, install MySQL 5.5.62 (mysql-5.5.62-win32.msi)

- Typical Setup ->
- Launch Configuration Wizard (after install) ->
- Standard Configuration ->
- Username: root
- Password: root

  
<img src="https://i.imgur.com/13YrXXd.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

<br /> 

Open IIS as an Admin

Register PHP from within IIS (PHP Manager -> C:\PHP\php-cgi.exe)

Reload IIS (Open IIS, Stop and Start the server)

<img src="https://i.imgur.com/hD2wTMt.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

<br /> 


Install osTicket v1.15.8

- From the “osTicket-Installation-Files” folder, unzip “osTicket-v1.15.8.zip” and copy the “upload” folder into “c:\inetpub\wwwroot”
- Within “c:\inetpub\wwwroot”, Rename “upload” to “osTicket”

Reload IIS (Open IIS, Stop and Start the server)

<img src="https://i.imgur.com/NnQbgwz.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

<br />

Go to sites -> Default -> osTicket

- On the right, click “Browse *:80”

<img src="https://i.imgur.com/jzXJqHb.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

<br />

Note that some extensions are not enabled

- Go back to IIS, sites -> Default -> osTicket
- Double-click PHP Manager
- Click “Enable or disable an extension”
- Enable: php_imap.dll
- Enable: php_intl.dll
- Enable: php_opcache.dll
- Refresh the osTicket site in your browser, observe the changes

<img src="https://i.imgur.com/Eidc0Zp.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

<br />

Rename: ost-config.php

- From: C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php
- To: C:\inetpub\wwwroot\osTicket\include\ost-config.php

<img src="https://i.imgur.com/qwpKkd4.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>


<br />

Assign Permissions: ost-config.php

- Disable inheritance -> Remove All
- New Permissions -> Everyone -> All

<img src="https://i.imgur.com/HtLIwuS.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

<br />

Continue Setting up osTicket in the browser (click Continue)

- Name Helpdesk
- Default email (receives email from customers)

<br />

MySQL Configuration:

  From the “osTicket-Installation-Files” folder, install HeidiSQL.
  
- Open Heidi SQL
- Create a new session, root/root
- Connect to the session
- Create a database called “osTicket”

<img src="https://i.imgur.com/5HYqeXa.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>


<img src="https://i.imgur.com/7P2DzTZ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

Continue Setting up osTicket in the browser

- MySQL Database: osTicket
- MySQL Username: root
- MySQL Password: root
- Click “Install Now!”

<img src="https://i.imgur.com/gfmf3lk.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

<p>

Congratulations, hopefully it is installed with no errors!
Browse to your help desk login page: http://localhost/osTicket/scp/login.php

End Users osTicket URL:
http://localhost/osTicket/ 

<img src="https://i.imgur.com/Wy7FyeU.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

</p>
<br />
