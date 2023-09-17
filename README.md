# Server-Creation-DC

-video tut placeholder

<h2>System requirments</h2>
<!---input download instructions--->
<b><a href="https://www.virtualbox.org/wiki/Downloads">Virtual Box</a></b>
<b><a href="https://www.microsoft.com/en-us/evalcenter/download-windows-server-2019">Windows Server</a></b>

<h1>Create new Virutal Machine</h1>
This will be the domain controller. Internet NIC and internal NIC
- img placeholder (dc 1, dc2)

<h3>Create network adapter (internal NIC)</h3>
-img placeholder 

Open settings > network > 
  - adapeter 1 will have no changes, this is the "home" network
  - adapter 2 > enable network adapter > set internal network (dc3,dc4)

<h3>Input ISO img:</h3>
-img placeholder (dc5)

- Select VM > Start > DVD > Select windows server iso >mount and retry boot


<h1>Windows Server Setup:</h1>
  - img Placeholder (dc6)

  - <b>Choose "standard evaluation (desktop experience)"(dc7)
  - <b>Choose custom installation</b>(dc8,9 and 10 optional)
  - <b>Create admin credentials</b>

<h3>Setup internal network ip addressing and configuration:</h3>
 - <b>Open Network & Internext settings > Ethernet > Change adapter options</b>

- To find out wich adapter is internal network, right click on either option > status > details
- img placeholder
- The option with IP:starting with "169.254.ect.ect is what will be used to set internal network
- Right click on internal network > properties
-   - Double click on TCP/IPv4
    - IP address: 172.16.0.1
    - Subnetmask: 255.255.255.0
    - Preferred DNS server: 127.0.0.1 (loop back address)
 
- Rename PC


<h3>Active directory installation</h3>
-img placeholder for server manager dashboard (roles and features can use same img)
- add roles and features
    -  installation type:role-based installation
    -  Server Selection: Your server from the pool of options
    -  Server Roles: select "Active directory Domain Services" > add features > next
    - Features: (defualt selection) 
    - AD DS: (default selection)
    -Confirm and install

<h3>Domain Creation</h3>
-img placeholder for server manager dashboard (roles and features can use same img)(use flag icon)
-  Post-deplyment Configuration: Promter this server to a domain  ontroller
-  Deployment Configuration: add a new forest 
-  -  Root domain Name: input "yourdomain.com"
-  Domain Controller Options: Create password
-  DNS Options: uncheck "create DNS delegation
-  additional options,Paths,Review options,prerequisites check > install

<h3>Dedicated domain admin account creation</h3>
-img place holder V
- Click on start > windows administrative tools > active directory users and computers 

img place holder (for active directory window)
-right click on domain > new > organizational unit > rename to Admin
-  -  img placeholder(for OU)
   -  right click on admin OU >new > user
   -  input details
 
   -  Right click on new user > properties > member of > add
   -  img placeholder (for select groups image)
   -  input "domain admins" > click on check names
Confirm domain admin is working by signing out of administrator and log back in with domain admin credentials 


<h3>Remote Access Server / Network Address Translation Installation</h3>
-img placeholder(server dashboard)
- skip to server roles > Remote Access
-   Select next on Features and Remotes Acess <--------- use this verion to write steps
-  Role Services > select Routing > add features
- Select next on Web Server Role (IIS) and Role Services
-  Confirmation > install

-img placeholder(server dashboard/ highlight tools then routing and remote access)
-  img placeholder (routing and remote access window)
-  right click on computer name > configure and enable routing and remote access
-  img placeholder (setip wizard for each view, place inline as array, images will speak for instructions)


<h3>DHCP Server Setup</h3>
-img placeholder(server dashboard)
-skip to Server Roles: Select DHCP Server > add features > next
- Select next for features and DHCP Server
-  Confirmation > install

-img placeholder(server dashboard / tools > DHCP)
-img placeholder(DHCP window)
-  expand domain arrow > right click on IPv4 > New Scope
-  img placeholder(Scope setup wizard)
-  in Scope name input IP range<----------------important detail bold this
-  img placeholder (Scope setup wizard: IP address range section show with details already listed)
-  Lease duration (specificy reason for longer or shorter lease)
-  img placeholder(Configure DHCP Optoins: YES)
-  img placeholder(Router Default Gateway) text = enter domain contoller IP address
-  Select next for Domain Name and DNS Servers, WINS Servers and Activate Scope
-  Right click on domain > refresh > authorize > refresh

