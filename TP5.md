# **TP5 : Un ptit LAN à nous**

## I. Setup

> **☀️ Uniquement avec des commandes, prouvez-que :**

_gab@gab-VirtualBox:~$ ip a_

1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN group default qlen 1000
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
       valid_lft forever preferred_lft forever
    inet6 ::1/128 scope host noprefixroute 
       valid_lft forever preferred_lft forever

2: enp0s3: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc pfifo_fast state UP group default qlen 1000
    link/ether 08:00:27:41:c3:76 brd ff:ff:ff:ff:ff:ff
    inet 10.5.1.11/24 brd 10.5.1.255 scope global noprefixroute enp0s3
       valid_lft forever preferred_lft forever
    inet6 fe80::a00:27ff:fe41:c376/64 scope link 
       valid_lft forever preferred_lft forever

_____________________________________________________

_gab@gab-VirtualBox:~$ ip a_

1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN group default qlen 1000
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
       valid_lft forever preferred_lft forever
    inet6 ::1/128 scope host noprefixroute 
       valid_lft forever preferred_lft forever

2: enp0s3: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc pfifo_fast state UP group default qlen 1000
    link/ether 08:00:27:f1:e3:af brd ff:ff:ff:ff:ff:ff
    inet 10.5.1.12/24 brd 10.5.1.255 scope global noprefixroute enp0s3
       valid_lft forever preferred_lft forever
    inet6 fe80::a00:27ff:fef1:e3af/64 scope link 
       valid_lft forever preferred_lft forever

_____________

_[gab@localhost network-scripts]$ ip a_

1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN group default qlen 1000
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
       valid_lft forever preferred_lft forever
    inet6 ::1/128 scope host 
       valid_lft forever preferred_lft forever

2: enp0s3: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc fq_codel state UP group default qlen 1000
    link/ether 08:00:27:64:1e:66 brd ff:ff:ff:ff:ff:ff
    inet 10.0.2.15/24 brd 10.0.2.255 scope global dynamic noprefixroute enp0s3
       valid_lft 86252sec preferred_lft 86252sec
    inet6 fe80::a00:27ff:fe64:1e66/64 scope link 
       valid_lft forever preferred_lft forever
       
3: enp0s8: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc fq_codel state UP group default qlen 1000
    link/ether 08:00:27:0c:85:3f brd ff:ff:ff:ff:ff:ff
    inet 10.5.1.254/24 brd 10.5.1.255 scope global noprefixroute enp0s8
       valid_lft forever preferred_lft forever
    inet6 fe80::a00:27ff:fe0c:853f/64 scope link 
       valid_lft forever preferred_lft forever

____


_[gab@localhost ~]$ ip a_

1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN group default qlen 1000
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
       valid_lft forever preferred_lft forever
    inet6 ::1/128 scope host 
       valid_lft forever preferred_lft forever

2: enp0s3: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc fq_codel state UP group default qlen 1000
    link/ether 08:00:27:64:1e:66 brd ff:ff:ff:ff:ff:ff
    inet 10.0.2.15/24 brd 10.0.2.255 scope global dynamic noprefixroute enp0s3
       valid_lft 85414sec preferred_lft 85414sec
    inet6 fe80::a00:27ff:fe64:1e66/64 scope link 
       valid_lft forever preferred_lft forever

3: enp0s8: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc fq_codel state UP group default qlen 1000
    link/ether 08:00:27:0c:85:3f brd ff:ff:ff:ff:ff:ff
    inet 10.5.1.254/24 brd 10.5.1.255 scope global noprefixroute enp0s8
       valid_lft forever preferred_lft forever
    inet6 fe80::a00:27ff:fe0c:853f/64 scope link 
       valid_lft forever preferred_lft forever

___

_[gab@localhost ~]$ ping 10.5.1.11_

PING 10.5.1.11 (10.5.1.11) 56(84) bytes of data.
64 bytes from 10.5.1.11: icmp_seq=1 ttl=64 time=1.23 ms
64 bytes from 10.5.1.11: icmp_seq=2 ttl=64 time=0.830 ms
^C
--- 10.5.1.11 ping statistics ---
2 packets transmitted, 2 received, 0% packet loss, time 1001ms
rtt min/avg/max/mdev = 0.830/1.030/1.230/0.200 ms


