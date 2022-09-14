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
For those members of the [Melbourne Raspberry Pi Hackers](https://melbourne-rpi.com.au/) / [EMDRC](https://www.emdrc.com.au/) looking to flash a sonde with our call sign here is the [firmware](https://https://hab.rohbot.cc/RS41ng-firmware.zip) I prepared eariler.. 
## Flashing Firmware to the Sonde
* For this you will need a ST-Link V2. I bought mine off eBay for $12 AUD [link](https://www.ebay.com.au/itm/393083134149)
* You will also need to download and install the [STM32 ST-LINK utility](https://www.st.com/en/development-tools/stsw-link004.html)
![st-link](https://github.com/rohbot/rohbot-blog/raw/master/img/st-link.jpg) 
1. Connect the ST-LINK to the RS41 with jumper wires (this is the configuration I used)
### ST-LINK V2 Connector
```
Programer cable connections:
RS41 ----- ST-LINK
===================
Pin 1 ----- GND (Pin 5)
Pin 5 ----- 5.0V (Pin 9)
Pin 8 ----- SWCLK (Pin 2)
Pin 9 ----- SWDIO (Pin 4)
```
### Vaisala RS41 Expansion Connector Pinout
Based on work by DF8OE
Viewed into port from outside
```
----------|     |----------
|  9    7    5    3    1  |
|                         |
|  10   8    6    4    2  |
---------------------------
```
1. Open up ST-Link Utility
2. Click ***Target*** and then ***Connect*** and you should see something like this:
![st-util](https://github.com/rohbot/rohbot-blog/raw/master/img/st-util.jpg)
3. If this is the first time flashing the sonde, you will need to disable ***Read Out Protection***  
Click ***Target***, then ***Option Bytes*** and make sure ***Read Out Protection*** is disabled
![option-bytes](https://github.com/rohbot/rohbot-blog/raw/master/img/options_bytes.jpg)
4. You should now be ready to flash new firmware to the sonde
Click ***Target***, then ***Program and Verify*** and select the *RS41HUP.bin* you have either compiled or downloaded [here](https://github.com/rohbot/rohbot-blog/raw/master/img/RS41HUP_RPHMELB-4FSK.zip)
Hit ***Start*** to flash the file to the sonde
If it works next time you push the power button on the Sonde it should be transmitting on 434.2 MHz
   
# Disclaimer
This is not the only way to flash the [RS41HUP](https://github.com/darksidelemm/RS41HUP) firmware to a RS41 but this is what worked for me
I compiled the firmware using WSL and then flashed the Sonde in Windows 10. I haven't tried using [openOCD](http://openocd.org/) or stlink
   
