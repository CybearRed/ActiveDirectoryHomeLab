<h1>ACTIVE DIRECTORY HOME LAB</h1>



<h2>Description</h2>
In this project I walk through how to create an Active Directory using Oracle Virtual Box. Being able to configure and run this lab will help to develop an understanding of how Acitve Directory and Windows networking works. I will be utilizing powershell as part of this project as well. This project aims to boost competencies in Active Directory, PowerShell, Windows Server, and Virtualization (Oracle VirtualBox).
<br />

<h2>Languages and Utilities Used</h2>

- <b>PowerShell</b> 
- <b>Oracle VirtualBox</b>
- <b>Active Directory</b>

<h2>Environments Used </h2>

- <b>Windows 10</b> (21H2)
- <b>Windows Server 2019</b>

<h2>Pre-Setup</h2>

<b>Step 1: Download the ISO files for Windows Server 2019 and Windows 10</b>

<b>Step 2: Download and install Oracle VirtualBox</b>

<b>Step 3: Install the Server 2019 ISO on Oracle VB. Name it something to reference it as the direct controller. Configure settings as such:</b>
 
 - Network > Enable Network Adapter 1 and set it to NAT > Enable Network Adapter 2 and set it to Internal Network (It will be set to 'intnet' which is fine)

 - You'll have to configure the Storage and System (CPUs, RAM, and HDD) to run the OS on the VM. (Rule of thumb: CPUs = 2 is really enough to start. RAM = 2048mb which is 2GB of RAM. 20~25GB of memory is good to start)

 - Once the settings have been configured in VB, start the machine and install the Windows Server 2019 ISO. (Select standard desktop experience) (Custom Installation)  
 
<b>Step 4: Install the Windows 10 OS (64 bit) on Oracle VB. Name it something to reference it as the client. Configure settings as such:</b>
  
 - Network > Enable Network Adapter 1 and make sure it's set to Internal Network (It will be set to 'intnet' which is fine)
  
 - You'll have to configure the Storage and System (CPUs, RAM, and HDD) to run the OS on the VM. (Rule of thumb: CPUs = 2 is really enough to start. RAM = 2048mb which is 2GB of RAM. 20~25GB of memory is good to start)

 - Once the settings have been configured in VB, start the machine and install the Windows Server 2019 ISO. (Select standard desktop experience) (Custom Installation)


<h2>Program walk-through:</h2>

<p align="center">
Launch the utility: <br/>
<img src="https://i.imgur.com/62TgaWL.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Select the disk:  <br/>
<img src="https://i.imgur.com/tcTyMUE.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Enter the number of passes: <br/>
<img src="https://i.imgur.com/nCIbXbg.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Confirm your selection:  <br/>
<img src="https://i.imgur.com/cdFHBiU.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Wait for process to complete (may take some time):  <br/>
<img src="https://i.imgur.com/JL945Ga.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Sanitization complete:  <br/>
<img src="https://i.imgur.com/K71yaM2.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Observe the wiped disk:  <br/>
<img src="https://i.imgur.com/AeZkvFQ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
