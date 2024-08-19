
<p align="center"></p>

![image](https://github.com/user-attachments/assets/8f6c3b05-cf00-470e-8d8c-82ef39916863)


<h1>VPN -- Installation and Setup</h1>
This tutorial outlines how to install and setup a virtual private network.<br />




<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Proton VPN

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)



<h2>Introduction to VPNs</h2>

<p>
Whether for personal privacy or corporate security, VPNs play a crucial role in maintaining a secure and private internet experience.By routing your internet traffic through a VPN server, a VPN hides your IP address and ensures that your online activities remain private and protected from eavesdroppers. In a corporate setting, VPNs are essential for allowing employees to securely access company resources from remote locations. This enables seamless work from home, secure access to internal networks, and protection of sensitive data during transit. VPNs utilize a process called tunneling, which involves encapsulating and encrypting data packets as they travel across the internet. This creates a "tunnel" through which data can pass securely, preventing unauthorized access and ensuring data integrity. 
</p>

<br />

<h2>Installation</h2>


<p>
For this tutorial we are going to make use of the VPN service Proton VPN which offers a free subscription option for users while allowing us to gain a good baseline for how a VPN works. 
</p>
<br />
<p>
  To get started I created a virtual machine in Azure, for an exercise like this I typically choose a machine that makes use of a standard two virtual CPUs as one is not always enough for my computing needs. For the image option, the Windows 10 option will suffice for what I am going to need for this tutorial. I chose the location East US as this will provide a location that is not exactly where I am from (the Midwest). Once the Virtual machine is created we can make use of Remote Desktop to log into our virtual machine and begin the installation process. 
</p>

![image](https://github.com/user-attachments/assets/25e4686b-9f4e-41db-a209-98ee3f8f5aab)

<p>
After we log into our newly created VM using Remote Desktop Connection, we can make use of the website https://whatismyipaddress.com/ to view the public IP address of our virtual machine. A public IP address is a unique identifier assigned to your device by your internet service provider (ISP) that allows it to communicate with other devices over the internet. This address is visible to websites and services you interact with, revealing information about your location and internet service provider.

When using a VPN, your PC's public IP address appears as the IP address of the VPN server rather than your actual IP address. This masking process enhances your privacy and security by hiding your real location and making your online activities less traceable. The VPN effectively routes your internet traffic through its own servers, replacing your public IP address with that of the VPN server, thus providing anonymity and protecting your data. Note that because I chose the East US option for a location when creating my VM, its location is displayed as the Washington D.C. metro area with an IP address of 172.203.131.19. 
</p>
<br />

![ip_from_East_US](https://github.com/user-attachments/assets/b4879628-eb51-4b93-a154-39edf288e548)

<br />

<p>
  Now that we have our virtual machine set up and we have made a note of its location and IP address let's install our VPN service. For this tutorial I will be utilizing a free subscription of the Proton VPN service which can be found at their website. After clicking on the link to Proton's website navigate to and click on the "Get Proton VPN Free" button on the homepage. You will be directed to a pricing page. Scroll down to find the free plan option and click on the "Get Free" button. You will be prompted to create a Proton account. Enter your desired username, email address, and password. Proton VPN will send a verification email to the address you provided. Open the email and click on the verification link to activate your account. After verifying your account, you will be directed to the download page. Select the appropriate version for your operating system (Windows, macOS, Linux, Android, or iOS) and download the installer. Remember, the machine I created is a Windows 10 machine.  
</p>
<p>
  Run the installer and follow the on-screen instructions to install the Proton VPN client on your device. Once installed, launch the client. Open the Proton VPN application and log in using the credentials you created during the sign-up process.
</p>

<br />

![Windows_vpn_download](https://github.com/user-attachments/assets/721862fd-91f8-4f36-92a0-84b8dc397278)
<br />

![proton_install](https://github.com/user-attachments/assets/95343a79-d35b-4569-ae02-235589753c8f)

<br />

<h2>Setup</h2>

<p>
  After logging in, you will see a list of available servers. Select a server from the free plan options and click "Connect". Please note that with the free subscription there may not be any options available as in this case. If this occurs you may simply click on the "Quick Connect" button and Proton will provide you with their next available server. Once connected, your internet traffic will be routed through the Proton VPN server, masking your real IP address and encrypting your data.
</p>

<br />

![VPN_before_connection](https://github.com/user-attachments/assets/8a094e2e-d14a-4194-a98d-fa87bfec6252)
<br />

<p>
  Now that we have connected to a Proton server and see what the result is. As we can see in the top image below once I connected to the Proton server the first server that is available is one in Romania. Also note that our public IP address has changed. What this means is since we have connected to the Romania server Proton has established a tunnel btween our machine and the Proton server. Essentially, our web traffic will be routed through this server in Romania while we are connected instead of routing straight to its destination, concealing our actual IP and sensitive data. Note in the image below our IP address has changed.
</p>
<br />

![proton_vpnserver_romainia](https://github.com/user-attachments/assets/5ce07d70-7e9b-4e39-93f8-1096ca7d6fb7)

<br />

<p>
  For fun let's take a look at Google and see what effect this connection has on our browser. If we go to the Google home site, what do you think we will find. Interestingly enough we see that Google is now in Romanian instead of English as it would be if we were logged in from a server inside the United States. This is because since we are connected to a server that is located within the country of Romania it is as if we are browsing from that VPN server in Romania and Google will act as such. 
</p>

<br />

![google_romania](https://github.com/user-attachments/assets/71e805d2-c39e-4c22-86f3-2233efb7dfc5)
