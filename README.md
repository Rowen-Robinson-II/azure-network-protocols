<p align="center">
<img src="https://i.imgur.com/Ua7udoS.png" alt="Traffic Examination"/>
</p>

<h1>Network Security Groups (NSGs) and Inspecting Traffic Between Azure Virtual Machines</h1>
In this tutorial, we observe various network traffic to and from Azure Virtual Machines with Wireshark as well as experiment with Network Security Groups. <br />



<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Various Command-Line Tools
- Various Network Protocols (SSH, RDH, DNS, HTTP/S, ICMP)
- Wireshark (Protocol Analyzer)

<h2>Operating Systems Used </h2>

- Windows 10 (21H2)
- Ubuntu Server 22.04


<h2>Network Security Groups (Confiuring A Firewall)</h2>

<h3 align="center">Virtual Machines</h3>
<img width="959" alt="image" src="https://github.com/user-attachments/assets/3538c25d-5cb7-4fc8-807d-10c150378255">
</p>
<p>
Three Virtual machines were created: "DC-1", "Client-1", and "Client-2" all are on the same virtual network, share the same resource group, and are in the same subnet.DC-1 was deployed with windows server 2022, Client-1 was deployed with windows 10, Client-2 was deployed with Ubuntu 22.04. Client-1's DNS settings have been configured to DC-1's private IP address.
</p>
<br>
<br>
<br />

<h3 align="center">Configuring A Firewall</h3>

<img width="959" alt="image" src="https://github.com/user-attachments/assets/5c00c9bd-c986-471d-b674-1dcf54d9578e">
<p>
From Client-1 ping Client-2's private IP address and observe traffic via wireshark
</p>
<br>
<br>
<br />

<h3 align="center">Configuring A Firewall</h3>

<img width="959" alt="image" src="https://github.com/user-attachments/assets/4a26af0f-8a55-493b-b6d4-baa71ca5e9e6">
<p>
start a non-stop ping to Client-2
</p>
<br>
<br>
<br />

<h3 align="center">Configuring A Firewall</h3>

<img width="958" alt="image" src="https://github.com/user-attachments/assets/fd6cb28a-1845-44b9-82c1-b0242ef93039">
<p>
disable incoming ICMP traffic via Newtork Security Groups. Go to settings then inbound security rules. Create a rule with 290 priority that denies all traffic.
</p>
<br>
<br>
<br />

<h3 align="center">Configuring A Firewall</h3>

<img width="959" alt="image" src="https://github.com/user-attachments/assets/0e15ece6-9d80-49b9-9d78-a32218343f45">
<p>
observe stopped ICMP traffic in wireshark, then re-enable incoming traffic
</p>
<br>
<br>
<br />

<h2>Inspecting Traffic Between Azure Virtual Machines</h2>

<h3 align="center">Observing SSH Traffic</h3>
<p>
<img width="959" alt="image" src="https://github.com/user-attachments/assets/fcd80aeb-fe46-4dee-bda5-c8074f2a2cac">
</p>
<p>
Filter wireshark traffic to only include SSH packets
</p>
<br>
<br>
<br />

<h3 align="center">Observing DHCP Traffic</h3>
<p>
<img width="959" alt="image" src="https://github.com/user-attachments/assets/bdbac5e6-6571-43a6-9c23-5c24422200d4">
</p>
<p>
Filter wireshark traffic to only include DHCP traffic using "ipconfig /renew" in powershell as an administrator
</p>
<br>
<br>
<br />

<h3 align="center">Observing DNS Traffic</h3>
<p>
<img width="959" alt="image" src="https://github.com/user-attachments/assets/31034ba7-1325-491a-bf7d-06299fdc2fe3">
</p>
<p>
Filter wireshark traffic to only include DNS traffic using "nslookup" in powershell as an administrator
</p>
<br>
<br>
<br />



