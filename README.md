# Server-Creation-DC

<!---video tut placeholder--->

<h2>Requirments</h2>
<!---input download instructions--->

-  <b><a href="https://www.virtualbox.org/wiki/Downloads">Virtual Box</a></b>
-  <b><a href="https://www.microsoft.com/en-us/evalcenter/download-windows-server-2019">Windows Server</a></b>

<h1>Create new Virutal Machine</h1>
This will be the domain controller. Internet NIC and internal NIC
- img placeholder                                                                                                           (dc 1, dc2)


<img src="https://github.com/narvee09/IT-images/blob/main/DC1.JPG?raw=true" height=360>



<h3>Create network adapter (internal NIC)</h3>

<div>
Open settings > network > adapeter 1 will have no changes, this is the "home" network
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc3.JPG" width=600 h=300>  
</div>
 
<br>
<br>
<br>
<br>
<br>

 <!---markdown spaces refference, each <br> is space format--->

  
<div> - adapter 2 > enable network adapter > set internal network
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc3.JPG"  height=600>
                                                          (dc3,dc4)
</div>

<br>
<br>
<br>
<br>
<br>

<h3>Input ISO img:</h3>
-img placeholder                                                                                                     (dc5)
<div> Select VM > Start > DVD > Select windows server iso >mount and retry boot
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc5.JPG"  height=200 >
</div>

<br>
<br>
<br>
<br>
<br>

<h1>Windows Server Setup:</h1>
  - img Placeholder                                                                                                       (dc6)

<div>
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc6.JPG"  height=400>
</div>

<br>
<br>

<div>  choose "standard evaluation (desktop experience)"chose custom installation and create admin credentials
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc7.JPG"  height=400>(dc7)
                                                                                                           (dc8,"9 and 10 optional")  virtual machine will restart.
  
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc11.JPG"  height=400>(dc11)
</div>
<br>
<br>
<div> When using virtual box click here to input crtl+alt+del
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc12.JPG"  height=400>
                                                                                             (dc12)
</div>

<br>
<br>
<br>

<h3>Setup internal network ip addressing and configuration:</h3>

 <div>  Open Network & Internext settings > Ethernet > Change adapter options
  <img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc13.JPG" width="500">  <img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc14.JPG" width="500">
</div>(dc13,dc14)

<br>
<br>
<br>

<div> 
 To find out wich adapter is internal network, right click on either option > status > details
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc15.JPG"  height=500> 
 The option with IP:starting with "169.254.ect.ect is what will be used to set internal network
 <img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc16.JPG"  height=500>(dc15,dc16)

<br>
<br>
<br>

<div>
Right click on internal network > properties
</div>
 <div>
  <img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc17.JPG"  height=400>(dc17)
 </div>

<div>
  -   - Double click on TCP/IPv4, in the preffered DNS server field use 127.0.0.1 as the look back address
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc18.JPG"  height=600>
                                                                                                          (dc18)
- Rename PC
</dvi>

<br>
<br>
<br>

<h3>Active directory installation</h3>
<div>
 server manager dashboard navigate to add roles and features
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc server manager add roles and features.JPG"  height=600>(roles and features can use same img)
</div>

<br>

<div>
 installation type:role-based installation  Server Selection: choose Your server from the pool of options  Server Roles: select "Active directory Domain Services" > add features > next
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc19.JPG"  height=500> 
 <br>
 <br>
<div>
 For the features and ADDS screens choose the default selection then confirm and install
</div>
 <div>
 <img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc20.JPG"  height=400>8<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc21.JPG"  height=400>(dc21)
</div>
 
<br>
<br>
<br>

<h3>Domain Creation</h3>
-img placeholder for server manager dashboard
<div> 
 Post-deployment Configuration: protoe this server to a domain controller
 
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc%20server%20manager%20flag%20icon%20promot%20this%20server.JPG"  height=500>
</div>

