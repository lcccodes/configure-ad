<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>On-premises Active Directory Deployed in the Cloud (Azure)</h1>
This is an abbreviated outline of notes on the setup (from scratch) and installation of Active Directory within Azure Virtual Machines.<br />


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
<p>
**NB: The first time I went through, it took me countless attempts to be able to validate a second VM if I was trying to put it in the same region and the same vNet. The only thing which eventually worked (after trying all kinds of combinations of which order I was creating each machine in) --- was waiting even longer before clicking "Review and Create." Even after it's clear that the same vNet used for the server is ready --- I deliberately added extra waiting time in case one of the other elements was still creating (I still don't know if that's what was going on). That's what finally worked.
</p>
You'll also need to change the settings of the vNIC for the server from dynamic to static. Go to the NIC from within the Network Settings on the server's blade and navigate from there.<p></p>


![image](https://github.com/lcccodes/configure-ad/assets/171904823/ecbac8f6-e776-4af9-a77d-49ba57fa5551)

</p>
<br />


<b>Part 2: Checking connectivity.</b>
<p>

  ![image](https://github.com/lcccodes/configure-ad/assets/171904823/2f645421-5f75-4d02-ab86-41b9cbdefea0)

</p>
<p>
Through Windows Defender Firewall (Advanced Settings) on the server, you'll need to first "enable" incoming ICMP traffic before you can ping the server from the client. Here you only need to enable the two lines for "Echo Request."
</p>
<br />


<b>Part 3: Install Active Directory and promote to a domain controller.</b>
<p>

  ![image](https://github.com/lcccodes/configure-ad/assets/171904823/1ca6c8df-2291-4bb7-95ec-0194f36fcb72)

</p>
<p>
[ABOVE]: After Active Directory installs, you should see a yellow exclamation mark in the upper right -- if you click on this, you'll see the option to "promte this to a domain controller." Click on that.
</p>
<p>

![image](https://github.com/lcccodes/configure-ad/assets/171904823/aae613cc-efc0-41e9-afec-4f085257b34a)


</p>
<p>
[ABOVE]: This is where you'll need to choose "Add a new forest" and also choose the domain name for the controller. All users will belong to this domain, and from here on out, will need to login through the domain when logging into the domain controller and any joined clients.

**NB: ISSUES LOGGING BACK INTO THE DOMAIN CONTROLLER:
</p>
<p>
  
  ![image](https://github.com/lcccodes/configure-ad/assets/171904823/0b9dade2-1ac6-4e3a-9313-d9da0a0b9066)


</p>
<p>
You'll need to keep the IP address for the COMPUTER NAME, but in the USERNAME field, you'll need to input the FQDN (Fully Qualified Domain Name): it will look something like this (based on whatever you input in the step above):

<b>mydomain.com\username</b>

The point here is to make sure you're inputting this as the USERNAME and not as the COMPUTER NAME.
</p>
<br />


<b>Part 4: Configure AD within Server Manager and add a Domain Admin</b>
<p>

  ![image](https://github.com/lcccodes/configure-ad/assets/171904823/a7181f7b-12fc-49d2-bc19-a076546dc46b)

</p>
<p>
Once the domain controller is running and you can log in, now you can open "Active Directory Users and Computers" and begin to create the organizational units and admin users you need.
NB: Once you've added a user to the _ADMINS folder (for example), make sure you actually add them to that security group, too -- right click on their name, go to Properties, "Member of," and ADD. Start typing Domain Admins and select this, apply, hit "OK."
</p>
<p>

  ![image](https://github.com/lcccodes/configure-ad/assets/171904823/9215f7d6-91aa-49be-a2d6-7a015409d9e0)

</p>
<p>
Be sure to give the domain admin a specific and not a generic username, e.g., don't use "Admin"
</p>
<br />


<b>Part 5: Join the client to the domain.</b>
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
FIVE. .....
</p>
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
FIVE. .....
</p>
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
FIVE. .....
</p>
<br />


<b>Part 6: Adding multiple users with Powershell; Resetting Accounts and Passwords</b>
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
SIX......
</p>
<br />
