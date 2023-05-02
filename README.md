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

- Install/Enable llS with CGI
- PHP Manager for llS
- Rewrite Module
- PHP 7.3.8
- VC_redist.x86.exe
- MySQL 5.5.62


<h2>Installation Steps</h2>

<p>
<img src= "https://i.imgur.com/RfHgbOe.png" height="80%" width="80%" alt="Virtual Machine Step" />
</p>
<p>
To begin, login into your Microsoft Azure account and create a windows 10 virtual machine(VM) with 2-4 virtual CPUs along with a new resource group.
When creating the VM, allow it to create a new Virtual Network(Vnet)(it should do that automatically). You can call your virtual machine name and resource group whatever you would like. Also be sure to choose a region that matches where you are geographically located.
</p>

___ 

<p>
<img src="https://i.imgur.com/FFCEjq3.png" height="80%" width="80%" alt="Virtual Machine Step Two"/>
</p>
<p>
For this tutorial we will be naming the virtual machine Vm-osticket, and use whatever username and password you would like. 
Please remember to write down your username and password somewhere so that you don't forget it because we will be using both later on in this tutorial. Once you finish filling out the basics tab click review and create.
</p>

___

<p>
<img src="https://i.imgur.com/XlcbNbo.png" height="80%" width="80%" alt="Remote into virtual machine"/>
</p>
<p>
Now that your virtual machine has been created the next step is to remote desktop into your virtual machine or if you're a mac user you will need to download Microsoft Remote Desktop from the app store and use that to remote into your virtual machine. Be sure to grab the public IP address from your virtual machines page in Azure as you will need it for this step. Also in order to connect you will need the username and password that you established with your virtual machine.
</p>

___

<p>
<img src="https://i.imgur.com/c4n95WM.png" height="80%" width="80%" alt="Enabling IISs in Windows with CGI"/>
</p>
<p>
Now that we have connected to the virtual machine the next step is to enable IIS in Windows with CGI. We do this by going into the control panel,
select programs and then "select turn windows featues on or off". Then select "Internet Information Services" and then "World Wide Web Services"
and then "Application Development Features" and check the box for CGI like shown above. Click ok and the changes will be applied. This step allows 
us to install PHP manager later on so its important that you don't skip it.
</p>

___

<p>
<img src="https://i.imgur.com/zmsSSdL.png" height="80%" width="80%" alt="Downloaing PHP Manager"/>
</p>
<p>
Next download PHP manager for llS Version 1.5.0 and select I agree in the license agreement section.
</p>

___

<p>
<img src="https://i.imgur.com/HvlpzL1.png" height="80%" width="80%" alt="Downloading Rewrite Module"/>
</p>
<p>
Next download and install the rewrite module. 
</p>

___

<p>
<img src="https://i.imgur.com/dRrzi96.png" height="80%" width="80%" alt="Create Folder in C Drive called PHP"/>
</p>
<p>
Next create a new directory in the C Drive and call it PHP. You can get to the C Drive by going to "This PC" and clicking "Windows (C:)"
</p>

___

<p>
<img src="https://i.imgur.com/1TcWQg3.png" height="80%" width="80%" alt="Downloading PHP 7.3.8"/>
</p>
<p>
Now download PHP 7.3.8 and unzip the contents into the new PHP folder that was created in the C Drive.
</p>

___

<p>
<img src="https://i.imgur.com/LV8hW03.png" height="80%" width="80%" alt="Downloading VC_redist"/>
</p>
<p>
Next download and install VC_redist.x86.exe.
</p>

___

<p>
<img src="https://i.imgur.com/YoF5zR5.png" height="80%" width="80%" alt="Download MySQL 5.5.62"/>
</p>
<p>
Next download and install MySQL 5.5.62 choose typical install, select the standard configuration option and install as windows service. 
We will be setting the password to password1 but you can set it to whatever you would like.
</p>

___

<p>
<img src="https://i.imgur.com/96vuVtc.png" height="80%" width="80%" alt="Register PHP"/>
</p>
<p>
Next open llS as an admin and register PHP from within IIS. Once this is done, restart IIS.
</p>

___

<p>
<img src="https://i.imgur.com/0pIqoSz.png" height="40%" width="40%" alt="Download OsTicket"/> 
</p>
<p>
<img src="https://i.imgur.com/Dp1Mtzu.png" height="40%" width="40%" alt="Rename Folder"/> 
</p>

<p>
Download OsTicket v.1.15.8 and extract and copy “upload” folder to c:\inetpub\wwwroot. Within c:\inetpub\wwwroot
rename "upload" to "osTicket".
</p>

___


<p>
<img src="https://i.imgur.com/CynK0ed.png" height="80%" width="80%" alt="Enable Extensions PartOne"/>
</p>
<p>
Next restart IIS and then inside of IIS go to sites, then select "default website" and then select OsTicket and click "Browse *:80" 
on the right. You should get the screen above and you will notice some extensions haven't been enabled yet.
</p>

___

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>

___

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>

___
