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
<img src="https://github.com/bck9marketing/osticket-prereqs/assets/159003800/97986285-c1e5-44a7-bfce-000014b14db2" height="80%" width="80%" alt="Disk Sanitization Steps"/>
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
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />
