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

<img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>


</p>
<br />
