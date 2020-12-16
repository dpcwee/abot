### A-Bot
##### Last version 1.02

Бесплатный спотовый бот для алгоритмической торговли на бирже Binance.  
На данный момент поддерживается торговля только на парах к BTC.  

![](img-1.png)  

**ВНИМАНИЕ! БОТ РАБОТАЕТ ТОЛЬКО НА АККАУНТАХ, ЗАРЕГИСТРИРОВАННЫХ ПО РЕФЕРАЛЬНОЙ ССЫЛКЕ РАЗРАБОТЧИКА!  
Binance: [Регистрация по реферальной ссылке](https://www.binance.com/en/register?ref=NYGPPWD2)  
Referal ID: `NYGPPWD2`**  

#### Ключи команд:
* `-s` — Запуск бота  
* `-h` — Сбросить всю историю торговли по парам из разрешённого для торговли списка монет. Открытые позиции на бирже не будут отменены, но удаляться из базы данных бота  
* `-m` — Удалить или добавить монету в разрешённый для торговли список бота  
* `-p` — Удалить торговые параметры бота и присвоить новые значения  
* `-k` — Удалить все имеющиеся у бота API ключи, включая настройки Telegram  

#### Рекомендации:
Для того, чтобы бот работал корректно, пользователю не рекомендуется вмешиваться в торговлю по парам из его белого списка. Бот использует уникальный клиентский ID и на него не влияют ордера пользователя, совершенные посредством веб-сайта Binance или сторонних программ, имеющих доступ к торговому аккаунту, но при этом пользователь может ошибочно распорядиться активами, задействованными в работе бота, и, т.к. торговые данные по работе программы храняться в локальной базе данных, новый запрос бота к Binance может не сработать, если фактические данные баланса активов отличаются от тех, которые храняться локально ботом, что повлечёт за собой сброс истории по торговой паре и обнуление статистики по ней.  

В идеале, бота рекомендуется подключить к второстепенному аккаунту, на котором пользователь не будет производить торговых действий на спотовом рынке. Это гарантирует изолированность программы и её стабильную работу.  

Если у Вас небольшой баланс, следует ограничить количество одновременно торгуемых пар. Исходите из расчёта 1 торговая пара = 0.001 BTC на балансе. Итого, если у Вас, например, 0.03 BTC на балансе, ограничьтесь 30 парами, чтобы в случае даунтренда у Вас оставались средства для усреднения позиций.

Бот оплачивает комиссию биржи в BNB, эту опцию он включает автоматически при каждом запуске. Также он постоянно проверяет баланс BNB и докупает токен за BTC в случае, если его количество меньше 0.1, поэтому пользователю необходимо держать баланс в BTC для дозакупки Binance Coin, иначе бот просто не будет совершать новые сделки до тех пор, пока условие не будет истинным.

Также, при переносе бота в другую директорию, не забудь перенести файл abot.db вместе с ним.

#### Распространённые ошибки:
* APIError(code=-1021): Timestamp for this request was 1000ms ahead of the server's time — системное время и время биржи отличаются более, чем на секунду. Для этого синхронизируйте время в настройках операционной системы, через CMD от имени администратора или с помощью бесплатной утилиты http://www.timesynctool.com/.  
* A reques to the Telegram API was unsuccessful. Error code: 404. Description: Not Found — Введены неверные данные от Telegram-бота/чата для оповещений.  

#### Контакты:  
*[Официальный чат Telegram](https://t.me/abot_chat)* — для обсуждений, связи с разработчиками и развития проекта  

#### Параметры API настройки:
* API ключи — пара API ключей для обращения к Binance ([API-Management](https://www.binance.com/ru/usercenter/settings/api-management))  
* Реферальный ID — Реферальный ID Вашего аккаунта, зарегистрированного по нашему приглашению ([Referal ID](https://www.binance.com/ru/my/dashboard) — слева вверху в личном кабинете)  
* Уведомления в Telegram — При включенном параметре отправляет уведомления в группу/канал в случае успешной сделки  
  * API-Token — токен, выданный BotFather ([@BotFather](https://t.me/botfather)) при создании Telegram-бота  
  * @NAME — <@ИМЯ_СООБЩЕСТВА> для отправки уведомлений. Бот, созданный на предыдущем шаге, должен состоять в группе/канале и быть её администратором с включенными возможностями публикации сообщений и изменения профиля  

#### Инструкция для включения уведомлений в Telegram:
Если Вы запускаете бота впервые, то переходите сразу к инструкции.  
Если же бот уже работает без включенных уведомлений и Вы хотите активировать эту опцию, Вам потребуется либо перезапустить бота и удалить API ключи (следовательно, вводить заново пару API ключей от Binance и включать Telegram-уведомления), либо остановить бота, открыть файл abot.db с помощью текстового редактора (например Блокнота), находящийся в той же директории, где и бот, и изменить параметры "tg_notification": "y", "tg_token": "ТОКЕН_ВАШЕГО_БОТА", "tg_name": "@ИМЯ_ВАШЕГО_БОТА" (ТОКЕН_ВАШЕГО_БОТА и @ИМЯ_ВАШЕГО_БОТА получите в ходе выполнения инструкции).  
  
1. Обращаемся к [BotFather'у](https://t.me/botfather) в Telegram и создаём нового бота (вводим команду /newbot или выбираем её через контекстное меню)  
2. Вводим любое имя бота (например test_push_abot)  
3. Далее придумываем уникальный юзернейм для бота, который оканчивается на 'bot' (например **exambot_abot**)  
4. При успешном создании BotFather пришлёт нам сообщение, в котором будет указана ссылка на созданного бота и его API token (например 1432166624:AAHSlGrfaFP21BXLihyGXPiUv_urjarJhty). Запишите token в приватное место  
5. Создайте публичный или частный канал (Меню -> Создать канал), придумайте его название. Далее, если канал будет публичным, придумайте ему @НАЗВАНИЕ (например **test_push_abot_channel**). Если же канал будет приватным, то Вам нужно будет получить его chat_id (как это сделать, смотрите [здесь](https://cms3.ru/kak-poluchit-chat-id-telegram/))  
6. После того, как Вы создали канал, добавьте туда созданного ранее бота и сделайте его администратором с возможностью изменения профиля канала и публикацией сообщений (первые две галочки возможности администратора)  
7. Запустите A-Bot и на этапе 'Использовать Telegram-бота для отправки уведомлений?' введите латинскую 'y', затем API token, который выдал Вам BotFather и @НАЗВАНИЕ Вашего канала, где в администраторах находиться Telegram-Bot, созданный на 5 этапе (**test_push_abot_channel**)  
Теперь каждый раз, когда бот полностью закрывает позицию на продажу, Вы будете получать уведомление в Ваш канал!

![](img-3.png)  
![](img-4.png)  

#### Торговые параметры:
* `Сумма минимального ордера` [min >= 0.0001] — размер первого ордера на покупку в BTC, с которого бот начинает работать по торговой паре (например 0.0002)  
* `Минимальное суточное падение цены` [%] — На сколько процентов должна упасть цена по отношению к цене 24-мя часами ранее (например 5)  
* `Желаемая прибыль от сделки` [%] — Ожидаемая прибыль от продажи без учёта суточной дельты и трейлинг-стопа (например 4)  
* `Разница рыночной цены и цены последней покупки для усреднения` [%] — Значение, определяющее процент падения цены в текущий момент по отношению к последней покупке актива ботом (например 5)  
* `Использовать сетку усреднений` [y/n] — Если ***Y***, то при усреднении бот будет увеличивать процент падения, необходимый для нового усреднения  
  * `Шаг увеличения сетки` [%] — На сколько процентов увеличивать последующую разницу рыночной цены и цены последней покупки для усреднения (например 0.5)  
* `Максимальное количество одновременно торгуемых пар` — Допустимое количество открытых позиций (например 50)  
  * `-1` [-1] — Не ограничивать количество одновременно торгуемых ботом пар  
  * `0` [0] — Работать только с уже открытыми ордерами и не совершать новые покупки  
  * `1 и более` [1-999] — Указать количество позиций вручную  
* `Использовать общую рыночную дельту суточной цены` [y/n] — Суммировать торговые параметры с общей суточной дельтой по отобранным парам из белого списка. Данный параметр сделает стратегию более гибкой, но может уменьшить прибыль  
* `Использовать трейлинг-стоп` [y/n] — Отодвигать цену продажи в зависимости от движения цены актива. С включенным трейлингом позиция не закрывается сразу, а продаётся минимальными частями, чтобы увеличить потенциальную прибыль, либо закрывается полностью по минимальному положительному стопу. Также трейлинг-стоп служит и стоп-лоссом, гарантируя прибыльность каждой сделки. Данный параметр сделает стратегию более гибкой, но может уменьшить прибыль  
  * `Процент активации трейлинг-стопа` [%] — При каком падении от текущего хай-уровня активировать трейлинг-стоп для частичной/полной продажи. (например 0.5)  
  
![](img-2.png)  

#### Будет реализовано в будущем:
* Интеграция внутрибиржевого арбитражного бота  
* Интеграция бота для ловли сквизов  
* Графический интерфейс
* Веб-интерфейс
