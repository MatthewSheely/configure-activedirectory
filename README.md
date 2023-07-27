<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>Configure Active Directory within Azure (Cloud)</h1>
This tutorial outlines the implementation of configuring Active Directory within Azure Virtual Machines.<br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory 
- PowerShell

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)

<h2>High-Level Deployment and Configuration Steps</h2>

- Create a Resource Group
- Create a Static Address (DC-1)
- Create a Virtual Machine (Client-1)
- Adjust DC-1's IP Settings to Static 
- Confirm Connection between Client-1 & DC-1
- 

<h2>Deploy and Configure</h2>

<p>
<p align="center">
<h3>Create a Resource Group</h3>
  
To get started we will need to make a Resource Group to store our Virtual Machines (DC-1 & Client-1)
<p>  
  <p align="center">
<img src="https://i.imgur.com/8xvnzhz.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p align="center">
<img src="https://i.imgur.com/Be0xNy8.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

<p>
<p align="center">
<h3>Create a Static Address (DC-1)</h3> 
</p>
Once our Resource Group is created we can now create our DC-1 Virtual Machine. 
<p align="center">
<img src="https://i.imgur.com/ywweOiG.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>  
<p>
  In this tutorial, the original settings will work for both VMs. Be sure to select Windows Server 2022 as the Operating System for DC-1. 
  
  <p align="center">
<img src="https://i.imgur.com/pxQeJyj.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<p>
<p align="center">
 <img src="https://i.imgur.com/8vf4Tqj.png" height="80%" width="80%" alt="Disk Sanitization Steps"/> 
</p>
Once you have completed creating DC-1 VM. Go to the VM page to confirm the VM is populating in the correct Resource Group.
<br />
<p align="center">
<h3>Create a Virtual Machine (Client-1)</h3>   
<p>
  Now that DC-1 is been created, It is time to create Client-1. Be sure to make confirm that the Regions and Resource Groups are consistent across both VMs. Then Select Windows 10 as the operating system for Client-1.   
  <p align="center">
<img src="https://i.imgur.com/iJ1aA01.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<p align="center">
<img src="https://i.imgur.com/opkG2Kl.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>  
</p>
<h3>Adjust DC-1's IP Settings to Static </h3>
The purpose of setting the DC-1 IP address to Static is so the IP address never changes.
<p></p>
<p align="center">
<img src="https://i.imgur.com/TeVGcb8.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
  <p></p>
  
<h3>Confirm Connectivity Between Client-1 & DC-1</h3>
<p></p>
To test our connectivity, start by logging into Client-1's VM. Once logged in, open a command line. We are using the Powershell application for this example. Then ping DC-1's private IP address.
<p>
<p align="center">
<img src="https://i.imgur.com/atBtEb4.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
  <p>
As displayed above, DC-1 is not receiving a ping from Cleint-1. This is because DC-1's Windows Firewall is blocking ICMP traffic. To fix this we will need to log into DC-1's VM and change the configuration to allow ICMP traffic.    
</p>
Once logged into DC-1. Type into the Windows search bar WF.MSC(Microsoft Common Console Document). This gives us access to the Domain Controller settings used to enable ICMP. Select Inbound Rules.
<p></p>
<p align="center">
<img src="https://i.imgur.com/TABH1Ux.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<p></p>
Enable both ICMPv4 Core Networking Diagnostics on the local windows firewall.
<p></p>
<p align="center">
<img src="https://i.imgur.com/5OaH1es.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<p></p>
Once adjusted you can go back to Client-1 and ping DC-1. This time the ping should be received and displayed as such (below). 
<p></p>
<p align="center">
<img src="https://i.imgur.com/SPbz3Ac.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<P></P>
<h3>Install Active Directory</h3>

Login to DC-1, Add Roles and Features 
<p align="center">
<img src="https://i.imgur.com/jriNUBO.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<p></p>
Select Active Directory Doman Service 
<p align="center">
<img src="https://i.imgur.com/rEeHxqM.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
  <p></p>
Confirm & Install 
<p align="center">
<img src="https://i.imgur.com/UJddzZn.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
  <p></p>
Promote as a Domain Controller 
