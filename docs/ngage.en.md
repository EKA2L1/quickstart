# N-Gage

**N-Gage** is a 2003 game console by **Nokia**, powered by the Series 60 version 1. At the core, it's just a phone running Symbian OS with some exclusive functionalities. 

This page is intended to laid out the road of getting the emulator running, for those who exclusively want to try out this phone.

## Obtaining the N-Gage system ROM

For those who are used to **Nitendo/PlayStation game consoles,** consider this ROM as a BIOS. The emulator relies on this to run **N-Gage** games.

If you have an **N-Gage**, you can dump this ROM yourself. Here is the method:

1. Compile and obtain the Symbian Dumper EXE from [**Rusty Starship**](https://gitlab.com/tambre/rusty_starship/-/tree/master/symbian_dumper) by *Raul Tambre*

2. Copy the EXE onto your MMC card.

3. Insert the MMC card into the N-Gage.

4. Use a File Explorer like **FE Explore** or **X-plore** and copy the EXE to somewhere in the C: drive

5. Run the copied EXE. The ROM, BOOT and ROOT should be dumped in the MMC card.

6. Access the MMC card on computer and obtain only the ROM file. Rename it to *SYM.ROM*

## Install N-Gage device from ROM

Using the *ROM* obtained, install the device using the [*ROM + RPKG method*](/basic/installdevice/#rom-rpkg-method).

!!! note
	Using this method, you just need to browse to the ROM. For ease, name the ROM as *SYM.ROM*. If it asked you for RPKG, contact the developer for support.
	
## Install N-Gage games

**N-Gage** game files sit on MMC card, unprotected in **FAT32** filesystem. There is usually two types of game version you might have access to:

- **Patched games:** These games are patched by hacker to bypass DRM. Most of the times they will be very thoughtful to disable multiplayer and *N-Gage Arena* too, to encourage you to buy the game after trying out the patch.

- **DRM-ed game:** These games rely on the presence of a physical MMC card to check for its MMC-ID, to see if the game is contained on a copied-card or not sit on a MMC card at all. The executable of the game is obsfucated so that reverse engineering is harder. Most of N-Gage libraries do this.

For **Patched games**, see install instructions [here](/basic/installapp/#n-gage-game-card-dump).

For **DRM-ed game**, in the future, planned **AAru** support should simplify the play process. But for now, there is no way to install them. See the next section on how to play them.

## Play DRM-ed N-Gage games

**EKA2L1** provides some method to simulate the MMC environment. To play authenticate DRM-protected games on the emulator:

1. Edit the *MMC-ID* to have the same value as on a real *MMC-ID card* contains the game you want to play. There are some written applications that can do this extraction. Please contact the emulator developers on interest.

	+ On **Android**, open the upper-right menu, and go to **Settings/System**. Edit the MMC ID setting here.

	+ On **Desktop**, open the config.yml, which is in your current running directory (on **Windows**, it should be in the same folder as the *EXE*). Edit or add the MMC-ID key-value pair. Here is an example:

		```yaml
			mmc-id: 00000000-00000000-00000000-00000000
		```
		
2. Mount the game folder. The root of the game folder should contains a **System** folder.

	+ On **Android**, open the upper-right menu, and choose **Mount MMC/SD card**
	
	+ On **Desktop**, go to *File/Mount game card dump/Folder*, and browse to the folder you want to mount.
		
		* Note that the **Folder** field shows the name of the current folder. If the field shows **System**, it is not valid. But the emulator will put out a warning for you if that happens.

<figure markdown>
  ![N-Gage game card dialog](/assets/ngage/mount_example.png)
  <figcaption>Mount game card dump window</figcaption>
</figure>

	
!!! note
	Due to scoped storage change on Android, running the mounted game will take a long time to startup and might freeze in the way.

		
The game should appear in the application list if there's no problem. You can click on the game icon to play.