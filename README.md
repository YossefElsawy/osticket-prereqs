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

- [Step 2.1: Connecting to VM and enabling features](https://www.loom.com/share/f596070ba6304f4e85bc57c7ae90f437?sid=1cb847d9-960d-41a8-b467-bf0c501760fe)

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


- [Step 2.2: Enabling and installing remaining features](https://www.loom.com/share/a265074d64f04749a9c915d439e85da2?sid=cf27cbc4-05ae-4b97-9356-ab73ee09bbcd)

<p>
Continuing on we will now install the PHP Manager (PHPManagerForIIS_V1.5.0.msi) along with Rewrite Module (rewrite_amd64_en-US.msi). Open the files and go through the installation.

The next step is to create the PHP folder in the C Drive. 

After you created the folder you want to download the PHP 7.3.8 folder (php-7.3.8-nts-Win32-VC15-x86.zip). 
### Note: Make sure to unzip the folder in the newly created PHP folder located in the C Drive.


![image](https://github.com/YossefElsawy/osticket-prereqs/assets/141590348/27c951a8-633d-4978-b52d-4a7235001877)

After that you will want to download VC_redist.x86.exe and go through the installation process

Lastly, we wil want to download MySQL 5.5.62 (mysql-5.5.62-win32.msi) the installation process is shown below

Select Typical for the Setup Type 

![image](https://github.com/YossefElsawy/osticket-prereqs/assets/141590348/ed320989-41eb-449f-a969-6d6d56bc4e5d)

Then Standard Configuration

![image](https://github.com/YossefElsawy/osticket-prereqs/assets/141590348/52b69ea7-4614-4094-ae86-b1dcc4d32cd2)

Then Install as Windows Service > Then make sure to set the password to something you can remember. In this project I used "Password1". The username that is given to you is "root"
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />


- [Step 2.3: Enabling and installing remaining features](https://www.loom.com/share/c7f50b5f75654aeeaa84a7f5ca8b3362?sid=e29b6fdd-57df-4aa7-8e5c-b55b1364db6a)

<p>

Open IIS as an Admin (Right click on ISS and click on the option "Run as Administrator"

![image](https://github.com/YossefElsawy/osticket-prereqs/assets/141590348/38d773fa-4107-4f8f-94ed-6efcce0ed1c9)


Register PHP from within IIS by double clicking on 'PHP Manager' > Register new PHP version > php-cgi (this is located in the PHP folder on the C drive) ; make sure to click on restart in IIS (located on the right side of the application when clicking on the connection "VM-osTicket"

 ![image](https://github.com/YossefElsawy/osticket-prereqs/assets/141590348/f943add1-4ae8-480a-a8e1-95d33f84f517) ![image](https://github.com/YossefElsawy/osticket-prereqs/assets/141590348/253d9706-0af1-430e-83a5-35440d8f1269)

 Now we will install osTicket ; Download osTicket files. Go into the folder and move the folder "upload" to "c:\inetpub\wwwroot" and rename it to "osTicket". Reload IIS to make sure that everything is updated.

If you go back into IIS, you will see osTicket under 'Default Web Site' under connections. If you click on Browse.80 it will load osTicket.

![tempsnip](https://github.com/YossefElsawy/osticket-prereqs/assets/141590348/b4ea551d-c259-4b62-ad80-8283814d279a)

To enable the necessary PHP extensions, open IIS, navigate to sites > Default > osTicket; double-click PHP Manager. You will need to enable the following: php_imap.dll, php_intl.dll, and php_opcache.dll. Refresh the osTicket webpage and you will see a few more check marks added.

Go to C:\inetpub\wwwroot\osTicket\include directory and rename "ost-sampleconfig.php" to "ost-config.php".
In that same folder go back to ost-config.php and change the permissions
Properties > Security > Advanced > Disable Inheritance > Remove all inherited permissions from this object. 

Then you want to click Add > Select a Principal > Enter "Everyone" in the "Enter the object name to select" and then click "Check Names" > Okay

After that you'll click on Full Control > Ok > Apply > Ok

Go back to osTicket webpage and create a helpdesk name, email and admin user information. Make sure to remember the username.

Lastly, we will download HeidiSQL ; go through the installation.

Once it is opened, click new and then enter a password. Make sure to remember this password, this project I used 'Password1'; click open. 
Use the SQL information to fill in the remaining information on the osTicket installation page. You will need the username, password, and the name of the sql database.
To create the SQL database you will right click on 'Unnamed' > Create new > database. Title it osTicket. On the osTicket page finalize the entry and click install now.
 
Finally, we will do some cleanup. Go to C:\inetpub\wwwroot\osTicket and delete the folder 'Setup'
Then go to C:\inetpub\wwwroot\osTicket\include and right click on "ost-config,php"
Properties > Security > Advanced
Double click on "Everyone" and uncheck all of them except for "Read" and "Read and Execute" 
Then click Ok > Apply > Ok

This completes Section 1 of the lab

<hr>
<h1><p align=center>All Done</p></h1>

<h2><p align=center>Next Demonstration:<br><a href="https://github.com/YossefElsawy/post-install-config/blob/main/README.md">osTicket - Post-Install Configuration</a></p></h2>
