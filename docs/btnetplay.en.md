# Bluetooth netplay

**EKA2L1** can route local bluetooth network to either *LAN* or *Internet*. Currently, this is mainly used for bridiging N-Gage local bluetooth multiplayer. 

This page will instruct you on how to configure and setup multiplayer on EKA2L1 through 2 main modes: *LAN* and *Server*. *Direct IPs*  will be mentioned later after the two modes.

## Open configuration window

In this window/view, you can choose *Bluetooth netplay mode*, and edit some more configuration variables that will be relevant later on.

### Android

Navigate to the top-right three dots button, touch and select **Settings**. In **Settings**, choose **Bluetooth Netplay**.

### Desktop

In the main window, navigate to *Bluetooth/Netplay/Configure* The configure window appears.

## Configure for LAN

### Mechanism

*LAN* mode will allow all players in the same local network, or in more readable language: people in the same house, in the same classroom, connect to the same Internet router, etc...

*LAN* mode will only use **IPv4** to broadcast message across all devices on network, asking if any devices that is running on **EKA2L1** want to connct to the current device. Other devices that is running **EKA2L1** will hear the request, check the secert passphrase, and if it matches, they will respond back with an accept message to the one sending the broadcast.

### Steps

In the configuration window, choose *LAN* as the bluetooth netplay mode.

To allow only some specific people to be able to discover and play with you, set yourself a **Password**. People with the same *Password* can see each others, and those that does not have your password will not see you.

Send the password to people you want to play with, ask them to copy the password to the **Password** field/preference in the configuration window.

After that, restart the emulator for the change to be effective. On Android, please exit and relaunch the emulator again.

## Configure for Server

### Mechanism

**EKA2L1** instances will login and register itself to the server. When the other instances ask for a scan to find other players, the server will reply back with IPs of people who have the same password as the one who is asking. After that, emulator instances will do *P2P* with each others.

By default, the server address is [btnetplay.12z1.com](http://btnetplay.12z1.com). But since it's developer-powered server that requires money to run, and there's no stable fund, you should consider changing to a community-powered server. Else you can [donate](/donation) to the developers (server cost for now is 5$ a month) :)

### Steps

In the configuration window, choose *Server* as the bluetooth netplay mode.

#### Configure the network router

To make your emulator instance visible to other emulator instances:

- If you use *IPv4*, check if your router has UPnP enabled.
	* If yes, toggle the **Enable UPnP** option to *On*.
	* If no, then you need to setup manual port forwarding (also called port mapping). Go to the router control panel, and enable port forwarding for your computer, for these ports:
		+ Port 35689 *(UDP or TCP/UDP)*
		+ Port 15000 - 15100 *(TCP or TCP/UDP)*

<figure markdown>
  ![Example port forward rules](/{{ {{ assets_root }}_root }}/btnetplay/example_port_forward_rules.png)
  <figcaption>Example port forward/mapping rules for EKA2L1 on a Huawei router</figcaption>
</figure>

- If you use *IPv6*:
	* Check if your router has IPv6 firewall enabled. If the answer is yes, exclude these ports from the firewall:
		+ Port 35689 *(UDP or TCP/UDP)*
		+ Port 15000 - 15100 *(TCP or TCP/UDP)*
		
	* Turning off the firewall completely is not recommended.
	

!!! note
	For the port range from 15000 to 15100, these depends on the *Port offset* value you set. *Port offset* value should not be changed by normal users, unless you know what it does (the same functionality as in **PPSSPP**)
  
	For more specific instructions on how to do manual port forwarding or enable UPnP, consider searching the internet for your specific-router or network operators. 
	
!!! note
	Try to avoid using mobile network like 3G/4G. They don't have control panel to allow port-forwarding or add IPv6 firewall exception. If some mobile operators have control panel then you can try.
	
#### Configure inside the emulator

In the configuration window, choose *Server* as the bluetooth netplay mode.

<figure markdown>
  ![List of configurations in Server mode on Desktop version](/{{ assets_root }}/btnetplay/configure_window_desktop.png)
  <figcaption>List of configurations in Server mode on Desktop version</figcaption>
</figure>


- To allow only some specific people to be able to discover and play with you, set yourself a **Password**. People with the same *Password* can see each others, and those that does not have your password will not see you. 
  Send the password to people you want to play with, ask them to copy the password to the **Password** field/preference in the configuration window.

- You can change to another server by editing the *Server address* configuration. By default the server is [btnetplay.12z1.com](http://btnetplay.12z1.com).

After that, restart the emulator for the change to be effective. On Android, please exit and relaunch the emulator again.

## Configure for Direct IPs

### Mechanism

Direct IPs is a more secertive mode. Each players add IPs of other players you want to play with. Port forwarding or firewall excluding methods, like in *Server mode*, are required.

### Steps

1. Visit server mode's [Configure the network router](##configure-the-network-router) section and follow the instructions
2. Visit bluetooth netplay configuration window, switch the mode to *Direct IPs*
3. On:
    - **Desktop**: Click on the big **Open friends' IP editor** button, or visit *Bluetooth/Netplay/Friends' IP editor*
    - **Android**: Click on the **Direct IPs manager** preference in the configuration window
4. Add/remove your friend IPs. Then relaunch the emulator. On Android, you should exit and reopen the emulator again.

## Changing in-game name

To change the in-game name in local bluetooth mode, you need to change the device's Bluetooth name.

- **Android:** Click on the three dots, then go to *Settings/System*. Click on the **Friendly device name** to change the current name.
- **Windows:** Go to *File/Preferences/System*, and look for a **Friendly device name** input field. You can change the device name in here, and it will be auto-saved.

## IPv6 play warnings

If you use IPv6 to play online, there will be moment where the temporary IPv6 got released and a new one replaced. When you encounter connection failure, try to reconnect your wifi/internet. 

Additionally, if you want to play for a while without interruption, try increase the **IPv6 lease time**. This is the time interval between two IPv6 temporary address replacement. Usually it will be 24 hour.