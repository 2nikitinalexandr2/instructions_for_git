* выполняем команды в терминале powershell От имени администратора:
* Команда для включения VM:
```
dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart
```
*  Команда для включения WSL:
```
dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart
```
* Команда для переключения WSL на вторую версию:
```
wsl --set-default-version 2
```
* Скачать обновлнение для WSL для 64-битных ОС:
* https://docs.microsoft.com/ru-ru/windows/wsl/install-manual#step-4---download-the-linux-kernel-update-package

* Установка дистрибутива ubuntu :
```
wsl --install -d Ubuntu
```
* Как перейти в домашнюю папку Ubuntu из Windows:
```
\\wsl$\Ubuntu\home\<username>
```
* Как перейти в домашнюю папку Windows из Ubuntu:
```
cd /mnt/c/Users/<username>
```
* Создать символьную ссылку на домашний каталог windows и назвать win_home:
```
ln -s /mnt/c/Users/<username> win_home
```
* проверить версию wsl установленной машины:
```
wsl -l -v
```