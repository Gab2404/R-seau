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