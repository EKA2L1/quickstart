# Install a device

First, build or [download](https://12z1.com/download/) EKA2L1 for the target platform you want to run the emulator on.

## Installation method to choose

Depends on what device you want to use, the installation method differs. There are two main method: using *ROM+RPKG* and using *firmware*

### ROM + RPKG method

Devices that run on S60v1 and S60v2 like Nokia N-Gage, Nokia N70, etc... should use this method. S60v1 devices should only need the ROM for this installation method.

### Firmware method

S60v3 devices and higher (S60v5, S^3, Belle, ...). These firmware are distributed widely, so they are easier to obtain then ROM+RPKG.

## Required files

### For S60v1 and S60v2 devices (N-Gage, N70, etc...)
- The ROM of the device
- The RPKG file
	- This is a custom container of the Z drive (the same device as where the ROM was dumped). See [Dumping section on Wiki](https://github.com/EKA2L1/EKA2L1/wiki/Dumping-the-ROM-and-ROFS) to find out how to dump it.
	- The file may only be needed with S60v2 devices. The emulator will asks for it during the installation if it detects only ROM alone is not enough.
	
### For S60v3 and upper (5320, 5800, N97, N-Gage 2.0 compatible devices, etc...)

There are two options that you can choose:

- ROM and RPKG of the device (same as S60v1 and S60v2)
- A firmware of the target device. **Make sure** the firmware you got also has a VPL file along with it.

At the moment, for users only interested in N-Gage 2.0, Nokia 5320 device is the most maintained and supported device for this purpose.


## Install steps for PC (Windows, MacOS, Linux)

Launch the emulator with command line option **--help** if you want to interact through command lines and need list of commands.


To install a new device, please go to *File/Install/Device*, or follow the dialog that ask you to install a device appears on first run of the emulator.


<figure markdown>
  ![The device install dialog](/{{ assets_root }}/setup/device_dialog.png)
  <figcaption>The device install dialog</figcaption>
</figure>

### Install by ROM and RPKG

Choose the **Device dump** installation method in the combo-box, and click the first *Browse* to select the ROM you have prepared. If the emulator detects that the ROM is not enough alone, a RPKG file browser will appear.

<figure markdown>
  ![The RPKG field appears with 5320 ROM selected](/{{ assets_root }}/setup/device_dialog_with_rpkg.png)
  <figcaption>The RPKG field appears with 5320 ROM selected</figcaption>
</figure>

After you have filled all the paths, press **Install**. If you want to cancel the installation, you can press the **Cancel** button next to **Install**.

Then wait for the progress bar to be completed and a success dialog to pop up.

### Install by firmware

Choose the **Firmware (VPL)** installation method in the combo-box. The ROM label will be renamed to VPL, and then you can click **Browse** to choose the VPL that came along with the firmware.

<figure markdown>
  ![The VPL install dialog](/{{ assets_root }}/setup/device_dialog_vpl.png)
  <figcaption>The VPL install dialog</figcaption>
</figure>

A dialog should appear request you to choose a firmware variant. This usually is related to region of the device and its style (black or red), and should not matter much on the emulator.

After that is the same process as **Device dump**.

<figure markdown>
  ![Installation success dialog](/{{ assets_root }}/setup/device_dialog_install_success.png)
  <figcaption>Installation success dialog</figcaption>
</figure>

If you meets the dialog above, then that means you are done installing a device.

## Install steps for Android

First run of the emulator should show you a dialog that requests you to install a device. Press the *Install* dialog, to quickly get to the **Device manager**.

<figure markdown>
  ![The request install dialog](/{{ assets_root }}/setup/android_device_install_request.jpg)
  <figcaption>The request install dialog</figcaption>
</figure>

If the dialog does not appear, press the three dots at the top right of your screen, and select **Devices**.

<figure markdown>
  ![Android devices screen](/{{ assets_root }}/setup/android_devices_activity.jpg)
  <figcaption>Android devices screen</figcaption>
</figure>

In this screen:

  - If you have prepared a ROM (and RPKG if needed), choose the **Device dump** installation method, and press on the *ROM* button to select the ROM you have prepared. If the emulator detects that the ROM is not enough alone, a RPKG file browser will appear.

  - If you have prepared a firmware, choose the **Firmware (VPL)** installation method. The ROM button will be renamed to VPL, and then you can click on the *VPL* button to choose the VPL that came along with the firmware.

<figure markdown>
  ![All file paths are filled](/{{ assets_root }}/setup/android_device_all_choosen.jpg)
  <figcaption>All file paths are filled</figcaption>
</figure>


After you have filled all the paths, press *Install*. You can only cancel this operation by exiting the app, and no need further action until a small toast notification tells you that the installation is success or encounters failures.

<figure markdown>
  ![New device appeared after installation](/{{ assets_root }}/setup/android_new_device_appears.jpg)
  <figcaption>New device appeared after installation</figcaption>
</figure>


!!! note
	If you have encountered failure during the installation, please visit the [Discord](https://discord.gg/5Bm5SJ9) server to receive support.
