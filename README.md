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

- For the purposes of this tutorial, I will be using a 4 vCPU virtual machine through Microsoft Azure. Link [here](https://github.com/bck9marketing/VM) to get one set up.
- Download the necessary installation files through [Link 1](https://drive.google.com/drive/u/1/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6) & [Link 2](https://www.heidisql.com/installers/HeidiSQL_12.3.0.6589_Setup.exe)

<h2>Installation Steps</h2>

<p>
<img src="https://github.com/bck9marketing/osticket-prereqs/assets/159003800/1da164ea-e77e-41ed-b489-c6b478df9337" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://github.com/bck9marketing/osticket-prereqs/assets/159003800/6c9b6830-b743-4e03-955d-1f907754dc19" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Once logged into our vm, we're going to download our installation files. This should leave us with 1 zip folder with many files inside and 1 HeidiSQL install.
</p>
<br />

<p>
<img src="https://github.com/bck9marketing/osticket-prereqs/assets/159003800/1b0d972d-f6c7-4b4e-9186-76c4961c41eb" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Next we're going to open "Control Panel" by searching for it in the bottom left windows search bar. From there click "Programs".</p>
<br />

<p>
<img src="https://github.com/bck9marketing/osticket-prereqs/assets/159003800/5a6ee8c0-d338-4dec-ae5f-a198ebd711f9" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://github.com/bck9marketing/osticket-prereqs/assets/159003800/dc6bd872-b2f6-4960-92e7-e0ec695d3a19" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://github.com/bck9marketing/osticket-prereqs/assets/159003800/2079ec73-f606-4f86-a05d-089ab1a5bd35" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
From here click on "Turn Windows features on or off" underneath "Programs and Features". In the window that pops up, search for and then check "Internet Information Services". Now expand the "Internet Information Services" folder that you just checked on by clicking the + button next to it. Within this folder we want to expand the "World Wide Web Services" folder, and within THAT folder expand "Application Development Features" and check "CGI". Going back to the "World Wide Web Services" folder, expand "Common HTTP Features" and make sure everything inside is checked on.<br>
 Compare your folder with the image above and once sure everything is correct, click ok and let windows install everything. Close out of that window and the control panel once windows completes the changes.
</p>
<br />

<p>
<img src="https://github.com/bck9marketing/osticket-prereqs/assets/159003800/eb6a0086-080c-4984-a105-6b506d2a281e" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Next we're going to create a folder named "PHP" inside our C drive. This can be done by opening File Explorer, clicking "This PC" on the left, clicking "Local Disk (C:)" on the right, right clicking within that window and clicking "New>Folder". We will also in another File Explorer window go into our zip file containing our installation files and install both "PHPManagerForISS_V1.5.0" and "rewrite_amd64_en-US".
</p>
<br />

<p>
<img src="https://github.com/bck9marketing/osticket-prereqs/assets/159003800/e869c357-b099-4d35-b16a-4583d7f5ae78" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Within that installation zip, we're going to go inside the "php-7.3.8-nts-Win32-VC15-x86" zip file and then drag all of its contents into the "PHP" folder we just created.
</p>
<br />

<p>
<img src="https://github.com/bck9marketing/osticket-prereqs/assets/159003800/f3ddfb33-29fc-4350-b42f-487cced39d4b" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Also inside that installation zip we're going to go ahead and install "VC_redist.x86" and "mysql-5.5.62-win32". For the mysql install, click "Typical" for the setup type and post install launch the configuration wizard. In the new window choose "Standard Configuration" and use "Password1" for the password. Leave everything else as is during the install.
</p>
<br />

<p>
<img src="https://github.com/bck9marketing/osticket-prereqs/assets/159003800/75bbaa8c-168f-47a8-afb1-94b31b492158" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Next we're going to open Internet Information Services Manager as administrator by searching "ISS" in the windows search bar, right clicking "Internet Information Services (ISS) Manager" and clicking "Run as administrator"
</p>
<br />

<p>
<img src="https://github.com/bck9marketing/osticket-prereqs/assets/159003800/b1b43811-52b0-41c7-a494-141c9fe2d035" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://github.com/bck9marketing/osticket-prereqs/assets/159003800/b645d267-573b-49f8-8842-9dbfb95b7352" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://github.com/bck9marketing/osticket-prereqs/assets/159003800/4debbbc7-19e6-4f6c-bba4-ded5be08d8fb" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Once we're inside ISS Manager, open "PHP Manager" and then click "Register new PHP version". In the window that pops up click the "..." button and in the new File Explorer window that pops up, navigate to the "PHP" folder you created earlier. This folder should be in the directory C:\PHP. Inside the PHP folder should be a file named "php-cgi", click that file and then click open. Click ok. Now navigate back to the home ISS Manager page by double clicking VM-1 in the top left and once there click the restart button on the right.
</p>
<br />

<p>
<img src="https://github.com/bck9marketing/osticket-prereqs/assets/159003800/c12f2033-f446-4939-9aed-810c40c435f6" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://github.com/bck9marketing/osticket-prereqs/assets/159003800/2ca74153-7d39-40c7-9740-a3fad1f2a0f2" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Next go back to your installation zip, go inside the "osTicket-v1.15.8" zip file and copy the "upload" folder. This folder then needs to be pasted into "C:\inetpub\wwwroot". Once pasted there rename the "upload" folder to "osTicket". Once again restart the server inside "ISS Manager".
</p>
<br />

<p>
<img src="https://github.com/bck9marketing/osticket-prereqs/assets/159003800/dad12c0b-b981-46f9-b190-bb1cbe32ecd8" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Within "ISS Manager" on the left expand "Sites" and then expand "Default Web Site", click osTicket and then on the right, click "Browse*:80(http)". This will open your browser with an osTicket installer. Leave that window be for now.
</p>
<br />

<p>
<img src="https://github.com/bck9marketing/osticket-prereqs/assets/159003800/88122fbd-7d8b-435a-8ac7-48e429d62ec9" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://github.com/bck9marketing/osticket-prereqs/assets/159003800/3357da42-fc29-456f-8113-3b5eb4ccb452" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://github.com/bck9marketing/osticket-prereqs/assets/159003800/d953a8ed-f210-4fba-b1da-e8e50c4da3d3" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://github.com/bck9marketing/osticket-prereqs/assets/159003800/b9a615be-dfde-4d13-b421-bee5a5f4be1c" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Back to ISS Manager within that same "osTicket" folder, open PHP Manager on the right. Towards the bottom click "Enable or disable an extension". In this next page towards the bottom Disabled greyed out options, find and enable the following options by right clicking each one and clicking enable :<br>
 - php_imap.dll<br>
 - php_intl.dll<br>
 - php_opcache.dll<br>
With those enabled refresh the osTicket installer page in your browser.
</p>
<br />

<p>
<img src="https://github.com/bck9marketing/osticket-prereqs/assets/159003800/50d1f741-610b-402a-89ac-0318f14f4642" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://github.com/bck9marketing/osticket-prereqs/assets/159003800/4b3c4e8a-18c6-4580-a26a-9f70d6a123e0" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Before continuing the osTicket browser install, navigate to "C:\inetpub\wwwroot\osTicket\include\" and rename the "ost-sampleconfig.php" file towards the bottom to "ost-config.php". Then right click this file and click "Properties".
</p>
<br />

<p>
<img src="https://github.com/bck9marketing/osticket-prereqs/assets/159003800/9d5216d5-3b3c-494f-9e66-01ffd0017ae4" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://github.com/bck9marketing/osticket-prereqs/assets/159003800/13bb05ef-4d26-4380-9bd7-c0efc3dc9f44" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://github.com/bck9marketing/osticket-prereqs/assets/159003800/d668f58b-b0e8-46f7-a164-556a3a44645c" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
In this "Properties" window go to the "Security" tab and click the "Advanced" button. In the new window named "Advanced Security Settings for ost-config.php" click "Disable inheritance" and then select "Remove all inherited permissions from this object". Go back to the "Advanced Security Settings" window click "Add", click "Select a principle" in the next window, and in the window after that type in "Everyone" into the textbox. Click ok. Now in the "Permission Entry" window select all the permissions and click ok. Now back in the "Advanced Security Settings" window hit Apply then Ok.
</p>
<br />

<p>
<img src="https://github.com/bck9marketing/osticket-prereqs/assets/159003800/adc881a7-80d5-49f8-9070-1dd8198c2131" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://github.com/bck9marketing/osticket-prereqs/assets/159003800/fb302c41-4463-4dad-b4f4-ba3aaa734961" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
With that out of the way we can now go back to our browser osTicket installer and click "Continue". For this tutorial we're going to fill out the installation form with basic test information. Take note of the entries I used for the form and copy them. Make sure you use different emails for the "Default Email" box under System Settings and the "Email Address" box under Admin User. "Password1" will be used for every password.
</p>
<br />

<p>
<img src="https://github.com/bck9marketing/osticket-prereqs/assets/159003800/db09bb9e-7fba-4bea-a5b3-aa509c763453" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://github.com/bck9marketing/osticket-prereqs/assets/159003800/7253fccf-b024-4127-8a85-8827c84ccb35" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Before we can finish the osTicket installer we have to install HeidiSQL, so navigate to your downloads folder and install "HeidiSQL_12.3.0.6589_Setup". Launch HeidiSQL when the install is finished.<br>
 With HeidiSQL open, click "New" in the bottom left. Type in "Password1" in the right Password text box and then click open.
</p>
<br />

<p>
<img src="https://github.com/bck9marketing/osticket-prereqs/assets/159003800/5abe1b02-a0d7-4b7e-8133-4de69ecbb718" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://github.com/bck9marketing/osticket-prereqs/assets/159003800/2f6184e3-53cf-4133-a488-30be0a26dbf7" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
In our new HeidiSQL window we will now create a new database by right clicking "Unnamed" on the left > Create new > Database . Name this database "osTicket" and click ok.
</p>
<br />

<p>
<img src="https://github.com/bck9marketing/osticket-prereqs/assets/159003800/7b79e481-6f5a-465a-89c6-502154dc4a8c" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
We can now go back to our osTicket installation form and fill out the remaining boxes by inputing "osTicket" under MySQL Database, "root" under MySQL Username, and "Password1" under MySQL Password. Click "Install Now". osTicket should now be installed!
</p>
<br />

<p>
<img src="https://github.com/bck9marketing/osticket-prereqs/assets/159003800/aeb67611-83ba-4ec3-9ae3-1d6e4789194d" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Before moving on to the next section, we're going to navigate to C:\inetpub\wwwroot\osTicket\ and delete the "setup" folder. Then go into the "include" folder and rechange the permissions for "ost-config.php". Same as before : Right click > Properties > Security tab > Advanced button> Open the Allow Everyone tab under Permission entries> Check only Read and Read & Execute>Ok>Apply>Ok. 
</p>
<br />

<p>
<img src="https://github.com/bck9marketing/osticket-prereqs/assets/159003800/c67cbd9f-ddb5-446a-aa36-c109c8d21a78" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
osTicket Help Desk Login Page : http://localhost/osTicket/scp/login.php<br>
osTicket End User Page: http://localhost/osTicket/
</p>
<br />
