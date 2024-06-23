<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>On-premises Active Directory Deployed in the Cloud (Azure)</h1>
This is an abbreviated outline of notes on the setup (from scratch) and installation, on-premises, of Active Directory within Azure Virtual Machines.<br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services
- PowerShell ISE

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (22H2)

<h2>Overview: Deployment and Configuration </h2>

- Part 1: Setup of two VMs (Windows server and client) on the same region and vNet.
- Part 2: Checking connectivity.
- Part 3: Install Active Directory and promote to a domain controller.
- Part 4: Configure AD within Server Manager and add a Domain Admin
- Part 5: Join the client to the domain.
- Part 6: Adding multiple users with Powershell; Resetting Accounts and Passwords

<h2>Word of Caution: 3 Places You Might Get Stuck (see ** within steps below) </h2>

- Validating the Second VM (Part 1)
- Logging In to the Domain Controller (Part 3)
- Logging in to the Client as a Domain Admin (Part 5)

<h2>Before You Start</h2>

<p>
ONE...............
</p>
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<br />
  
<h2>Deployment and Configuration Steps</h2>

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
ONE...............
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
TWO...................
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
THREE....................
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
FOUR.......
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
FIVE. .....
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
SIX......
</p>
<br />
