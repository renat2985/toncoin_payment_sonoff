
# Оплата ваших услуг через TonCoin

 Удобный и быстрый способ внедрения платных услуг с использованием криптовалюты TonCoin. Процесс простой: Вы открываете любой крипто кошелек, сканируете QR-код (Его можно например распечатать на листике с необходимой суммой), переводите эту указанную сумму, и как только платеж будет получен, реле активируется и включит ваш прибор на заданное вами время. Это может быть любой прибор, от чайника, кофемашины и лампочки до включения электричества в помещение или любом другом месте.

Вы можете собрать устройство самостоятельно или попросить это сделать меня для вас. Для заказа готового устройства свяжитесь через [Telegram](https://t.me/ESPiotDevice), Skype: renat2985

<img src="https://github.com/renat2985/toncoin_payment_sonoff/blob/main/doc/intro2.png">

### Основные функции:

1. **Подключение устройства:**
   - При первом включении, если устройство не находит роутер, или если вы нажмёте кнопку на самом ESP, оно создаст точку доступа с именем “TonCoin payments”.
     
     <img src="https://github.com/renat2985/toncoin_payment_sonoff/blob/main/doc/WiFi.png" width="200px">
   - Подключитесь к этой точке (пароль не требуется) и откройте браузер, где введите http://192.168.4.1. Обычно после подключения к Wi-Fi автоматически откроется Activ portal, который перенаправит вас на нужную страницу.
     
     <img src="https://github.com/renat2985/toncoin_payment_sonoff/blob/main/doc/AP1.png" width="300px">
   - Нажмите "Configure WiFi" для настройки.

2. **Настройка устройства:**
   - **Роутер и пароль:** Введите данные для подключения к вашему Wi-Fi.
   - **Device Name:** Укажите имя устройства, например, "Buy coffee".
   - **Your Toncoin Wallet:** Введите адрес вашего кошелька для приема платежей.
   - **Сurrency:** Выберите валюту, в которой хотите получать оплату (EUR, USD, RUB, BYN, BGN, GBP и др.). Это необходимо для автоматической конвертации суммы в TonCoin на основе текущего курса, который обновляется каждый час через coinmarketcap.com.
   - **Service Currency Price:** Укажите цену в выбранной валюте, которую клиент должен оплатить.
   - **Payment Tolerance:** В этой ячейке указывается допустимая погрешность в цене. Поскольку стоимость Ton постоянно колеблется, здесь нужно указать диапазон отклонений (одной цифрой), который вы готовы принять при оплате.
   - **Relay Work Time:** Укажите, на сколько секунд должно включиться реле. Это может быть от одной секунды (например, для имитации нажатия кнопки) до нескольких минут или часов.
     
     <img src="https://github.com/renat2985/toncoin_payment_sonoff/blob/main/doc/APFull.png" width="500px">





### Инструкции для самостоятельной сборки:

Для самостоятельной сборки устройства вам потребуется устойство sonoff. 
Дополнительно вам понадобятся:
- Программатор, например USB to TTL / PL230
- Паяльник и провода

  <img src="https://github.com/renat2985/toncoin_payment_sonoff/blob/main/doc/flash_gpio4.png" width="500px">


Удачи! Если у вас возникнут вопросы, не стесняйтесь обращаться ко мне.


# Web installer (recommended)
## [https://renat2985.github.io/toncoin_payment_sonoff/](https://renat2985.github.io/toncoin_payment_sonoff/)



### Для совсем профи инструкция для прошивки через программатор
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

If you like this project, you can give me a cup of coffee :coffee:

<img src="https://github.com/renat2985/toncoin_payment_sonoff/blob/main/doc/donate.png" width="700px">

- PayPal [https://www.paypal.me/RKevrels](https://www.paypal.me/RKevrels/5)