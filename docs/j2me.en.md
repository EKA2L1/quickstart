# J2ME

Most phones running **Symbian** has support for playing J2ME apps/games to some extend, starting from Series 60 version 1. 

The J2ME runtime and J2ME player is included in the ROM, and with each iteration of Symbian, the J2ME runner evolved and sometime is completely different from previous J2ME runner on older **Symbian** version.

!!! note
	The support of running J2ME applications on EKA2L1 comes off as just-for-fun. If you want to play J2ME games with more customization, check out **KEmulator** on desktop, or **[J2ME-Loader](/j2me)** on Android
	
## Supported emulated devices

EKA2L1 tries to utilise the J2ME runners on ROM of installed devices. Currently, devices that ran these OS versions can be used to run J2ME applications on emulator:

- **Series 60 version 1** (S60v1)

Due to the complexity of the J2ME system, OS version starting from Series 60 version 2 (S60v2) has not been supported. The priority of working on the support is low.

## Supported MIDP versions

The emulator will only accept J2ME with the following MIDP versions *(declared in MANIFEST.MF):*

- **MIDP 1.0**

This is due to the fact that S60v1 J2ME runner only support MIDP 1.0.

## Install and play JARs

**1.** Make sure you have switched to an S60v1 device.

**2.** Click on the **File** menu, and then navigate to **Install/JAR**. Click and choose JAR file you want to install.

![desc](/assets/j2me/j2me_install_menu_and_device.png)

For example, in the image above, you can see N-Gage device being choosen in the right-hand combo box. And **File/Install/JAR** menu is displayed.

- A dialog will appear after telling you if the installation is success or encountered error. The error message should be straight forward to understand. 
- If you encountered the error that the JAR can not be installed on the current device, check if your current active device *(see the device combobox next to the search bar, at the upper of the app grid)* is a **S60v1** device or not

**3.** After the installation finished, next to the device list combo-box next to the app search bar, you will see a button.

- If its name is **Symbian**, that means the app list is in native Symbian mode. It will only display native applications and games, that is **commonly installed** through the **SIS/SISX** format.
- If its name is **J2ME**, the app list grid will switch to J2ME mode, which will display only J2ME game.

<figure markdown>
  ![App list in Symbian mode](/assets/j2me/j2me_native_app_list.png)
  <figcaption>App list in Symbian mode, which displays native game.</figcaption>
</figure>

The image above shows the native application list in action. The button being circled and arrow-pointed is naming the current application list mode.

To switch to **J2ME mode**, press on that same button.

<figure markdown>
  ![App list in J2ME mode](/assets/j2me/j2me_app_list.png)
  <figcaption>The app list is now in J2ME mode. Native applications are not in display anymore.</figcaption>
</figure>

To switch back to **Symbian mode**, press on that same button again.

Toggle the button will switch between the two modes.

## FAQs

**Q:** I have installed the JARs successfully, but when I come back and launch them, the emulator says *Can't open the application!*. How to fix it?

**A:** You should first check if you are using the correct device to play those J2ME games. For now, only **S60v1** devices are supported, so make sure the current device is S60v1.

&nbsp;

**Q:** The game is MIDP-1.0 but they still does not work on emulator!

**A:** Some games depend on different vendor's APIs or simply just missing some kind of API that **S60v1 J2ME** runner does not provide. However, if you are confident that it runs on the original phone, you can raise an issues with the developers.