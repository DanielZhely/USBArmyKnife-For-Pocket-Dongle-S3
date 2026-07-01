<p align="center">
  <h1><strong>INTRODUCTION</strong></h1>
</p>

---
The Pocket Dongle S3 is a clone of the Lilygo T-Dongle S3. It was supposed to be a cheap clone of the Lilygo, but turned out to have better raw hardware onboard. The official build of the USBArmyKnife does support the Pocket Dongle S3, but only by using the _generic_ ESP32 S3 build that is provided alongside the 6 other builds, _yuck_. The other devices have the firmware built completely around them, _all except the Pocket Dongle S3_. So I took matters into my own hands and strapped together a new firmware with support for the 16MB Flash Storage and more importantly, the _8MB of PSRAM_ that it features. _What will you do with 2x the storage and approx. 25.6x of PSRAM?_ It's all up for you to decide!

<p align="center">
  <h1><strong>COMPATIBILITY</strong></h1>
</p>

---

Pocket-Dongle-S3 N16R8 **ONLY!!**

Buy from 'GNPE Development Board Factory' Store on AliExpress only.

Link: https://www.aliexpress.com/item/1005009024098181.html?spm=a2g0o.order_list.order_list_main.22.5efa18026bG7NB 

<p align="center">
  <h1><strong>COMPARISON</strong></h1>
</p>

---

_bold text means better_

| Spec | Pocket Dongle S3 (N16R8) | Lilygo T-Dongle S3 |
| :--- | :---: | :---: |
| MCU | ESP32-S3 | ESP32-S3 |
| Flash Storage | 16MB | 16MB |
| RAM | 𝟴𝗠𝗕 𝗣𝗦𝗥𝗔𝗠 **+** 𝟱𝟭𝟮𝗞𝗕 𝗦𝗥𝗔𝗠 | No PSRAM + 512KB SRAM |
| Display | 0.96' 160x80 65k Color LCD  | 0.96' 160x80 65k Color LCD |
| Manufacturer | GNPE Development Board Factory | lilygo Official Store |
| Price | **€**𝟭𝟭.𝟲𝟮 | €16.43 |
| Extras | None | 𝗥𝗚𝗕 𝗟𝗘𝗗 **+** 𝘂.𝗙𝗟 𝗔𝗻𝘁𝗲𝗻𝗻𝗮 𝗖𝗼𝗻𝗻𝗲𝗰𝘁𝗼𝗿 |

<p align="center">
  <h1><strong>HOW TO INSTALL</strong></h1>
</p>

---

_go to this page first: https://espressif.github.io/esptool-js/ , when doing any step, allow whatever permissions the site asks for and whatever add-ons it wants to install_

## Step One - **Wipe**

<ul>
  <li>Under '<strong>Program</strong>' select '<strong>Baudrate:</strong>' and set it to 115200 via the dropdown menu. Now hold the 'Boot' button on your device and plug it in, <strong>only stop holding when the computer detects it</strong> then press the blue 'Connect' button and allow the browser access to your device.</li>
  <br>
  <li>You'll see a red '<strong>Erase Flash</strong>' button, click it.
    <br><br>
    <img src="readmeAssets/dontforgetTowipeyourbackside.png" alt="Wipe Flash" width="350">
  </li>
  <br>
  <li>After clicking it, look at the end of the black console for a '<code>Chip erase completed successfully in 3.0s</code>'
    <br><br>
    <img src="readmeAssets/webterminalwipe.png" alt="Wipe Complete" width="400">
  </li>
  <br>
  <li><em>Wipe complete!</em> Now disconnect the device and refresh the web page.</li>
</ul>

## Step Two - **Install**
* After refreshing the page, select a Baudrate of 115200, hold the 'Boot' button on your device and plug it in, **only stop holding when the computer detects it** then press Connect and Allow the browser access to your device.

