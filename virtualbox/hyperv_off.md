* источник: https://remontka.pro/virtualbox-hyperv-same-system/

bcdedit /copy {current} /d "Отключить Hyper-V"
Будет создана новый пункт меню загрузки Windows, также в командной строке отобразится GUID этого пункта.
Введите команду
bcdedit /set {отобразившийся GUID} hypervisorlaunchtype off