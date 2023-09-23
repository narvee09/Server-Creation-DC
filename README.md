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
<br>
<div> 
 Choose "standard evaluation (desktop experience)", custom installation and create admin credentials after doing so the virtual machine will restart.
</div>
<br>
<div>
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc6.JPG"  width=500>
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc7.JPG"  width=500>
</div>
<br>
<br>
<div align=center>
 When using virtual box click here to <i>input</i> "crtl+alt+del" ⬇️
</div>
<br>
<div>
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc11.JPG"  width=500>
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc12.JPG"  width=500>
</div>

<br>

<h3>Setup internal network ip addressing and configuration:</h3>
<br>
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
 The option with IP:address begining with "169.254.xx.xx" is what will be used to set internal network, when this is seen it means the DHCP server is not reachable. We will resolove this in the upcoming steps.
</div>
<br>
<div>
 <img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc16.JPG"  height=500>
</div>
 <br>
<div>
Right click on internal network > properties then couble click on TCP/IPv4, in the preffered DNS server field use 127.0.0.1 as the loop back address.
</div>
<br>
<div>
  <!---img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc17.JPG"  height=400--->
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc18.JPG"  height=600>
</div>

<br>

<h3>Active directory installation</h3>
<br>
<div>
Navigate to the server manager dashboard then in the add roles and features window. Installation type:role-based installation  Server Selection: choose Your server from the pool of options  Server Roles: select "Active directory Domain Services".
</div>
<br>
<div>
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc server manager add roles and features.JPG"  height=350>
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc19.JPG"  height=350> 
</div>
 <br>
<div>
 For the features and AD DS screens choose the default selection then confirm and install.
</div>
<br>
 <div>
 <img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc20.JPG"  height=400><img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc21.JPG"  height=400>
</div>
 
<br>

<h3>Domain Creation</h3>
<br>
<div> 
 Post-deployment Configuration: protoe this server to a domain controller then click on Deployment Configuration.
</div>
<br>
<div>
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc%20server%20manager%20flag%20icon%20promot%20this%20server.JPG"  height=450>
</div>
<br>
<div>
Add a new forest in the "Root domain Name" field input "yourdomain.com". Create a password in  DNS Options uncheck "create DNS delegation additional options then navigate through the prompts, Paths, Review options, prerequisites check and finally click on install install. Once this is complete the server will restart.
</div>
<br>
<div>
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc22.JPG" width=500>
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc23.JPG" width=500>
</div>

<br>

<h3>Dedicated domain admin account creation</h3>
<br>
<div>
Next we will create an administrator account that will function as the server admin and client admin.
Click on start then windows administrative tools, active directory users and computers.
</div>
<br>
<div>
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc24.JPG"  height=500>
</div>
<br>
<div>
Right click on domain and create a new organizational unit and rename it to Admin.
</div>
<br>
<div>
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc25.JPG"  width=500>
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc26.JPG"  height=300>
</div>

<br>

<h3>Add user to group</h3>
<br>
<div>
right click on admin OU and create a new user and input details.
</div>
<br>
<div>
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc27.JPG"  width=500>
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc28.JPG"  height=300>
</div>
<br>
<div>
Right click on new user then properties, member of, add
  Input "domain admins", click on check names and finally click apply then ok.
 </div>
 <br>
 <div>
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc29.JPG"  width=500>
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc30.JPG"  width=500>  
 </div>
<br>
 <div>
  Confirm the new domain admin account is working by signing out of administrator and logging back in with domain admin credentials.
 </div>
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc31.JPG"  height=500>

<br>

<h3>Remote Access Server / Network Address Translation Installation</h3>
<br>
<div>
 Navigate to server manager dashboard, add roles and features and follow the prompts to the server roles section and select remote access. Under remote access select Routing then add features. Select next on Web Server Role (IIS) and Role Services confirm then install.
 </div>
 <br>
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
  Right click on computer name > configure and enable routing and remote access to begin setup. When navigating through the wizard you must select "(NAT)" then your "home" network to use network address translation.
</div> 
<br>
<div>
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc35.JPG"  width=350>
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc36.JPG"  width=300>
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc40.JPG"  height=200>
</div>

<br>

<h3>DHCP Server Setup</h3>
<br>
<div>
Navigate to server dashboard once more and click on add roles and features follow the prompts and  select DHCP Server, add features, next for features and DHCP Server Confirmation then install.
</div>
<br>
<div>
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc41.JPG"  height=400>
</div>
<br>
<div>
 Navigate to tools then DHCP expand  the domain arrow, right click on IPv4 then "New Scope".
</div>
<div>
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc42.JPG"  height=350>
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc43.JPG"  height=350>
</div>

<br>

<br>
<h4>Scope Configuration</h4>
<div>
In <strong>Scope name input IP range</strong> and on the "Router Default Gateway" window enter the domain contoller IP address.
Select next for Domain Name and DNS Servers, WINS Servers and Activate Scope. 
</div>
<div>
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc44.JPG"  width=300>
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc45.JPG"  width=300>
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc46.JPG"  width=300>
</div>
<br>
<br>
<div>
 Lease duration can be set here which is related to the length of time an address can be <i>held</i> in use. A coffee shop may want to have a much short lease if free wifi is provided to guests.
</div>
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
Right click on the domain, refresh, authorize and refresh again.
</div>
<br>
 <div>
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc55.JPG"  width=200>
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc56.JPG"  width=300>
<img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/DC/dc57.JPG"  height=300>
</div>
 
<br>
<br>

 
 <div>
In <a href="https://github.com/narvee09/Client-Creation-VM-/blob/main/README.md" >this</a> next step we will set up a virual client to use the internal network and add it to the newly created domain.
</div>
<br>
<div>
 <img src="https://github.com/narvee09/IT-images/blob/main/Basic%20IT/Client/dc58.JPG" >  
  </div>
<br>
<br>
<br>
