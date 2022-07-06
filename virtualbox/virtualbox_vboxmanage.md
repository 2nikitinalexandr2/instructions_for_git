Импорт ВМ и снапшоты:
* импорт образа Debian 11.ova:
```
vboxmanage import "D:\chrome\Debian 11.ova"
```
*  снапшот с именем Clean
```
vboxmanage snapshot "Debian 11" take Clean
```
* импорт образа Windows 10 (Орг. администрирования).ova:
```
vboxmanage import "D:\chrome\Windows 10 (Орг. администрирования).ova"
```
*  снапшот с именем Clean
```
vboxmanage snapshot "Windows 10 (Орг. администрирования)" take Clean
```

* настроить сеть, в общих настройках VirtualBox создать сеть OrgNat-10-0-2 с настройками: подсеть 10.0.2.0/24 и отключенный dhcp. В настройках сети импортированных ВМ установить сеть NAT: OrgNat-10-0-2. Это можно сделать, выполнив скрипт:
```
vboxmanage natnetwork add --netname "OrgNat-10-0-2" --network 10.0.2.0/24 --enable --dhcp on --ipv6 off
```
```
vboxmanage modifyvm "Debian 11" --nic1 natnetwork --nat-network1 "OrgNat-10-0-2"
```
```
vboxmanage modifyvm "Windows 10 (Орг. администрирования)" --nic1 natnetwork --nat-network1 "OrgNat-10-0-2"
```
```
vboxmanage modifyvm "Debian 11" --nic2 none
```
```
vboxmanage modifyvm "Windows 10 (Орг. администрирования)" --nic2 none
```
* включить вложенную виртуализацию - enable nested vtx/amd-v
```
VBoxManage modifyvm "Windows 10 (Орг. администрирования)" --nested-hw-virt on
```

```
vboxmanage import "D:\chrome\Windows 2019 (Орг. администрирования).ova"
```
```
vboxmanage snapshot "Windows 2019 (Орг. администрирования)" take Clean
```

```
vboxmanage modifyvm "Windows 2019 (Орг. администрирования)" --nic1 natnetwork --nat-network1 "OrgNat-10-0-2"
```

```
vboxmanage modifyvm "Windows 2019 (Орг. администрирования)" --nic2 none
```