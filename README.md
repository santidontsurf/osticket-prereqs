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
</p>
<p>
In Azure, create a resource group and title it "osTicketrg" then a virtual network under that same resource group titled "osticketrg-vnet". Afterwards create a VM with 2 vcpus, 8 GiB Memory and put it under the same resource group.
</p>
 <img width="1701" alt="Screenshot 2025-05-29 at 11 36 38 AM" src="https://github.com/user-attachments/assets/b5acbb0b-579f-4f38-b558-d1ced7d62c7c" />
<br />
<p>
</p>
<p>Next simply connect to your newly created VM using RDP using the public IPv4 address. If you are a Mac user you will have to download Microsoft Remote Desktop(RDP). 
</p>
<img width="1092" alt="Screenshot 2025-05-29 at 11 37 31 AM" src="https://github.com/user-attachments/assets/0e159f71-7f90-453c-ba42-a7a671bd2919" />
</p>
<br />

