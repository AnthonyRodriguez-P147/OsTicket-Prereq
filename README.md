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
</p>
<p>
Before accessing remote desktop with the admin user account and password be sure to configure your Network Security Group (NSG) to allow RDP ports (3389 for windows / SSH(22) for linux. Other ports you need are http 80 and https 443 to allow web traffic for the OsTicket interface.
<br />
  
  ![image](https://github.com/user-attachments/assets/eb5e605b-a6d9-463d-bf8b-862a2a72e00c)

<p>
Next log into your Vm using the public Ip address and the admin name a passowrd. 
  
  <h2> Installing osticket</h2>
  
  ![image](https://github.com/user-attachments/assets/bd6a3208-1d93-4183-ab7d-7a850ec3615b)    ![image](https://github.com/user-attachments/assets/7fb5288d-709e-4433-9694-0577c152785a)


  Once you are in the Virtual machine you can use this link osTicket-Installation-Files.zip to download the folder and drag it your desktop. We can then right click it and press extract all. Make sure its in the desktop osticket installation folder.
</p>
<br />
<h2> Installing osticket</h2>
<p>
  Next we are going to install/ enable IIS in windows, the IIS will be serviceing osticket. To enable it we go the start menu and go to the control pannel and go to programs 

  ![image](https://github.com/user-attachments/assets/622fd580-ada8-4e75-bf73-32361391f554)

  ![Screenshot 2025-02-26 150443](https://github.com/user-attachments/assets/8ae686fa-6cfe-4d4a-b4c6-073e13a0e53b)
  
   On the left side we can click on turn windows Features on or off

  ![image](https://github.com/user-attachments/assets/45ac6d65-6005-49a9-8aba-3beb00af8afc)
  
  enable internet information services and click the dropdown menu

  ![Screenshot 2025-02-26 150759](https://github.com/user-attachments/assets/4a081007-0bb0-41bf-beac-c5cc0734fee9)
 
  Click on the dropdown for world eide web service
  
  ![image](https://github.com/user-attachments/assets/8c02fcd1-639f-4b79-831f-59cf41900485)

 click on the dropdown menu for Application Develpment features

![Screenshot 2025-02-26 152038](https://github.com/user-attachments/assets/fee81892-f0de-44b9-843d-2eb48155fd73)

Click to enable CGI
 
After CGI is finished enabling go the osTicket folder open it and click on php manager 

![Screenshot 2025-02-26 152440](https://github.com/user-attachments/assets/d7abdfd8-ef82-4f3d-981f-326043d84596)

After you are done installing and agreeing to the terms of service, from the osticket folder intall the read write module (rewrite_am64_en-US msi)

![Screenshot 2025-02-26 152719](https://github.com/user-attachments/assets/ba996c26-826e-44b8-9b1a-374969bdbf80)



![Screenshot 2025-02-26 153015](https://github.com/user-attachments/assets/23262eb2-86e9-48d4-8e55-1f54f71a5045)


</p>
<br />
