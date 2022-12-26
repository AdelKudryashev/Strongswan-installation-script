This script is designed to automatically install the Strongswan daemon. Use Ubuntu 20.04. On it this script is tested and works well.

<h2>Installation.</h2>
Before running the script, find out your network interface. Use command
<font color="red">ip route show default</font>
to find out your network interface.
After applying the command, you will see output like
<font color="red">Output
default via your_server_ip dev ens3 proto static</font>. After <font color="red">dev</font> there will be the required interfaces, in this case it is <font color="red">ens3</font>. Insert your interface in the script, use the search for this.

Use the command <font color="red">sh startshan.sh</font> to run the script

At the end of the script installation, you will need to confirm the inclusion of the ufw firewall twice. just press <font color="red">y</font> and <font color="red">Enter</font>.

<h2>Usage.</h2>
You will need to add a username and password.
Edit the sudo <font color="red">/etc/ipsec.secrets</font> file. Inside the file there is a template for how to add a new user.
After saving the file, restart Strongswan using the command.
sudo systemctl restart strongswan-starter

You can get a certificate with the help of the command
<font color="red">cat /etc/ipsec.d/cacerts/ca-cert.pem</font>
Keep the text between
<font color="red">-----BEGIN CERTIFICATE----- and -----END CERTIFICATE-----</font>
to the local computer including these two lines in a <font color="red">.pem</font> file




Этот скрипт предназначен для автоматической установки демона Strongswan. Используйте Ubuntu 20.04, на ней этото скипт протестирован и работает хорошо.

<h2>Установка.</h2>
Перед запуском скрипта узнайте свой сетевой интерфейс. Используйте команду 
<font color="red">ip route show default</font> чтобы узнать свой сетевой интерфейс.
После применения команды вы увидите вывод вида
<font color="red">Output
default via your_server_ip dev ens3  proto static</font>. После <font color="red">dev</font> будет нужный интерфейc, в данном случае это <font color="red">ens3</font>. Вставьте в скрипте ваш интерфейс, используйте поиск для этого.

Используйте команду <font color="red">sh startshan.sh</font>  для запуска скрипта.

В конце установки скрипта два раза нужно будет подтвердить включение брандмауэра ufw. просто нажмите <font color="red">y</font> и <font color="red">Enter</font>.

<h2>Использование.</h2>
Вам нужно будет добавить логин и пароль пользователя.
Отредактируйте файл <font color="red">sudo /etc/ipsec.secrets</font>. Внутри файла есть шаблон как добавлять нового пользователя.
После сохранения файла перезагрузите Strongswan используя команду.
<font color="red">sudo systemctl restart strongswan-starter</font>

Получить сертефикат можно с помошью команды
<font color="red">cat /etc/ipsec.d/cacerts/ca-cert.pem</font>
Сохраните текст, заключенный между
<font color="red">-----BEGIN CERTIFICATE-----</font> и <font color="red">-----END CERTIFICATE-----</font>
на локальный компьютер включая эти две строки в файл с расширением <font color="red">.pem</font>
