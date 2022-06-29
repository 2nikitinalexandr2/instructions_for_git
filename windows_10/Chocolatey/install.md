* проверяем настройки политики запуска скриптов
```
PS C:\Windows\system32> Get-ExecutionPolicy
Restricted
```

* Restricted – запрещен запуск скриптов PowerShell, можно выполнять только интерактивные команды в консоли; 
  
* изменим на RemoteSigned – можно запускать локальные PowerShell скрипты без ограничения. Можно запускать удаленные PS файлы с цифровой подписью (нельзя запустить PS1 файлы, скачанные из Интернета, запущенные из сетевой папки по UNC пути и т.д.);
  
```
Set-ExecutionPolicy RemoteSigned –Force
```
* или на `Bypass -Scope Process`
  ```
   Set-ExecutionPolicy Bypass -Scope Process
  ```

* опция –Force чтобы не появлялся запрос подтверждения
   
* устанвока клиента Chocolatey - менеджера пакетов в среде Windows по аналогии с apt-get в Linux Мире
* установка:обязательно запустить powershell или cmd от администратора:
```
Set-ExecutionPolicy Bypass -Scope Process -Force; [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://community.chocolatey.org/install.ps1'))
```
* источники: 
  * https://chocolatey.org/install#individual
  * https://winitpro.ru/index.php/2020/06/03/powershell-execution-policy-zapusk-scriptov/
  * https://habr.com/ru/post/143996/
  * https://lifehacker.ru/chocolatey/