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

![image](https://github.com/user-attachments/assets/a4f383f7-0c74-486c-954f-60625e73f56b)
![image](https://github.com/user-attachments/assets/c5310a4e-ff79-4b6d-962c-98466d08b0fc)


<p>
Once we have made our two new Organizational Unit folders we are now going to make a user in the _ADMIN folder. We do this by first selecting the _ADMIN folder then right clicking it and selecting new and then user. Fill out the user information in the spaces provided for this example I will using John Doe with the user logon name as john_admin. For the passwords setting do what ever is appropriate for your situation. I am doing the easiest of settings and passwords just for this lab but in a real work place the password part should be taken extremely seriously. So now the user has been added and you can see it in the _ADMINS folder but just because it is in a folder we created called _ADMINS and has admin in the logon name doesn't make it an admin yet! We need to Add john_admin to the “Domain Admins” Security Group to make it a real admin. To do this we simply right click the John doe user in the foler of _ADMINS and select properties and then Member of tab and click add and then type domain admins and check names then hit ok and after ok hit apply and now John Doe is an admin.  
</p>
<br />

![image](https://github.com/user-attachments/assets/2ed28b28-23d8-4214-9939-ba40d9574ffd)


<p>
I am now going to exit this virtual machine and log back in as my newly created Admin account John Doe. 
</p>
<br />

<p>
As I wait for my new Admin User john doe to log in on my DC-1 Domain controller virtual machine I am going to use this time to connect my Client-1 virtual machine to the Domain. To do this we log onto our Client-1 machine and right click the windows start button on the home page and then select System. Once this is done a window should pop up and the top should say About in big text now click Rename this PC (advanced) on the right hand side and when the system properties window pops up we will want to select change near the bottom and in the Computer Name/Domain Changes window we will want to select the Domain radio button and type in your domain and hit ok. It will then prompt you to log in with an account with permissions to join this domain and that is what we just created in the last step so im going to log in with my John Doe admin account and it should reset my VM if all is entered correctly. Now when it restarts it should now be apart of our Domain!
</p> 
<br />

![image](https://github.com/user-attachments/assets/cc055b57-72ed-4f20-b223-22b8996c7bd5)


<p>
For the Final Step 
</p>
<br />
