
1. root@debian:/etc/bind# systemctl status bind9
```
● named.service - BIND Domain Name Server
     Loaded: loaded (/lib/systemd/system/named.service; enabled; vendor preset: e>
     Active: active (running) since Wed 2022-06-29 16:17:04 MSK; 1s ago
       Docs: man:named(8)
   Main PID: 452 (named)
      Tasks: 4 (limit: 1810)
     Memory: 10.5M
        CPU: 57ms
     CGroup: /system.slice/named.service
             └─452 /usr/sbin/named -f -u bind

июн 29 16:17:04 debian named[452]: network unreachable resolving './NS/IN': 2001:>
июн 29 16:17:04 debian named[452]: zone 127.in-addr.arpa/IN: loaded serial 1
июн 29 16:17:04 debian named[452]: zone server.com/IN: loaded serial 2
июн 29 16:17:04 debian named[452]: zone 255.in-addr.arpa/IN: loaded serial 1
июн 29 16:17:04 debian named[452]: zone server.com/IN: sending notifies (serial 2)
июн 29 16:17:04 debian named[452]: zone localhost/IN: loaded serial 2
июн 29 16:17:04 debian named[452]: all zones loaded
июн 29 16:17:04 debian named[452]: running
июн 29 16:17:04 debian named[452]: managed-keys-zone: Key 20326 for zone . is now>
июн 29 16:17:04 debian named[452]: resolver priming query complete
```
2. root@debian:/etc/bind# host server.com localhost
```
Using domain server:
Name: localhost
Address: ::1#53
Aliases:

server.com has address 10.0.2.15
```
3. root@debian:/etc/bind# host sites.server.com localhost
```
Using domain server:
Name: localhost
Address: ::1#53
Aliases:

sites.server.com is an alias for www.server.com.
www.server.com is an alias for server.com.
server.com has address 10.0.2.15

```
4. root@debian:/etc/bind# host 10.0.2.15 localhost
```
Using domain server:
Name: localhost
Address: ::1#53
Aliases:

15.2.0.10.in-addr.arpa domain name pointer server.com.
```
5. root@debian:/etc/bind# host yandex.ru localhost
```
Using domain server:
Name: localhost
Address: ::1#53
Aliases:

yandex.ru has address 5.255.255.55
yandex.ru has address 5.255.255.50
yandex.ru has address 77.88.55.70
yandex.ru has address 77.88.55.66
yandex.ru has IPv6 address 2a02:6b8:a::a
yandex.ru mail is handled by 10 mx.yandex.ru.
```
6. root@debian:/etc/bind# host 10.0.2.15
```
15.2.0.10.in-addr.arpa domain name pointer server.com.
```
* такой ответ если изменить файл конфигурации разрешения имен /etc/resolf.conf
```
nameserver 127.0.0.1
```