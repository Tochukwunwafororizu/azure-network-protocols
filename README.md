<p align="center">
<img src="https://i.imgur.com/Ua7udoS.png" alt="Traffic Examination"/>
</p>

<h1>Network Security Groups (NSGs) and Inspecting Traffic Between Azure Virtual Machines</h1>
In this tutorial, we observe various network traffic to and from Azure Virtual Machines with Wireshark as well as experiment with Network Security Groups. <br />






<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Various Command-Line Tools
- Various Network Protocols (SSH,  DNS,  ICMP)
- Wireshark (Protocol Analyzer)

<h2>Operating Systems Used </h2>

- Windows 10 (21H2)
- Ubuntu Server 20.04



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

  
</p>
<p>  
Next: We are going to configure a firewall ( Network security group). To do that we are going to initiate non-stop ping. On our windows powershell ping 10.0.0.5 (private IP Address of Linux vm) -t and watch it go non stop. In the background as we can see wireshark is capturing these pings.
  
</p>
<br />

<p>
<img src="https://i.imgur.com/FCZT4GV.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
 

</p>
<p> 
Next: Diasable icmp traffic. We are going to configure Linux vm cloud firewall (The network security group) and tell it to block all incoming ping traffic from the windows vm and we are going to observe what happens when we do that. To achieve this, go to the Linux vm -Networking- Network settings - Linux-vm-nsg(Network Security Group) - Settings -Inbound security rules( Create a rule for inbound traffic coming) - Add a rule. After observing it re- enable it again by simply  deleting the rule.

<p>
<img src="https://i.imgur.com/mJxK0XQ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/QhQjrir.png" height="80%" width="80%" alt="Disk Sanitization Steps"/> 
<img src="https://i.imgur.com/cUnOT5q.png" height="80%" width="80%" alt="Disk Sanitization Steps"/> 
<img src="https://i.imgur.com/CpCY5jf.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/tOMoe1Z.png" height="80%" width="80%" alt="Disk Sanitization Steps"/> 
<img src="https://i.imgur.com/HzsqsH9.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/Kgk173c.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>


</p>
<p> 
Next: We are going to observe SSH traffic in wireshark. The SSH (secure shell) is used to make a secure connection from one computer to another. To observe the traffic, we will go to our windows computer and make ssh connection into our Linux computer and observe the traffic. Open up windows powersell and type  ssh labuser@10.0.0.5(private IP Address of our Linux computer). Notice our prompt changed to labuser@Linux-vm which means we are actually connected to the Linux machine.

<p>
<img src="https://i.imgur.com/n3Ur7r8.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>  
<img src="https://i.imgur.com/BfxHIhL.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>


</p>
<p> 
dfff

 
<p>
<img src="https://i.imgur.com/z5vUWaG.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
