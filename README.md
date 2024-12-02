# Active Directory Home Lab Part 1: Configuring Server Domain Controller

<h2>Description</h2>
In this Active Directory Home Lab, I installed Windows Server 22, configured Active Directory services, configured the server as Domain Controller 01 (DC01), created Domain Users, and linked user endpoint to my domain.  
<br />


<h2>Languages and Utilities Used</h2>

- <b>Windows GUI</b>

<h2>Environments Used </h2>

- <b>Windows Server 22</b> 
- <b>Windows 11 Enterprise</b> 
<br />
<br />
I downloaded windows Server 22 form Micorsoft.

![1) download windows server 22](https://github.com/user-attachments/assets/ef419dd5-2f69-4452-90c6-9bc972ede739)

<br />
<br />
I configure VM settings to my liking. I had limited resources for this new install. 

![2) configure VM settings for windows server](https://github.com/user-attachments/assets/d6650555-59b0-4a02-bd95-634ee83670e7)

<br />
<br />
I renamed this PC as DC01 (Domain Controller 01).

![3) rename pc as DC01](https://github.com/user-attachments/assets/84877a35-511c-4f0b-bfa2-742d55ace1bc)

<br />
<br />
I clicked Tools>Add Roles> and went through installtion steps. I used default settings. 

![4) tools_add roles_configure settings, confirm results](https://github.com/user-attachments/assets/01d1b040-1a35-4522-b3c4-24f92b21b231)

<br />
<br />
After installation do not close window, instead I click "Promote this server to a domain controller" and went through the steps to configure my Active Directory Domain Services as "GothamCity.local". 

![5) configuring DC01 Server as Active Direcotry Domain Services](https://github.com/user-attachments/assets/b2d1cf7f-2a4d-4cc8-9157-56ab1a704dcd)

<br />
<br />
After configureation, Windows Server 22 retarts itself and I logged in as the administrator for GothamCity.local.

![6)logging in as domain admin](https://github.com/user-attachments/assets/d8fbb985-ef9d-4eb0-8577-11dc78eba10a)

<br />
<br />
I went to tools>add roles> and configured Active Directory Domain Services (make sure to click the box in "Server Roles" step), the rest were default settings. 

![7) adding certificate authority to DC01](https://github.com/user-attachments/assets/005c706a-220b-41dd-833b-884f86535bbb)

<br />
<br />
I confirmed settings before clicking configuration.  

![8) configuring active directory dc01 certificate services](https://github.com/user-attachments/assets/2e0de7e5-34b8-4db1-bbff-30137d442492)

<br />
<br />
Time to add users and computers to my new Active Directory Domain Server.  

![9) Creating Domain users tools ADusers and computers](https://github.com/user-attachments/assets/d457e547-9fa0-474a-9422-fb4f3c190610)

<br />
<br />
I started by putting all users in the "Security Group" into the users folder. This left me with Adminstrator and Guest users.  

![10)create groups OU, moving all security groups into group ](https://github.com/user-attachments/assets/8e138a51-a771-4980-bf54-cd08a0ef008d)

<br />
<br />
I created new users under the GothamCity.local domain.  

![11) New users created](https://github.com/user-attachments/assets/5c98e7fa-c4bb-4aba-b8bb-fa3a89868f08)

<br />
<br />
Before this in the VM settings for virtualbox, I created and connected the two VMs with a NAT Network named "AD Network".
I opened a cmd and ran ipconfig to set up my ipv4 network settings to match ipconfig.    

![12) configuring ipv4 settings on addc](https://github.com/user-attachments/assets/da4aeb01-0cf5-4d03-b6b8-95c612576481)

<br />
<br />
Switching over to the Windows 11 VM, I configured ipv4 settings to connect to the Active Directory Domain Server. Note that I made my ip address 1 number higher than my AD ip address for sequential order.
I also put the ip address of the AD server as the preferred DNS server. 

![13) winodws 11 ipv4 setup, using ADDC as DNS server, sequential ip](https://github.com/user-attachments/assets/e729162e-95e6-4ff0-8490-7503004e52e7)

<br />
<br />
I went searched "access work" in the search bar to go to the settings menu and clicked join a domain to enter Gothamcity.local. Spelling error in the screenshot*   

![14) joing GothamCity local domain](https://github.com/user-attachments/assets/e39e6de1-949c-4c2f-8a2b-2e5f9aa753c0)

<br />
<br />
I chose Batman@GothamCity.local as a standard user and granted access through logging in as adminstrator.  

![15) logging in as batman user](https://github.com/user-attachments/assets/32213dfb-1a10-49fa-9c60-338caad36d69)

<br />
<br />
Switching back over to the AD Server VM, I confirmed that the Batman@GothamCity.local's desktop is added within my domain.   

![16) Windows 11 VM now connected to AD ](https://github.com/user-attachments/assets/814afcc8-6928-497c-8e63-959c444adae7)

<br />
<br />
