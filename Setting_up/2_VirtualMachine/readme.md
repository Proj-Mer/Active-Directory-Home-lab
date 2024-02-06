![image](https://github.com/Proj-Mer/Active-Directory-Home-lab/assets/157049853/b92cdc87-52ce-4937-92a8-c2411edeff67)# Note!
- Before creating a new virtual box, ensure that your virtualization is enabled through [BIOS.](https://www.thomas-krenn.com/de/wikiDE/images/a/a9/SR2500-bios-intel-vt.png)
# Virtual Box
- Open up your virtual box and click on **New.**
  <p align="center"><img src="https://i.imgur.com/SJHmAP2.png" height="65%" width="55%" alt="New"/></p> <!--1-->

- Name your Virtual Machine. I named it as the **DomainController.**
  <p align="center"><img src="https://i.imgur.com/lbesZDE.png" height="75%" width="55%" alt="DC"/></p> <!--2-->

- Set your **RAM** and **CPU** for the VM.
- This depends on your computer specs. If you have high end hardware, you may increase the RAM and core for the VM.
  <p align="center"><img src="https://i.imgur.com/kOW34QK.png" height="75%" width="55%" alt="OMYGULAY"/></p> <!--3-->

- Set the size of your virtual hard disk.
- If you have a lot of spare space, you may increase as wanted.
  <p align="center"><img src="https://i.imgur.com/tjWxNvF.png" height="75%" width="55%" alt="brt"/></p> <!--4-->
- Click on **Settings** of the Virtual Machine.
- Go to **Network.**
- Choose **Internal Network** For the 2nd Adapter.
  - This is for the Dedicated VMWare Network.
  - Adapter 1 is reserved for the House internet which is the **NAT.**
    <p align="center"><img src="https://i.imgur.com/xnj46IH.png" height="75%" width="55%" alt="brt"/></p> <!--4-->
    
## Ease of use
- Easier to maneuver files as you may use the **Coppied Clipboard** and **Drag and drop** from your host system to the virtual machine.
  <p align="center"><img src="https://i.imgur.com/ljbD9Q4.png" height="75%" width="55%" alt="brt"/></p> <!--5-->
# Setting up the Domain Controller
- Open the domain controller virtual machine.
- Select the downloaded **server 2019 ISO.**
- Select **Mount and Retry boot.**
- Wait for the VM to boot up.
  <p align="center"><img src="https://i.imgur.com/MiOIK1v.png" height="75%" width="55%" alt="brt"/></p> <!--6-->

- After waiting, the Windows setup should display.
  <p align="center"><img src="https://i.imgur.com/xMrjiQF.png" height="75%" width="55%" alt="brt"/></p> <!--7-->
- Click **Install Now.**
  <p align="center"><img src="https://i.imgur.com/507Z0JL.png" height="75%" width="55%" alt="brt"/></p> <!--8-->
- Select the **Windows Server 2019 Evaluation (Desktop Experience).**
- Agree to the terms and conditions and go next. 
  <p align="center"><img src="https://i.imgur.com/JKfDTWd.png" height="75%" width="55%" alt="brt"/></p> <!--9-->
- Select **Custom: Install Windows only.**
  <p align="center"><img src="https://i.imgur.com/Brn59R1.png" height="75%" width="55%" alt="brt"/></p> <!--9-->
- Select Drive.
  <p align="center"><img src="https://i.imgur.com/2lLgduV.png" height="75%" width="55%" alt="brt"/></p> <!--9-->
- Wait for the server to Install.
  - It may restart a few times. Wait until the **Login Screen** is loaded.
  <p align="center"><img src="https://i.imgur.com/vhnOwTM.png" height="75%" width="55%" alt="brt"/></p> <!--9-->
- After installing, you are prompted to create a **password** for the administrator account.
  <p align="center"><img src="https://i.imgur.com/T2OySiE.png" height="75%" width="55%" alt="brt"/></p> <!--9-->
- You will then be prompted to the login screen.
- Log in using the your created password with the administrator account.
 <p align="center"> <img src="https://i.imgur.com/9NteP0z.png" width="45%" height="50%" /> <img src="https://i.imgur.com/CZDEIbU.png" width="45%" height="50%" style="float:left"/> </p>

**Note:** You may notice that the mouse is lagging and when resizing the Virtual box, it does not adjust properly.
The solution for this is to install the downloaded **extension pack** at the virtual box site. To implement this:

- Click on the devices of the virtual machine and select **Insert Guest Additions CD Image.**
- After clicking on it, notice that **CD Drive (D:)** has popped up.
<p align="center"> <img src="https://i.imgur.com/YAUrs1v.png" width="45%" height="50%" /> <img src="https://i.imgur.com/0TN92eC.png" width="45%" height="50%" style="float:left"/></p>

- Click on the **CD Drive (D:)** and select **amd64**
- Install and reboot.
  
  **Note:** You may notice that rebooting through the VM does not change anything. The solution to this is to **Shut Down** the VM and **Start** the **DC** again from the **Virtual Box.**
  <p align="center"> <img src="https://i.imgur.com/oMnV0WQ.png" width="45%" height="50%" /> <img src="https://i.imgur.com/9BoajV7.png" width="45%" height="50%" style="float:left"/></p>
Right Click on Windows -> System -> Rename your PC to DomainController

# IP addressing [setup.](https://i.imgur.com/HfjvWaX.jpg)
- Setting up for **NIC Internal** for the **VMware Network**
- Navigate to the **taskbar** and click on the **network icon** and click on the **Network & Internet settings**
  <p align="center"><img src="https://i.imgur.com/WFLqbDH.png" height="55%" width="55%" alt="brt"/></p> <!--9-->
- Navigate and click on **Change adapter options**
  <p align="center"><img src="https://i.imgur.com/iVXmr6L.png" height="55%" width="55%" alt="brt"/></p> <!--9-->

- Notice that there are two Ethernet connections.
- We should be able to differentiate and identify which connection is the **INTERNAL** and the **INTERNET** and properly name the said connections.
  <p align="center"><img src="https://i.imgur.com/5FTewTR.png" height="55%" width="55%" alt="brt"/></p> <!--9-->
- Upon inspection by clicking on the ethernet details, we could see that the IP for **DNS Server** is the gateway to my home router.
- We could conclude that **Ethernet** is our **Internet** connection.
- Right click on the **Ethernet** and we will rename it as our **_Internet_.**
- Notice that for the **Ethernet 2**, IPv4 address is autoconfigured as it was trying to fetch IP from somewhere but was unable to do so.
- Right click on the **Ethernet 2** and we will rename it as our **_Internal_.**
 <p align="center"> <img src="https://i.imgur.com/xXM4P2f.png" width="45%" height="50%" /> <img src="https://i.imgur.com/BlpGRZf.png" width="45%" height="50%" style="float:left"/></p>

- We will no be assigning IP address to the **Internal Network.**
- Navigate to the **_Internal_** network.
- Right click, and select **Properties.**
- Select **Internet Protocol Version 4 (TCP/IPv4).**
 <p align="center"> <img src="https://i.imgur.com/rwjtjzg.png" width="45%" height="50%" /> <img src="https://i.imgur.com/LwhqSux.png" width="45%" height="50%" style="float:left"/></p>

- Assigning the **IP** with accordance to the [diagram.](https://i.imgur.com/HfjvWaX.jpg)
  <p align="center"><img src="https://i.imgur.com/O8MCA4i.png" height="55%" width="55%" alt="brt"/></p> <!--9-->

# Installing and Setting Up Active Directry Domain Services
- Now we will be installing the AD DS by clicking on **Add roles and features** at the **Service Manager.**
  <p align="center"><img src="https://i.imgur.com/oQHvFwb.png" height="55%" width="55%" alt="brt"/></p> <!--9-->
  
- Click on next until **Server Selection.**
- Since we only have one server, select the named server which is the **DomainController** and click next.
  <p align="center"><img src="https://i.imgur.com/cSJ1vKg.png" height="55%" width="55%" alt="brt"/></p> <!--9-->
  
- At the **Server Roles**, select the **Active Directory Domain Services**, click **add features** and click next.
  <p align="center"> <img src="https://i.imgur.com/eiVRfHA.png" width="45%" height="50%" /> <img src="https://i.imgur.com/bX3J9kE.png" width="45%" height="50%" style="float:left"/></p>
  
- At the **Confirmation** click Install and wait for it to complete.
  <p align="center"> <img src="https://i.imgur.com/BDUxuK2.png" width="45%" height="50%" /> <img src="https://i.imgur.com/lEhTUNt.png" width="45%" height="50%" style="float:left"/></p>
  
- We installed the AD DS but did not really create the domain yet.
- Notice that at the top right icon which is the notification, click on it.
 <p align="center"> <img src="https://i.imgur.com/AEAVsp7.png" width="45%" height="50%" /> <img src="https://i.imgur.com/BorC868.png" width="45%" height="50%" style="float:left"/></p>
 
- The **Deployment Configuration** should pop up.
- Click on **Add forest** and enter any root domain name you want. I named it as **mydomain.com** as it is the most generic and easy to follow.
- Click on next
<p align="center"><img src="https://i.imgur.com/c6a6dk2.png" height="55%" width="55%" alt="brt"/></p> <!--9-->

- You may or may not put password but since this is just a home lab.
<p align="center"><img src="https://i.imgur.com/aUiHjkj.png" height="55%" width="55%" alt="brt"/></p> <!--9--> 

- Click on next until **prerequesite check** and then click on install.
<p align="center"><img src="https://i.imgur.com/JtIwf5k.png" height="55%" width="55%" alt="brt"/></p> <!--9--> 

# Creating a Dedicated Admin Account.
- After the install, it will restart and should require you to login to the **MYDOMAIN/Administrator** account.
<p align="center"><img src="https://i.imgur.com/Yvl0yho.png" height="55%" width="55%" alt="brt"/></p> <!--9--> 

- Now we will create our own dedicated admin account instead of using the built in administrator account.
- By doing so, we need to click on **windows.**
- click on **Windows Administrative Tools.**
- click on **Active Directory Users and Computers.**
 <p align="center"> <img src="https://i.imgur.com/ZzNq1GQ.png" width="45%" height="50%" /> <img src="https://i.imgur.com/sZqH0SR.png" width="45%" height="50%" style="float:left"/></p>

- Create and Organizational Unit (OU) to put in the admin account that is to be created.

  [An organizational unit (OU)](https://www.techtarget.com/searchwindowsserver/definition/organizational-unit-OU)- is a container within a Microsoft Active Directory domain which can hold users, groups and computers.
  <p align="center"><img src="https://i.imgur.com/5vabJJq.png" height="55%" width="55%" alt="brt"/></p> <!--9--> 
- I named it as **_ADMINS** for the OU of the adminstrator accounts.
   <p align="center"> <img src="https://i.imgur.com/zZ4p3OH.png" width="45%" height="50%" /> <img src="https://i.imgur.com/bLuTxvW.png" width="45%" height="50%" style="float:left"/></p>
- We will now be creating a user through the created **_ADMINS** folder.
- Right click on the created **_ADMINS** folder.
- Hover on **New** and select **user**
  
**NOTE:** There are some naming conventions where you put the initial and then the last name, first name and employee ID, and other types.
For this example we will format it as first initial and last name.
 <p align="center"> <img src="https://i.imgur.com/PlbSYgG.png" width="45%" height="50%" /> <img src="https://i.imgur.com/jOqLu2D.png" width="45%" height="50%" style="float:left"/></p>

- After creating the user, set up the password and click finish.
- You will notice the newly created user at the **_ADMINS** folder.
  <p align="center"> <img src="https://i.imgur.com/yGDc1IH.png" width="45%" height="50%" /> <img src="https://i.imgur.com/6aSmHx0.png" width="45%" height="50%" style="float:left"/></p>

- Set the user as a domain admin by clicking right click on the **user** -> **member of** -> **add** -> **Domain admin** -> **check names** -> **Apply** -> **ok**.
  <p align="center"><img src="https://i.imgur.com/tAWYZpP.png" height="55%" width="55%" alt="brt"/></p> <!--9--> 

- Now we can use the created dedicated admin account for the domain controller.
- Sign in using the domain admin account.
<p align="center"><img src="https://i.imgur.com/d8vHqgN.png" height="55%" width="55%" alt="brt"/></p> <!--9--> 

# Installing RAS/NAT.
- After succesfully logging in to the dedicated domain admin account.
- In the **Service Manager.**
- Click on **Add roles and features.**
- On the **Server Roles** tab, select **Remote Access.**
   <p align="center"><img src="https://i.imgur.com/7x3m3PT.png" height="55%" width="55%" alt="brt"/></p> <!--9-->
- Click next until the **Roles Services** tab.
- Click on **routing** and select **add feature**.
- **Direct Access and VPN (RAS)** will be automatically come with the routing.
  <p align="center"><img src="https://i.imgur.com/arNV6Oe.png" height="55%" width="55%" alt="brt"/></p> <!--9-->
- On the **Confirmation** tab, select install and wait.
  <p align="center"> <img src="https://i.imgur.com/E4HSHiu.png" width="45%" height="50%" /> <img src="https://i.imgur.com/BDPAUBU.png" width="45%" height="50%" style="float:left"/></p>

- On the **Service Manager**, select tools and select **Routing and Remote Access**.
  <p align="center"><img src="https://i.imgur.com/H3mrWBX.png" height="55%" width="55%" alt="brt"/></p> <!--9-->
- Right click on the **DomainController** and select **Configure and Enable Routing and Remote Access.**
  <p align="center"><img src="https://i.imgur.com/24vOCJx.png" height="55%" width="55%" alt="brt"/></p> <!--9-->
- Click Next and select **Network Address Translation (NAT)**.
  <p align="center"><img src="https://i.imgur.com/6JM6Gn9.png" height="55%" width="55%" alt="brt"/></p> <!--9-->
  
