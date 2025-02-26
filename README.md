# OsTicket-Prereq
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

- Item 1 Create a Resource group in Microsoft Azure

- Item 2 Create a Windows 10 Vm/Linux within Azure

- Item 3 Configure a Network Security Group (NSG) rules
- Item 4
- Item 5

<h2>Installation Steps</h2>


![image](https://github.com/user-attachments/assets/ec152dda-5598-44a9-bbcb-ff999e894223)

</p>
<p>
Go to you Azure portal and type Resource groups, and specify the region for the group so we can choose the best location for the Virtual machine 
</p>
<br />


![image](https://github.com/user-attachments/assets/ea888c52-3cf1-40d9-926e-904febafed2c)

![image](https://github.com/user-attachments/assets/de20c6d3-3ca4-467d-9151-2ee57d960bc3)


</p>
<p>
When creating the Vm it is important to pick the resource group that you made earlier. Name the Vm and choose the region you are in. For the image pick the windows 10 operating system  or Ununtu Server for linux. For Vm size ste standard_B1s is for slower traffic while the StandardD1s_v2 is for better performance. When creating a Admin account be sure to use a strang password or an SSH key for Linux Vm
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Before accessing remote desktop with the admin user account and password be sure to configure your Network Security Group (NSG) to allow RDP ports (3389 for windows / SSH(22) for linux. Other ports you need are http 80 and https 443 to allow web traffic for the OsTicket interface.
<br />
