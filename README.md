<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This lab demonstrates the deployment of osTicket, an open source help desk ticketing system used in teal-world IT support environments.<br />
The focus of this section is on prerequisites and installation, including environment preparation and dependency configuration required to successfully install and run osTicket<br />

<h2>Video Demonstration</h2>

- ### [YouTube: How To Install osTicket with Prerequisites](https://www.youtube.com)

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop (RDP)
- Internet Information Services (IIS)
- Windows 10
- MySQL
- HeidiSQL
- PHP Manager For IIS
- PHP 7.3.8 (NTS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>Required Files</h2>

- **[Download osTicket Installation Files in VM](https://drive.usercontent.google.com/download?id=1b3RBkXTLNGXbibeMuAynkfzdBC1NnqaD&export=download&authuser=0)**
  - osTicket v1.15.8
  - PHP 7.3.8 (NTS)
  - PHP Manager for IIS
  - MySQL 5.5.62
  - Rewrite Module (rewrite_amd64_64_en-US.msi)
  - Microsoft Visual C++ Redistributable (VC_redist.x86)

<h2>Installation Steps</h2>
<h2> 1. Create azure virtual machine in Microsoft Azure </h2>
Set up a virtual machine named osticket-vm in the East US 2 region. Use the Windows 10 Enterprise 22H2 (x64, Gen2) image and configure it with 2 vCPUs and 8 GiB of memory. Set the username to labuser and the password to osTicketPassword1!, then select Review + Create. 
<p>
<img width="1517" height="1313" alt="Screenshot (1311)" src="https://github.com/user-attachments/assets/71695009-7b96-40d4-8d81-1041146d698f" />

<img width="1152" height="1307" alt="Screenshot (1313)" src="https://github.com/user-attachments/assets/956a8a47-ec71-4caa-8a2f-8816ecbb45f8" />

<img width="1153" height="1312" alt="Screenshot (1314)" src="https://github.com/user-attachments/assets/8348de62-b8ac-47a7-9e47-5d89c4bffe5e" />

<h2> 2. Log into the virtual machine using Remote Desktop </h2>
Once the virtual machine is created, go to its settings in Azure and find the public IP address. Use this IP address to log into the virtual machine via Remote Desktop (RDP) using the username and password set earlier.
<img width="895" height="449" alt="Screenshot (72)" src="https://github.com/user-attachments/assets/acc805d4-f2b0-479c-9359-eef8533c15f0" />
<img width="908" height="448" alt="Screenshot (73)" src="https://github.com/user-attachments/assets/71be50a0-2901-4746-a2a0-571b43e5e1ca" />
<img width="1712" height="1054" alt="Screenshot (74)" src="https://github.com/user-attachments/assets/77fdba28-1a2f-4e28-b462-d71abdead2f2" />

<h2> 3. Download and unzip osTicket installation files </h2>
Download the osTicket intstallation files and unzip them to the desktop of the virtual machine.

[osTicket Installation Files in VM](https://drive.usercontent.google.com/download?id=1b3RBkXTLNGXbibeMuAynkfzdBC1NnqaD&export=download&authuser=0)

<h2> 4. Enable IIS and CGI in control panel </h2>
Open Control Panel and select Programs, then click <b>Turn Windows features on or off</b>. In the list, make sure <b>Internet Information Services</b> (IIS) is enabled. Under <b>Internet Information Services</b> &#8594; <b>World Wide Web Services</b> &#8594; <b>Application Development Features</b>, enable <b>CGI</b>. 




<br />



<br />
