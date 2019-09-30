## Making a private cloud with Virtual Box  
In this lab we are going to learn how to install, configure and understand how the cloud technology work. I'm usingn Win10 in the host computer and Ubuntu for Virtual machine. For virtualization,in this example, i use Virtual Box, can use VMware as well(steps almost same). You can donwload all the above software in the links below:     
[Ubuntu](https://ubuntu.com/download/desktop)  
[Virtual Box](https://www.virtualbox.org/wiki/Downloads)  
[Virtual Box Extension](https://download.virtualbox.org/virtualbox/ )  
**1) First do the installation of Virtual Box and install Ubuntu on it. I will not describe in details these steps, lots of materials out there, one of them [here](https://www.lifewire.com/run-ubuntu-within-windows-virtualbox-2202098)**
**2) Set the path to your virtual machine by pressing** **Ctrl + g**     
![](/img/General.png)  
**3)Create a Virtual Networks within Virtual Machine(->Host Network Manager)**    
I've created Adapter #2 and set the IPv4 to :**192.168.100.1**  
When you apply the changes, you can check from your host in `cmd`  
  ![](/img/NC.png)  
  ![](/img/ipconfig.png)   
  
After that run your Virtual Machine, and hit the CTRL + ALT + T buttons to open up terminal, in the terminal first type this command    
`sudo apt update && sudo apt upgrade -y`
after updating your Ubuntu, can start configuring the **NC**.   
In terminal, type in `sudo nmtui` 
![](/img/nmtui.png)    
In activate connection choose the second NC that we have created previously and activate it. Now we are able to ping our VM from the host:    
  ![](/img/ping_vm.png)    
  And vice versa  
  ![](/img/ping_host.png)      
  **4) Install the second Virtual Machine**  
  Clone the existed Ubuntu VM:  
  1. Right click on VM, press Clone  
  ![](/img/clone.png)    
  2. Choose Generate new MAC addresses for all network adapters  
  ![](/img/clone_2.png)    
  3. Choose Linked clone and start cloning  
  ![](/img/clone_1.png)     
  4. Create the new NC for the clone as in step3 but change it's IP address, for example i've set it to: 192.168.100.11  
  **5) Restart the VM  
  **6) Now we are able to connect to our VM, but first we need to install the Virtaul Box Extension that we've downloaded in the beginign.  
  Press **CTRL + g** go to **Extensions** and add that downloaded package and finish the installiation. All VMs need to be turned off !  
  Set the port # for the first VM, and use the Remote Desktop Connection App to connect (app included in Win10)   
  ![](/img/ports.png)    
     
  ![](/img/result.png)  
  
  
  

