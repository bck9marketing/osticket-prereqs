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
