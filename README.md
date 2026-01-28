  <p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This lab demonstrates the deployment of osTicket, an open source help desk ticketing system used in real-world IT support environments.<br />
The focus of this section is on prerequisites and installation, including environment preparation and dependency configuration required to successfully install and run osTicket<br />

<h2>Video Demonstration</h2>

- ### [YouTube: How To Install osTicket with Prerequisites](https://www.youtube.com)

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Computer)
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
<h2> 1. Create Azure virtual machine in Microsoft Azure </h2>
Set up a virtual machine named <b>osticket-vm</b> in the <b>East US 2</b> region. Use the <b>Windows 10 Enterprise 22H2 (x64, Gen2)</b> image and configure it with 2 vCPUs and 8 GiB of memory. Set the username to <b>labuser</b> and the password to <b>osTicketPassword1!</b>, then select <b>Review + Create</b>. 
<p>
<img width="1517" height="1313" alt="Screenshot (1311)" src="https://github.com/user-attachments/assets/71695009-7b96-40d4-8d81-1041146d698f" />
<img width="1152" height="1307" alt="Screenshot (1313)" src="https://github.com/user-attachments/assets/956a8a47-ec71-4caa-8a2f-8816ecbb45f8" />
<img width="1153" height="1312" alt="Screenshot (1314)" src="https://github.com/user-attachments/assets/8348de62-b8ac-47a7-9e47-5d89c4bffe5e" />

<h2> 2. Log into the virtual machine using Remote Desktop </h2>
Once the virtual machine is created, go to its settings in Azure and find the public IP address. Use this IP address to log into the virtual machine via <b>Remote Desktop</b> (RDP) using the username and password set earlier.
<img width="895" height="449" alt="Screenshot (72)" src="https://github.com/user-attachments/assets/acc805d4-f2b0-479c-9359-eef8533c15f0" />
<img width="908" height="448" alt="Screenshot (73)" src="https://github.com/user-attachments/assets/71be50a0-2901-4746-a2a0-571b43e5e1ca" />
<img width="1712" height="1054" alt="Screenshot (74)" src="https://github.com/user-attachments/assets/77fdba28-1a2f-4e28-b462-d71abdead2f2" />

<h2> 3. Download and unzip osTicket installation files </h2>
Download the <b>osTicket intstallation files</b> and unzip them to the desktop of the virtual machine.

