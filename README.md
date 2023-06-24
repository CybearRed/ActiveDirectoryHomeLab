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
This is a network map that's going to act as our guide for setting up active directory <br/>
 <br />
<img src="https://i.imgur.com/POBDPEt.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
<b>IN SERVER 2019</b>  <br/>
 <br />
 <b>STEP 1:</b> ESTABLISH THE IP ADDRESS FOR THE INTERNAL NETWORK (The NAT network will be utilizing our connection for internet access so it already has an IP)

  - Setup IP address for the INTERNAL network. The The network adapter from NAT is pulling internet from our home address so that will have the typical IP of our home. The IP of the INTERNAL adapter is not connected and so the 
	 DHCP is automatically giving it an IP. (Home is usually a 10.0.?.? for example). Select the network tab in bottom right corner and go to ethernet. Select change adapter
	 options > rename the Connected network as _INTERNET_ (or something to indicate there's a connection), and the Internal Non-Connected network X_Internal_X (or something to indicate there's no connection on that network).

 - Go back to the network icon in the bottom right corner > change adapter options > select the INTERNAL network > Right click and select properties > Select IPV4 and select 'use the
	 following IP address to change > set IP to what we mapped out on our network map 172.16.0.1 and same for subnet mask, 255.255.255.0 ( Default gateway will assign itself as the domain controller itself will serve as 
	 the default gateway, and when we install active directory the DNS server will assign itself. So for the preferred DNS you can enter its own IP address or the loopback addres which
	 is 127.0.0.1)
<br />

<img src="https://i.imgur.com/0iFQtaT.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
<b>Step 2:</b> RENAME THE PC 
<br/>

 - Right click start menu > System > Rename this PC. I renamed it Domain Controller as this is the server that will give/restrict internet access to the client.
<br />

<b>Step 3:</b> INSTALL ACTIVE DIRECTORY DOMAIN SERVICES (AD DS) AND CREATE A DOMAIN

 - In the Server Manager Window select Add roles and features > Next: Installation Type > Next: Server Selection (Should only be 1 listed that we set up) > Server Roles: Select Active Directory Domain Services > 
	 Next: Features> Next: AD DS >Confirmation: Install. Select the icon at the top for notifications, under Post-deployment Configuration select 'Promote This server to a domain controller 

 - Promoting the server to a domain controller will create the actual domain.  In the Deployment configuration select Add new forest and assign Root Domain Name (Can be anything really/I used mydomain.com for simplicity
	 and walkthrough purposes) select Next > Create Password, Next > Next through everything until you get to 'Install.' The system will restart once it's complete and you should now see a MYDOMAIN/Administrator title on the login
	screen. 
<br />
<img src="https://i.imgur.com/yNZZx1X.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
<b>Step 4:</b> Build our own dedicated admin account  
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
