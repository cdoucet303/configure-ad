<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>On-premises Active Directory Deployed in the Cloud (Azure)</h1>
This tutorial outlines the implementation of on-premises Active Directory within Azure Virtual Machines.<br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services
- PowerShell

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)

<h2>High-Level Deployment and Configuration Steps</h2>

- Step 1
- Step 2
- Step 3
- Step 4

<h2>Deployment and Configuration Steps</h2>

<p>
For the first step I created a Resource Group in Microsoft Azure so that I could then create two Virtual Machines and a Subnet. After creating the Resource Group I will create a Virtual Network that both of our Virtual Machines will join. Then I will make one Virtual Machine of Windows Server 2022 and this will be our Domain Controller. The next Virtual machine I will make is a Windows 10 and this will simulate our Clients joining the Domain. Once those are made I can now start Congiguring the Active Directory.
</p>
<br />

![image](https://github.com/user-attachments/assets/da1a27af-a8d6-4210-8a45-064f7bc11b2d)

<p>
For the second step we want to make the IP address on our Domain Controller static so it doesn't change whether the machine is turned off or restarted. After that we will make sure our Client-1 Virtual Machine is connected to the Domain Controllers DNS server by using the DC-1 private IP.
</p>
<br />

![image](https://github.com/user-attachments/assets/abc6ce69-8e30-437f-b799-63eb1145a8df)
![image](https://github.com/user-attachments/assets/affe08ea-feb4-4ed0-b21c-6c52671c3a58)

<p>
I will now log in to the Domain Controller through Remote Desktop Connection on Windows with the public IP Azure has provided me with. I will disable the firewalls so that when I test the ping command here in a minute on my Client-1 virtual machine it will come through and The Client-1 PC is connected to the Domain Controller PC.
</p>
<br />

![image](https://github.com/user-attachments/assets/f5f762b4-079f-4bc6-8e79-b67eed1646bf)

<p>
Third step is I'm going to log in to the Client-1 PC through Remote Desktop Connection on Windows with the public IP Azure has provided me and then once logged in I will open Powershell and use the ping command and ping the private IP address of the DC-1 PC to check if I am connected to the Domain Controller. 
</p>
<br />

![image](https://github.com/user-attachments/assets/d2117e79-8adb-4b8d-9821-aa9714b7e071)

<p>
For the Final Step I will run the command ipconfig /all on the same Virtual machine I am on (Client-1) and it should display the DC-1 private IP as my DNS server if all done correctly.
</p>
<br />

![image](https://github.com/user-attachments/assets/ee29e9cc-5233-456e-953b-29cdc242ea26)

