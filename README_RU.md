
# Оплата ваших услуг через TonCoin

 Удобный и быстрый способ внедрения платных услуг с использованием криптовалюты TonCoin. Процесс простой: Вы открываете любой крипто кошелек, сканируете QR-код (Его можно например распечатать на листике с необходимой суммой), переводите эту указанную сумму, и как только платеж будет получен, реле активируется и включит ваш прибор на заданное вами время. Это может быть любой прибор, от чайника, кофемашины и лампочки до включения электричества в помещение или любом другом месте.

Вы можете собрать устройство самостоятельно или попросить это сделать для вас. Для заказа готового устройства свяжитесь через [Telegram](https://t.me/ESPiotDevice), [Skype](https://skype:renat2985?chat), [Discord](https://discord.com/invite/zaGaDuGe).
У нас есть похожий проект с экраном, [посмотри](https://github.com/renat2985/toncoin_payment).


[![IMAGE ALT TEXT HERE](https://github.com/renat2985/toncoin_payment_sonoff/blob/main/doc/intro3.png)](https://www.youtube.com/watch?v=zKdVJmzJNLM&list=PL6NJTNxbvy-LpsI6D_1RM6v5YWDvsm5j4)

### Основные функции:

1. **Подключение устройства:**
   - При первом включении, если устройство не находит роутер, или если вы нажмёте кнопку на самом ESP, оно создаст точку доступа с именем “TonCoin payments”.
     
     <img src="https://github.com/renat2985/toncoin_payment_sonoff/blob/main/doc/WiFi.png" width="200px">
   - Подключитесь к этой точке (пароль не требуется) и откройте браузер, где введите http://192.168.4.1. Обычно после подключения к Wi-Fi автоматически откроется Activ portal, который перенаправит вас на нужную страницу.
     
     <img src="https://github.com/renat2985/toncoin_payment_sonoff/blob/main/doc/AP1.png" width="300px">
   - Нажмите "Configure WiFi" для настройки.

2. **Настройка устройства:**
   - **Роутер и пароль:** Введите данные для подключения к вашему Wi-Fi.
   - **Device Name:** Укажите имя устройства, например, "Buy coffee". Вы можете опционально добавить в это поле GPIO пины. Пример: Device_name:12,11,22, где Device_name — это название устройства, а 12,11,22 — это соответствующие номера пинов для реле, кнопка сброса и светодиода (RELAY_PIN,BUTTON_PIN,LED_PIN).
   - **Your Toncoin Wallet:** Введите адрес вашего кошелька для приема платежей.
   - **CoinMarketCap API:** Это сервис, который позволяет получать текущую цену TonCoin в фиатной валюте. Для тестирования можно не менять API, но если вы планируете использовать устройство на постоянной основе, настоятельно рекомендуется зарегистрироваться на сайте [CoinMarketCap](https://coinmarketcap.com/api/) и получить свой собственный API. Т.к. бесплатная версия позволяет делать до 10 000 запросов в месяц на получение цены. Для 10 устройств этого вполне достаточно, но если наше API будет использоваться большим количеством устройств, не все смогут получать актуальную цену, и в результате оплата может не пройти.
   - **Сurrency:** Выберите валюту, в которой хотите получать оплату (EUR, USD, RUB, BYN, BGN, GBP и др.). Это необходимо для автоматической конвертации суммы в TonCoin на основе текущего курса, который обновляется каждый час через coinmarketcap.com.
   - **Service Currency Price:** Укажите цену в выбранной валюте, которую клиент должен оплатить.
   - **Payment Tolerance:** В этой ячейке указывается допустимая погрешность в цене. Поскольку стоимость Ton постоянно колеблется, здесь нужно указать диапазон отклонений (одной цифрой), который вы готовы принять при оплате.
   - **Relay Work Time:** Укажите, на сколько секунд должно включиться реле. Это может быть от одной секунды (например, для имитации нажатия кнопки) до нескольких минут или часов.

   _Обратите внимание, если начал мигать синий светодиод — это сигнал, что что-то пошло не так. Возможно, вы неправильно написали свой Toncoin кошелек. Также это может указывать на неправильный API от CoinMarketCap. Если вы используете стандартный API (не меняли его), возможно, он превысил лимит, и вам нужно сделать собственный [CoinMarketCap API](https://coinmarketcap.com/api/). Плохой сигнал WiFi. Еще одна причина может быть в том, что закончился пробный период программного обеспечения._
     
  <img src="https://github.com/renat2985/toncoin_payment_sonoff/blob/main/doc/APFull.png" width="500px">





### Инструкции для самостоятельной сборки:

Для самостоятельной сборки вам потребуется любое из этих устройств: SONOFF OLD, [SONOFF RF R2, SONOFF BASICR2](https://github.com/renat2985/toncoin_payment_sonoff/blob/main/doc/flash_gpio_r2.png), [SONOFF Mini R1, SONOFF Mini R2](https://github.com/renat2985/toncoin_payment_sonoff/blob/main/doc/flash_gpio_mini_r2.png), [SONOFF S26, SONOFF S26R2](https://github.com/renat2985/toncoin_payment_sonoff/blob/main/doc/flash_gpio_s26.jpg).

Дополнительно вам понадобятся:
- Программатор, например USB to TTL / PL230
- Паяльник и провода

  <img src="https://github.com/renat2985/toncoin_payment_sonoff/blob/main/doc/flash_gpio4.png" width="500px">


Мы добавили поддержку устройств SONOFF на базе ESP32 (Dual R3, Mini R4, Basic R4, POW, THR316), но большинство из них пока не прошло полное тестирование. Если у вас возникнут проблемы, пожалуйста, свяжитесь с нами, и мы постараемся помочь.
На устройствах с ESP8266 (Mini R1, Mini R2, S26, S26R2) все GPIO (пины) оставались неизменными. Вам не нужно ничего настраивать. Однако на ESP32 многие пины изменились в зависимости от модели устройства. Мы решили не выпускать отдельные прошивки для каждой модели, так как это усложнило бы их поддержку. Поэтому вам нужно будет вручную настроить GPIO для вашего устройства. Для этого после имени устройства добавьте : далее сначала GPIO реле, затем для GPIO кнопки сброса, и в конце GPIO для светодиода (LED).
Ниже вы найдете список устройств и соответствующих им GPIO. Просто скопируйте нужные настройки, и устройство должно заработать.
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

Удачи! Если у вас возникнут вопросы, не стесняйтесь обращаться ко мне.


# Web installer (recommended)
## [https://renat2985.github.io/toncoin_payment_sonoff/](https://renat2985.github.io/toncoin_payment_sonoff/)


### Для совсем профи инструкция для прошивки через программатор
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
  { "path": "./build/esp32.esp32.esp32*/toncoin_payment_sonoff.ino.bootloader.bin", "offset": 4096 },
  { "path": "./build/esp32.esp32.esp32*/toncoin_payment_sonoff.ino.partitions.bin", "offset": 32768 },
  { "path": "./build/esp32.esp32.esp32*/boot_app0.bin", "offset": 57344 },
  { "path": "./build/esp32.esp32.esp32*/toncoin_payment_sonoff.ino.bin", "offset": 65536 }
```

### ESP8266 NodeMCU Flasher
https://github.com/nodemcu/nodemcu-flasher
Download Release: [Win32](https://github.com/nodemcu/nodemcu-flasher/blob/master/Win32/Release/ESP8266Flasher.exe) or [Win64](https://github.com/nodemcu/nodemcu-flasher/blob/master/Win64/Release/ESP8266Flasher.exe).



## :battery: Donation

If you like this project, you can give me a cup of coffee :coffee:

<img src="https://github.com/renat2985/toncoin_payment_sonoff/blob/main/doc/donate.png" width="700px">

- PayPal [https://www.paypal.me/RKevrels](https://www.paypal.me/RKevrels/5)