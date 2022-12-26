This script is designed to automatically install the Strongswan daemon. Use Ubuntu 20.04. On it this script is tested and works well.

<h2>Installation.</h2>
Before running the script, find out your network interface. Use command
</br><strong>ip route show default</strong></br>
to find out your network interface.
After applying the command, you will see output like
</br><strong>Output</br>
default via your_server_ip dev ens3 proto static</strong>. After <strong>dev</strong> there will be the required interfaces, in this case it is <strong>ens3</strong>. Insert your interface in the script, use the search for this.

Use the command <strong>sh startshan.sh</strong> to run the script

At the end of the script installation, the question will appear twice <strong>Command may disrupt existing ssh connections. Proceed with operation (y|n)?</strong>.

At the end of the script installation, you will need to confirm the inclusion of the ufw firewall twice. Just press <strong>y</strong> and <strong>Enter</strong>.

<h2>Usage.</h2>
You will need to add a username and password.
Edit the <strong>/etc/ipsec.secrets</strong> file. Inside the file there is a template for how to add a new user.
After saving the file, restart Strongswan using the command
</br><strong>sudo systemctl restart strongswan-starter</strong></br>

You can get a certificate with the help of the command
</br><strong>cat /etc/ipsec.d/cacerts/ca-cert.pem</strong></br>
Keep the text between
</br><strong>-----BEGIN CERTIFICATE----- and -----END CERTIFICATE-----</strong></br>
to the local computer including these two lines in a <strong>.pem</strong>file




Этот скрипт предназначен для автоматической установки демона Strongswan. Используйте Ubuntu 20.04, на ней этото скипт протестирован и работает хорошо.

<h2>Установка.</h2>
Перед запуском скрипта узнайте свой сетевой интерфейс. Используйте команду 
</br><strong>ip route show default</strong></br> чтобы узнать свой сетевой интерфейс.
После применения команды вы увидите вывод вида
</br><strong>Output</br>
default via your_server_ip dev ens3  proto static</strong>. После <strong>dev</strong> будет нужный интерфейc, в данном случае это <strong>ens3</strong>. Вставьте в скрипте ваш интерфейс, используйте поиск для этого.

Используйте команду <strong>sh startshan.sh</strong> для запуска скрипта.

В конце установки скрипта два раза появится вопрос <strong>Command may disrupt existing ssh connections. Proceed with operation (y|n)?</strong>. Нужно будет подтвердить включение брандмауэра ufw. просто нажмите <strong>y</strong> и <strong>Enter</strong>.

<h2>Использование.</h2>
Вам нужно будет добавить логин и пароль пользователя.
Отредактируйте файл <strong>/etc/ipsec.secrets</strong>. Внутри файла есть шаблон как добавлять нового пользователя.
После сохранения файла перезагрузите Strongswan используя команду
</br><strong>sudo systemctl restart strongswan-starter</strong></br>/

Получить сертефикат можно с помошью команды
</br><strong>cat /etc/ipsec.d/cacerts/ca-cert.pem</strong></br>
Сохраните текст, заключенный между
</br><strong>-----BEGIN CERTIFICATE-----</strong> и <strong>-----END CERTIFICATE-----</strong></br>
на локальный компьютер включая эти две строки в файл с расширением <strong>.pem</strong>