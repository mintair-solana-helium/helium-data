# helium-data
collecting data thru helium

## Software
- Arduino IDE

## Hardware
- [Adafruit Feather M0 Radio with LoRa Radio Module](https://www.adafruit.com/product/3178)
- [Adafruit PMSA003I Air Quality Breakout](https://www.adafruit.com/product/4632)
- [Lithium Ion Polymer Battery](https://www.adafruit.com/product/258) (to power the PMSA, optional)

## Run

### Arduino IDE Setup
1. Navigate to **Tools > Boards > Boards Manager**, search for **Arduino SAMD Boards (32-bits ARM Cortex-M0+)**, select the newest version and install
2. Navigate to **Preferences**, find the section at the bottom called **Additional Boards Manager URLs**, add this url in the text box: `https://adafruit.github.io/arduino-board-index/package_adafruit_index.json`
3. Open **Manage Libraries**, install following libraries:
    - IBM LMIC framework
    - Adafruit PM25AQI
4. Update IBM LMIC framework config.h

    This library requires that a config file be setup properly. After you have installed the IBM LMIC framework library, navigate to it's directory on your operating system found below. Next, replace the config.h file in this directory with this config.h file.

    linux: /home/{user}/Arduino/libraries/IBM_LMIC_framework/src/lmic windows: Documents/Arduino/libraries/IBM_LMIC_framework/src/lmic mac os: Documents/Arduino/libraries/IBM_LMIC_framework/src/lmic


### Setup Feather M0 board
Jumping IO1 to Pin6 to enable the RFM95 radio module:

![](https://docs.helium.com/img/use-the-network/devices/development/adafruit/adafruit-feather-m0-rfm95/adafruit-feather-m0-rfm95-jumper-pins.jpg)

### Flash to board
1. Navigate to **Select Tools > Board: > Adafruit Feather M0** and select this board
2. Copy air_quality.ino into the Arduino sketch
    - fill in your wallet address
    - fill in the AppEUI(lsb), DevEUI(lsb), and AppKey(msb)
3. Upload the sketch to board
