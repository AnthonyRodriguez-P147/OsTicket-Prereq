# OsTicket-Prereq
<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />


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
<h2> Creating a Resource group in Azure</h2>


![image](https://github.com/user-attachments/assets/ec152dda-5598-44a9-bbcb-ff999e894223)

</p>
<p>
Go to you Azure portal and type Resource groups, and specify the region for the group so we can choose the best location for the Virtual machine 
</p>
<br />

<h2> Creating Virtual machine</h2>

![image](https://github.com/user-attachments/assets/ea888c52-3cf1-40d9-926e-904febafed2c) ![image](https://github.com/user-attachments/assets/de20c6d3-3ca4-467d-9151-2ee57d960bc3)




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
<h2> Control Pannel Settings</h2>
<p>
  Next we are going to install/ enable IIS in windows, the IIS will be serviceing osticket. To enable it we go the start menu and go to the control pannel and go to programs 

  ![image](https://github.com/user-attachments/assets/622fd580-ada8-4e75-bf73-32361391f554)

 ![Screenshot 2025-02-26 210202](https://github.com/user-attachments/assets/ad6c4bc2-cdc7-4275-ad36-29ee059b65d9)

  
   On the left side we can click on turn windows Features on or off

  ![image](https://github.com/user-attachments/assets/45ac6d65-6005-49a9-8aba-3beb00af8afc)  ![Screenshot 2025-02-26 150759](https://github.com/user-attachments/assets/4a081007-0bb0-41bf-beac-c5cc0734fee9)
  
  enable internet information services and click the dropdown menu

 
  Click on the dropdown for world wide web service
  
 ![Screenshot 2025-02-26 210213](https://github.com/user-attachments/assets/fac46e75-f603-4ff4-8a80-820fab46c0fe)


 click on the dropdown menu for Application Develpment features

Click to enable CGI
 <h2> Prereq</h2>
After CGI is finished enabling go the osTicket folder open it and click on php manager 

![Screenshot 2025-02-26 210227](https://github.com/user-attachments/assets/299e8cf3-1a1c-44bc-a262-974a90e99591)
 ![Screenshot 2025-02-26 152719](https://github.com/user-attachments/assets/ba996c26-826e-44b8-9b1a-374969bdbf80) ![Screenshot 2025-02-26 153015](https://github.com/user-attachments/assets/23262eb2-86e9-48d4-8e55-1f54f71a5045)

After you are done installing and agreeing to the terms of service, from the osticket folder install the read write module (rewrite_am64_en-US msi)



</p>
<br />

<p>

![Screenshot 2025-02-26 160942](https://github.com/user-attachments/assets/432aa24a-373e-46e7-8b75-274d5610d3c0)

  
  After it is done installing create a new folder in the C windows drive and name it PHP. 


  Then from the osTicket-Installation-Files' folder unzip PHP 7.3 8 (php-7.3.8-nts-Win32-VC15-x86.zip) into the “C:\PHP” folder
Select browse and select the PHP folder

![Screenshot 2025-02-26 210242](https://github.com/user-attachments/assets/2ab52123-03ab-43f7-88d2-d8a69333dcc6)

![Screenshot 2025-02-26 210251](https://github.com/user-attachments/assets/5bf687ed-8ca8-4624-a080-26d93b0fa376)


![Screenshot 2025-02-26 215619](https://github.com/user-attachments/assets/fca8bb5e-b97d-4cec-9111-91b660e76ceb)


![Screenshot 2025-02-26 161726](https://github.com/user-attachments/assets/406c0f73-f54c-4fa1-b0a9-9c7396f00fce)

![Screenshot 2025-02-26 224422](https://github.com/user-attachments/assets/ed7681c1-7279-4f10-822b-753dacbe128a)

![Screenshot 2025-02-26 224849](https://github.com/user-attachments/assets/bed27713-a353-4f61-9a05-5f4c4253e902)

We are missing some extensions 
we go back to PhP Manager and Double-click PHP Manager
Click “Enable or disable an extension”
we need to enable these three Enable: php_imap.dll Enable: php_intl.dll Enable: php_opcache.dll


Next we rename ost-config.php From: C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php
To: C:\inetpub\wwwroot\osTicket\include\ost-config.php

![Screenshot 2025-02-26 225653](https://github.com/user-attachments/assets/7346e2e0-d09e-49aa-b21f-0e245ccfd090)

![Screenshot 2025-02-26 225808](https://github.com/user-attachments/assets/6380a0f8-3241-4db5-9d81-65697f52199f)

![Screenshot 2025-02-26 230101](https://github.com/user-attachments/assets/5ac2de69-78d9-4ab5-89b6-36651181e21c)



![Screenshot 2025-02-26 230411](https://github.com/user-attachments/assets/4612038f-33e5-4de7-b358-7cc53c4cbcb9)

![Screenshot 2025-02-26 230429](https://github.com/user-attachments/assets/744b145e-ff1b-4315-bc24-0063ab512706)

![Screenshot 2025-02-26 230439](https://github.com/user-attachments/assets/cb846e19-2f07-4772-939a-a5e1ffde12a4)

after that we disable inheritance, and add new permissions. For this example we will give everyone permissions not good to do in real life. 

![Screenshot 2025-02-26 230607](https://github.com/user-attachments/assets/0b3f7223-6e8a-4c02-a908-5420105881cf)

<h1>
Now we can begin basic intallation for osTicket

![Screenshot 2025-02-26 230739](https://github.com/user-attachments/assets/7b8cd63f-6991-4f38-bce8-f9ec72bb5ea9)

  
</h1>

We can start by naming it whatever we want, filling out he email and making the admin user.
After we go back to osTicket insatll files and install HeidiSQL 

![Screenshot 2025-02-26 231235](https://github.com/user-attachments/assets/3ea4cd60-05b4-4f73-a527-17c37221ee43)
![Screenshot 2025-02-26 231305](https://github.com/user-attachments/assets/36c0efbb-04ff-46f7-b86a-f3a32fcf2ced)

We launch HeidiSQL 
![Screenshot 2025-02-26 231511](https://github.com/user-attachments/assets/5e9fe0d3-f54c-449f-a911-bbffdc39aed5)

Create a new session, root/root
Connect to the session
Create a database called “osTicket”

![image](https://github.com/user-attachments/assets/4de29674-1d52-4e8b-9938-6963469b3223)


![image](https://github.com/user-attachments/assets/2726703c-5aba-4fc8-b3a0-5e42652ba507)

Continue Setting up osTicket in the browser
MySQL Database: osTicket
MySQL Username: root
MySQL Password: root
Click “Install Now!”

![Screenshot 2025-02-26 232028](https://github.com/user-attachments/assets/25fbe9b1-c34b-4cb6-8f8d-46644f145b7a)

</p>
<br />
