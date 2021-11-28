## Ubuntu on a 9 years old Chromebook

[< back](https://codethepast.github.io/)

In **2013**, when I was working in the US, I bought a **Chromebook Acer C720P-6666** (with touchscreen) that worked well for long time. It was not my main machine, but was perfect for some activities and handy for the small size.

Unfortunately, at the end of 2019 Google decided to stop supporting my model (the current policy is to support Chromebook models up to 6.5 years from their production date, more details [here](https://www.theguardian.com/technology/askjack/2019/sep/12/can-i-still-use-my-chromebook-now-it-is-no-longer-supported)). After some time I started experiencing software issues and glitches, and of course not having OS updates means to face serious security risks. Therefore, I decided to challenge myseft in installing **another OS on this laptop**, an Ubuntu distro of Linux, giving a try to this 9 years old laptop to continue journey together. Together with this OS upgrade I also wanted to provide more disk memory. 

In this post I describe and comment step by step the entire process and the results of this upgrades!

## The Acer C720P

Nowadays, it is not easy to find online the full specs about the Acer C720P, but [here](https://www.laptopmag.com/reviews/laptops/acer-chromebook-c720p) you have the main information. To get an extended review of the Acer C720P by *Brad Linder* you can read this [post](https://liliputing.com/2014/03/acer-c720p-touchscreen-chromebook-review.html).
For your documentation I provide here the top- and bottomview of the laptop before opening it.

![Top view](https://codethepast.github.io/UbuntuOnChromebook/UbuntuOnChrome10.jpg)

![Bottom view](https://codethepast.github.io/UbuntuOnChromebook/UbuntuOnChrome11.jpg)

And here the picture of the sticker with the product's detail (yes, it was made in December 2013!).

![Laptop detail](https://codethepast.github.io/UbuntuOnChromebook/UbuntuOnChrome12.jpg)


## Back-up your data and create a recovery for the Chrome OS (ust in case...)

### You need:
1. a drive to backup your documents;
2. a SD card or USB pendrive with at least 2 GB, to save a recovery of ChromeOS - in case you will want to reinstall the original OS.
3. (optional, but sometimes needed) an additional computer, Linux or Windows. 

Please consider backing up your documents before starting this operation as they will not be retained during the operation (or better, they will remain in your old SSD, but not authomatically copied to the new one).

Furthermore, you may want to cerate a recovery of your ChromeOS. Until mid 2019 you could download the OS image from your chromebook by typing chrome://imageburner into the address bar of the browser. Nowadays, from your chromebook or from a Windows machines you need instal an extension for the chrome browser, that is the [Chromebook Recovery Utility](https://chrome.google.com/webstore/detail/chromebook-recovery-utili/pocpnlppkickgojjlmhdmidojbmbodfm) that you can download from the Chrome Web Store. Users are not super happy about how the extension works and many issues and delays are reported for this procedure. 

From a **Linux computer** you can more easily download the Recovery Tool [here](https://dl.google.com/dl/edgedl/chromeos/recovery/linux_recovery.sh), then change the script permissions to allow execution with the following command: 
```
$ sudo chmod 755 linux_recovery.sh
```
Run the script with root privileges with the following command: 
```
$ sudo bash linux_recovery.sh
```
Follow the on-screen instructions to create recovery media. You will be asked to enter your device's HD model number (or HWID). How to find your HD model number? type chrome://system in the chrome browser and search for the HWID (mine model number for example is PEPPY E6A-O3G-A9V) You will have to insert the recovery SD card or USB drive (that will be reformatted authomaticaly). This may teake several minutes.


## Hardware upgrade

Differently from other models, the Acer C720P has the touchscreen and only 2GB of RAM, that unfortunately cannot be expanded. As for the disk, the laptop originally has a 32GB SSD, that is enough for a web based chromebook, but might be tight for a complete Ubuntu system. 
**NOTE: You will invalidate your warranty when you open your laptop and change the SSD. You’re on your own if you break anything.**

### You need:
1. a small cross-head screwdriver;
2. a new, larger SSD. 64GB and 128GB have been tested and work well. Please note that for this model the SSD is a M.2 SATA 2242 form factor type.

There are several online resources that show how easy is to open the laptop and change the original SSD with a new one:
- Here a [video](https://www.youtube.com/watch?v=AZa5kWBfbWM) by *unlokia* showing how to properly open this laptop model and how to find the different hardware components.
- Here a [video](https://www.youtube.com/watch?v=LrrL2Qy2PGI) by *Isaac* mounting a 64GB SSD. 
- Here a [video](https://www.youtube.com/watch?v=c9rKQVtEjNc) by *Daniel Berry* mounting a 64GB SSD.
- Here a [blogpost](https://www.umpcportal.com/2014/01/how-to-upgrade-the-acer-c720-chromebook-with-an-m-2-sata-from-mydigitalsdd/) and a [video](https://www.youtube.com/watch?v=-jOHHyJMgWk) by *Steve Paine* mounting a 128GB SSD.

In order to open the laptop you need to turn it off and to remove 13 screws placed on the bottom side (Note: one of the screw is hidden under the round "seal" sticker - If you mind, once you’ve broken that sticker you don’t have a warranty anymore!). Then gently insert a thin plastic tool/point or a card in the gap between the bottom side and the keyboard side to completely free the bottom side (better to start from the hinges, anyway I suggest to watch the linked videos). 

I provide here a view of the opened laptop.

![Inside the laptop](https://codethepast.github.io/UbuntuOnChromebook/UbuntuOnChrome13.jpg)

To get an idea of the architecture of the Acer C720 (the model without touchscreen and with 4GB of RAM) you can see the following image, taken from [here](https://www.chromium.org/chromium-os/developer-information-for-chrome-os-devices/acer-c720-chromebook).

![C720 hardware architecture](https://samsclass.info/128/proj/c720-chromebook-annotated-innards.png)

*For the numbers: 1. CPU. 2. RAM (here 4GB, mine has only 2GB). 3. System firmware. 8MB SPI Flash. 4. NGFF (M.2) SSD. 5. Battery enable switch. 6. Battery enable screw. 7. Write-protect screw. 8. Servo debug header. 9. NGFF (M.2) WWAN connector.*

This is the detail of the original 32GB SSD in place.

![The original SSD in place](https://codethepast.github.io/UbuntuOnChromebook/UbuntuOnChrome14.jpg)

It is very easy to change the SSD: just remove the single screw, carefully slide the SSD out, gently put the new SSD in the slot (paying attention to respect the direction of the card and do not touch the contacts as the skin acids are dangerous for the electronic contacts).
Push the bottom side back in its position (better to start from the rear) and screw back all the 13 screws.

You can now turn the Chromebook on. You will see an error message. If you insert the recovery SD card or USB drive the recovery will start automatically. Just wait for the install to complete and you’re done. If the restore fails you will have to doublecheck (and in case download again) the recovery drive again.


## Ubuntu side-by-side ChromeOS (with Crouton)

Instead of erasing your ChromeOS and installing a linux based OS you can easily run a Debian-based Linux side-by-side ChromeOs. To do that we can run a script called **Crouton** which lets you uickly switch from one environment to the other just by pressing a few keyboard buttons.
Note: there is also another project [**ChrUbuntu**](https://github.com/iantrich/ChrUbuntu-Guides/blob/8d7e5ed1495c9f10fd6b542c960f53fe101e35b9/Guides/Installing%20ChrUbuntu.md) that allows to install Ubuntu on the internal storage (or on a usb drive) and run a dualboot with ChromeOS; for this see the [blogpost](https://www.linux.com/topic/desktop/how-install-linux-acer-c720-chromebook/) by *Jack Wallen*.

With Crouton, your Linux OS is sharing the kernel with ChromeOS. That means all of the hardware including the WiFi and touchscreen will work perfectly in both the OS. 

To run Crouton you just need to [enter developer mode](https://www.chromium.org/chromium-os/developer-information-for-chrome-os-devices/acer-c720-chromebook) on the Chromebook by holding the Esc and Refresh keys and tapping the power button. Then follow the instructions at the [Crouton GitHub page](https://github.com/dnschneid/crouton) to download and install the Linux OS distribution of your choice.

For a discussion of Crouton on Chromebook you can see this [post](https://liliputing.com/2014/03/acer-c720p-touchscreen-chromebook-review.html) and the [video](https://www.youtube.com/watch?v=bYGAr_OBBoo) by *Brad Linder*.

First, you have to download the latest release from [here](https://goo.gl/fd3zc). 
Then, open a shell in your Chromebook by pressing Ctrl + Alt + T; type "shell" and hit enter. Execute the installer executable with 
```
$ sudo install -Dt /usr/local/bin -m 755 ~/Downloads/crouton
```
To see the help text launch it with 
```
$ sudo crouton
```
To see what Linux distros are available to Crouton, you can type:
```
$ crouton -r list
```
For example, to run the ligth weight Xubuntu distribution (Xfce, Ubuntu 16.04 LTS) you can type:
```
$ sudo crouton -t xfce
```
Once the installation is over you can run Xfce and ump into the desktop environment by typing:
```
$ sudo enter-chroot startxfce4
```
or with the shortcut, 
```
$ sudo startxfce4
```
Here you will find all the softawares shipped with the distro or install more (through the Ubuntu Software Center). Online there are a few resources related to arguments you can add to the installing command string or about installing more recent Ubuntu releases (ie. Focal Fossa see [here](https://github.com/dnschneid/crouton/issues/4265) or [here](https://bleepcoder.com/crouton/602619482/focal-fossa)).

If you want to switch to the ChromeOS just press Ctrl + Alt + Shift + Back, while pressing Ctrl + Alt + Shift + Forward will bring you to your running Linux distribution. To exit it, just log out of Xfce, or type "exit in the Chrome terminal.

Remember that when you exit the developer mode the Chromebook will wipe all your data and return to its factory settings.

In the Crouton GitHub page there are more details for more advanced operations. Only remember that if you want to delete Crouton you have to type 
```
$ sudo edit-chroot -d evilchroot
```
or the shortcut: 
```
$ sudo delete-chroot evilchroot
```


## Remove ChromeOS and install Ubuntu

If you don't want to use ChromeOS at all, you can replace the OS entirely with Ubuntu (or another operating system). It is a bit more tricky, but doable.
**Note that the touch screeen might not function properly (or at all)** or that you have to jump through some hoops in order to get it work.

There are a feww online resources that can help you in the process:
- Here a extended [blogpost](https://samsclass.info/128/proj/chromebooks3.htm) by *Sam Bowne* explaining the all process of installation of Ubuntu 15.04.
- Here a [blogpost](https://dbtechreviews.com/2018/09/how-to-install-ubuntu-on-chromebook-and-remove-chromeos/) and a [video](https://www.youtube.com/watch?v=AxsckwmRhfw) by *David Burgess* using Ubuntu 18.04.

### You need:
1. a small cross-head screwdriver;
2. a bootable Ubuntu on a usb drive (4GB or more). See instructions [here](https://ubuntu.com/tutorials/create-a-usb-stick-on-ubuntu#1-overview).

The process is as follows. First (*but in some resources this passage is not mentioned*), you have to open your laptop (see section above), remove the "write-protection" screw (n. 7 in the image shown above), and close the laptop again.

Power on your Chromebook and enter the developer mode by pressing Esc + Refresh, and taping the Power Button. This will wipe out your memory and restart the system with an error message saying "Chrome OS is missing or damaged".

Press Ctrl + D, release and then press Enter when prompted the message "To turn OS verification OFF, press ENTER". 

Do not press the space. After some 20 seconds you will hear a beeps and get a message saying "Your system is transitioning to Developer Mode." (there is a progress bar on the topleft of the page). After some 5 minutes, the "OS Verification is OFF" message will be reprompted together with three beeps, and the Chromebook will restart.

It will show again "OS verification is OFF". Press Ctrl+D to start ChromeOS.

> **2018 alternative**: Modify the Chromebooks BIOS: Turn the Chromebook on and press Ctrl + D to bypass the screen with the red exclamation mark. Your Chromebook is reset to factory settings so you will need to go through the Chrome OS setup again. Log in again (or "use as a guest"). Press Ctrl + Alt + T to bring up a terminal window tab. Type shell and press Enter. Type this: cd;bash <(curl https://johnlewis.ie/flash_cb_fw.sh), then press enter. Choose the option to Modify my Chromebook’s RW_LEGACY slot (that should be option 1), press enter and follow the on-screen instructions (ie. retype a sentence from the screen). At the end shut off the chromebook, power on again and press CTRL + D.

To Enable Developer BIOS and USB Boot, **do NOT log in** to ChromeOS. Press CTRL + ALT + Forward, log in as "chronos" (ust that, without any password).

Execute the following commands:
```
$ shell
$ sudo crossystem dev_boot_usb=1
$ sudo crossystem dev_boot_legacy=1
$ sudo /usr/share/vboot/bin/set_gbb_flags.sh 0x489
```

This will flash the BIOS to enable SeaBIOS, which allows you to boot from USB. (Now on startup, if you press Ctrl + L, you will get the BIOS screen instead of Chrome OS.)

Hold down the power button (or type "sudo poweroff") to turn the Chromebook off.

Insert the Ubuntu bootable USB drive and turn the power on again.

The prompt will say "SeaBIOS" (if you don't get the BIOS then press CTRL + L) and "Press ESC for boot menu", so press Esc. 

Press the number corresponding to your bootable USB. For Ubuntu should be called "Live Linux USB Drive" (there might be some other options that belongs to different partitions of te bootable usb), while the eMMC should be the Chromebooks internal HD. If there are problems you can type "help" at the boot: and access the Installation System for Ubuntu, then press enter.

Now Ubuntu live desktop will boot, and you will click on the icon to install Ubuntu. At the "Welcome" window, select "English" and "install Ubuntu". At the "Wireless" box, accept the default selection of "I don't want to connect..." and click Continue or connect to a wifi in order to download updates. Accept the default selections and click Continue at the "Preparing to install Ubuntu" screen.
When the "Installation type" box appears, click the "Erase disk and install Ubuntu" button. Click "Install Now".

After a minute or so, a box ask "Write the changes to disks?". Click Continue. Then will ask for your timezone, select your location and click Continue. In the "Keyboard layout" box, accept the default of "English (US)" and click Continue. In the "Who are you?" box, enter account information and password and click Continue.

After 5 to 10 minutes you will be asked to remove the installation media. Remove the usb drive and press Enter.

When the machine restarts, press Esc and select option 1 (the only available) and you will finally have Ubuntu! 
(if the chrome esclamtion mark page is shown again, press CTRL + D, or CTRL + L > scape > 1 and repeat as before, it should work). 


## Other Linux distros

For people interested in installing on this laptop model other Linux distributions I found:
1. [here](https://wiki.archlinux.org/title/Acer_C720_Chromebook#Locating_the_Write-Protect_Screw) some documentation about Arch;
2. [here](http://jeffhoogland.blogspot.com/2014/01/) and [here](https://www.linux.com/topic/desktop/how-install-linux-acer-c720-chromebook/) about Bodhi Linux.
3. And [here](https://www.youtube.com/watch?v=dq44cHvxTXI&t=327s) about Mint.


## To Restore the original ChromeOS

At the end of this experiemtn you may want to restore the original ChromeOS to your chromebook, here is how you can do it.
Remember that if you upgraded the SSD, you will have still the original ChromeOS on the old SSD, therefore you can consider just to switch hard disk!

For resources about restoring the original ChromeOs please visit the relative [Chromebook help page](https://support.google.com/chromebook/answer/1080595?hl=en#zippy=%2Cuse-a-linux-computer%2Cstep-download-a-new-copy-of-the-os%2Cstep-enter-recovery-mode). You can also check this [blogpost](https://www.linux.com/topic/desktop/how-install-linux-acer-c720-chromebook/) by *Jack Wallen* (look at the last section).

### You need:
1. SD card or usb drive with recovery ChromeOS (that you made previously)

Remove every device connected to your Chromebook (such as a mouse or external hard drive) and be sure to have enpugh power in your laptop battery (or to be coonnected to the power soklet).

**Enter the Chromebook recovery mode**: Press and hold Esc + Refresh, then press Power. Let go of Power. When a message shows on the screen, let go of the other keys. (On some Chromebook models: Press and hold Esc + Maximize, then press and release Power.)

You should see one of these messages: "ChromeOS is missing or damaged. Please insert a recovery USB stick or SD card." or "Please insert a recovery USB stick or SD card." (BTW, at the bottom of the page you can also see the HWID of your model).

![Recovery Mode page](https://codethepast.github.io/UbuntuOnChromebook/UbuntuOnChrome15.jpg)

Insert the USB flash drive or SD card that you used to create recovery media. You don't need to press enter as the chromebook will start processing the recovery mode. Wait and follow the on-screen instructions (this will take a few minutes).

![Recovery Mode checking](https://codethepast.github.io/UbuntuOnChromebook/UbuntuOnChrome16.jpg)

When the recovery is completed you will be asked to remove the recovery media (ie. the SD card or the USB drive you used). Afterwards, the system will restart automatically.
Here it is your Chromebook is back to its (not supported) fresh installation!

[< back](https://codethepast.github.io/)
