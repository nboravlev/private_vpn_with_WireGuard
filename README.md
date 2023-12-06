# private_vpn_with_WireGuard
Настроить личный ВПН туннель на выделенном сервере
---------------------------------------------------
## Фаза 1 - покупка выделенного сервера

1. Приобрести виртуальный сервер. [FirstBite](https://firstbyte.pro/?from=158726) обеспечивает хороший выбор по цене и географии расположения. Лучше отдавать предпочтение серверам, которые физически находятся ближе к вашей точке, отклик будет наверняка лучше. В зависимости от настроек цена стартует от 1,52Euro (плюс комиссия сервера в районе 10%). Для приватного использования достаточно 1 выделенного адреса и минимальных параметров по количеству ядер и памяти.


![хостинг FirstBite](https://github.com/nboravlev/private_vpn_with_WireGuard/blob/main/_1.PNG)

2. В настройках заказа необходимо прописать доменное имя. Не важно какое, важен именно формат как на скриншоте.

![имя домена как на скрине](https://github.com/nboravlev/private_vpn_with_WireGuard/commit/40ac8c53c0527b15f4a99a49a12730532f5b6677?diff=split&w=0#commitcomment-134307823)

3. Операционную системы выбирать Ubuntu-20.04
4. Панель Управления не понадобится
5. Все остальное оставить По умолчанию. Далее подтвердить и оплатить заказ. Обработка заказа обычно происходит в течение 30 мин
6. На почту, указанныю при оформлении заказа придет письмо с информацией для подключения к серверу. Нужны будут следующие данные

![подключение к серверу](https://github.com/nboravlev/private_vpn_with_WireGuard/commit/40ac8c53c0527b15f4a99a49a12730532f5b6677#commitcomment-134307823)

## Фаза 2 - настройка подключения к серверу

1. Для подключения возьмем программу [Putty](https://the.earth.li/~sgtatham/putty/latest/w64/putty.exe). Скачать, установить на свой компьютер. Окно программы выглядит примерно так:

![_4](https://github.com/nboravlev/private_vpn_with_WireGuard/assets/120275954/9aa5fae2-5f22-4a2e-974b-f8a823abbc83)

3. В строку HOST ввести значение ip из письма. Все отстальные поля должны быть как на скриншоте. В конце нажать **Open**

4. Подтвердить добавление ключа **Accept**
![_5](https://github.com/nboravlev/private_vpn_with_WireGuard/assets/120275954/891184c5-4f1b-4a26-b2b1-32b59cf96f34)
5. В следующем окне ввести логин из письма, нажать **Enter**
![_6](https://github.com/nboravlev/private_vpn_with_WireGuard/assets/120275954/c5140812-0311-4fe3-8527-a0c13707e12d)
6. В следующем окне ввести пароль из письма. Обратите внимание, что когда вы вводите пароль в консоль, он не отображается по соображениям безопасности. Пароль можно ввести через **Копировать** и **Вставить**. Он все еще не будет отображаться. Нажать **Enter**
![_7](https://github.com/nboravlev/private_vpn_with_WireGuard/assets/120275954/550bbb7e-54cc-4416-8a80-63b13dedd5ff)
7. При удачном входе на консоли отобразится что-то вроде
