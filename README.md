[🇷🇺 Русская версия документации здесь](https://github.com/renat2985/toncoin_payment_sonoff/blob/main/README_RU.md)

# Payment for Your Services via TonCoin

A convenient and fast way to implement paid services using the TonCoin cryptocurrency. The process is simple: You open any crypto wallet, scan the QR code (for example, it can be printed on a sheet with the required amount), transfer the specified amount, and as soon as the payment is received, the relay will activate and turn on your device for the time you set. This could be any device, from a kettle, coffee machine, or light bulb to powering electricity in a room or another location.

You can assemble the device yourself or ask to build it for you. To order a ready-made device, contact me via [Telegram](https://t.me/ESPiotDevice), [Skype](https://skype:renat2985?chat), [Discord](https://discord.com/invite/zaGaDuGe).

We have a similar project with a screen, [check it out](https://github.com/renat2985/crypto_payment_touchScreen).


[![IMAGE ALT TEXT HERE](https://github.com/renat2985/toncoin_payment_sonoff/blob/main/doc/intro4.png)](https://www.youtube.com/watch?v=zKdVJmzJNLM&list=PL6NJTNxbvy-LpsI6D_1RM6v5YWDvsm5j4)

### Key Features:

1. **Device Connection:**
   - When first powered on, if the device can’t find the router or if you press the button on the ESP itself, it will create an access point named “TonCoin payments.”
     
     <img src="https://github.com/renat2985/toncoin_payment_sonoff/blob/main/doc/WiFi.png" width="200px">
   - Connect to this access point (no password needed) and open a browser, then enter http://192.168.4.1. Usually, after connecting to Wi-Fi, the Captive portal will automatically open and redirect you to the desired page.
     
     <img src="https://github.com/renat2985/toncoin_payment_sonoff/blob/main/doc/AP1.png" width="300px">
   - Click "Configure WiFi" to proceed with the setup.

2. **Device Configuration:**
   - **Router and Password:** Enter your Wi-Fi connection details.
   - **Device Name:** Specify a device name, e.g., "Buy coffee.". You can optionally add GPIO pins in this field. Example: Device_name:12,0,13, where Device_name is the name of the device, and 12,0,13 are the corresponding pin numbers for the relay, erase button, and LED (RELAY_PIN,BUTTON_PIN,LED_PIN).
   - **Your Toncoin Wallet:** Enter your wallet address to receive payments.
   - **CoinMarketCap API:** Is a service that allows you to get the current TonCoin price in fiat currency. For testing, you can use the default API, but if you plan to use the device on a regular basis, it is highly recommended to register on the [CoinMarketCap](https://coinmarketcap.com/api/) website and get your own API. The free version allows up to 10,000 requests per month for price data. This is more than enough for 10 devices, but if our API is used by more devices, not everyone will be able to receive the actual price, and as a result, payments may fail.
   - **Currency:** Select the currency in which you want to receive payments (EUR, USD, RUB, BYN, BGN, GBP, etc.). This is necessary for automatic conversion to TonCoin based on the current exchange rate, updated hourly through coinmarketcap.com.
   - **Service Currency Price:** Specify the price in your selected currency that the customer should pay.
   - **Payment Tolerance:** In this field, specify the acceptable price deviation. Since the Ton price constantly fluctuates, you need to indicate a deviation range (as a single number) that you are willing to accept for payment.
   - **Relay Work Time:** Specify how long the relay should be activated in seconds. This can range from one second (for simulating a button press) to several minutes or hours.

      <img src="https://github.com/renat2985/toncoin_payment_sonoff/blob/main/doc/APFull.png" width="500px">

3. **Reset Settings:**
      To reset the device to its factory settings, follow these steps:
      1.	Press the Sonoff button on the device.
      2.	The device will reboot.
      3.	After rebooting, a Wi-Fi access point named Crypto Sonoff will appear.
      The device is now ready for reconfiguration.

_Please note, if the blue LED starts flashing, it is a signal that something went wrong. You might have entered your Toncoin wallet incorrectly. It could also indicate an incorrect CoinMarketCap API. If you are using the standard API (without changes), it may have exceeded the limit, and you might need to create your own CoinMarketCap API. The WiFi signal has disappeared. Another reason could be that the trial period of the software has expired._
     
### Instructions for Self-Assembly:

For self-assembly you will need any of these devices: SONOFF OLD, [SONOFF RF R2, SONOFF BASICR2](https://github.com/renat2985/toncoin_payment_sonoff/blob/main/doc/flash_gpio_r2.png), [SONOFF Mini R1, SONOFF Mini R2](https://github.com/renat2985/toncoin_payment_sonoff/blob/main/doc/flash_gpio_mini_r2.png), [SONOFF S26, SONOFF S26R2](https://github.com/renat2985/toncoin_payment_sonoff/blob/main/doc/flash_gpio_s26.jpg).

- A programmer, such as USB to TTL / PL230
- A soldering iron and wires

  <img src="https://github.com/renat2985/toncoin_payment_sonoff/blob/main/doc/flash_gpio4.png" width="500px">


We have added support for SONOFF devices based on the ESP32 (Dual R3, Mini R4, Basic R4, POW, THR316), but most of them have not yet undergone full testing. If you encounter any issues, please contact us, and we will do our best to assist you.
On devices with ESP8266 (Mini R1, Mini R2, S26, S26R2), all GPIO (pins) remained unchanged, and no configuration is required. However, with ESP32, many GPIO pins have changed depending on the device model. We decided not to release separate firmware for each model as it would make maintenance more complicated. Therefore, you will need to manually configure the GPIO for your device.
To do this, after the device name, add a colon (:) followed by the GPIO for the relay, then the GPIO for the reset button, and finally the GPIO for the LED.
Below, you will find a list of devices and their corresponding GPIO settings. Simply copy the necessary configurations, and the device should work.
```
Dual R3:27,0,13
Mini R4:26,0,19
Mini R4M:4,9,19
Basic R4:4,9,6
POW 16a:13,0,18
POW 20a:4,0,18
POW Ring:21,0,13
THR316:21,0,15
```

Good luck! If you have any questions, don't hesitate to reach out.


# Web installer (recommended)
## [https://renat2985.github.io/toncoin_payment_sonoff/](https://renat2985.github.io/toncoin_payment_sonoff/)


### For Advanced Users: Firmware Instructions via Programmer
### Specification [ESP8266 toncoin_payment_sonoff.ino.bin](https://github.com/renat2985/toncoin_payment_sonoff/raw/main/build/esp8266.esp8266.generic/toncoin_payment_sonoff.ino.bin) file
```
  -  Module: Generic ESP8266 Module
  -  Flash Size: 1M
  -  CPU Frequency: 80Mhz
  -  Flash Mode: DOUT
  -  Flash Frequency: 40Mhz

  { "path": "./build/esp8266.esp8266.generic/toncoin_payment_sonoff.ino.bin", "offset": 0 }
```

### Specification [ESP32 toncoin_payment_sonoff.ino.bin](https://github.com/renat2985/toncoin_payment_sonoff/raw/main/build/esp32.esp32.esp32/toncoin_payment_sonoff.ino.bin), [ESP32C3 toncoin_payment_sonoff.ino.bin](https://github.com/renat2985/toncoin_payment_sonoff/raw/main/build/esp32.esp32.esp32c3/toncoin_payment_sonoff.ino.bin), [ESP32S3 toncoin_payment_sonoff.ino.bin](https://github.com/renat2985/toncoin_payment_sonoff/raw/main/build/esp32.esp32.esp32s3/toncoin_payment_sonoff.ino.bin) file
```
  { "path": "./build/esp32.esp32.esp32*/toncoin_payment_sonoff.ino.bootloader.bin", "offset": 0 },
  { "path": "./build/esp32.esp32.esp32*/toncoin_payment_sonoff.ino.partitions.bin", "offset": 32768 },
  { "path": "./build/esp32.esp32.esp32*/boot_app0.bin", "offset": 57344 },
  { "path": "./build/esp32.esp32.esp32*/toncoin_payment_sonoff.ino.bin", "offset": 65536 }
```

### ESP8266 NodeMCU Flasher
https://github.com/nodemcu/nodemcu-flasher
Download Release: [Win32](https://github.com/nodemcu/nodemcu-flasher/blob/master/Win32/Release/ESP8266Flasher.exe) or [Win64](https://github.com/nodemcu/nodemcu-flasher/blob/master/Win64/Release/ESP8266Flasher.exe).

## :battery: Donation

If you like this project, you can buy me a cup of coffee :coffee:

<img src="https://github.com/renat2985/renat2985/raw/main/donate/donate.png" width="100%">

- PayPal [https://www.paypal.me/RKevrels](https://www.paypal.me/RKevrels/5)