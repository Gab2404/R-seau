# I. Simplest LAN

### **1. Quelques pings**

> **🌞 Prouvez que votre configuration est effective**

**_gabriel@zengab:~$ ip addr show wlo1_**

    2: wlo1: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc noqueue state UP group default qlen 1000
    link/ether e8:c8:29:cb:a5:8e brd ff:ff:ff:ff:ff:ff
    altname wlp0s20f3
    inet 10.33.77.166/20 brd 10.33.79.255 scope global dynamic noprefixroute wlo1
       valid_lft 81843sec preferred_lft 81843sec
    inet6 fe80::20d9:f698:7fc9:76ba/64 scope link noprefixroute 
       valid_lft forever preferred_lft forever

> **🌞 Tester que votre LAN + votre adressage IP est fonctionnel**

**_gabriel@zengab:~$ ping 192.168.56.101_**

    PING 192.168.56.101 (192.168.56.101) 56(84) bytes of data.
    64 bytes from 192.168.56.101: icmp_seq=1 ttl=64 time=1.01 ms
    64 bytes from 192.168.56.101: icmp_seq=2 ttl=64 time=0.753 ms
    64 bytes from 192.168.56.101: icmp_seq=3 ttl=64 time=0.771 ms
    64 bytes from 192.168.56.101: icmp_seq=4 ttl=64 time=0.795 ms

**_gab@gab-VirtualBox:~$ ping 10.33.77.166_**

    PING 10.33.77.166 (10.33.77.166) 56(84) bytes of data.
    64 bytes from 10.33.77.166: icmp_seq=1 ttl=63 time=0.647 ms
    64 bytes from 10.33.77.166: icmp_seq=2 ttl=63 time=0.624 ms
    C64 bytes from 10.33.77.166: icmp_seq=3 ttl=63 time=0.595 ms

> **🌞 Capture de ping**

**_gab@gab-VirtualBox:~$ sudo nc -l 0809_**

    Gros bg

> **🌞 Sur le PC serveur toujours**

**_gab@gab-VirtualBox:~$ sudo ss -lnpt_**

    State     Recv-Q    Send-Q       Local Address:Port        Peer Address:Port    Process                                                                         
    LISTEN    0         4096         127.0.0.53%lo:53               0.0.0.0:*        users:(("systemd-resolve",pid=430,fd=15))                                      
    LISTEN    0         4096            127.0.0.54:53               0.0.0.0:*        users:(("systemd-resolve",pid=430,fd=17))                                      
    LISTEN    0         4096             127.0.0.1:631              0.0.0.0:*        users:(("cupsd",pid=1162,fd=7))                                                
    LISTEN    0         4096                 [::1]:631                 [::]:*        users:(("cupsd",pid=1162,fd=6))                                                
    LISTEN    0         4096                     *:22                     *:*        users:(("sshd",pid=5081,fd=3),("systemd",pid=1,fd=168))                        

> **🌞 Sur le PC client/Echanger des messages**

**_gabriel@zengab:~$ nc 192.168.56.101 0809_**

    Gros bg


> **🌞 Utilisez une commande qui permet de voir la connexion en cours**

**_gabriel@zengab:~$ ss dst 192.168.56.101__**

    Netid         State         Recv-Q         Send-Q                 Local Address:Port                    Peer Address:Port        Process         
    tcp           ESTAB         0              0                       192.168.56.1:42160                 192.168.56.101:809                         
    tcp           ESTAB         0              0                       192.168.56.1:34096                 192.168.56.101:ssh                         
    tcp           ESTAB         0              0                       192.168.56.1:55328                 192.168.56.101:ssh                         


# III. Analyse de vos applications usuelles

### 2. Autres services