* Look under the '**Flash Address**' text, you'll see a box with the text '0x1000', remove it and in its place type '_0x0000_', then look to the right, under '**File**', click '**Browse...**', open the extracted folder containing all the bin files and _only select_ '**bootloader.bin**', then press the blue button saying '**Add File**' 3 TIMES. On the second Address, type '_0x8000_' and add the file named '**partitions.bin**', on the third address type '_0xE000_' (**NOT** 0xe000) and add the file named '**boot_app0.bin**', then on the fourth address, type '_0x10000_' (**NOT** 0x1000) and add the last file named '**firmware.bin**'.

<ul>
  <li>
    <strong>Overview:</strong>
    <br><br>
    <img src="readmeAssets/webaddresses.png" alt="Flash Layout" width="550">
    <br><br>
    <em>Leave the flash mode and frequency options as they are, only set size to 16MB.</em>
  </li>
</ul>

* Then simply press the blue button '**Program**' that's near the console and wait till it says '`Wrote 2310512 bytes (1540648 compressed) at 0x10000 in 12.405 seconds.
File  md5: 40a42ecc663aee1d6b8473f653ef63bf
Flash md5: 40a42ecc663aee1d6b8473f653ef63bf
Hash of data verified.
Leaving...
Hard resetting via RTS pin...`'. When it does, wait 5 seconds, unplug the device and close the page.

## Congratulations, device flashed successfully!
To boot into USBArmyKnife, just plug the device into any USB port that has power and see that it's booted on the LCD. To control it, open the Wi-Fi settings on a Smart Watch/Phone/Tablet/Computer and look for a network named '**iPhone14**' (_yes, really_), connect to it and use the password '**password**', then open a web browser and in the URL Bar (**NOT Search Bar**) type '**4.3.2.1:8080**' and you're in, _enjoy_!

## Extras & Goodies:

_the bold ones are ones i strongly recommend_

| Name | Function |
| :---: | :---: |
| **DuckyScript Executor** | **DuckyScript executer based on the File System API to easily execute scripts on the device without using the web interface.** |
| Fake Login Portal | Makes an access point that users can connect to and be redirected to your web page so they do what is shown on that web page. |
| _Testing..._ | _Project 3 is currently in testing._ |
| LCD Flashlight | Simple script that shows a white PNG on the screen that acts a fairly bright flashlight. |
| _Testing..._ | _Project 5 is currently in testing._ |
| _Testing..._ | _Project 6 is currently in testing._ |
| _Testing..._ | _Project 7 is currently in testing._ |
| Progress Bar | Simple green progress bar that fills the entire screen, useful for multistage tasks or showing that something is being performed, only visual. |
| _Testing..._ | _Project 9 is currently in testing._ |
| _Testing..._ | _Project 10 is currently in testing._ |
| _Testing..._ | _Project 11 is currently in testing._ |
| _Testing..._ | _Project 12 is currently in testing._ |
| _Testing..._ | _Project 13 is currently in testing._ |
| _Testing..._ | _Project 14 is currently in testing._ |

## Troubleshooting:
* _everything works..._

## Plans for the future:
* Add a second bar in the Web UI that shows PSRAM Usage alongside the internal SRAM Usage.

* Video tutorial.

Check out the original project by i-am-shodan: https://github.com/i-am-shodan/USBArmyKnife/tree/master

𝗥𝗲𝗮𝗰𝗵 𝗼𝘂𝘁 𝘁𝗼 "𝗱𝗮𝗻𝗶𝗲𝗹.𝗻𝟭𝟲𝗿𝟴𝗱𝗲𝘃𝗲𝗹𝗼𝗽𝗺𝗲𝗻𝘁@𝗴𝗺𝗮𝗶𝗹.𝗰𝗼𝗺" 𝗶𝗳 𝘆𝗼𝘂 𝗽𝗿𝗼𝘃𝗶𝗱𝗲 𝗳𝗲𝗲𝗱𝗯𝗮𝗰𝗸. 𝗧𝗵𝗮𝗻𝗸 𝘆𝗼𝘂.
