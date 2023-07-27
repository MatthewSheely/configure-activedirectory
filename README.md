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
- Create a Virtual Machine (Client-1)
- Create a Static Address (DC-1)
- Confirm Connection between Client-1 & DC-1
- 

<h2>Deployment and Configuration Steps</h2>

<p>
<p align="center">
<h3>Create a Resource Group</h3>
To get started we will need to make a Resource Group to store our Virtual Machines (DC-1 & Client-1)   
  <p align="center">
<img src="https://i.imgur.com/8xvnzhz.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p align="center">
<img src="https://i.imgur.com/Be0xNy8.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

<p>
<p align="center">
<h3>Create a Virtual Machine (Client-1)</h3> 
</p>
<br />
<p align="center">
<img src="https://i.imgur.com/ywweOiG.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>  
<p>
  <p align="center">
<img src="https://i.imgur.com/pxQeJyj.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<p align="center">
 <img src="https://i.imgur.com/8vf4Tqj.png" height="80%" width="80%" alt="Disk Sanitization Steps"/> 
</p>
<br />
<p align="center">
<h3>Create a Static Address (DC-1)</h3>   
<p>
  <p align="center">
<img src="https://i.imgur.com/iJ1aA01.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<p align="center">
<img src="https://i.imgur.com/opkG2Kl.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>  
</p>
<br />
<p align="center">
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
