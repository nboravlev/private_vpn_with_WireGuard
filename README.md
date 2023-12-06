# private_vpn_with_WireGuard
Настроить личный ВПН туннель на выделенном сервере
---------------------------------------------------
## Фаза 1 - покупка выделенного сервера

1. Приобрести виртуальный сервер. [FirstBite](https://firstbyte.pro/?from=158726) обеспечивает хороший выбор по цене и географии расположения. Лучше отдавать предпочтение серверам, которые физически находятся ближе к вашей точке, отклик будет наверняка лучше. В зависимости от настроек цена стартует от 1,52Euro (плюс комиссия сервера в районе 10%). Для приватного использования достаточно 1 выделенного адреса и минимальных параметров по количеству ядер и памяти.


![хостинг FirstBite](https://github.com/nboravlev/private_vpn_with_WireGuard/blob/main/_1.PNG)

2. В настройках заказа необходимо прописать доменное имя. Не важно какое, важен именно формат как на скриншоте.

![имя домена как на скрине](https://github.com/nboravlev/private_vpn_with_WireGuard/assets/120275954/de2f0f52-2857-46c9-a061-27369d6eca7d)

3. Операционную системы выбирать Ubuntu-20.04
4. Панель Управления не понадобится
5. Все остальное оставить По умолчанию. Далее подтвердить и оплатить заказ. Обработка заказа обычно происходит в течение 30 мин
6. На почту, указанныю при оформлении заказа придет письмо с информацией для подключения к серверу. Нужны будут следующие данные

![подключение к серверу](https://github.com/nboravlev/private_vpn_with_WireGuard/commit/40ac8c53c0527b15f4a99a49a12730532f5b6677)

## Фаза 2 - настройка подключения к серверу

1. Для подключения возьмем программу [Putty](https://the.earth.li/~sgtatham/putty/latest/w64/putty.exe). Скачать, установить на свой компьютер. Окно программы выглядит примерно так:

![_4](https://github.com/nboravlev/private_vpn_with_WireGuard/assets/120275954/9aa5fae2-5f22-4a2e-974b-f8a823abbc83)

3. В строку HOST ввести значение ip из письма. Все отстальные поля должны быть как на скриншоте. В конце нажать **Open**

4. Подтвердить добавление ключа **Accept**

![_5](https://github.com/nboravlev/private_vpn_with_WireGuard/assets/120275954/891184c5-4f1b-4a26-b2b1-32b59cf96f34)

5. В следующем окне ввести логин из письма, нажать **Enter**

![_6](https://github.com/nboravlev/private_vpn_with_WireGuard/assets/120275954/c5140812-0311-4fe3-8527-a0c13707e12d)

6. В следующем окне ввести пароль из письма. Обратите внимание, что когда вы вводите пароль в консоль, он не отображается по соображениям безопасности. Пароль можно ввести через **Копировать** и **Вставить**. Он все еще не будет отображаться. Нажать **Enter**<br>

![_8](https://github.com/nboravlev/private_vpn_with_WireGuard/assets/120275954/609f70b3-2c7d-4776-b9a1-f5c96bfbaeeb)

8. При удачном входе на консоли отобразится что-то вроде

![_7](https://github.com/nboravlev/private_vpn_with_WireGuard/assets/120275954/550bbb7e-54cc-4416-8a80-63b13dedd5ff)

## Фаза 3 - Установить [WireGuard](https://www.wireguard.com/)

1. Вввести команду (**Ctrl+С** + вставить путем нажатия правой кнопки мышки в черный экран где курсор):<br>
>*sudo apt update*
<br>Нажать **Enter**

2. Вввести команду (**Ctrl+С** + вставить путем нажатия правой кнопки мышки в черный экран где курсор):<br>
>*sudo apt install curl*
<br>Нажать **Enter** <br>ввести **Y** для подтверждения установки.

3. Вввести команду (**Ctrl+С** + вставить путем нажатия правой кнопки мышки в черный экран где курсор):<br>
>*curl https://raw.githubusercontent.com/complexorganizations/wireguard-manager/main/wireguard-manager.sh --create-dirs -o /usr/local/bin/wireguard-manager.sh*
<br>Нажать **Enter**

4. Вввести команду (**Ctrl+С** + вставить путем нажатия правой кнопки мышки в черный экран где курсор):<br>
>*chmod +x /usr/local/bin/wireguard-manager.sh*
<br>Нажать **Enter**

5. Вввести команду (**Ctrl+С** + вставить путем нажатия правой кнопки мышки в черный экран где курсор):<br>
>*bash /usr/local/bin/wireguard-manager.sh*
<br>Нажать **Enter**

6. Далее идут настройки из 15 пунктов везде оставить рекомендованное значение **1** и нажать **Enter**


7. По окончании установки вы увидите QR-код для подключения. <br> Фактически вы подняли собственный ВПН-сервер. Осталось настроть подключение на смартфоне и ноутбуке.

![_11](https://github.com/nboravlev/private_vpn_with_WireGuard/assets/120275954/4e75a68a-bbcc-4617-9fdf-f209e0d1d3cd)

## Фаза 4 - настройка подключения в смартфоне.

1. Для установки на смартфоне необходимо скачать и установить приложение **WireGuard** c **AppStore**

![_11](https://github.com/nboravlev/private_vpn_with_WireGuard/assets/120275954/28383353-6d3d-4d94-94e8-23c552e9a16c)
