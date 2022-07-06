1. Переключение на суперпользователя root, если зашли на сервер не от рута:
```
sudo su -l
```
2. Установка и запуск панельного файлового менеджера и редактора mc
```
apt update

apt -y install mc
```
3. Установка и настройка web-сервера
```
apt -y install apache2
```
4. Установка CMS Wordpress
```
apt -y install wordpress
```
5. Настройка виртуального хоста web-сервера:

* cкопировать пример настройки сайта из документации wordpress в системный каталог конфигурации web-сервера, через mc или командой:
```
cp /usr/share/doc/wordpress/examples/apache.conf /etc/apache2/sites-available/001-example.conf
```
6. Отредактировать файл /etc/apache2/sites-available/001-example.conf, убрав из него лишнее и оставив в нём только настройку виртуального хоста:
```
mcedit /etc/apache2/sites-available/001-example.conf
```
```
## A defined virtual host

NameVitrualHost *:80

<VirtualHost *:80>

ServerName blog.example.com

……

</VirtualHost>
```
Закомментировать строчку
```
 ServerName blog.example.com
```
1. Включить обязательные для сайта модули web-сервера для перенаправления запросов командами:
```
a2enmod rewrite

a2enmod vhost_alias
```
8. Выключить хост по-умолчанию и включить виртуальный хост для сайта командами:
```
a2dissite 000-default

a2ensite 001-example
```
9. Перезапустить сервис web-сервера
```
systemctl restart apache2
```
10. Проверить статус web-сервера
```
systemctl status apache2
```
11. Создать базу для сайта командами:
    * в Debian 11 (Virtualbox)	
```
apt -y install mariadb-server

mysql -u root -p
```

* в Ubuntu
```
apt -y install mysql-server

mysql -u root -p
```
* Далее выполняем sql команды:
```
create database wordpress;

CREATE USER 'wordpress'@'localhost' IDENTIFIED BY 'password';

flush privileges;

GRANT SELECT,INSERT,UPDATE,DELETE,CREATE,DROP,ALTER ON wordpress.* TO 'wordpress'@'localhost';

flush privileges;

quit
```
12.  Создать файл для подключения сайта к базе:

touch /etc/wordpress/config-default.php

mcedit /etc/wordpress/config-default.php

Написать в файл строчки:

<?php

define('DB_PASSWORD', 'password');

define('WP_CONTENT_DIR', '/var/lib/wordpress/wp-content');

define('FS_METHOD','direct');

?>

В случае каких либо проблем с установкой CMS Wordpress обратитесь к документации Ubuntu: https://ubuntu.com/tutorials/install-and-configure-wordpress

13. Необходимо открыть/пробросить порты HTTP(S)
* В виртуальной машине VirtualBox	
```
На запущенной либо закрытой ВМ перейти в: Устройства->Сеть->Настроить сеть, кнопка Дополнительно, Проброс портов.

Нажимаем +,

Порт хоста - 8080,

Порт гостя - 80
```
* На облачном сервере AWS
```
В AWS Management Console переходим в меню в EC2→Instances,

находим свой сервер, открываем, переходим на вкладку Security

нажимаем в Security groups на ссылку типа sg-….,

нажимаем Edit inbound rules, затем Add rule, выбираем HTTP,

в поле Source выбираем 0.0.0.0/0, ещё раз нажимаем Add rule , выбираем HTTPS, в поле Source выбираем 0.0.0.0/0, Нажимаем Save rules.
```
14. Зайти со своего компьютера через браузер на адрес:

- для AWS или OracleCloud: http://<внешний IP-адрес сервера>

- для виртуальной машины Virtualbox: http://localhost:8080

Произвести установку сайта:

Название сайта (Site Title): Тестовый сайт

Имя пользователя (Username): admin

Password: (будет сгенерирован, его нужно сохранить)

Your Email: (указать вашу почту)

15. Войти на сайт в панель администратора по адресу http://<внешний IP-адрес>/wp-admin/.

В настройках (Settings) при необходимости изменить язык и установить вашу таймзону.

16. Удалить запись «Hello World».

Добавить новую запись «Первая новость» в рубрику «Новости», опубликовать.

17. Добавить новую запись «График работы» в рубрику «Приказы», прикрепить любой файл, опубликовать.

18. Посмотреть результат — перейти на сайт, отправить IP-адрес сайта в результат выполнения работы.

P.S. Для корректной установки плагинов и тем необходимо дать доступ пользователю www-data к каталогам:
```
chown -RL www-data: /var/lib/wordpress
```