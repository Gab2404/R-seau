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

# IV.Network scanning et adresses IP

> **🌞 Effectue un scan du réseau auquel tu es connecté**

_PS C:\Users\gabri> nmap -sn -PR 192.168.56.1_

    Starting Nmap 7.95 ( https://nmap.org ) at 2024-10-06 18:54 Romance Daylight Time
    Nmap scan report for 192.168.56.1
    Host is up.
    Nmap done: 1 IP address (1 host up) scanned in 0.34 seconds

> **🌞 Changer d'adresse IP**

_PS C:\Users\gabri> Get-NetAdapter_

    Name                      InterfaceDescription                    ifIndex Status       MacAddress             LinkSpeed
    ----                      --------------------                    ------- ------       ----------             ---------
    OpenVPN Data Channel O... OpenVPN Data Channel Offload                 21 Disconnected                           1 Gbps
    Wi-Fi                     Intel(R) Wi-Fi 6E AX211 160MHz               19 Up           E8-C8-29-CB-A5-8E     144.4 Mbps
    Connexion réseau Bluet... Bluetooth Device (Personal Area Netw...      11 Disconnected E8-C8-29-CB-A5-92         3 Mbps
    Connexion au réseau l...2 TAP-NordVPN Windows Adapter V9                8 Disconnected 00-FF-4D-C2-35-31         1 Gbps
    Ethernet 2                VirtualBox Host-Only Ethernet Adapter         6 Up           0A-00-27-00-00-06         1 Gbps

_PS C:\Windows\system32> New-NetIPAddress -InterfaceIndex 19 -IPAddress 10.100.0.49 -PrefixLength 24 -DefaultGateway 10.100.0.254_


    IPAddress         : 10.100.0.49
    InterfaceIndex    : 19
    InterfaceAlias    : Wi-Fi
    AddressFamily     : IPv4
    Type              : Unicast
    PrefixLength      : 24
    PrefixOrigin      : Manual
    SuffixOrigin      : Manual
    AddressState      : Tentative
    ValidLifetime     :
    PreferredLifetime :
    SkipAsSource      : False
    PolicyStore       : ActiveStore

    IPAddress         : 10.100.0.49
    InterfaceIndex    : 19
    InterfaceAlias    : Wi-Fi
    AddressFamily     : IPv4
    Type              : Unicast
    PrefixLength      : 24
    PrefixOrigin      : Manual
    SuffixOrigin      : Manual
    AddressState      : Invalid
    ValidLifetime     :
    PreferredLifetime :
    SkipAsSource      : False
    PolicyStore       : PersistentStore

_PS C:\Windows\system32> Set-DnsClientServerAddress -InterfaceIndex 19 -ServerAddresses 10.100.0.1_