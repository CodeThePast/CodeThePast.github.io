## Ubuntu on a 9 years old Chromebook

[< back](https://codethepast.github.io/)

In **2013**, when I was working in the US, I bought a **Chromebook Acer C720P-6666** (with touchscreen) that worked well for long time. It was not my main machine, but was perfect for some activities and handy for the small size.

Unfortunately, at the end of 2019 Google decided to stop supporting my model (the current policy is to support Chromebook models up to 6.5 years from their production date, more details [here](https://www.theguardian.com/technology/askjack/2019/sep/12/can-i-still-use-my-chromebook-now-it-is-no-longer-supported)). After some time I started experiencing software issues and glitches, and of course not having OS updates means to face serious security risks. Therefore, I decided to challenge myseft in installing **another OS on this laptop**, an Ubuntu distro of Linux, giving a try to this 9 years old laptop to continue journey together. Together with this OS upgrade I also wanted to provide more disk memory. In this post I describe the process and the results of this upgrades, together with a few personal notes!

## The Acer C720P

Nowadays, it is not easy to find online the full specs about the Acer C720P, but [here](https://www.laptopmag.com/reviews/laptops/acer-chromebook-c720p) you have the main information. To get an extended review of the Acer C720P by *Brad Linder* you can read this [post](https://liliputing.com/2014/03/acer-c720p-touchscreen-chromebook-review.html).
For your documentation I provide here the top- and bottomview of the laptop before opening it.

![Top view](https://codethepast.github.io/UbuntuOnChromebook/UbuntuOnChrome10.jpg)

![Bottom view](https://codethepast.github.io/UbuntuOnChromebook/UbuntuOnChrome11.jpg)

And here the picture of the sticker with the product's detail (yes, it was made in December 2013!).

![Laptop detail](https://codethepast.github.io/UbuntuOnChromebook/UbuntuOnChrome12.jpg)


## Hardware upgrade

Differently from other models, the Acer C720P has the touchscreen and only 2GB of RAM, that unfortunately cannot be expanded. As for the disk, the laptop originally has a 32GB SSD, that is enough for a web based chromebook, but might be tight for a complete Ubuntu system. 
**NOTE: You will invalidate your warranty when you open your laptop and change the SSD. You’re on your own if you break anything.**

### You need:
1. a drive to backup your documents;
2. a 4GB SD card, to save a recovery of Chrome OS - in case you will want to reinstall the original OS.
3. a small cross-head screwdriver;
4. a new, larger SSD. 64GB and 128GB have been tested and work well. Please note that for this model the SSD is a SATA M.2 2242 form factor type.

Please consider backing up your documents before starting this operation as they will not be retained during the operation (or better, they will remain in your old SSD, but not authomatically copied to the new one).
Furthermore, you may want to cerate a recovery of your Chrome OS. Until mid 2019 you could download the OS image from your chromebook by typing chrome://imageburner into the adrress bar of the browser. Now you need to use the [Chromebook Recovery Utility](https://chrome.google.com/webstore/detail/chromebook-recovery-utili/pocpnlppkickgojjlmhdmidojbmbodfm) that you can download from the Chrome Web Store. May issues and delays are reported for this procedure, but as per today this is the only way to save an image of the OS. You wil be asked to enter your device's model number (mine is PEPPY E6A-O3G-A9V)  

There are several online resources that show how easy is to open the laptop and change the original SSD with a new one:
- Here a [video](https://www.youtube.com/watch?v=AZa5kWBfbWM) by *unlokia* showing how to properly open this laptop model and how to find the different hardware components.
- Here a [video](https://www.youtube.com/watch?v=LrrL2Qy2PGI) by *Isaac* mounting a 64GB SSD. 
- Here a [video](https://www.youtube.com/watch?v=c9rKQVtEjNc) by *Daniel Berry* mounting a 64GB SSD.
- Here a [blogpost](https://www.umpcportal.com/2014/01/how-to-upgrade-the-acer-c720-chromebook-with-an-m-2-sata-from-mydigitalsdd/) and a [video](https://www.youtube.com/watch?v=-jOHHyJMgWk) by *Steve Paine* mounting a 128GB SSD.

In order to open the laptop you need to remove 13 screws placed on the bottom side, then gently insert a plastic point or a card in the gap between the bottom side and the keyboard side (better to start from the hinges) to completely free the bottom side. I provide here a view of the opened laptop.

![Inside the laptop](https://codethepast.github.io/UbuntuOnChromebook/UbuntuOnChrome13.jpg)

To get an idea of the architecture of the Acer C720 (the model without touchscreen and with 4GB of RAM) you can see the following image, taken from [here](https://www.chromium.org/chromium-os/developer-information-for-chrome-os-devices/acer-c720-chromebook).

![C720 hardware architecture](https://samsclass.info/128/proj/c720-chromebook-annotated-innards.png)

*For the numbers: 1. CPU. 2. RAM (here 4GB, mine has only 2GB). 3. System firmware. 8MB SPI Flash. 4. NGFF (M.2) SSD. 5. Battery enable switch. 6. Battery enable screw. 7. Write-protect screw. 8. Servo debug header. 9. NGFF (M.2) WWAN connector.*

This is the detail of the original 32GB SSD in place.

![The original SSD in place](https://codethepast.github.io/UbuntuOnChromebook/UbuntuOnChrome14.jpg)

It is very easy to change the SSD: just remove the single screw, carefully slide the SSD out, gently put the new SSD in the slot (paying attention to respect the direction of the card and do not touch the contacts as the skin acids are dangerous for the electronic contacts).
Push the bottom side back in its position and screw back all the 13 screws.




## Ubuntu byside of Chrome OS (with Crouton)

How to operate with Chromium in Developer mode:
- https://www.chromium.org/chromium-os/developer-information-for-chrome-os-devices/acer-c720-chromebook

Focal Fossa with Crouton:
- https://github.com/dnschneid/crouton/issues/4265
- https://bleepcoder.com/crouton/602619482/focal-fossa
- Here a [post](https://liliputing.com/2014/03/acer-c720p-touchscreen-chromebook-review.html) and a [video](https://www.youtube.com/watch?v=bYGAr_OBBoo) by *Brad Linder*.


## Ubuntu as only OS

Remove the "write-protection" screw (n. 7 in the image shown above).

- Here a extended [blogpost](https://samsclass.info/128/proj/chromebooks3.htm) by *Sam Bowne* explaining the all process of installation.
- Here a [blogpost](https://dbtechreviews.com/2018/09/how-to-install-ubuntu-on-chromebook-and-remove-chromeos/) and a [video](https://www.youtube.com/watch?v=AxsckwmRhfw) by *David Burgess*.
- Here a [blogpost](https://www.linux.com/topic/desktop/how-install-linux-acer-c720-chromebook/) by *Jack Wallen* using ChrUbuntu or Bodhi Linux.

### You need:
1. usb with Ubuntu
2. usb with recovery ChromeOS


## Other Linux distros

For people interested in installing on this laptop model other Linux distributions I found [here](https://wiki.archlinux.org/title/Acer_C720_Chromebook#Locating_the_Write-Protect_Screw) some documentation about Arch, [here](http://jeffhoogland.blogspot.com/2014/01/) about Bodhi Linux, and [here](https://www.youtube.com/watch?v=dq44cHvxTXI&t=327s) about Mint.


## To Restore the original ChromeOS

- Here a [blogpost](https://www.linux.com/topic/desktop/how-install-linux-acer-c720-chromebook/) by *Jack Wallen* (check the last section).


[< back](https://codethepast.github.io/)
