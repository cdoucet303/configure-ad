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

- Install Active Directory 
- Create a Domain Admin user within the Domain
- Join Client-1 to the domain
- 

<h2>Deployment and Configuration Steps</h2>

<p>
For the first step we want to get on our Domain controller PC in this instance its our DC-1 virtual machine and automatically after bootup the Server Manager window should pop up and you're going to want to click on Add roles and features and hit next 2 times and in the Server Selection Window make sure its your server your connecting to then next again and now in the Server roles tab select Active Directory Domain Services and a little windows should pop up click add features and then click next until the install button is ready and click install. When it has been installed you should see a yellow flag with a yield looking symbol on the top right of the Server Manager home page
</p>
<br />

![image](https://github.com/user-attachments/assets/fc81518e-e0fa-498f-be82-5ff99b97e5af)


<p>
When it has been installed you should see a yellow flag with a yield looking symbol on the top right of the Server Manager home page. Click that flag and then click the blue sentences that reads Promote this erver to a domain controller. In the Deployment Configuration tab we will select the Add a new forest button and for the root domain name we will be using mydomain.com for this example and then hit next. In the next tab select and remember a password for the DSRM and then hit next. In the DNS options tab uncheck the Create DNS delegation box and now hit next until the Prerequesites Check tab and click install. When it has finished installing it will reset the PC and you will need to log in again but this time you log in with the username mydomain.com\username (whatever username you are using goes where username is).
<br />

![image](https://github.com/user-attachments/assets/8438725a-dc57-475c-abc6-e2c551fb8be7)
![image](https://github.com/user-attachments/assets/144db5b8-9f55-4f02-993e-78a848757b71)


<p>
And now after the DC-1 virtual machine has reset and we are logged in we will create a Domain Admin user. We start this by clicking the windows start button in the bottom left and then clicking the folder in the middle pane that says Windows Administrative Tools and then we click Active Directory Users and Computers. Once in the Active Directory Users and Computers windows we will select our domain which is mydomain.com for this example and then right click mydomain.com after selecting it select new and then click Organizational Unit. We will be making two of these brand new Organizational Unit folders so the first one I named _EMPLOYEES and the second I named _ADMINS
</p>
<br />

![image](https://github.com/user-attachments/assets/c5310a4e-ff79-4b6d-962c-98466d08b0fc)


<p>
 
</p>
<br />

img

<p>
For the Final Step 
</p>
<br />

img

