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

- Windows 10</b> (22H2)

<h2>List of Prerequisites</h2>

- Create a Virtual Machine on Azure : [Step 1: Create a Virtual Machine in Azure](https://www.loom.com/share/e7bb74ec79df42ae815d82b1f3953c32?sid=ac8feed0-3b61-41fc-8441-65f6489e6f3d)

- Have the installation items
![image](https://github.com/YossefElsawy/osticket-prereqs/assets/141590348/89bde17e-b283-4c54-9a8a-d39edd9e23c7)

- Item 3
- Item 4
- Item 5

<h2>Installation Steps</h2>

- [Step 2: Connecting to VM and enabling features](https://www.loom.com/share/f596070ba6304f4e85bc57c7ae90f437?sid=1cb847d9-960d-41a8-b467-bf0c501760fe)

<p>
Now we will connect to the VM via a Remote Desktop Connection. You will need to get the Public IP Address from the VM by clicking on the actual VM in Azure then getting the Public IP Address. Use the IP address to login on the RDP. After that the RDP will ask you for a login; make sure to use the username and password you created in the VM.
</p>
<p>
After logging into the VM, the first thing you will want to do is to Enable IIS in Windows and the other features. Step by step:
  
Search for Control Panel > Programs > Programs and Features > Turn Windows features on or off

Make sure to tick the box for Internet Information Systems

  Internet Information Systems > Application Development Features > [check] CGI

Internet Information Systems > Common HTTP Features > [check] HTTP Redirection and WebDAV Publishing

Now to verify that this step is completed go onto the web browser and enter 127.0.0.1 and you should get to a webpage that says Internet Information Services
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Continuing on we will now install the PHP Manager (PHPManagerForIIS_V1.5.0.msi) along with Rewrite Module (rewrite_amd64_en-US.msi). Open the files and go through the installation.

The next step is to create the PHP folder in the C Drive
![image](https://github.com/YossefElsawy/osticket-prereqs/assets/141590348/27c951a8-633d-4978-b52d-4a7235001877)

</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />
