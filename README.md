<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />



<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Windows App (Apple App Store)
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 11 Pro</b> (24H2)

<h2>List of Prerequisites</h2>

- Azure Virtual Machine
- Windows App
- osTicket Installation files
- Heidi SQL

<h2>Installation Steps</h2>

<p>
</p>
<p>
Using Microsoft Azure portal(portal.azure.com) we will create a virtual machine (VM) to use as a testing ground for this project and protect our physical device from anything that might malfunction along the way. VM's also allow us to use an operating system different from the one our device uses, in this case we will be using a Windows 11 Pro VM on a Macbook laptop.

 *(If you are working on a Windows laptop already you can skip the first three steps and starts at step four (IIS))*
</p>
<p>
In Azure, create a resource group and title it "osTicketrg" then a virtual network under that same resource group titled "osticketrg-vnet". Afterwards create a VM with 2 vcpus, 8 GiB Memory and put it under the same resource group.
</p>
<p align="center">
 <img alt="Screenshot 2025-05-29 at 11 36 38 AM" src="https://github.com/user-attachments/assets/b5acbb0b-579f-4f38-b558-d1ced7d62c7c" height="80%" width="80%" />
</p>
<br />
<p>
</p>
<p>Next, download Windows App from the App Store and launch it, then add a new PC and use your osTicketvm public IP address (highlighted above) as the PC name.
</p>
<p align="center">
 <img alt="Screenshot 2025-05-30 at 10 16 20 AM" src="https://github.com/user-attachments/assets/79e09dcb-1e15-4534-87b0-1e265743a428" height="40%" width="40%"/>
</p>
<p>After the VM is created in Windows App connect to it with the username and password created for the VM in Azure
</p>
<p align="center"><img alt="Screenshot 2025-05-30 at 10 26 25 AM" src="https://github.com/user-attachments/assets/b3b56e1e-fbe7-4c7d-9ff2-33750fbbf1af" height="80%" width="80%" /></p>
<p>Once you have your VM open you will have to enable IIS (Internet Information Services). To do so, access the control panel then select uninstall a program. On the left, select "Turn windows features on or off". A new window appears with a list of features, scroll until you see "Internet Information Services" enable it, then click on the "+" icon next to it, then find World Wide Web Services and make sure it's checked as well, and clink on the "+" icon next to it, then find Application Development Features and make sure it's checked as well, click "+", and make sure CGI is checked, then press OK to apply the changes.
</p>
<p align="center"><img alt="Screenshot 2025-05-30 at 10 42 49 AM" src="https://github.com/user-attachments/assets/c7544d51-8011-4a1a-b769-29088f722f94" height="80%" width="80%" />
</p>
<p>
  
</p>
<p align="center"><img alt="Screenshot 2025-06-06 at 11 29 07 AM" src="https://github.com/user-attachments/assets/53437b70-303b-403f-a308-3e198bc743db" height="80%" width="80%" />
</p>
<p>
With IIS enabled the next step is to install the osTicket dependencies. I have provided a link that allows you to download a zip folder with all dependencies. Download it and unzip it. The folder should be called “osTicket-Installation-Files”

*Link: https://drive.google.com/uc?export=download&id=1b3RBkXTLNGXbibeMuAynkfzdBC1NnqaD*

One you have downloaded and unzip the folder, its contents should look like this:
</p>
<p align="center">
<img alt="Screenshot 2025-05-30 at 11 07 47 AM" src="https://github.com/user-attachments/assets/3944f94b-74eb-44e9-af4b-b9a061c744bf" height="80%" width="80%" />
</p>
<p>
 
</p>
<p>The first dependency we will install is PHP Manager. Double-click on "PHPManagerForIIS_V1.5.0.msi" to begin the installation process.</p>
<p>Next, install the Rewrite Module file: "rewrite_amd64_en-US.msi"</p>
<p align="center"><img alt="Screenshot 2025-06-02 at 11 22 39 AM" src="https://github.com/user-attachments/assets/8fdf4e17-b9cf-4b86-b7fb-7e3c25e2c721" height="80%" width="80%" />
</p>
<p>Once both dependencies have been installed, from File Explorer, travel to "This PC -> Windows (C:)", then in the C:\ Drive right-click and add a new folder/directory titled "PHP" as shown below:</p>
<p align="center"><img alt="Screenshot 2025-06-02 at 11 25 11 AM" src="https://github.com/user-attachments/assets/f93bcf73-11ab-4aed-8294-c7c5dd0d68f1" height="80%" width="80%" />
</p>
<p>
 
