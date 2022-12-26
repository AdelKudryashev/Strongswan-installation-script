This script is designed to automatically install the Strongswan daemon. Use Ubuntu 20.04. On it this script is tested and works well.

## Installation.

Before running the script, find out your network interface. Use command
</br>**ip route show default**</br>
to find out your network interface.
After applying the command, you will see output like
</br>**Output</br>
default via your_server_ip dev ens3 proto static**. After **dev** there will be the required interfaces, in this case it is **ens3**. Insert your interface in the script, use the search for this. Replace all ens3 in the script with your network interface.

Use the command **sh startswan.sh** to run the script

At the end of the script installation, the question will appear twice **Command may disrupt existing ssh connections. Proceed with operation (y|n)?**. This will enable the firewall ufw. Just press **y** and **Enter**.

## Usage.

You will need to add a username and password.
Edit the **/etc/ipsec.secrets** file. Inside the file there is a template for how to add a new user.
After saving the file, restart Strongswan using the command
</br>**sudo systemctl restart strongswan-starter**</br>

You can get a certificate with the help of the command
</br>**cat /etc/ipsec.d/cacerts/ca-cert.pem**</br>
Save the text between
</br>**-----BEGIN CERTIFICATE----- and -----END CERTIFICATE-----**</br>
to the local computer including these two lines in a **.pem** file

</br>
</br>
</br>

Этот скрипт предназначен для автоматической установки демона Strongswan. Используйте Ubuntu 20.04, на ней этото скипт протестирован и работает хорошо.

## Установка.

Перед запуском скрипта узнайте свой сетевой интерфейс. Используйте команду 
</br>**ip route show default**</br> чтобы узнать свой сетевой интерфейс.
После применения команды вы увидите вывод вида
</br>**Output</br>
default via your_server_ip dev ens3  proto static**. После **dev** будет нужный интерфейc, в данном случае это **ens3**. Вставьте в скрипте ваш интерфейс, используйте поиск для этого. Замените в скрипте все ens3 на ваш сетевой интерфейс.
Используйте команду **sh startswan.sh** для запуска скрипта.

В конце установки скрипта два раза появится вопрос **Command may disrupt existing ssh connections. Proceed with operation (y|n)?**. Это включит брандмауэр ufw. просто нажмите **y** и **Enter**.

## Использование.

Вам нужно будет добавить логин и пароль пользователя.
Отредактируйте файл **/etc/ipsec.secrets**. Внутри файла есть шаблон как добавлять нового пользователя.
После сохранения файла перезагрузите Strongswan используя команду
</br>**sudo systemctl restart strongswan-starter**</br>/

Получить сертефикат можно с помошью команды
</br>**cat /etc/ipsec.d/cacerts/ca-cert.pem**</br>
Сохраните текст, заключенный между
</br>**-----BEGIN CERTIFICATE-----** и **-----END CERTIFICATE-----**</br>
на локальный компьютер включая эти две строки в файл с расширением **.pem**

