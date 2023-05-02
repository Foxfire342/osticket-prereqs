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
on the right. You should get the screen above and you will notice some extensions haven't been enabled yet. In order to use all of the 
features in OsTicket we have a few more extensions to enable (minus APCu and Zend OPcache extensions).
</p>

___

<p>
<img src="https://i.imgur.com/IkQkPg7.png" height="80%" width="80%" alt="Enable Extensions PartTwo"/>
</p>
<p>
All three extensions that need to be enabled will be back in IIS. Once in IIS we will need to click "Sites" on the left, then 
"Default Web Site" and then click osTicket. In the middle where it says OsTicket Home, select the PHP Manager. Once your inside the
PHP Manager go down to PHP Extensions and select "enable or disable an extension". Then enable php_imap.dll, php_intl.dll and php_opcache.dll
from the list. Once the extensions are enabled be sure to refresh your osTicket Installer page to confirm that the changes went into effect.
You should have green checks for everything except the last two extensions on the list.
</p>

___

<p>
<img src="https://i.imgur.com/cpMd0sR.png" height="80%" width="80%" alt="Rename File"/>
</p>
<p>
Next we will have to rename the ost-sampleconfig.php in the OsTicket folder to ost-config.php. This can
be done by going into the C Drive and select the inetpub folder and then clicking "wwwroot", and then selecting
"osTicket". Once in the osTicket folder click the "include" folder and then find ost-sampleconfig.php file and
rename it.
</p>

___

<p>
<img src="https://i.imgur.com/1pR1ZWy.png" height="40%" width="40%" alt="Enable Permissions"/>
</p>
<p>
<img src="https://i.imgur.com/fzUiVZ9.png" height="40%" width="40%" alt="Enable Permissions"/>
</p>
<p>
After renaming the file, we will need to right-click the file and go into properties to enable access to the file for everyone. 
Once in properties go to the securities tab and select advanced. Once in the advanced window, click disable interitance and remove 
all inherited permissions. Then click "Add" and then "Select a principal" and then type in everyone in the white box, press check names
and then press ok. Then checkbox full control to allow other users to access this file and select ok. And then in the next window select
apply and ok to solidify things.
</p>

___

<p>
<img src="https://i.imgur.com/3dke3V1.png" height="80%" width="80%" alt="Setting Up OsTicket Part1"/>
</p>
<p>
Now lets go back to the osTicket Installer page and click continue to finish setting up OsTicket. On the next page it will ask for a Helpdesk Name, default email and admin user information. Feel free to put whatever you would like in here but keep track of your username, password and default email as it will be needed later on. As for the Database Settings section we will leave this blank for now because we will need to download HeidiSQL first to fill this section out before pressing install now.
</p>

___

<p>
<img src="https://i.imgur.com/dGBAAvh.png" height="40%" width="40%" alt="Download HeidiSQL"/>
</p>
<p>
<img src="https://i.imgur.com/O8mVl7Q.png" height="40%" width="40%" alt="Download HeidiSQL"/>
</p>
<p>
To complete the osTicket installation we will be downloading HeidiSQL as shown above. By downloading HeidiSQL we will be able to connect to the SQL database inside of osTicket. After downloading HeidiSQL we will open it up and create a new connection to the database by clicking new in the bottome left hand corner of the window. You can choose any name that you would like for user but use the same password that you used for MySQL 5.5.62. Once you fill thos two fields out click "open". Next in the same Heidi window right click Unnamed and create a new database.
We will name it osticket for this example but you can name it whatever you would like.
</p>

___

<p>
<img src="https://i.imgur.com/dnyU5NA.png" height="80%" width="80%" alt="Setting Up OsTicket Part2"/>
</p>
<p>
Now that the osticket database is set up in Heidi we can now return to the osTicket Installer page. Under Database Settings use the same database
name that you established in Heidi as well as the same username and password. Once you fill this out, hit install now.
</p>

___

<p>
<img src="https://i.imgur.com/9ObSRhf.png" height="80%" width="80%" alt="OsTicket Installed"/>
</p>
<p>
Congratulations, you have fully installed osTicket!! The only thing left next is to perform some brief clean up and then we can head to osTicket
login page.
</p>

___

<p>
<img src="https://i.imgur.com/fR6luZX.png" height="40%" width="40%" alt="Delete setup file"/>
</p>
<p>
<img src="https://i.imgur.com/Cax9Mnq.png" height="40%" width="40%" alt="Update Permissions"/>
</p>
<p>
To clean things up we will need to return to the osTicket folder that is within the wwwroot folder in the C Drive from earlier. Once in
the folder delete the setup folder as shown above. And then lastly return to the ost-config.php file by clicking the include folder and
go back into properties and then security and then advanced and then change the permissions to "Read Only and Read & Execute" as shown 
above and then click ok and apply.
</p>

___

<p>
<img src="https://i.imgur.com/k9yYRzW.png" height="80%" width="80%" alt="Admin Login"/>
</p>
<p>
Your installation of osTicket is now complete!! Head over to your admin login page at http://localhost/osTicket/scp/login.php and proceed to login!
</p>

___
