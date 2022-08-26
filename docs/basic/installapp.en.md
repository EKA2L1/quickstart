# Install apps

EKA2L1 supported these installation methods:

- **SIS/SISX:** Universally across all platform (desktop, Android).
- **JAR:** A limited subset of J2ME apps/games can be installed and ran on the *Desktop* version of the emulator. For more information, see the [**J2ME**](/{{ posts_root }}/j2me) page.
- **N-Gage game card dump:** Game card dump that has been patched to be independent from MMC information can be installed into emulator storage. Raw game card dump should be load directly through Aaru dump (planned support).

## SIS/SISX

!!! note

	Please note that it's very recommended to install a device first and change to the target device you want to install the SIS on, before proceeding this steps.

	- This is crucial for packages like N-Gage 2.0, where it depends on the current active device to extract suitable game configurations file.

### For PC

Go to *File/Install/Package* and choose the SIS you want to install.

### For Android

Press on the **big green ``+`` button** on the bottom right of the main (app list) screen and choose the SIS you want to install.

## JAR

On desktop version of the emulator, click on the *File* menu, and navigate to *Install/JAR*.

!!! note
	The emulator currently only supported a limited subset of J2ME apps (mostly MIDP-1.0) and only able to install them on specific active device. Trying to install unsupported JAR or install supported JAR on unsupported devices will result in an error dialog.
	
	For more information, visit the [**J2ME**](/j2me) page.

## N-Gage game card dump

To install N-Gage game card as a game, on desktop version, navigte to *File/Install/N-Gage card game*.

Please choose the game folder that contains the **System** folder. This is very important!

<figure markdown>
  ![N-Gage game card dialog](/{{ assets_root }}/install_apps/install_ngage_card_game_folder.png)
  <figcaption>N-Gage game card dialog</figcaption>
</figure>

The above image shows the content of the folder that you should choose to install. Note that the **System** folder is present in this image.

On all operating systems, please note that the name field must not be the **System**, else the **System** folder will be choosen to be installed, resulting in a failure. If you accidentally select the **System** folder, try to press **Back button** and then open the correct folder again.

<figure markdown>
  ![N-Gage game card dialog](/{{ assets_root }}/install_apps/install_ngage_card_game_folder_wrong.png)
  <figcaption>Wrong folder choosen! Note the <b>System</b> folder in the red-circled folder name field</figcaption>
</figure>