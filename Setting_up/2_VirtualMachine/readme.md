# Note!
- Before creating a new virtual box, ensure that your virtualization is enabled through [BIOS.](https://www.thomas-krenn.com/de/wikiDE/images/a/a9/SR2500-bios-intel-vt.png)
# Virtual Box
- Open up your virtual box and click on **New**
  <p align="center"><img src="https://i.imgur.com/SJHmAP2.png" height="65%" width="55%" alt="New"/></p> <!--1-->

- Name your Virtual Machine. I named it as the **DomainController.**
  <p align="center"><img src="https://i.imgur.com/lbesZDE.png" height="75%" width="55%" alt="DC"/></p> <!--2-->

- Set your **RAM** and **CPU** for the VM.
- This depends on your computer specs. If you have high end hardware, you may increase the RAM and core for the VM.
  <p align="center"><img src="https://i.imgur.com/kOW34QK.png" height="75%" width="55%" alt="OMYGULAY"/></p> <!--3-->

- Set the size of your virtual hard disk
- If you have a lot of spare space, you may increase as wanted.
  <p align="center"><img src="https://i.imgur.com/tjWxNvF.png" height="75%" width="55%" alt="brt"/></p> <!--4-->
- Click on **Settings** of the Virtual Machine
- Go to **Network**
- Choose **Internal Network** For the 2nd Adapter
  - This is for the Dedicated VMWare Network
  - Adapter 1 is reserved for the House internet which is the **NAT**
    <p align="center"><img src="https://i.imgur.com/xnj46IH.png" height="75%" width="55%" alt="brt"/></p> <!--4-->
    
## Ease of use
- Easier to maneuver files as you may use the **Coppied Clipboard** and **Drag and drop** from your host system to the virtual machine.
  <p align="center"><img src="https://i.imgur.com/ljbD9Q4.png" height="75%" width="55%" alt="brt"/></p> <!--5-->
# Setting up the Domain Controller
- Open the domain controller virtual machine
- Select the downloaded **server 2019 ISO**
- Select **Mount and Retry boot**
- Wait for the VM to boot up.
  <p align="center"><img src="https://i.imgur.com/MiOIK1v.png" height="75%" width="55%" alt="brt"/></p> <!--6-->

- After waiting, the Windows setup should display.
  <p align="center"><img src="https://i.imgur.com/xMrjiQF.png" height="75%" width="55%" alt="brt"/></p> <!--7-->
- Click **Install Now.**
  <p align="center"><img src="https://i.imgur.com/507Z0JL.png" height="75%" width="55%" alt="brt"/></p> <!--8-->
- Select the **Windows Server 2019 Evaluation (Desktop Experience).**
- Agree to the terms and conditions and go next. 
  <p align="center"><img src="https://i.imgur.com/JKfDTWd.png" height="75%" width="55%" alt="brt"/></p> <!--9-->
- Select **Custom: Install Windows only**
  <p align="center"><img src="https://i.imgur.com/Brn59R1.png" height="75%" width="55%" alt="brt"/></p> <!--9-->
- Select Drive 
  <p align="center"><img src="https://i.imgur.com/2lLgduV.png" height="75%" width="55%" alt="brt"/></p> <!--9-->
- Wait for the server to Install 
  <p align="center"><img src="https://i.imgur.com/vhnOwTM.png" height="75%" width="55%" alt="brt"/></p> <!--9-->