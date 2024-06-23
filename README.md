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
NB: This is a relatively long process, depending on your existing skill level with Azure. 
I recommend that if you need to take a break, consider stopping your machines rather than trying to create them from scratch again (the step which took longest for me).
It's likely easier to keep them set up and configured while you complete the rest of the steps below. Stopped machines will say "deallocated" and when you're ready to use them again, you can just click "Start."
</p>

![image](https://github.com/lcccodes/configure-ad/assets/171904823/ea3de6af-1b0d-4659-bbaf-d798df0d6bf2)


<br />
  
<h2>Deployment and Configuration Steps</h2>

<b>Part 1: Setup of two VMs (Windows server and client) on the same region and vNet.</b>
<p>

  ![image](https://github.com/lcccodes/configure-ad/assets/171904823/84e26543-c927-4985-ab01-1822238f46d2)

</p>
<p>
Once you've got your server and client machines on the same vNet within the same region, your Resource Group page will show all of the associated resources which were automatically created with these [above]. These include the vNICs and Network Security Groups.

Deleting your resource group will automatically delete all resources contained within it. So if you need to delete only a single resource, it's best to do it from its own blade directly.
</p>
<br />


<b>Part 2: Checking connectivity.</b>
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
TWO...................
</p>
<br />


<b>Part 3: Install Active Directory and promote to a domain controller.</b>
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
THREE....................
</p>
<br />


<b>Part 1: Setup of two VMs (Windows server and client) on the same region and vNet.</b>
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
FOUR.......
</p>
<br />


<b>Part 1: Setup of two VMs (Windows server and client) on the same region and vNet.</b>
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
FIVE. .....
</p>
<br />


<b>Part 1: Setup of two VMs (Windows server and client) on the same region and vNet.</b>
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
SIX......
</p>
<br />
