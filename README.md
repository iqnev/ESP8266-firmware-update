### ESP8266 firmware update

The ESP8266 Firmware can be installed for two reasons: If you want to update the ESP8266 Firmware to its latest version or to completely install the new firmware (in case it was overwritten by any program). So, let's get started. To check the version of firmware, as well as to update the firmware, need to connect the module to a computer via serial port. The module can be connected via the Arduino board, or through a USB-UART adapter.

------------


###  Connecting via the Arduino board
So, the connections are as follows.

SP8266  |  Arduino 
 — — — — — — — — -
     RX     |    RX
     TX |      TX
    GND | GND 
    VCC | 3.3V 
  CH_PD | 3.3V 
 GPIO 0 | GND 


### Check the current firmware version
To send AT commands and view the responses need to use any software serial port monitor. The baud rate of the default 115200 baud.
Check the current firmware version can be performed by AT-command: **AT+GMR**

Also it is necessary to know the flash memory size of ESP module, firmware upload address depend on it size. This manual describes updated firmware of module with flash memory size 8Mbit (512KB+512KB) or 16Mbit (1024KB+1024KB), as the most common. Flash memory size can be found if send the AT-command from reset: **AT+RST**

### The tool for firmware update
To update the firmware you must download the special tool application and the firmware itself. [[1] Flash Download Tools][Flash Download Tools]  You must go to "Tools" section

### Firmware
The firmware can also be downloaded from the [[2]firmware][firmware]. You must go to “SDKs & Demos” section and download firmware ESP8266 NONOS SDK

### Settings
Run the application Flash Download Tools v2.4. In the opening window must correctly chose the downloaded files and setup the connection mode.
Downloadable files are located in the "bin" directory with the firmware files. For each file you must specify a valid address download

| Downloadable file  | Flash 8Mbit (512KB+512KB)  | Flash 16Mbit (1024KB+1024KB) |
| ------------ | ------------ | ------------ |
| esp_init_data_default.bin  |  0xFC000 | 0x1FC000  |
| blank.bin  | 0xFE000  | 0x1FE000  |
|  boot_v1.7.bin or later |0x00000   | 0x00000  |
|  user1.1024.new.2.bin |  0x01000 | 0x01000  |
|  user1.1024.new.2.bin |  0x81000 | 0x81000  |

[![FLASH_DOWNLOAD_TOOLS_v2.4](https://raw.githubusercontent.com/iqnev/ESP8266-firmware-update/master/flash_esp8286.JPG "FLASH_DOWNLOAD_TOOLS_v2.4")](https://raw.githubusercontent.com/iqnev/ESP8266-firmware-update/master/flash_esp8286.JPG "FLASH_DOWNLOAD_TOOLS_v2.4")

1. Set the following settings:
2. SPIAutoSet — set
3. CrystalFreq - 26M
4. FLASH SIZE – 8Mbit or 16Mbit depending on the size of the flash memory
5. COM PORT – select the port that is connected to ESP
6. BAUDRATE – 115200


[Flash Download Tools]: https://www.espressif.com/en/products/hardware/esp8266ex/resources " Flash Download Tools"
[firmware]: https://www.espressif.com/en/products/hardware/esp8266ex/resources "firmware"