<div>
THen click on Deployment Configuration: add a new forest Root domain Name: input "yourdomain.com"-  Domain Controller Options: Create password  DNS Options: uncheck "create DNS delegation additional options,Paths,Review options,prerequisites check > install > the server will restart 
</div>
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc22.JPG" width=400 height=400>9<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc23.JPG" width=400 height=400>(optional dc 23)


<br>
<br>
<br>

<h3>Dedicated domain admin account creation</h3>

<div> 
 - Click on start > windows administrative tools > active directory users and computers 
</div>
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc24.JPG"  height=400>(dc24)


 <div>                                                                                                (for active directory window)
-right click on domain > new > organizational unit > rename to Admin
 </div>
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc25.JPG"  height=400> <img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc26.JPG"  height=500>(dc25,dc26)

<div>
right click on admin OU >new > user and input details
</div>
   -  <img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc27.JPG"  height=600>8<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc28.JPG"  height=400>(dc28)

 <div>
Right click on new user > properties > member of > add
 </div>
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc29.JPG"  height=500>(dc29)


<div>
 input "domain admins" > click on check names > Click apply then ok.
</div>
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc30.JPG"  height=500>(dc30)

 <div>
  Confirm domain admin is working by signing out of administrator and log back in with domain admin credentials       (dc31)
 </div>
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc31.JPG"  height=500>

<br>
<br>

<h3>Remote Access Server / Network Address Translation Installation</h3>
-img placeholder(server dashboard)
<div>
- skip to server roles > Remote Access
-   Select next on Features and Remotes Access <--------- use this verion to write steps
 </div>

 <div>
   Role Services > select Routing > add features. Select next on Web Server Role (IIS) and Role Services Confirmation then install
 </div>
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc32.JPG"  height=400>8<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc33.JPG"  height=400>(dc33)


-img placeholder(server dashboard/ highlight tools then routing and remote access)

<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc34.JPG"  height=600>(dc34)
-  img placeholder (routing and remote access window)
  <div>
  Right click on computer name > configure and enable routing and remote access
  </div> 
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc35.JPG"  height=400>(<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc36.JPG"  height=600> <img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc40.JPG"  height=600>        (dc36 - dc40)
<!--[the option that is connected to the internet, find out proper name for this]--->

<h3>DHCP Server Setup</h3>
<div>                                                                                                (server dashboard)
-skip to Server Roles: Select DHCP Server > add features > next Select next for features and DHCP Server Confirmation > install
</div>
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc41.JPG"  height=400>(dc41)


-img placeholder
<div>
 Navigate to tools then DHCP
</div>
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc42.JPG"  height=400>(server dashboard / tools > DHCP)(dc42)

<div>
-  expand domain arrow > right click on IPv4 > New Scope
</div>
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc43.JPG" width=500 height=400>(dc43)
-  img placeholder

<br>
<br>
<br>
<br>

<div>
 -  in Scope name input IP range<----------------important detail bold this img placeholder (Scope setup wizard: IP address range section show with details already listed) Lease duration (specificy reason for longer or shorter lease)

(Configure DHCP Optoins: YES)
(Router Default Gateway) text = enter domain contoller IP address

 Select next for Domain Name and DNS Servers, WINS Servers and Activate Scope Right click on domain > refresh > authorize > refresh
</div>
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc44.JPG"  height=300> >>
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc45.JPG"  height=300>
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc46.JPG"  height=300> >>
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc47.JPG"  height=300>
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc48.JPG"  height=300> >>
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc49.JPG"  height=300>
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc50.JPG"  height=300> >>
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc51.JPG"  height=300>
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc52.JPG"  height=300> >>
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc53.JPG"  height=300>
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc54.JPG"  height=300>(Scope setup wizard)(dc44 - dc54)

<br>

<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc55.JPG"  height=400>
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc56.JPG"  height=400>
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc57.JPG"  height=400>(dc55 - dc57)


-img placeholder(show DCT hosting virtual client using internal network)
