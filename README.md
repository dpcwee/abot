## A-Bot

**Никаких других официальных сайтов с репозиториями и контактами, кроме GitHub и Telegram, у проекта нет!**  

Бесплатный спотовый бот для алгоритмической мультивалютной торговли на бирже Binance.    

![](./screen/img-1.png)  
![](./screen/img-2.png)  

**ВНИМАНИЕ! БОТ РАБОТАЕТ ТОЛЬКО НА АККАУНТАХ, ЗАРЕГИСТРИРОВАННЫХ ПО РЕФЕРАЛЬНОЙ ССЫЛКЕ РАЗРАБОТЧИКА!  
Binance: [Регистрация по реферальной ссылке](https://binance.com/ru/register?ref=C2GCPXJA)  
Referal ID: `C2GCPXJA`**  
Если у Вас возникли трудности с мультиаккаунтом, свяжитесь с **@dpcwee** в Telegram

### Поддержать печенькой:
`0x7680b3c00923fe29c62fb157e69187a918a076cd` — сеть BEP20 для любой крипты на Binance  

### Контакты:  
*[Официальный чат Telegram](https://t.me/abot_chat)* — для обсуждений, связи с разработчиками и развития проекта  

### Форумы:
*[Cryptotalk](https://cryptotalk.org/topic/332721-%D0%B1%D0%B5%D1%81%D0%BF%D0%BB%D0%B0%D1%82%D0%BD%D1%8B%D0%B9-%D1%82%D0%BE%D1%80%D0%B3%D0%BE%D0%B2%D1%8B%D0%B9-%D0%B1%D0%BE%D1%82-%D0%B4%D0%BB%D1%8F-binance/)* *[Bits.Media](https://forum.bits.media/index.php?/topic/178120-a-bot-%D0%B1%D0%B5%D1%81%D0%BF%D0%BB%D0%B0%D1%82%D0%BD%D1%8B%D0%B9-%D0%B1%D0%BE%D1%82-%D0%B4%D0%BB%D1%8F-binance/)*

### Полезные ссылки:
*[Google Cloud](https://dpcwee.medium.com/%D0%BF%D0%BE%D0%BB%D1%83%D1%87%D0%B0%D0%B5%D0%BC-%D0%B1%D0%B5%D1%81%D0%BF%D0%BB%D0%B0%D1%82%D0%BD%D1%8B%D0%B5-6-%D0%BC%D0%B5%D1%81%D1%8F%D1%86%D0%B5%D0%B2-google-cloud-1da76f2f62fd)* — гайд на получение бесплатного сервера для бота  
*[Screen команды для сервера](http://itautsors.ru/ispolzuem-komandu-screen-v-linux)* — работа бота в фоновом режиме на линуксе  
*[Калькулятор усреднений](https://ihakimov.ru/calcmid/)* — калькулятор усреднений  
*[Сводная эксель-таблица доходности](https://mega.nz/file/gUwQAQDT#ooSVkOJapIkx4_RN22a3O98upz3DFDftPLEkZseLHrU)* — Таблица для расчёта примерной будущей доходности бота исходя из текущих значений прибыльности  
*[Лесенка усреднений](https://mega.nz/file/NIpAmABb#skqeEX9i45pSUV53A-R1jS_4zXcXJHN3Z00wM0Uwox8)* — Расчёт будущих усреднений, исходя из параметров buy_down и step_aver  
*[Сложный процент](https://wpcalc.com/slozhnyj-procent/)* — Расчёт доходности от вложенных средств за выбранный период  

### Описание стратегии:
Бот работает по стратегии усреднения. Суть стратегии заключается в снижении средней цены входа в актив путём увеличения веса позиции в случае, если рыночная стоимость актива снижается по отношению к текущей стоимости ордера. Иными словами, при входе в сделку бот, исходя из пользовательских торговых настроек, размещает ордер на продажу с заданным процентом профита, но если стоимость актива падает по отношению к первой покупке, не достигнув ордера на продажу, и опускается ниже заданного значения в %, бот отменяет ордер на продажу, докупает определённое количество монет, которое всегда больше количества монет в предыдущем отменённом ордере, и размещает новую заявку на продажу по цене (`новая средняя цена покупки` + `% желаемой прибыли`). Таким образом, при падении рыночной стоимости актива бот постоянно анализирует текущие ордера и рыночные данные, сопоставляя условия настроек торговой стратегии и биржевую активность, и докупает монеты, увеличивая их общий объём и снижая новую цену продажи.

![](./screen/img-9.png)  

### Обозначения статуса ордеров:
![](./screen/img-12.png) — Ордер на покупку исполнен  
![](./screen/img-13.png) — Размещён ордер на продажу  
![](./screen/img-14.png) — Ордер на продажу исполнен, позиция закрыта  
![](./screen/img-15.png) — Ордер на продажу отменён для усреднения  
![](./screen/img-16.png) — Ордер на продажу отменён и активирован трейлинг-стоп  
![](./screen/img-17.png) — Частичная продажа позиции трейлингом по маркету  
![](./screen/img-18.png) — Полная продажа позиции по трейлингу, позиция закрыта  

### Ключи команд:
* `-s` — Запуск бота  
* `-o` — Посмотреть все открытые ботом позиции на бирже  
* `-m` — Удалить, добавить или сбросить параметры разрешённого для торговли списока монет  
* `-k` — Изменить настройки API ключей от Binance или параметры Telegram-уведомлений  
* `-p` — Изменить параметры торговли и работы бота  
* `-h` — Сбросить всю историю торговли по парам из разрешённого для торговли списка монет. Открытые позиции на бирже не будут отменены, но удалятся из базы данных бота  
* `-i` — Удаление торговой статистики обнулит показатели прибыли и успешных сделок, совершенных ботом  
* `-e` — Безопасный выход из бота (в главном меню)/безопасная остановка торговли и выход в главное меню (при работающем боте)

### Обозначения информационной консоли:
* `s` — Время исполнения последнего цикла скрипта в секундах  
* `•` — Индикатор разницы времени бота и сервера биржи, условный пинг  
  * `Зелёный` — Стабильное соединение  
  * `Жёлтый` — Имеется незначительное отставание  
  * `Красный` — Данный цвет сигнализирует о большой задержке между временем событий на бирже и сообщениями об этих событиях в потоке веб-сокета  
* `М` — Максимальное количество одновременно открытых позиций, автоматически регулирующееся ботом при соответствующей включенной настройке
* `Б` — Свободный баланс
* `Л` — Самый близкий к продаже актив (`название монеты` `разница рыночной цены и цены ордера на продажу в %` (`цена ордера`))  
* `Д` — Суточная дельта пар из белого списка в процентах, условно обозначающая тренд рынка  

![](./screen/img-8.png)  

### Правила использования:
* Для того, чтобы бот начал работу с ручным ордером, актив должен находится в разрешённом списке монет и на нём не должно быть уже открытых ордеров  
* Если покупка актива исполнилась удачно и бот взял в работу Ваш ордер, не пытайтесь выставить новые ордера на покупку в надежде, что бот снова начнёт работу с ними. Если бот подхватил ручной ордер, то дальнейшие действия с монетой он будет производить самостоятельно, не обращая внимания на ваши заявки по ней  
* Не дублируйте ручные ордера для подхватывания ботом. Если хотите войти в сделку — разместите один ордер на покупку. Если Вы хотите переставить этот ордер — сначала отмените его и только после этого создайте новую заявку на покупку  
* Не распоряжайтесь активами, которые находятся в работе у бота. Если видите свободный баланс — проверьте монету в терминале, возможно, бот работает по этой монете с активированным трейлингом  

### Запуск:
*Windows (только 10-я 64-битная)*: Скачайте **[A-Bot.exe](https://github.com/dpcwee/abot/releases/latest)** и запускаете программу  
*Linux (минимум 18.04)*: Скачайте **[A-Bot-BTC](https://github.com/dpcwee/abot/releases/latest)**  
(`wget https://github.com/dpcwee/abot/releases/download/{ВЕРСИЯ}/A-Bot`,  где вместо ***{ВЕРСИЯ}*** укажите последнюю версию),  
дайте ему права командой `chmod 755 A-Bot`, после чего запустите командой `./A-Bot`  

### Обновление:
*Windows*: Скачиваете новую версию в директорию со старым файлом (с перезаписью)  
*Linux*: В директории с ботом вводите команду на удаление старой версии `rm A-Bot`,  
затем вводите команду `wget https://github.com/dpcwee/abot/releases/download/{ВЕРСИЯ}/A-Bot`,  
где вместо ***{ВЕРСИЯ}*** указываете последнюю версию, после чего даёте права файлу `chmod 755 ./A-Bot`  
и запускаете его командой `./A-Bot`

### Работа с screen:
1) При первом запуске/перезагрузке сервера вводим `screen -S <name_screen>` (например `screen -S abot`), попадаем сразу в новый screen и запускаем `./A-Bot`  
2) Запустили бота и можете разрывать соединение с сервером, бот будет работать в фоновом режиме в созданном скрине  
3) Выход из скрина осуществляется командой Ctrl + A, затем отдельно D  
4) При повторном подключении к серверу с существующими скринами вводим `screen -x` (подключение к единственному скрину) или `screen -x <name_screen>`, если их несколько, попадая в нужный скрин  
5) В случае перезагрузки сервера (reboot или другой апокалипсис), подключаемся к серверу и повторяем описанный цикл с 1-го пункта  

### Параметры API настройки:
* API ключи — пара API ключей для обращения к Binance ([API-Management](https://www.binance.com/ru/usercenter/settings/api-management))  
* Реферальный ID пользователя — ID Вашего аккаунта на Binance, зарегистрированного по нашему приглашению ([Referal ID](https://www.binance.com/ru/my/dashboard) — слева вверху в личном кабинете)  
* BEP20-кошелёк — адрес человека на Binance в сети Binance Smart Chain (BSC), который рассказал Вам о боте  
* Уведомления в Telegram — при включенном параметре отправляет уведомления в группу/канал в случае закрытия позиции  
  * API-Token — токен, выданный BotFather ([@BotFather](https://t.me/botfather)) при создании Telegram-бота  
  * @name — <@name> или <chat_id> для отправки уведомлений. Бот, созданный на предыдущем шаге, должен состоять в группе/канале и быть её администратором с включенными возможностями публикации сообщений и изменения профиля  

![](./screen/img-7.png)  

### Инструкция для включения уведомлений в Telegram:
1. Обращаемся к [BotFather'у](https://t.me/botfather) в Telegram и создаём нового бота (вводим команду /newbot или выбираем её через контекстное меню)  
2. Вводим любое имя бота  
3. Далее придумываем уникальный юзернейм для бота, который оканчивается на 'bot' (например ***exambot_abot***)  
4. При успешном создании BotFather пришлёт нам сообщение, в котором будет указана ссылка на созданного бота и его API token (например 1432166624:AAHSlGrfaFP21BXLihyGXPiUv_urjarJhty). Запишите token в приватное место  
5. Создайте публичный или частный канал (Меню -> Создать канал), придумайте его название. Далее, если канал будет публичным, придумайте ему @name (например ***test_push_abot_channel*** (@name — это название в ссылке t.me/test_push_abot_channel после слэша)), добавьте в канал созданного ранее бота ***exambot_abot*** и сделайте его администратором с возможностью изменения профиля канала и публикацией сообщений (первые две галочки возможности администратора). Если же канал будет приватным, то Вам нужно будет получить его chat_id (напишите в свой канал любое сообщение и перешлите его этому боту [@userinfobot](https://telegram.me/userinfobot). В ответ Вы получите сообщение с его chat_id. Оно будет выглядеть примерно как "-100XХХХХХХХХХ")  
6. Запустите A-Bot и в настройках параметров API и Telegram включите Telegram-уведомления, затем введите API token, который выдал Вам BotFather и @name/chat_id Вашего канала, где в администраторах находится Telegram-Bot, созданный на 5 этапе (***@test_push_abot_channel***)  
Теперь каждый раз, когда бот полностью закрывает позицию на продажу, Вы будете получать уведомление в Ваш канал!

![](./screen/img-3.png)  
![](./screen/img-4.png)  

### Торговые параметры:
* `name_list` [str] — Название текущего пресета настроек (в случае команды -sve сохранится в список настроек с этим именем) (например main)  
* `min_bnb` [min >= 0.01] — Минимальный свободный баланс BNB, ниже которого бот будет докупать минимально допустимое количество BNB по рыночной цене (например 0.03)  
* `min_balance` [min >= 0] — Не покупать/усреднять позиции, если свободный баланс составляет меньше заданного % от общего баланса (например 15)  
* `min_order` [min >= 1] — Множитель размера первого ордера на покупку. Стоимость первого ордера будет рассчитываться, как **минимальный допустимый размер ордера на бирже * min_order** (например 1.2). На USDT это 10$, на BTC это 0.0001. Лимиты можно найти [здесь](https://www.binance.com/ru/trade-rule)  
* `min_price` [min >= 0.00000001 USDT] — Минимальная рыночная стоимость монеты, эквивалент в USDT которой равен **рыночному курсу монеты в USD**, ниже которого бот не будет открывать новые сделки по этой паре, лишь усреднять, если стоит ордер на продажу (например 0.05)  
* `daily_percent` [-100 < min < 99999] — Ниже какого значения должнен упасть показатель % суточного изменения цены на бирже, чтобы бот осуществил первую покупку по паре (например -5)  
* `sell_up` [min > 0.15] — Желаемый % прибыли от продажи без учёта суточной дельты и трейлинг-стопа (например 1.65)  
* `buy_down` [min < 0] — На сколько % должна упасть рыночная цена актива по отношению к цене его последней покупки, чтобы бот усреднил позицию (например -5)  
* `max_trade_pairs` — Допустимое количество позиций на продажу, которое бот может держать одновременно открытыми (например 20). Если количество открытых ботом ордеров станет равно или больше **max_trade_pairs**, бот перестанет совершать новые покупки (кроме усреднений)  
  * `-1` [-1] — Не ограничивать количество одновременно торгуемых ботом пар  
  * `0` [0] — Работать только с уже открытыми ордерами и не совершать новые покупки  
  * `1 и более` [1-999] — Указать максимальное количество позиций вручную  
* `auto_trade_pairs` [y/n] — Разрешить боту автоматически регулировать количество разрешённых пар? Если ***Y***, бот будет автоматически корректировать максимальное количество одновременно торгуемых пар, если предыдущий параметр настроек задан пользователем вручную от 1 до 999  
* `delta_percent` [y/n] — Использовать общую рыночную дельту суточной цены? Если ***Y***, суммировать торговые параметры с общей суточной дельтой (направлением рынка) по отобранным парам из белого списка. Данный параметр сделает стратегию более гибкой, но может уменьшить прибыль  
* `num_aver` [y/n] — Использовать сетку усреднений? Если ***Y***, то при усреднении бот будет увеличивать процент падения цены, необходимый для нового усреднения актива, на **buy_down** + (**1** + **количество усреднений**) * **step_aver**  
  * `step_aver` [%] — Шаг увеличения сетки. На сколько процентов увеличивать последующую разницу рыночной цены и цены последней покупки для усреднения (например 1.35)  
* `quantity_aver` [min >= 1] — Множитель размера усреднения от текущего веса позиции (например 2). Иными словами, при усреднении бот будет покупать **текущее количество монет** * **quantity_aver**, тем самым новая позиция будет равна **текущее количество монет** * **quantity_aver** + **текущее количество монет**. Не рекомендуется делать этот параметр ниже 2  
* `trailing_stop` [y/n] — Использовать трейлинг-стоп? Если ***Y***, отодвигать цену продажи в зависимости от движения цены актива. С включенным трейлингом позиция не закрывается сразу, а продаётся частями **trailing_part** на приближенных к максимальным значениям ценам, чтобы увеличить потенциальную прибыль, либо закрывается полностью при падении цены и её приближении к средней цене покупки. Данный параметр сделает стратегию более гибкой, но может уменьшить прибыль 
  * `trailing_percent` [min > 0] — При каком падении от локального хай-уровня цены активировать трейлинг-стоп для частичной/полной продажи (например 0.25)  
  * `trailing_part` [100 >= min >= 0] — Размер частичной продажи по трейлингу в % от общего веса позиции (например 10)  
  * `trailing_price` [min >= 0.00000001 USDT] — Активировать трейлинг-стоп только на активах стоимостью в эквиваленте к USD выше заданного процента. Это позволяет избегать минусовых сделок из-за слишком большого процента спреда монет с низкой стоимостью (например 0.2)  
* `user_order` [y/n] — Работа с пользовательскими ордерами после ручной покупки. Если ***Y***, то в случае покупки пользователем монеты из разрешённого списка бот автоматически поставит на продажу купленное количество монет и будет работать с этой парой так же, как и в остальных случаях, ориентируясь на торговые настройки. Также уже открытые ордера можно будет усреднять вручную: для этого во время работы бота купить нужное количество монет, после чего бот отменит ордер на продажу, рассчитает новые данные и выставит ордер по новой цене  
* `fiat_currencies` [RUB UAH ...] — Если включены уведомления в Telegram, то ежедневная статистика торгов будет рассчитываться в этих валютах вместе с **quote_asset**  
* `quote_asset` [USDT BTC ...] — Котируемые валюты для торговли (то есть те монеты, в паре к КОТОРЫМ торгуются монеты из разрешённого списка (ADA/**USDT**, ADA/**BTC**), а не которые торгуются к ним)  
* `double_asset` [y/n] — Если ***Y***, бот сможет покупать одну и ту же монету на нескольких котируемых активах (**ADA**/USDT и **ADA**/BTC)  

![](./screen/img-5.png)  

### Пример работы бота:

![](./screen/img-6.png)  
![](./screen/img-10.png)  
