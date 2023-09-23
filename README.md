# Server-Creation-DC

<!---video tut placeholder--->

<h2>Technologies Used</h2>

- <b>Active Directory</b>
- <b>Windows 10</b>
- <b>Windows Server 2019</b>

<h2>Requirments</h2>
<!---input download instructions--->

-  <b><a href="https://www.virtualbox.org/wiki/Downloads">Virtual Box</a></b>
-  <b><a href="https://www.microsoft.com/en-us/evalcenter/download-windows-server-2019">Windows Server</a></b>

<h1>Create new Virutal Machine</h1>
<br>
<div>
<a href="https://github.com/narvee09/Client-Creation-VM-">Virtual Machine creation tutorial</a>
</div>
<br>
<div>
<img src="https://github.com/narvee09/IT-images/blob/main/DC1.JPG?raw=true" height=360>
</div>

<br>

<h3>Create network adapter (internal NIC)</h3>
<div>
Open settings then click on  network, adapter 1 will have no changes, this is your "home" network,
adapter 2 will be represent the private internal network. Click on adapter 2 then enable network adapter and set internal network in the dropdown menu.
</div>
<br>
<div>
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc3.JPG"  width=500>
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc4.JPG"  width=500>
</div>
 
<br>
 <!---markdown spaces refference, each <br> is space format--->

<h4>Input ISO img:</h4>
<div>
 Select VM select start and an opportunity input windows server iso. Click on mount and retry boot
</div>
<br>
<div>
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc5.JPG"  height=200 >
</div>

<br>

<h1>Windows Server Setup:</h1>
<div> 
 Choose "standard evaluation (desktop experience)", custom installation and create admin credentials after doing so the virtual machine will restart.
</div>
<div>
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc6.JPG"  width=500>
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc7.JPG"  width=500>
</div>
<br>
<br>
<div align=right>
 When using virtual box click here to <i>input</i> "crtl+alt+del"
</div>
<br>
<div>
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc11.JPG"  width=500>
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc12.JPG"  width=500>
</div>

<br>

<h3>Setup internal network ip addressing and configuration:</h3>

 <div>
 Right click on the Network icon then click open network & Internet settings. Navigate to ethernet and select change adapter options. To find out which adapter will be used as the internal network, right click on either option, status, details.
 </div>
 <br>
 <!--- <img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc13.JPG" width="500"> ---> 
 
 <div>
 <img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc14.JPG" height=350>
 <img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc15.JPG" height=350>
 </div>
<br>
<div> 
 The option with IP:address begining with "169.254.xx.xx" is what will be used to set internal network, when this is seen it means the DHCP server is not reachable.
</div>
 <img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc16.JPG"  height=500>
<br>
<div>
Right click on internal network > properties then couble click on TCP/IPv4, in the preffered DNS server field use 127.0.0.1 as the loop back address
</div>
<br>
<div>
  <!---img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc17.JPG"  height=400--->
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc18.JPG"  height=600>
</div>

<br>
<br>
<br>

<h3>Active directory installation</h3>
<div>
Navigate to the server manager dashboard then in the add roles and features window. Installation type:role-based installation  Server Selection: choose Your server from the pool of options  Server Roles: select "Active directory Domain Services".
</div>
<div>
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc server manager add roles and features.JPG"  height=350>
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc19.JPG"  height=350> 
</div>

 <br>
 <br>
 
<div>
 For the features and AD DS screens choose the default selection then confirm and install.
</div>
 <div>
 <img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc20.JPG"  height=400><img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc21.JPG"  height=400>
</div>
 
<br>
<br>
<br>

<h3>Domain Creation</h3>
<div> 
 Post-deployment Configuration: protoe this server to a domain controller then click on Deployment Configuration.
</div>
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc%20server%20manager%20flag%20icon%20promot%20this%20server.JPG"  height=450>

<br>
<br>

<div>
Add a new forest Root domain Name: input "yourdomain.com". Domain Controller Options: Create password  DNS Options: uncheck "create DNS delegation additional options,Paths,Review options,prerequisites check > install > the server will restart 
</div>
<div>
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc22.JPG" width=500>
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc23.JPG" width=500>
</div>

<br>
<br>
<br>

<h3>Dedicated domain admin account creation</h3>
<div> 
 - Click on start > windows administrative tools > active directory users and computers 
</div>
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc24.JPG"  height=500>

<br>
<br>

 <div>
Right click on domain and create a new  organizational unit and rename it to Admin
 </div>
 <div>
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc25.JPG"  width=500>
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc26.JPG"  height=300>
</div>

<br>
<br>

<h3>Add user to group</h3>
<div>
right click on admin OU and create a new user and input details
</div>
<div>
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc27.JPG"  width=500>
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc28.JPG"  height=300>
</div>

<div>
Right click on new user > properties > member of > add
  Input "domain admins" > click on check names > Click apply then ok.
 </div>
 <div>
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc29.JPG"  width=500>
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc30.JPG"  width=500>  
 </div>

<br>
<br>

 <div>
  Confirm domain admin is working by signing out of administrator and log back in with domain admin credentials.
 </div>
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc31.JPG"  height=500>

<br>
<br>

<h3>Remote Access Server / Network Address Translation Installation</h3>
<div>
 Navigate to server manager dashboard and follow the prompts to the server roles section and select remote access select next on Features and Remotes Access 
 </div>

 <div>
   Role Services > select Routing > add features. Select next on Web Server Role (IIS) and Role Services Confirmation then install
 </div>
 <div>
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc32.JPG"  width=500>
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc33.JPG"  width=500>
</div>
<br>
<br>
<div>
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc34.JPG"  height=600>
</div>

<br>

<div>
  Right click on computer name > configure and enable routing and remote access
</div> 
<br>
<div>
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc35.JPG"  width=350>
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc36.JPG"  width=300>
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc40.JPG"  height=200>
</div>
<!--[the option that is connected to the internet, find out proper name for this]--->

<h3>DHCP Server Setup</h3>
<div>
Navigate to server dashboard once more and click on add roles and features follow the prompts and  select DHCP Server, add features, next for features and DHCP Server Confirmation then install.
</div>
<br>
<div>
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc41.JPG"  height=400>
</div>


<div>
 Navigate to tools then DHCP 
 expand domain arrow > right click on IPv4 > New Scope
</div>
<div>
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc42.JPG"  height=350>
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc43.JPG"  height=350>
</div>

<br>

<br>
<h4>Scope Configuration</h4>
<div>
 -  in Scope name input IP range<----------------important detail bold this img placeholder (Scope setup wizard: IP address range section show with details already listed) Lease duration (specificy reason for longer or shorter lease)

(Configure DHCP Optoins: YES)
(Router Default Gateway) text = enter domain contoller IP address

 Select next for Domain Name and DNS Servers, WINS Servers and Activate Scope Right click on domain > refresh > authorize > refresh
</div>
<div>
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc44.JPG"  width=300>
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc45.JPG"  width=300>
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc46.JPG"  width=300>
</div>
<br>
<br>
<div>
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc47.JPG"  width=300>
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc48.JPG"  width=300>
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc49.JPG"  width=300>
</div>
<br>
<br>
<div>
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc50.JPG"  width=300>
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc51.JPG"  width=300>
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc52.JPG"  width=300>
</div>
<br>
<br>
<div>
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc53.JPG"  width=300>
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc54.JPG"  width=300>
</div>

<br>

<h4>Refresh and authorize IPv4 configuration</h4>
<div>
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc55.JPG"  width=200>
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc56.JPG"  width=300>
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc57.JPG"  height=300>
</div>

-img placeholder(show DCT hosting virtual client using internal network)
