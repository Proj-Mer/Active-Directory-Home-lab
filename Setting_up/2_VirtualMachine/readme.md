# Note!
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
