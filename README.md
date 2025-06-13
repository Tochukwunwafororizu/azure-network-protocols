<p align="center">
<img src="https://i.imgur.com/Ua7udoS.png" alt="Traffic Examination"/>
</p>

<h1>Network Security Groups (NSGs) and Inspecting Traffic Between Azure Virtual Machines</h1>
In this tutorial, we observe various network traffic to and from Azure Virtual Machines with Wireshark as well as experiment with Network Security Groups. <br />


<h2>Video Demonstration</h2>



<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Various Command-Line Tools
- Various Network Protocols (SSH, RDH, DNS, HTTP/S, ICMP)
- Wireshark (Protocol Analyzer)

<h2>Operating Systems Used </h2>

- Windows 10 (21H2)
- Ubuntu Server 20.04

<h2>High-Level Steps</h2>

- Step 1
- Step 2
- Step 3
- Step 4

<h2>Actions and Observations</h2>

<p>



<p>
We will start by creating two virtual machines(Windows, Linux[Ubuntu]) and create a virtual Network named Lab2-Vnet. Most importanly, the two VM  created must have the same Resource Group name and Virtual Network. After that is done, we will now install Microsoft Remote Desktop and connect it to Windows 10 Virtual Machine.
</p>
<br />

<p>
<img src="https://i.imgur.com/No8kL9X.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/J2XtLQL.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>  
</p>
<p>
Next: We are going to install Protocol Analyser (Wireshark). It let's us see all the activities happening on our Window 10 Network Interface Card. It's generally use for monitoring and Analysing Network traffic. We will then open Wireshark and start packet capture. Within
the wireshark, filter for ICMP traffic only. ICMP traffic is what ping command uses to test connectivity between two devices. When we type in ICMP notice nothing shows up. We will now from the windows VM attempt to ping the Linux VM. TO do that,we will go to our Linux vm and take the private IP Address and go back to our windows vm and open up powershell and ping private IP Address of our Linux vm and  it will ping ICMP traffic of the two vm machines.

</p>
<br />

<p>
<img src="https://i.imgur.com/PhQDv1Q.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/UkGnCsX.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/7xHulwD.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>  
<img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/>  

  
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />
