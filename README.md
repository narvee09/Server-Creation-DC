# Server-Creation-DC

<!---video tut placeholder--->

<h2>Requirments</h2>
<!---input download instructions--->

-  <b><a href="https://www.virtualbox.org/wiki/Downloads">Virtual Box</a></b>
-  <b><a href="https://www.microsoft.com/en-us/evalcenter/download-windows-server-2019">Windows Server</a></b>

<h1>Create new Virutal Machine</h1>
This will be the domain controller. Internet NIC and internal NIC
- img placeholder                                                                                                           (dc 1, dc2)


<img src="https://github.com/narvee09/IT-images/blob/main/DC1.JPG?raw=true" width=600 height=300>



<h3>Create network adapter (internal NIC)</h3>
-img placeholder 

Open settings > network > 

<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc3.JPG" width=600 h=300>

  - adapeter 1 will have no changes, this is the "home" network

<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc3.JPG" widnth=600 height=300>

  - adapter 2 > enable network adapter > set internal network                                                             (dc3,dc4)

<h3>Input ISO img:</h3>
-img placeholder                                                                                                     (dc5)
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc5.JPG" >
- Select VM > Start > DVD > Select windows server iso >mount and retry boot


<h1>Windows Server Setup:</h1>
  - img Placeholder                                                                                                       (dc6)
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc6.JPG" width=600 height=300>

  - <b>Choose "standard evaluation (desktop experience)"

<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc7.JPG" width=500 height=300>(dc7)
  - <b>Choose custom installation</b>                                                                                (dc8,"9 and 10 optional")  virtual machine will restart.
  - <b>Create admin credentials</b>
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc11.JPG" width=500 height=300>(dc11)

<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc12.JPG" width=500 height=300>
  - <b> When using virtual box click here to "input" crtl+alt+del </b>                                                  (dc12)

<h3>Setup internal network ip addressing and configuration:</h3>
 - <b>Open Network & Internext settings > Ethernet > Change adapter options</b>
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc13.JPG" width=500 height=300>  <img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc14.JPG" width=500 height=300>(dc13,dc14)

- To find out wich adapter is internal network, right click on either option > status > details
- img placeholder
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc15.JPG" width=500 height=300> <img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc16.JPG" width=500 height=300>(dc15,dc16)
- The option with IP:starting with "169.254.ect.ect is what will be used to set internal network
- Right click on internal network > properties
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc17.JPG" width=500 height=300>(dc17)

<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc18.JPG" width=500 height=300>
-   - Double click on TCP/IPv4                                                                                        (dc18)
    - IP address: 172.16.0.1
    - Subnetmask: 255.255.255.0
    - Preferred DNS server: 127.0.0.1 (loop back address)
 
- Rename PC


<h3>Active directory installation</h3>
-img placeholder for server manager dashboard

<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc server manager add roles and features.JPG" width=500 height=300>(roles and features can use same img)
- add roles and features
    -  installation type:role-based installation
    -  Server Selection: Your server from the pool of options
    -  Server Roles: select "Active directory Domain Services" > add features > next
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc19.JPG" width=500 height=300> <img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc20.JPG" width=500 height=300>(dc19,dc20)
    - Features: (defualt selection) 
    - AD DS: (default selection)
    -Confirm and install
  <img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc21.JPG" width=500 height=300>(dc21)

<h3>Domain Creation</h3>
-img placeholder for server manager dashboard
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc%20server%20manager%20flag%20icon%20promot%20this%20server.JPG" width=500 height=300>(roles and features can use same img)(use flag icon)
-  Post-deplyment Configuration: Promote this server to a domain  controller
-  Deployment Configuration: add a new forest
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc22.JPG" width=500 height=300>(dc22)
-  -  Root domain Name: input "yourdomain.com"
-  Domain Controller Options: Create password
-  DNS Options: uncheck "create DNS delegation
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc23.JPG" width=500 height=300>(optional dc 23)
-  additional options,Paths,Review options,prerequisites check > install > the server will restart

<h3>Dedicated domain admin account creation</h3>
-img place holder V                                                         
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc24.JPG" width=500 height=300>(dc24)
- Click on start > windows administrative tools > active directory users and computers 

img place holder                                                                                                   (for active directory window)
-right click on domain > new > organizational unit > rename to Admin
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc25.JPG" width=500 height=300> <img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc26.JPG" width=500 height=300>(dc25,dc26)
-  -  img placeholder(for OU)
   -  right click on admin OU >new > user
   -  <img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc27.JPG" width=500 height=300>(dc27)
   -  input details
   <img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc28.JPG" width=500 height=300>(dc28)
 
   -  Right click on new user > properties > member of > add
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc29.JPG" width=500 height=300>(dc29)
   -  img placeholder (for select groups image)
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc30.JPG" width=500 height=300>(dc30)
   -  input "domain admins" > click on check names > Click apply then ok.
 
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc31.JPG" width=500 height=300>
Confirm domain admin is working by signing out of administrator and log back in with domain admin credentials       (dc31)


<h3>Remote Access Server / Network Address Translation Installation</h3>
-img placeholder(server dashboard)
- skip to server roles > Remote Access
-   Select next on Features and Remotes Access <--------- use this verion to write steps
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc32.JPG" width=500 height=300>(dc32)
-  Role Services > select Routing > add features
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc33.JPG" width=500 height=300>(dc33)
- Select next on Web Server Role (IIS) and Role Services
-  Confirmation > install

-img placeholder(server dashboard/ highlight tools then routing and remote access)
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc34.JPG" width=500 height=300>(dc34)
-  img placeholder (routing and remote access window)
-  right click on computer name > configure and enable routing and remote access
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc35.JPG" width=500 height=300>(dc35)
-  img placeholder (setip wizard for each view, place inline as array, images will speak for instructions)
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc36.JPG" width=500 height=300> <img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc40.JPG" width=500 height=300>        (dc36 - dc40)
<!--[the option that is connected to the internet, find out proper name for this]--->

<h3>DHCP Server Setup</h3>
-img placeholder                                                                                                  (server dashboard)
-skip to Server Roles: Select DHCP Server > add features > next
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc41.JPG" width=500 height=300>(dc41)
- Select next for features and DHCP Server
-  Confirmation > install

-img placeholder
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc42.JPG" width=500 height=300>(server dashboard / tools > DHCP)(dc42)
-img placeholder(DHCP window)
-  expand domain arrow > right click on IPv4 > New Scope
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc43.JPG" width=500 height=300>(dc43)
-  img placeholder
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc44.JPG" width=500 height=300>
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc45.JPG" width=500 height=300>
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc46.JPG" width=500 height=300>
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc47.JPG" width=500 height=300>
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc48.JPG" width=500 height=300>
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc49.JPG" width=500 height=300>
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc50.JPG" width=500 height=300>
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc51.JPG" width=500 height=300>
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc52.JPG" width=500 height=300>
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc53.JPG" width=500 height=300>
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc54.JPG" width=500 height=300>(Scope setup wizard)(dc44 - dc54)
-  in Scope name input IP range<----------------important detail bold this
-  img placeholder (Scope setup wizard: IP address range section show with details already listed)
-  Lease duration (specificy reason for longer or shorter lease)
-  img placeholder(Configure DHCP Optoins: YES)
-  img placeholder(Router Default Gateway) text = enter domain contoller IP address
-  Select next for Domain Name and DNS Servers, WINS Servers and Activate Scope
-  Right click on domain > refresh > authorize > refresh

<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc55.JPG" width=500 height=300>
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc56.JPG" width=500 height=300>
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc57.JPG" width=500 height=300>(dc55 - dc57)


-img placeholder(show DCT hosting virtual client using internal network)
