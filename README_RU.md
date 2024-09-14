
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
   - **Device Name:** Укажите имя устройства, например, "Buy coffee".
   - **Your Toncoin Wallet:** Введите адрес вашего кошелька для приема платежей.
   - **CoinMarketCap API:** Это сервис, который позволяет получать текущую цену TonCoin в фиатной валюте. Для тестирования можно не менять API, но если вы планируете использовать устройство на постоянной основе, настоятельно рекомендуется зарегистрироваться на сайте [CoinMarketCap](https://coinmarketcap.com/api/) и получить свой собственный API. Т.к. бесплатная версия позволяет делать до 10 000 запросов в месяц на получение цены. Для 10 устройств этого вполне достаточно, но если наше API будет использоваться большим количеством устройств, не все смогут получать актуальную цену, и в результате оплата может не пройти.
   - **Сurrency:** Выберите валюту, в которой хотите получать оплату (EUR, USD, RUB, BYN, BGN, GBP и др.). Это необходимо для автоматической конвертации суммы в TonCoin на основе текущего курса, который обновляется каждый час через coinmarketcap.com.
   - **Service Currency Price:** Укажите цену в выбранной валюте, которую клиент должен оплатить.
   - **Payment Tolerance:** В этой ячейке указывается допустимая погрешность в цене. Поскольку стоимость Ton постоянно колеблется, здесь нужно указать диапазон отклонений (одной цифрой), который вы готовы принять при оплате.
   - **Relay Work Time:** Укажите, на сколько секунд должно включиться реле. Это может быть от одной секунды (например, для имитации нажатия кнопки) до нескольких минут или часов.
     
     <img src="https://github.com/renat2985/toncoin_payment_sonoff/blob/main/doc/APFull.png" width="500px">





### Инструкции для самостоятельной сборки:

Для самостоятельной сборки вам потребуется любое из этих устройств: SONOFF OLD, [SONOFF RF R2, SONOFF BASICR2](https://github.com/renat2985/toncoin_payment_sonoff/blob/main/doc/flash_gpio_r2.png), [SONOFF Mini R1, SONOFF Mini R2](https://github.com/renat2985/toncoin_payment_sonoff/blob/main/doc/flash_gpio_mini_r2.png).
Дополнительно вам понадобятся:
- Программатор, например USB to TTL / PL230
- Паяльник и провода

  <img src="https://github.com/renat2985/toncoin_payment_sonoff/blob/main/doc/flash_gpio4.png" width="500px">


Удачи! Если у вас возникнут вопросы, не стесняйтесь обращаться ко мне.


# Web installer (recommended)
## [https://renat2985.github.io/toncoin_payment_sonoff/](https://renat2985.github.io/toncoin_payment_sonoff/)



### Для совсем профи инструкция для прошивки через программатор
### Specification [toncoin_payment_sonoff.ino.bin](https://github.com/renat2985/toncoin_payment_sonoff/raw/main/build/esp8266.esp8266.generic/toncoin_payment_sonoff.ino.bin) file
```
  -  Module: Generic ESP8266 Module
  -  Flash Size: 1M
  -  CPU Frequency: 80Mhz
  -  Flash Mode: DOUT
  -  Flash Frequency: 40Mhz
  -  Upload Speed: 921600
```

### NodeMCU Flasher
https://github.com/nodemcu/nodemcu-flasher
Download Release: [Win32](https://github.com/nodemcu/nodemcu-flasher/blob/master/Win32/Release/ESP8266Flasher.exe) or [Win64](https://github.com/nodemcu/nodemcu-flasher/blob/master/Win64/Release/ESP8266Flasher.exe).



## :battery: Donation

If you like this project, you can give me a cup of coffee :coffee:

<img src="https://github.com/renat2985/toncoin_payment_sonoff/blob/main/doc/donate.png" width="700px">

- PayPal [https://www.paypal.me/RKevrels](https://www.paypal.me/RKevrels/5)