<p align="center">
<img src="https://i.imgur.com/Ua7udoS.png" alt="Traffic Examination"/>
</p>

<h1>Network Security Groups (NSGs) and Inspecting Traffic Between Azure Virtual Machines</h1>
In this tutorial, we use Wireshark to analyze various types of network traffic between Azure Virtual Machines, including ICMP, SSH, DHCP, DNS, and RDP. Additionally, we experiment with Network Security Groups (NSGs) to observe how firewall rules impact network communication. <br />


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

- Step 1:  Set Up Virtual Machines
- Step 2:  Analyze ICMP Traffic 
- Step 3:  Configure Network Security Groups (NSGs)
- Step 4:  Inspect Protocols in Wireshark

<h1>Actions and Observations</h1>

<h2>Step 1:  Create Virtual Machines (VMs)</h2>
-Create a Windows 10 VM and an Ubuntu VM in the same Resource Group and Virtual Network.
<h4>Observation:</h4> Ensuring both VMs are in the same network allows seamless communication between them. These VMs will be used to simulate different network traffic and behaviors.

<h2>Step 2:  Observe ICMP Traffic</h2>
-Use Wireshark on the Windows 10 VM to capture ICMP traffic while pinging the Ubuntu VM.
<h4>Observation:</h4>  Wireshark shows ICMP Echo Request and Echo Reply messages when pinging, demonstrating basic network connectivity.

<h2>Step 3:  Configure Firewall (NSG)</h2>
-Disable and re-enable ICMP traffic via Network Security Group settings for the Ubuntu VM.
<h4>Observation:</h4>  Disabling ICMP will stop ping requests in Wireshark, and re-enabling will restore the traffic, showing how NSGs control access to VMs.

<h2>Step 4:  Observe SSH, DHCP, DNS, and RDP Traffic</h2>
-Capture SSH traffic (when connecting from Windows 10 to Ubuntu), DHCP traffic (on IP renewal), DNS queries, and RDP traffic.
<h4>Observation:</h4>  Each filter will show relevant traffic types: SSH traffic appears as secure data exchanges, DHCP shows IP renewal, DNS shows domain resolution, and RDP traffic demonstrates continuous data transmission.

<h2>Conclusion</h2>

In conclusion, this lab provided hands-on experience with network traffic analysis and firewall management in Azure. By observing various traffic types—such as ICMP, SSH, DHCP, DNS, and RDP—and experimenting with Network Security Groups, we gained insight into how network traffic flows between Azure Virtual Machines. We also learned the critical role of NSGs in controlling and securing network access, as well as how tools like Wireshark can be utilized to monitor and analyze traffic patterns in real-time.
