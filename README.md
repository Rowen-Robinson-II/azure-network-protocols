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


<h2>Network Security Groups</h2>

<h3 align="center">Virtual Machines (Pre-Configured)</h3>
<img width="959" alt="image" src="https://github.com/user-attachments/assets/c0bf980b-fde7-4818-9681-cf91097b5101">
</p>
<p>
Two Virtual machines were created one named "DC-1" the other "Client-1" both are on the same virtual network, share the same resource group, and are in the same subnet.DC-1 was deployed with windows server 2022 while Client-1 was deployed with windows 10. Client-1's DNS settings have been configured to DC-1's private IP address.
</p>
<br>
<br>
<br />

<h3 align="center">Configure Group Policy to Lockout the account after 5 attempts</h3>
<p>
<img width="959" alt="image" src="https://github.com/user-attachments/assets/51a97893-2f84-4c64-a708-45cb4b9044db">
</p>
<p>
log into DC-1 go to Group Policy Management. Right-Click "Account Lockout Policy". Via Group Policy Management Editor go to Computer configuration -> Policies -> Windows Setting -> Security Settings -> Account Policies -> Account Lockout policy. Configure the lockout settings, then link the policy the the specified domain. Force update the policy using Command Prompt by typing "gpupdate /force"
</p>
<br>
<br>
<br />

<h3 align="center">Enabling and Disabling Accounts</h3>
<p>
<img width="958" alt="image" src="https://github.com/user-attachments/assets/84d53f5e-0488-45c0-b001-264dd8a5dee4">
</p>
<p>
To disable/enable an account go to Active Directory Users and Computers find a user in the _EMPLOYEE folder right-click their name then disable/enable as needed
</p>
<br>
<br>
<br />

<h2>Inspecting Traffic Between Azure Virtual Machines</h2>

<h3 align="center">Enabling and Disabling Accounts</h3>
<p>
<img width="958" alt="image" src="https://github.com/user-attachments/assets/84d53f5e-0488-45c0-b001-264dd8a5dee4">
</p>
<p>
To disable/enable an account go to Active Directory Users and Computers find a user in the _EMPLOYEE folder right-click their name then disable/enable as needed
</p>
<br>
<br>
<br />

<h3 align="center">Enabling and Disabling Accounts</h3>
<p>
<img width="958" alt="image" src="https://github.com/user-attachments/assets/84d53f5e-0488-45c0-b001-264dd8a5dee4">
</p>
<p>
To disable/enable an account go to Active Directory Users and Computers find a user in the _EMPLOYEE folder right-click their name then disable/enable as needed
</p>
<br>
<br>
<br />

<h3 align="center">Enabling and Disabling Accounts</h3>
<p>
<img width="958" alt="image" src="https://github.com/user-attachments/assets/84d53f5e-0488-45c0-b001-264dd8a5dee4">
</p>
<p>
To disable/enable an account go to Active Directory Users and Computers find a user in the _EMPLOYEE folder right-click their name then disable/enable as needed
</p>
<br>
<br>
<br />
