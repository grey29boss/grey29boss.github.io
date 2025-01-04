### Linux Mint 22 Cinnamon 
bluetooth адаптер не видит устройства ( не видит наушники, телефон, и телефон тоже не видит ноутбук).
Гугление привело к такому: 

>Многим чипсетам Broadcom для Bluetooth требуется прошивка, которую нельзя распространять.
Некоторые чипсеты будут работать без прошивки, но некоторые функции не будут доступны.

[Отсюда](https://forums.linuxmint.com/viewtopic.php?p=2153091#p2153091)

Поэтому узнаём какое у нас устройство:
Вводим в терминале:
```
lsusb
```
Получаем:
```
Bus 002 Device 004: ID 0a5c:216d Broadcom Corp. BCM43142A0 Bluetooth 4.0
```
И [там же](https://forums.linuxmint.com/viewtopic.php?p=2153091#p2153091)
```
wget https://github.com/winterheart/broadcom-bt-firmware/raw/master/brcm/BCM43142A0-0a5c-216d.hcd
sudo cp BCM43142A0-0a5c-216d.hcd /lib/firmware/brcm/BCM.hcd
```
Перезагружаемся и всё работает!!!