_[gab@localhost ~]$ ping 10.5.1.12_

PING 10.5.1.12 (10.5.1.12) 56(84) bytes of data.
64 bytes from 10.5.1.12: icmp_seq=1 ttl=64 time=1.56 ms
64 bytes from 10.5.1.12: icmp_seq=2 ttl=64 time=1.06 ms
^C
--- 10.5.1.12 ping statistics ---
2 packets transmitted, 2 received, 0% packet loss, time 999ms
rtt min/avg/max/mdev = 1.056/1.308/1.560/0.252 ms

____

## 1. Accès internet routeur

> **☀️ Déjà, prouvez que le routeur a un accès internet**

_[gab@localhost ~]$ ping 1.1.1.1_

PING 1.1.1.1 (1.1.1.1) 56(84) bytes of data.
64 bytes from 1.1.1.1: icmp_seq=1 ttl=63 time=94.6 ms
64 bytes from 1.1.1.1: icmp_seq=2 ttl=63 time=51.7 ms
^C
--- 1.1.1.1 ping statistics ---
2 packets transmitted, 2 received, 0% packet loss, time 999ms
rtt min/avg/max/mdev = 51.688/73.146/94.604/21.458 ms

____

> **☀️ Activez le routage**

_[gab@localhost ~]$ sudo firewall-cmd --add-masquerade --permanent_

[sudo] password for gab: 
Warning: ALREADY_ENABLED: masquerade
success

___

## 2. Accès internet clients

> **☀️ Prouvez que les clients ont un accès internet**

_gab@client1:~$ ping www.ynov.com_

PING www.ynov.com (172.67.74.226) 56(84) bytes of data.
64 bytes from 172.67.74.226: icmp_seq=1 ttl=61 time=75.8 ms
64 bytes from 172.67.74.226: icmp_seq=2 ttl=61 time=73.9 ms
^C
--- www.ynov.com ping statistics ---
2 packets transmitted, 2 received, 0% packet loss, time 1001ms
rtt min/avg/max/mdev = 73.859/74.843/75.828/0.984 ms

____

> **☀️ Montrez-moi le contenu final du fichier de configuration de l'interface réseau**

network:
  version: 2
  renderer: networkd
  ethernets:
    enp0s3:
      dhcp4: no
      addresses: [10.5.1.12/24]
      gateway4: 10.5.1.254
      nameservers:
          addresses: [1.1.1.1]

____

## III. Serveur SSH

> **☀️ Sur routeur.tp5.b1, déterminer sur quel port écoute le serveur SSH**

_[gab@localhost ~]$ sudo ss -lnpt | grep 22_

LISTEN 0      128          0.0.0.0:22        0.0.0.0:*    users:(("sshd",pid=704,fd=3))
LISTEN 0      128             [::]:22           [::]:*    users:(("sshd",pid=704,fd=4))

___

> **☀️ Sur routeur.tp5.b1, vérifier que ce port est bien ouvert**

_[gab@localhost ~]$ sudo ss -npt | grep 22_

ESTAB 0      0         10.5.1.254:22       10.5.1.1:56624 users:(("sshd",pid=1368,fd=4),("sshd",pid=1353,fd=4))

___

## IV. Serveur DHCP
### 3. Rendu attendu

_sudo dnf -y install dhcp-server_

_sudo nano /etc/dhcp/dhcpd.conf_

# DHCP Server Configuration file.
#   see /usr/share/doc/dhcp-server/dhcpd.conf.example
#   see dhcpd.conf(5) man page
#
option domain-name-servers     1.1.1.1;

subnet 10.5.1.0 netmask 255.255.255.0 {
    # specify the range of lease IP address
    range dynamic-bootp 10.5.1.137 10.5.1.237;
    # specify broadcast address
    option broadcast-address 10.0.0.255;
    # specify gateway
    option routers 10.5.1.254;
}
