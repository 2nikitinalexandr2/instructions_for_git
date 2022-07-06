1. root@debian:~# systemctl status apache2
```
● apache2.service - The Apache HTTP Server
     Loaded: loaded (/lib/systemd/system/apache2.service; enabled; vendor preset: enabled)
     Active: active (running) since Tue 2022-07-05 16:42:51 MSK; 38min ago
       Docs: https://httpd.apache.org/docs/2.4/
   Main PID: 10811 (apache2)
      Tasks: 11 (limit: 1133)
     Memory: 116.0M
        CPU: 12.718s
     CGroup: /system.slice/apache2.service
             ├─10811 /usr/sbin/apache2 -k start
             ├─10812 /usr/sbin/apache2 -k start
             ├─10814 /usr/sbin/apache2 -k start
             ├─10815 /usr/sbin/apache2 -k start
             ├─10816 /usr/sbin/apache2 -k start
             ├─11474 /usr/sbin/apache2 -k start
             ├─11476 /usr/sbin/apache2 -k start
             ├─11492 /usr/sbin/apache2 -k start
             ├─11493 /usr/sbin/apache2 -k start
             ├─11494 /usr/sbin/apache2 -k start
             └─11590 /usr/sbin/apache2 -k start

июл 05 16:42:51 debian systemd[1]: apache2.service: Succeeded.
июл 05 16:42:51 debian systemd[1]: Stopped The Apache HTTP Server.
июл 05 16:42:51 debian systemd[1]: Starting The Apache HTTP Server...
июл 05 16:42:51 debian apachectl[10810]: AH00548: NameVirtualHost has no effect and will be removed >
июл 05 16:42:51 debian apachectl[10810]: AH00558: apache2: Could not reliably determine the server's>
июл 05 16:42:51 debian systemd[1]: Started The Apache HTTP Server.
```
2. root@debian:~# systemctl status mysql
```
● mariadb.service - MariaDB 10.5.15 database server
     Loaded: loaded (/lib/systemd/system/mariadb.service; enabled; vendor preset: enabled)
     Active: active (running) since Tue 2022-07-05 16:43:24 MSK; 38min ago
       Docs: man:mariadbd(8)
             https://mariadb.com/kb/en/library/systemd/
    Process: 11353 ExecStartPre=/usr/bin/install -m 755 -o mysql -g root -d /var/run/mysqld (code=ex>
    Process: 11354 ExecStartPre=/bin/sh -c systemctl unset-environment _WSREP_START_POSITION (code=e>
    Process: 11356 ExecStartPre=/bin/sh -c [ ! -e /usr/bin/galera_recovery ] && VAR= ||   VAR=`cd /u>
    Process: 11416 ExecStartPost=/bin/sh -c systemctl unset-environment _WSREP_START_POSITION (code=>
    Process: 11418 ExecStartPost=/etc/mysql/debian-start (code=exited, status=0/SUCCESS)
   Main PID: 11403 (mariadbd)
     Status: "Taking your SQL requests now..."
      Tasks: 13 (limit: 1133)
     Memory: 88.4M
        CPU: 3.856s
     CGroup: /system.slice/mariadb.service
             └─11403 /usr/sbin/mariadbd

июл 05 16:43:24 debian mariadbd[11403]: Version: '10.5.15-MariaDB-0+deb11u1'  socket: '/run/mysqld/m>
июл 05 16:43:24 debian systemd[1]: Started MariaDB 10.5.15 database server.
июл 05 16:43:24 debian /etc/mysql/debian-start[11420]: Upgrading MySQL tables if necessary.
июл 05 16:43:24 debian /etc/mysql/debian-start[11423]: Looking for 'mysql' as: /usr/bin/mysql
июл 05 16:43:24 debian /etc/mysql/debian-start[11423]: Looking for 'mysqlcheck' as: /usr/bin/mysqlch>
июл 05 16:43:24 debian /etc/mysql/debian-start[11423]: This installation of MariaDB is already upgra>
июл 05 16:43:24 debian /etc/mysql/debian-start[11423]: There is no need to run mysql_upgrade again f>
июл 05 16:43:24 debian /etc/mysql/debian-start[11423]: You can use --force if you still want to run >
июл 05 16:43:24 debian /etc/mysql/debian-start[11431]: Checking for insecure root accounts.
июл 05 16:43:24 debian /etc/mysql/debian-start[11435]: Triggering myisam-recover for all MyISAM tabl>
```
3. root@debian:~# mysql -e "SELECT table_name FROM information_schema.tables WHERE table_schema = 'wordpress';"
```
+-----------------------+
| table_name            |
+-----------------------+
| wp_term_relationships |
| wp_usermeta           |
| wp_users              |
| wp_termmeta           |
| wp_commentmeta        |
| wp_comments           |
| wp_terms              |
| wp_term_taxonomy      |
| wp_postmeta           |
| wp_links              |
| wp_options            |
| wp_posts              |
+-----------------------+
```