[🇷🇺 Русская версия документации здесь](https://github.com/renat2985/toncoin_payment_sonoff/blob/main/README_RU.md)

# Payment for Your Services via TonCoin

A convenient and fast way to implement paid services using the TonCoin cryptocurrency. The process is simple: You open any crypto wallet, scan the QR code (for example, it can be printed on a sheet with the required amount), transfer the specified amount, and as soon as the payment is received, the relay will activate and turn on your device for the time you set. This could be any device, from a kettle, coffee machine, or light bulb to powering electricity in a room or another location.

You can assemble the device yourself or ask me to build it for you. To order a ready-made device, contact me via [Telegram](https://t.me/ESPiotDevice), Skype: renat2985.

<img src="https://github.com/renat2985/toncoin_payment_sonoff/blob/main/doc/intro.png">

### Key Features:

1. **Device Connection:**
   - On first power-up, or if the device cannot find the router, it will create an access point named "TonCoin payment."
     
     <img src="https://github.com/renat2985/toncoin_payment_sonoff/blob/main/doc/WiFi.png" width="200px">
   - Connect to this access point (no password needed) and open a browser, then enter http://192.168.4.1. Usually, after connecting to Wi-Fi, the Captive portal will automatically open and redirect you to the desired page.
     
     <img src="https://github.com/renat2985/toncoin_payment_sonoff/blob/main/doc/AP1.png" width="300px">
   - Click "Configure WiFi" to proceed with the setup.

2. **Device Configuration:**
   - **Router and Password:** Enter your Wi-Fi connection details.
   - **Device Name:** Specify a device name, e.g., "Buy coffee."
   - **Your Toncoin Wallet:** Enter your wallet address to receive payments.
   - **Currency:** Select the currency in which you want to receive payments (EUR, USD, RUB, BYN, BGN, GBP, etc.). This is necessary for automatic conversion to TonCoin based on the current exchange rate, updated hourly through coinmarketcap.com.
   - **Service Currency Price:** Specify the price in your selected currency that the customer should pay.
   - **Payment Tolerance:** In this field, specify the acceptable price deviation. Since the Ton price constantly fluctuates, you need to indicate a deviation range (as a single number) that you are willing to accept for payment.
   - **Relay Work Time:** Specify how long the relay should be activated in seconds. This can range from one second (for simulating a button press) to several minutes or hours.
     
     <img src="https://github.com/renat2985/toncoin_payment_sonoff/blob/main/doc/APFull.png" width="500px">


### Instructions for Self-Assembly:

To assemble the device yourself, you will need a Sonoff device. Additionally, you will need:
- A programmer, such as USB to TTL / PL230
- A soldering iron and wires


  <img src="https://github.com/renat2985/toncoin_payment_sonoff/blob/main/doc/flash_gpio4.png" width="500px">


Good luck! If you have any questions, don't hesitate to reach out.


# Web installer (recommended)
## [https://renat2985.github.io/toncoin_payment_sonoff/](https://renat2985.github.io/toncoin_payment_sonoff/)


### For Advanced Users: Firmware Instructions via Programmer
### Specification .bin files
```
  -  Module: Generic ESP8266 Module
  -  Flash Size: 1M
  -  CPU Frequency: 80Mhz
  -  Flash Mode: QIO
  -  Flash Frequency: 40Mhz
  -  Upload Speed: 921600
```

## [toncoin_payment_sonoff.ino.bin](https://github.com/renat2985/toncoin_payment_sonoff/raw/main/build/esp8266.esp8266.generic/toncoin_payment_sonoff.ino.bin)

### NodeMCU Flasher
https://github.com/nodemcu/nodemcu-flasher
Download Release: [Win32](https://github.com/nodemcu/nodemcu-flasher/blob/master/Win32/Release/ESP8266Flasher.exe) or [Win64](https://github.com/nodemcu/nodemcu-flasher/blob/master/Win64/Release/ESP8266Flasher.exe).

## :battery: Donation

If you like this project, you can buy me a cup of coffee :coffee:

<img src="https://github.com/renat2985/toncoin_payment_sonoff/blob/main/doc/donate.png" width="700px">

- PayPal [https://www.paypal.me/RKevrels](https://www.paypal.me/RKevrels/5)