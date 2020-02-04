### ESP8266 firmware update

The ESP8266 Firmware can be installed for two reasons: If you want to update the ESP8266 Firmware to its latest version or to completely install the new firmware (in case it was overwritten by any program). So, let's get started. To check the version of firmware, as well as to update the firmware, need to connect the module to a computer via serial port. The module can be connected via the Arduino board, or through a USB-UART adapter.

------------


###  Connecting via the Arduino board
So, the connections are as follows.
1. VCC to 3.3V
2. GND to GND
3. TX to TX of Arduino UNO
4. RX to RX of Arduino UNO (through level converter)
5. GPIO0 to GND
6. RST to GND through Push Button
7. CH_PD to 3.3V

image

### Check the current firmware version
To send AT commands and view the responses need to use any software serial port monitor. The baud rate of the default 115200 baud.
Check the current firmware version can be performed by AT-command: **AT+GMR**

Also it is necessary to know the flash memory size of ESP module, firmware upload address depend on it size. This manual describes updated firmware of module with flash memory size 8Mbit (512KB+512KB) or 16Mbit (1024KB+1024KB), as the most common. Flash memory size can be found if send the AT-command from reset: **AT+RST**

### The tool for firmware update
To update the firmware you must download the special tool application and the firmware itself Flash Download Tools v2.4  You must go to "Tools" section

### Firmware
The firmware can also be downloaded from the official site. You must go to “SDKs & Demos” section and download firmware ESP8266 NONOS SDK

### Settings
