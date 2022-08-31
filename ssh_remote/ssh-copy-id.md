* connect to host without password
`ssh-copy-id -i ~/.ssh/mykey user@host`
* после ввода команды выполниться скрипт и запросит пароль
```
$ ssh-copy-id -i ~/.ssh/id_rsa.pub root@192.168.0.59
/usr/bin/ssh-copy-id: INFO: Source of key(s) to be installed: "/c/Users/user/.ssh/id_rsa.pub"
/usr/bin/ssh-copy-id: INFO: attempting to log in with the new key(s), to filter out any that are already installed
/usr/bin/ssh-copy-id: INFO: 1 key(s) remain to be installed -- if you are prompted now it is to install the new keys
root@192.168.0.59's password:
```
* где ~/.ssh/mykey публичнй ключ
* если пароль введен верно то поступи предложение авторизоваться
```
Number of key(s) added: 1

Now try logging into the machine, with:   "ssh 'root@192.168.0.59'"
and check to make sure that only the key(s) you wanted were added.
```
* `ssh root@192.168.0.59`
