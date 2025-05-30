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
 <img alt="Screenshot 2025-05-29 at 11 36 38 AM" src="https://github.com/user-attachments/assets/b5acbb0b-579f-4f38-b558-d1ced7d62c7c" height="80%" width="80%" />
<br />
<p>
</p>
<p>Next, download Windows App from the App Store and launch it, then add a new PC and use your osTicketvm public IP address (highlighted above) as the PC name.
</p>
<p>
 <img alt="Screenshot 2025-05-30 at 10 16 20 AM" src="https://github.com/user-attachments/assets/79e09dcb-1e15-4534-87b0-1e265743a428" height="40%" width="40%"/>
</p>
<p>After the VM is created in Windows App connect to it with the username and password created for the VM in Azure
</p>
<p><img alt="Screenshot 2025-05-30 at 10 26 25 AM" src="https://github.com/user-attachments/assets/b3b56e1e-fbe7-4c7d-9ff2-33750fbbf1af" height="80%" width="80%" /></p>
<p>Once you have your VM open you will have to enable IIS (Internet Information Services). To do so, access the control panel then select uninstall a program. On the left, select "Turn windows features on or off". A new window appears with a list of features, scroll until you see "Internet Information Services" enable it then click OK.
</p>
<p><img alt="Screenshot 2025-05-30 at 10 42 49 AM" src="https://github.com/user-attachments/assets/c7544d51-8011-4a1a-b769-29088f722f94" height="80%" width="80%" />
</p>
<p>
With IIS enabled the next step is to install the osTicket dependencies. I have provided a link that allows you to download a zip folder with all dependencies. Download it and unzip it. The folder should be called “osTicket-Installation-Files”

*Link: https://drive.google.com/uc?export=download&id=1b3RBkXTLNGXbibeMuAynkfzdBC1NnqaD*

One you have downloaded and unzip the folder, its contents should look like this:
</p>
<p>
<img alt="Screenshot 2025-05-30 at 11 07 47 AM" src="https://github.com/user-attachments/assets/3944f94b-74eb-44e9-af4b-b9a061c744bf" height="80%" width="80%" />
</p>
<p>
 
</p>
<p>The first dependency we will install is PHP Manager. Double-click on "PHPManagerForIIS_V1.5.0.msi" to begin the installation process.</p>
<br />