</p>
<p>
 Travel back to the osTicket-Installation-Files folder and go into the PHP zipped folder "php-7.3.8-nts-Win32-VC15-x86.zip."
 </p>
<p align="center"> <img alt="Screenshot 2025-06-02 at 11 38 20 AM" src="https://github.com/user-attachments/assets/4b5a49d3-a81c-458f-a4a3-a970f95de905" height="60%" width="80%"/>
</p>
<p>
  Once in, choose Extract All from the top menu and choose the extraction destination folder as our new PHP directory back in the C:\ drive 
</p>
<p align="center"><img alt="Screenshot 2025-06-02 at 11 38 34 AM" src="https://github.com/user-attachments/assets/fbbf6960-bd05-455c-82e3-58783f02767f" height="60%" width="80%" />
</p>
<p>Your PHP folder should now look like this:</p>
<p align="center"><img alt="Screenshot 2025-06-02 at 11 44 48 AM" src="https://github.com/user-attachments/assets/3d863143-b01e-480c-be8e-0b20336ad6fb" height="60%" width="80%"/>
</p>
<p>
 Travel back to the osTicket-Installation-Files folder once again and install "VC_redist.x86.exe".
 When you first open it you will have two options: "Extract All" or "Run". Choose Run then install the dependency. 
</p>
<p align="center"><img alt="Screenshot 2025-06-02 at 11 53 59 AM" src="https://github.com/user-attachments/assets/7d3f30da-b822-4509-a1f3-a13b328feb56" height="80%" width="80%"/>
</p>
<p>Then, install MySQL 5.5.62 "mysql-5.5.62-win32.msi" and choose "typical" out of the three setup options.</p>
<p align="center"><img alt="Screenshot 2025-06-03 at 11 11 59 AM" src="https://github.com/user-attachments/assets/71aeb2f7-303d-4f45-a6b6-118841356c92" height="80%" width="80%"/>
</p>
<p>
</p>

<p>Make sure that "Launch the MySQL configuration wizard" is checked before you finish the installation.</p>
<p align="center"><img alt="Screenshot 2025-06-03 at 11 13 16 AM" src="https://github.com/user-attachments/assets/19416432-70c3-4f7a-aa0d-141821b084b6" height="80%" width="80%"/>
</p>
<p>
</p>
<p>Once configuration wizard is open you can choose "standard" configuration and proceed with the process until you are asked to create a password for the root account. Make sure that the password you create is secure and that you can remember it. Once you have created a password for the root account you can execute the configuration.</p>
<p align="center"><img alt="Screenshot 2025-06-03 at 11 16 12 AM" src="https://github.com/user-attachments/assets/ab8a991e-0752-424f-a857-3c3d2a4d4a63" height="80%" width="80%"/>
</p>
<p> 
</p>
<p>Next, we'll search for Internet Information Services (IIS) Manager and open it as an administrator.</p>
<p align="center"><img alt="Screenshot 2025-06-06 at 11 22 29 AM" src="https://github.com/user-attachments/assets/662ef2f8-e234-49c6-b2a8-ab07c17d5043" height="80%" width="80%" />
</p>
<p>Inside IIS, double-click on PHP Manager to open it, and under PHP Setup click "Register New PHP Version" and travel to our PHP folder in the C drive and choose php-cgi.exe, then click OK. </p>
<p align="center"><img alt="Screenshot 2025-06-07 at 10 12 00 AM" src="https://github.com/user-attachments/assets/9d10a367-ed5c-46b5-97cc-a6189347ad92" height="80%" width="80%" />
</p>
<p>Travel back to the main IIS window, on the upper right corner of the window click "Stop" then "Start" to refresh PHP Manager.</p>
<p align="center"><img alt="Screenshot 2025-06-07 at 10 16 08 AM" src="https://github.com/user-attachments/assets/49d9c77e-405f-4c80-85dc-760bb22037f9" height="80%" width="80%"/>
</p>
<p>Next, travel back to the installation folder extract "osTicket-v1.15.8.zip". Once extracted, copy the upload folder that was inside into C:\inetpub\wwwroot. Once copied, rename the folder "osTicket".</p>
<p align="center"><img alt="Screenshot 2025-06-07 at 10 26 30 AM" src="https://github.com/user-attachments/assets/3ad74406-000c-4a6c-a58f-bd061378bf0d" height="80%" width="80%" />
</p>
<
<br />


