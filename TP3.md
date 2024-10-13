# I. ARP basics
> ### **☀️ Avant de continuer...**

_gabriel@zengab:~$ ifconfig_

    inet6 2a02:8440:6115:5a55:2c79:fec:e77a:1898  prefixlen 64  scopeid 0x0<global>
        
    inet6 fe80::2c0:e434:5c9c:f1b  prefixlen 64  scopeid 0x20<link>

    inet6 2a02:8440:6115:5a55:5c86:5b64:8339:6439  prefixlen 64  scopeid 0x0<global>

> ### **☀️ Affichez votre table ARP**

_gabriel@zengab:~$ sudo arp -a 172.20.10.1_


    _gateway (172.20.10.1) at 06:99:bb:00:aa:64 [ether] on wlo1

> ### **☀️ Déterminez l'adresse MAC de la passerelle du réseau de l'école**

_PS C:\Users\gabri> ipconfig /all_

Carte réseau sans fil Wi-Fi :

    Passerelle par défaut. . . . . . . . . : 10.33.79.254

(Je ne peux pas avoir l'adresse mac de l'école je fais ce tp chez moi)

## 1. Basics

> **☀️ Déterminer**

_gabriel@zengab:~$ arp -a_

    ? (192.168.56.101) at <incomplete> on vboxnet0
    ? (192.168.56.102) at 08:00:27:b3:15:e5 [ether] on vboxnet0
    _gateway (172.20.10.1) at 06:99:bb:00:aa:64 [ether] on wlo1

> **☀️ DIY**

