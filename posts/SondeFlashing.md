---
title: How to Flash a Sonde
description: Flashing a RS 41 with RS41HUP Firmware
date: 2020-01-25
tags:
  - 
  - Radiosonde
  - STM32
layout: layouts/post.njk

---
*Disclaimer* - This is not the only way to flash the [RS41HUP](https://github.com/darksidelemm/RS41HUP) firmware to a RS41 but this is what worked for me
I compiled the firmware using WSL and then flashed the Sonde in Windows 10. I haven't tried using [openOCD](http://openocd.org/) or stlink

## Catch a Sonde
Go out and track down a Radiosonde that's been launched by the BOM. It might be helpful to check out [auto_rx](https://github.com/projecthorus/radiosonde_auto_rx) project
## Crack it open
1. Using a small flat head screw driver, lever it under the front clip until it pops off 
![front clip](https://github.com/rohbot/rohbot-blog/raw/master/img/front-hook.jpg)
1. Removing the rear clip is a little trickier. Try to push the clips white plastic bit
![rear clip](https://github.com/rohbot/rohbot-blog/raw/master/img/rear-clip.jpg)
Once you get the clips off it good to cut them off with some sidecutters, so it doesn't get snagged
## Compiling the RS41HUP firmare
1. Follow the instructions on [RS41HUP Readme](https://github.com/darksidelemm/RS41HUP)
I managed to compile it using [Windows Sub System for Linux](https://docs.microsoft.com/en-us/windows/wsl/install-win10) but your mileage may vary 
For those members of the [Melbourne Raspberry Pi Hackers](https://melbourne-rpi.com.au/) looking to flash a sonde with our call sign here is the [firmware](https://github.com/rohbot/rohbot-blog/raw/master/img/RS41HUP_RPHMELB-4FSK.zip) I prepared eariler.. 
## Flashing Firmware to the Sonde
1. For this you will need a ST-Link V2. I bought mine off eBay for $12 AUD [link](https://www.ebay.com.au/itm/393083134149)
2. You will also need to downloadd and install the STM32 ST-LINK utility [link](https://www.st.com/en/development-tools/stsw-link004.html)