# I. Récolte d'informations

>**🌞 Adresses IP de ta machine:**

_PS C:\Users\gabri> ipconfig_

Carte réseau sans fil Wi-Fi :

    Passerelle par défaut. . . . . . . . . : 10.33.79.254


>**🌞 Si t'as un accès internet normal, d'autres infos sont forcément dispos...**

_PS C:\Users\gabri> ipconfig /all_

Carte réseau sans fil Wi-Fi :

    Passerelle par défaut. . . . . . . . . : 10.33.79.254
    Serveur DHCP . . . . . . . . . . . . . : 10.33.79.254
    Serveurs DNS. . .  . . . . . . . . . . : 8.8.8.8

> **🌟 BONUS : Détermine s'il y a un pare-feu actif sur ta machine**

_PS C:\Windows\system32> netsh advfirewall show currentprofile_

    paramètres Profil public :

    État                                  Actif
    Stratégie de pare-feu                 BlockInbound,AllowOutbound
    LocalFirewallRules                    N/A (magasin d'objets de stratégie de groupe uniquement)
    LocalConSecRules                      N/A (magasin d'objets de stratégie de groupe uniquement)
    InboundUserNotification               Activer
    RemoteManagement                      Désactiver
    UnicastResponseToMulticast            Activer

# II. Utiliser le réseau

> **🌞 Envoie un ping vers...**

_PS C:\Windows\system32> ping 10.33.77.166_

    Envoi d’une requête 'Ping'  10.33.77.166 avec 32 octets de données :
    Réponse de 10.33.77.166 : octets=32 temps<1ms TTL=128
    Réponse de 10.33.77.166 : octets=32 temps<1ms TTL=128
    Réponse de 10.33.77.166 : octets=32 temps<1ms TTL=128
    Réponse de 10.33.77.166 : octets=32 temps<1ms TTL=128

    Statistiques Ping pour 10.33.77.166:
    Paquets : envoyés = 4, reçus = 4, perdus = 0 (perte 0%),
    Durée approximative des boucles en millisecondes :
    Minimum = 0ms, Maximum = 0ms, Moyenne = 0ms

_PS C:\Windows\system32> ping 127.0.0.1_

    nvoi d’une requête 'Ping'  127.0.0.1 avec 32 octets de données :
    Réponse de 127.0.0.1 : octets=32 temps<1ms TTL=128
    Réponse de 127.0.0.1 : octets=32 temps<1ms TTL=128
    Réponse de 127.0.0.1 : octets=32 temps<1ms TTL=128
    Réponse de 127.0.0.1 : octets=32 temps<1ms TTL=128

    Statistiques Ping pour 127.0.0.1:
    Paquets : envoyés = 4, reçus = 4, perdus = 0 (perte 0%),
    Durée approximative des boucles en millisecondes :
    Minimum = 0ms, Maximum = 0ms, Moyenne = 0ms

> **🌞 On continue avec ping. Envoie un ping vers...**

 _PS C:\Windows\system32> ping 10.33.77.29_

    Envoi d’une requête 'Ping'  10.33.77.29 avec 32 octets de données :
    Réponse de 10.33.77.29 : octets=32 temps=210 ms TTL=128
    Réponse de 10.33.77.29 : octets=32 temps=208 ms TTL=128
    Réponse de 10.33.77.29 : octets=32 temps=210 ms TTL=128
    Réponse de 10.33.77.29 : octets=32 temps=41 ms TTL=128

    Statistiques Ping pour 10.33.77.29:
    Paquets : envoyés = 4, reçus = 4, perdus = 0 (perte 0%),
    Durée approximative des boucles en millisecondes :
    Minimum = 41ms, Maximum = 210ms, Moyenne = 167ms

_PS C:\Windows\system32> ping www.roblox.com_

    Envoi d’une requête 'ping' sur edge-term4-lhr2.roblox.com [128.116.119.4] avec 32 octets de données :
    Réponse de 128.116.119.4 : octets=32 temps=21 ms TTL=52
    Réponse de 128.116.119.4 : octets=32 temps=25 ms TTL=52
    Réponse de 128.116.119.4 : octets=32 temps=24 ms TTL=52
    Réponse de 128.116.119.4 : octets=32 temps=25 ms TTL=52

    Statistiques Ping pour 128.116.119.4:
    Paquets : envoyés = 4, reçus = 4, perdus = 0 (perte 0%),
    Durée approximative des boucles en millisecondes :
    Minimum = 21ms, Maximum = 25ms, Moyenne = 23ms

> **🌞 Faire une requête DNS à la main**

_PS C:\Windows\system32> nslookup roblox.com_

    Serveur :   dns.google
    Address:  8.8.8.8

    Réponse ne faisant pas autorité :
    Nom :    roblox.com
    Address:  128.116.44.4