[osTicket Installation Files in VM](https://drive.usercontent.google.com/download?id=1b3RBkXTLNGXbibeMuAynkfzdBC1NnqaD&export=download&authuser=0)

<h2> 4. Enable IIS and CGI in control panel </h2>
Open <b>Control Panel</b> and select <b>Programs</b>, then click <b>Turn Windows Features on or off</b>. In the list, make sure <b>Internet Information Services</b> (IIS) is enabled. Under <b>Internet Information Services</b> &#8594; <b>World Wide Web Services</b> &#8594; <b>Application Development Features</b>, enable <b>CGI</b>. 

<img width="592" height="439" alt="Screenshot (75)" src="https://github.com/user-attachments/assets/a3f998fd-e53b-429c-972f-b062b2f28ee8" />
<img width="588" height="443" alt="Screenshot (76)" src="https://github.com/user-attachments/assets/7b5a24fc-5653-448d-9d4d-da110b48cb86" />
<img width="343" height="305" alt="Screenshot (77)" src="https://github.com/user-attachments/assets/aa109ab8-f687-4e11-9a2e-c6095fb65f57" />

<h2> 5. Install PHP Manager for IIS</h2>
Install PHP Manager for IIS by running <b>PHPManagerForIIS_V1.5.0</b> from the unzippped osTicket installation files.
<img width="794" height="484" alt="Screenshot (89)" src="https://github.com/user-attachments/assets/747fd14f-032c-4fa6-870b-7535ef25bccd" />

<h2> 6. Install rewrite module </h2>
Install <b>rewrite_amd64_en-US</b> from the osTicket installation files folder.
<img width="797" height="478" alt="Screenshot (90)" src="https://github.com/user-attachments/assets/2153597d-2483-413f-ae6d-52df3527b6b0" />

<h2> 7. Create PHP folder in root directory of C: drive </h2>
Create a new folder in the root of the C: drive (C:) and name it <b>PHP</b><br>

<img width="413" height="283" alt="Screenshot (940)" src="https://github.com/user-attachments/assets/f9cd3bbf-d94a-4c5b-a68c-0e098b41625d" />

<h2> 8. Extract PHP files to the C:\PHP Folder </h2>
Now we need to move the files in <b>php-7.3.8-nts-Win32-VC15-x86</b> into the folder that was created on the C: drive <br>

<img width="547" height="505" alt="Screenshot (94)" src="https://github.com/user-attachments/assets/02f2f20d-b8f3-4e29-a0e7-9ae28d432b60" />
<img width="1088" height="1015" alt="Screenshot (95)" src="https://github.com/user-attachments/assets/ff22992a-fccf-4465-8a92-90e6b0e7031e" />

<h2> 9. Install Microsoft Visual C++ Redistributable (x86)</h2>
Install <b>VC_redist.x86</b> from the osTicket installation files folder<br>

<img width="544" height="458" alt="Screenshot (96)" src="https://github.com/user-attachments/assets/c0e34c3e-eba8-4759-9f3e-e53cebbd1ef7" />

<h2> 10. Install mysql-5.5.62 </h2>
Install <b>mysql-5.5.62-win32</b> from the osTicket installation files folder<br>

Setup: Typical &#8594; Launch MySQL Instance Configuration Wizard &#8594; Standard Configuration &#8594; Username: root Password: root <br>  

<img width="534" height="502" alt="Screenshot (97)" src="https://github.com/user-attachments/assets/8dd6f3fe-c495-426b-a742-a252073ea6ba" />
<img width="379" height="298" alt="Screenshot (98)" src="https://github.com/user-attachments/assets/781d9768-480b-4b53-9c87-064dd0b4853c" />
<img width="377" height="298" alt="Screenshot (99)" src="https://github.com/user-attachments/assets/5bbbe8fc-2f56-4df6-9261-83aa1f9eeb08" />
<img width="372" height="283" alt="Screenshot (100)" src="https://github.com/user-attachments/assets/678b08ae-2254-4876-8c9a-b42dae5f5f7b" />
<img width="372" height="284" alt="Screenshot (101)" src="https://github.com/user-attachments/assets/0f13df9f-e92d-413f-ab90-60d24ab5bfd5" />

<h2> 11. Open IIS as administrator and register php-cgi.exe </h2>
Open up <b>Internet Information Services (IIS) Manager</b> as administrator. Open <b>PHP manager</b> and register <b>php-cgi.exe</b> which is located in C:\PHP. Restart the server to apply changes<br>

<img width="335" height="410" alt="Screenshot (102)" src="https://github.com/user-attachments/assets/213d4801-1799-430b-bd84-efbe5a7721f2" />
<img width="703" height="345" alt="Screenshot (103)" src="https://github.com/user-attachments/assets/5ca2866b-7cb4-44f5-8978-901a7e11748a" />
<img width="705" height="360" alt="Screenshot (104)" src="https://github.com/user-attachments/assets/15403c45-f5f7-4eb3-8bfe-99df467e19e6" />
<img width="917" height="408" alt="Screenshot (105)" src="https://github.com/user-attachments/assets/fd100465-f5ec-4eb2-809b-e969fe2b26c1" />
<img width="709" height="358" alt="Screenshot (107)" src="https://github.com/user-attachments/assets/98a3a4d2-af00-4cd0-ba88-636456e461a2" />
<img width="706" height="350" alt="Screenshot (108)" src="https://github.com/user-attachments/assets/d99b9d1e-d36e-4481-a9ad-45193c2eabd1" />

<h2> 12. Extract osTicket-v1.15.8 </h2>
Extract <b>osTicket-v1.15.8</b> from the osTicket installation files folder to C:\inetpub\wwwroot. Rename folder that was extracted to osTicket. Then restart server again.<br>

<img width="602" height="440" alt="Screenshot (109)" src="https://github.com/user-attachments/assets/9c6ec526-db12-4928-b44e-44298eacfb5d" />
<img width="597" height="464" alt="Screenshot (110)" src="https://github.com/user-attachments/assets/28e160ad-3bbb-4cc3-aa2a-2ec816067bb2" />
<img width="587" height="465" alt="Screenshot (111)" src="https://github.com/user-attachments/assets/f87d70e4-2a94-42a8-a71a-a4b855527759" />
<img width="588" height="444" alt="Screenshot (115)" src="https://github.com/user-attachments/assets/2fb32bcd-4f88-4a74-83c7-a54c10e5de5d" />
<img width="582" height="441" alt="Screenshot (114)" src="https://github.com/user-attachments/assets/efb28cd3-01ec-4fde-927c-55ce5787e0ac" />
<img width="706" height="350" alt="Screenshot (108)" src="https://github.com/user-attachments/assets/e7360713-33f8-49eb-951b-d68d5fd83893" />

<h2> 13. Access osTicket website via IIS Manager </h2>
Go back to IIS Manager and click <b>Browse *:80(http)</b> in the actions pane to verify that the osTicket site is running correctly. <br>

<img width="1726" height="746" alt="Screenshot (1317)" src="https://github.com/user-attachments/assets/f74a57b3-e2ac-4a3a-8cc7-90ca16618b9d" />
<img width="1548" height="976" alt="Screenshot (1318)" src="https://github.com/user-attachments/assets/7fb7beb5-e917-47d3-a755-89ef50b415dd" />

[!IMPORTANT] If you encounter a <b>404 Not Found</b> or any other error screen, a previous step was likely performed incorrectly. Before moving forward, please:

- Review the previous instructions carefully.
- Verify your directory mapping.
- Confirm your IIS configuration settings.

<h2> 14. Enable PHP extensions for osTicket</h2>
Back in IIS Manager go to Sites &#8594; Default Web Site &#8594; osTicket and select <b>PHP Manager</b>. Select <b>Enable or disable an extension</b> and enable the following extensions:

- php_imap.dll
- php_intl.dll
- php_opcache.dll

Refresh the osTicket website to see changes. 

<img width="1725" height="751" alt="Screenshot (1319)" src="https://github.com/user-attachments/assets/1397213f-7789-4ff7-80cd-1cc3c15e93e2" />
<img width="1733" height="752" alt="Screenshot (1320)" src="https://github.com/user-attachments/assets/a690106b-96c8-4f55-9101-bd89deec2d29" />
<img width="1730" height="748" alt="Screenshot (1322)" src="https://github.com/user-attachments/assets/ab6aa243-30de-46b3-8bff-8dae2de8dee5" />
<img width="1729" height="748" alt="Screenshot (1323)" src="https://github.com/user-attachments/assets/b485e262-5f4f-4627-9b9b-19a84cd1c4bf" />
<img width="1733" height="752" alt="Screenshot (1324)" src="https://github.com/user-attachments/assets/8963a586-8d05-4709-b91a-b7700039b378" />
<img width="1567" height="983" alt="Screenshot (1325)" src="https://github.com/user-attachments/assets/b88e41a2-48ea-455e-8100-7f7cef3144d2" />

<h2> 15. Rename ost-config.php file and assign permissions </h2>
  1. <b>Rename configuration file:</b> Navigate to <b>C:\inetpub\wwwroot\osTicket\include</b> and rename <b>ost-sampleconfig.php</b> to <b>ost-config.php</b> <br>
  2. <b>Modify file permissions:</b> Right-click <b>ost-config.php</b> and select Properties.

  - Go to the <b>Security</b> and click <b>Advanced</b>
  - Click <b>Disable inheritance</b>, then choose <b>Remove all inherited permissions from this object</b>.

  3. <b>Assign User Access:<b/> Click <b>Add</b> &#8594; <b>Select a principal</b>.

  - Type <b>Everyone</b> into the object name box and click ok.
  - Check the box for <b>Full Control</b>, then click OK and Apply to save changes. 

<img width="1115" height="651" alt="Screenshot (1331)" src="https://github.com/user-attachments/assets/11af8a65-51d6-42ff-b27e-0d1d18733066" />
<img width="1122" height="807" alt="Screenshot (1346)" src="https://github.com/user-attachments/assets/d95ace90-4dc8-4b04-9672-b5517f6fece4" />
<img width="1117" height="802" alt="Screenshot (1345)" src="https://github.com/user-attachments/assets/848bc9e4-a624-4ed7-a948-7af61e3e6d83" />
<img width="1132" height="919" alt="Screenshot (1337)" src="https://github.com/user-attachments/assets/94557a5a-1387-4b3b-a0c8-155908c9f0ed" />
<img width="1123" height="966" alt="Screenshot (1338)" src="https://github.com/user-attachments/assets/67514f8d-966d-4caa-b0d4-211402b0b73d" />
<img width="1121" height="906" alt="Screenshot (1339)" src="https://github.com/user-attachments/assets/6ae01f54-bc74-42e2-8531-fe0ae6a7b5f6" />
<img width="1134" height="746" alt="Screenshot (1341)" src="https://github.com/user-attachments/assets/94ade4fa-f946-4474-836c-f41279875e8b" />
<img width="1136" height="750" alt="Screenshot (1342)" src="https://github.com/user-attachments/assets/91cdac49-01a4-4c0a-a9de-8f24a2bb48c7" />
<img width="1105" height="897" alt="Screenshot (1344)" src="https://github.com/user-attachments/assets/2ea0a7c7-ca38-4b62-a9d9-7a0d059fdc39" />

<h2> 16. Continue osTicket setup </h2>
Return to your browser to continue the osTicket setup. Enter the following configurations details:

- Helpdesk Name: Helpdesk
- Default Email: helpdesk@gmail.com
- First Name: [Your choice]
- Last name: [Your choice]
- Email Address: [Your choice]
- Username: adminuser
- Password: Password1

<img width="1562" height="977" alt="Screenshot (1347)" src="https://github.com/user-attachments/assets/072fa355-b0dd-451e-9587-9e8f94c9e85c" />
<img width="1538" height="1177" alt="Screenshot (1348)" src="https://github.com/user-attachments/assets/2ed14d24-caa1-4125-be1c-0801ed81fa34" />
<img width="1716" height="1170" alt="Screenshot (1350)" src="https://github.com/user-attachments/assets/e4c24515-5596-4bb0-a957-fa3513ab62ba" />
<img width="1548" height="1170" alt="Screenshot (1352)" src="https://github.com/user-attachments/assets/4f3ecba6-3163-446c-9728-f9a302865e88" />
<img width="1551" height="1186" alt="Screenshot (1353)" src="https://github.com/user-attachments/assets/d4db0c90-032c-478c-9ae8-99448ed4ae72" />
<img width="924" height="593" alt="Screenshot (980)" src="https://github.com/user-attachments/assets/5f9ab66f-73e7-4a92-bc8b-0fb189e55289" />
<img width="935" height="597" alt="Screenshot (981)" src="https://github.com/user-attachments/assets/ca1d188b-c4e5-469b-973f-dc73c8715401" />
<img width="929" height="577" alt="Screenshot (982)" src="https://github.com/user-attachments/assets/68096657-2474-44ef-8058-2157f15d6111" />
<img width="1037" height="1117" alt="Screenshot (983)" src="https://github.com/user-attachments/assets/561b95ed-d315-448e-8db8-2e85c88e0ad2" />
<img width="1050" height="1128" alt="Screenshot (984)" src="https://github.com/user-attachments/assets/5c74226a-3c58-4db1-8be2-15dbee3c5f6b" />

<h2> 17. Install HeidiSQL and create database </h2>

Part 1. <b>Create the Database<b/>
 1. Install HeidiSQL: Locate the <b>HeidiSQL<b/> installer in your osTicket files folder and complete the installation.
 2. Establish a new session: Open <b>HeidiSQL<b/>, click <b>New<b/>, and enter the following credentials:
     - Username: root
     - Password: root
 3. Create Database: Right-click <b>Unnamed<b/> in the sidebar.
     - Navigate to <b>Create new<b/> &#8594; <b>Database<b/>.
     - Name the database <b>osTicket<b/> and click OK. 






Go to the osTicket Installation Files folder and install <b>HeidiSQL</b>. Once <b>HeidiSQL</b> is installed open it and select <b>New</b>. Enter the following to creat new session:

- Username: root
- Password: root

Right-click on <b>Unnamed<b/> &#8594; <b2>Create new<b/> &#8594; <b>database<b/>. Name the database <b2>osTicket<b/> and select ok.<br>
Go back to the osTicket setup in the browser and under the <b>Database Settings<b/> put in the following 

- MySQL Hostname: osTicket
- MySQL Username: root
- MySQL Password: root

Select Install now to finish. 
