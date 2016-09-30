rtl8723bu
=========

Driver for RTL8723BU

## Determine the chipset
````
$ lsusb 

Now you should see one line that approximately resembles one line in the following output (examples from my own computers):

Bus 002 Device 003: ID 0bda:8176 Realtek Semiconductor Corp.
Bus 002 Device 004: ID 0bda:8178 Realtek Semiconductor Corp.
Bus 002 Device 007: ID 0bda:818b Realtek Semiconductor Corp.
Bus 002 Device 008: ID 0bda:8812 Realtek Semiconductor Corp.
Bus 002 Device 009: ID 0bda:b720 Realtek Semiconductor Corp.
Bus 002 Device 009: ID 0bda:8179 Realtek Semiconductor Corp.

2 Realtek RTL8188CUS and RTL8192CU chipsets (0bda:8176 and 0bda:8178)
3 Realtek RTL8723BE chipset
4 Realtek RTL8723AU chipset (0bda:b720)
5 Realtek RTL8188EU chipset (0bda:8179)
6 Realtek RTL8192EU chipset (0bda:818b)
7 Realtek RTL8812AU chipset (0bda:8812)
8 Realtek RTL8723BU chipset (0bda:b720)

```

## Realtek RTL8723BU chipset (0bda:b720)

* Note: unfortunately, the RTL8723BU and the RTL8723AU chipset share the same USB ID.... Which is of course highly annoying. The how-to below is for the RTL8723BU chipset; 

* sudo apt-get install git build-essential linux-headers-$(uname -r) gksu leafpad

* git clone https://github.com/nuodong/rtl8723bu
* cd rtl8723bu
* make 
* sudo make install
* /etc/modprobe.d/blacklist.conf
````
# The rtl8723au and the rtl8723bu drivers are flawed,
# so they need to be prevented from loading.
# This should give the 8723au or the 8723bu driver
# the chance to load instead.
blacklist rtl8723au
blacklist r8723au
#blacklist rtl8723bu
#blacklist r8723bu
```
* Reboot your computer.

## More info about RTL chipset
* https://sites.google.com/site/easylinuxtipsproject/reserve-7#TOC-The-rtlwifi_new-driver-from-lwfinger


