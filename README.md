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
<img width="1919" height="749" alt="image" src="https://github.com/user-attachments/assets/79b6c103-f289-4697-a43c-cc19569ee6f6" />

<img width="1901" height="722" alt="image" src="https://github.com/user-attachments/assets/c956f5df-9a94-4739-a713-f3790147e230" />

</p>
<p>
Next: We are going to install Protocol Analyser (Wireshark). It lets us see all the activities happening on our Window 10 Network Interface Card. It's generally use for monitoring and Analysing Network traffic. We will then open Wireshark and start packet capture. Within
the wireshark, filter for ICMP traffic only. ICMP traffic is what ping command uses to test connectivity between two devices. When we type in ICMP notice nothing shows up. We will now from the windows VM attempt to ping the Linux VM. TO do that,we will go to our Linux vm and take the private IP Address and go back to our windows vm and open up powershell and ping private IP Address of our Linux vm and  it will ping ICMP traffic of the two vm machines.

</p>
<br />

<p>
<img width="1920" height="1048" alt="image" src="https://github.com/user-attachments/assets/e458d1d1-b607-4406-97d8-d1faeebf148b" />

<img width="1920" height="1020" alt="image" src="https://github.com/user-attachments/assets/4bb80ecd-14b7-41f0-a0dd-3b130f2f9b90" />

<img width="1920" height="1026" alt="image" src="https://github.com/user-attachments/assets/68e9b6fc-7e54-4b40-be65-b7a2d2f34ad6" />


  
</p>
<p>  
Next: We are going to configure a firewall ( Network security group). To do that we are going to initiate non-stop ping. On our windows powershell ping 10.0.0.5 (private IP Address of Linux vm) -t and watch it go non stop. In the background as we can see wireshark is capturing these pings.
  
</p>
<br />

<p>
<img width="1893" height="1046" alt="image" src="https://github.com/user-attachments/assets/ce15a718-140a-46e2-bbd8-d7ac47a8fece" />

 

</p>
<p> 
Next: Diasable icmp traffic. We are going to configure Linux vm cloud firewall (The network security group) and tell it to block all incoming ping traffic from the windows vm and we are going to observe what happens when we do that. To achieve this, go to the Linux vm -Networking- Network settings - Linux-vm-nsg(Network Security Group) - Settings -Inbound security rules( Create a rule for inbound traffic coming) - Add a rule. After observing it re- enable it again by simply  deleting the rule.

<p>
<img width="1906" height="1010" alt="image" src="https://github.com/user-attachments/assets/efc024d7-fed6-4789-b162-9d6ab9368148" />

<img width="1918" height="850" alt="image" src="https://github.com/user-attachments/assets/b6b9742b-68a7-437b-80bc-18e15c76229f" />
 
<img width="1912" height="930" alt="image" src="https://github.com/user-attachments/assets/13360a6c-56f6-4455-ba63-fc8a1794930c" />
 
<img width="1914" height="860" alt="image" src="https://github.com/user-attachments/assets/230ddbed-be95-46cf-9cc2-8d707f9f1f30" />

<img width="1920" height="1063" alt="image" src="https://github.com/user-attachments/assets/1096b975-7c53-4fa0-b306-41a9029af02b" />

<img width="1916" height="890" alt="image" src="https://github.com/user-attachments/assets/b0de6068-89eb-41bc-9289-a94e9cab88c6" />

<img width="1909" height="1050" alt="image" src="https://github.com/user-attachments/assets/75f35c0b-8148-4787-8704-d00fa723c11f" />



</p>
<p> 
Next: We are going to observe SSH traffic in wireshark. The SSH (secure shell) is used to make a secure connection from one computer to another. To observe the traffic, we will go to our windows computer and make ssh connection into our Linux computer and observe the traffic. Open up windows powersell and type  ssh labuser@10.0.0.5(private IP Address of our Linux computer). Notice our prompt changed to labuser@Linux-vm which means we are actually connected to the Linux machine.

<p>
<img width="752" height="420" alt="image" src="https://github.com/user-attachments/assets/44d62a9c-322c-46c0-b056-deacfde117f3" />
  
<img width="1840" height="1036" alt="image" src="https://github.com/user-attachments/assets/0ae59eea-cba9-4ddd-8409-f3f31c7d9cfa" />



</p>
<p> 
Finally, we are going to filter for DNS and see the traffic.

 
<p>
<img width="1805" height="1078" alt="image" src="https://github.com/user-attachments/assets/18b8b403-ab08-4353-a08b-6e2460a9714a" />

