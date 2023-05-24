 This script is designed to automatically install the Strongswan daemon. Use Ubuntu 20.04. On it this script is tested and works well.

## Installation.

Before running the script, find out your network interface. Use command
```
ip route show default
```
to find out your network interface.
After applying the command, you will see output like
```Output</br>
default via your_server_ip dev eth0 proto static
```
After **dev** there will be the required interfaces, in this case it is **eth0**. Insert your interface in the script, use the search for this. Replace all eth0 in the script with your network interface.

To run the script use this command
```
yes | sudo sh startswan.sh
```


## Usage.

You will need to add a username and password.
Edit the file
```
/etc/ipsec.secrets
```
Inside the file there is a template for how to add a new user.
After saving the file, restart Strongswan using the command
```
sudo systemctl restart strongswan-starter
```

You can get a certificate with the help of the command
```
cat /etc/ipsec.d/cacerts/ca-cert.pem
```
Save the text between
</br>**-----BEGIN CERTIFICATE----- and -----END CERTIFICATE-----**</br>
to the local computer including these two lines in a **.pem** file

</br>
</br>
</br>

Этот скрипт предназначен для автоматической установки демона Strongswan. Используйте Ubuntu 20.04, на ней этото скипт протестирован и работает хорошо.

## Установка.

Перед запуском скрипта узнайте свой сетевой интерфейс, используя команду 
```
ip route show default
```
После применения команды вы увидите вывод вида
```
Output
default via your_server_ip dev eth0  proto static
```
После **dev** будет нужный интерфейc, в данном случае это **eth0**. Вставьте в скрипте ваш интерфейс, используйте поиск для этого. Замените в скрипте все eth0 на ваш сетевой интерфейс.
Для запуска скрипта используйте команду
```
yes | sudo sh startswan.sh
```


## Использование.

Вам нужно будет добавить логин и пароль пользователя.
Отредактируйте файл
```
/etc/ipsec.secrets
```
Внутри файла есть шаблон как добавлять нового пользователя.
После сохранения файла перезагрузите Strongswan используя команду
```
sudo systemctl restart strongswan-starter
```

Получить сертефикат можно с помошью команды
```
cat /etc/ipsec.d/cacerts/ca-cert.pem
```
Сохраните текст, заключенный между
</br>**-----BEGIN CERTIFICATE-----** и **-----END CERTIFICATE-----**</br>
на локальный компьютер включая эти две строки в файл с расширением **.pem**


