#  TP6 : Des bo services dans des bo LANs

## 2. Marche à suivre

### ☀️ Prouvez que...

_[gab@DHCP ~]$ ping 10.6.2.11_

```PING 10.6.2.11 (10.6.2.11) 56(84) bytes of data.
64 bytes from 10.6.2.11: icmp_seq=1 ttl=63 time=0.929 ms
64 bytes from 10.6.2.11: icmp_seq=2 ttl=63 time=1.20 ms
^C
--- 10.6.2.11 ping statistics ---
2 packets transmitted, 2 received, 0% packet loss, time 1001ms
rtt min/avg/max/mdev = 0.929/1.062/1.196/0.133 ms
```
_[gab@DHCP ~]$ ping ynov.com_

```PING ynov.com (104.26.11.233) 56(84) bytes of data.
64 bytes from 104.26.11.233 (104.26.11.233): icmp_seq=1 ttl=61 time=16.9 ms
64 bytes from 104.26.11.233 (104.26.11.233): icmp_seq=2 ttl=61 time=47.1 ms
^C
--- ynov.com ping statistics ---
2 packets transmitted, 2 received, 0% packet loss, time 1002ms
rtt min/avg/max/mdev = 16.946/32.007/47.069/15.061 ms
```
_[gab@Web ~]$ ping ynov.com_
```
PING ynov.com (104.26.10.233) 56(84) bytes of data.
64 bytes from 104.26.10.233 (104.26.10.233): icmp_seq=1 ttl=61 time=21.0 ms
64 bytes from 104.26.10.233 (104.26.10.233): icmp_seq=2 ttl=61 time=22.0 ms
^C
--- ynov.com ping statistics ---
2 packets transmitted, 2 received, 0% packet loss, time 1002ms
rtt min/avg/max/mdev = 21.020/21.523/22.026/0.503 ms
```
## 2. Client

### ☀️ Prouvez que...

_gab@Client:~$ ip a_
```
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN group default qlen 1000
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
       valid_lft forever preferred_lft forever
    inet6 ::1/128 scope host noprefixroute 
       valid_lft forever preferred_lft forever
2: enp0s3: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc pfifo_fast state UP group default qlen 1000
    link/ether 08:00:27:b7:19:71 brd ff:ff:ff:ff:ff:ff
    inet 10.6.1.37/24 brd 10.6.1.255 scope global dynamic noprefixroute enp0s3
       valid_lft 42558sec preferred_lft 42558sec
    inet6 fe80::310d:f9c8:91f1:286c/64 scope link noprefixroute 
       valid_lft forever preferred_lft forever
```

_gab@Client:~$ resolvectl status_
```
Global
         Protocols: -LLMNR -mDNS -DNSOverTLS DNSSEC=no/unsupported
  resolv.conf mode: stub

Link 2 (enp0s3)
    Current Scopes: DNS
         Protocols: +DefaultRoute -LLMNR -mDNS -DNSOverTLS DNSSEC=no/unsupported
Current DNS Server: 1.1.1.1
       DNS Servers: 1.1.1.1
```

_gab@Client:~$ ip rout show_
```
default via 10.6.1.254 dev enp0s3 proto dhcp src 10.6.1.37 metric 100 
10.6.1.0/24 dev enp0s3 proto kernel scope link src 10.6.1.37 metric 100 
```

_gab@Client:~$ ping google.com_
```
PING google.com (142.251.37.46) 56(84) bytes of data.
64 bytes from mrs09s13-in-f14.1e100.net (142.251.37.46): icmp_seq=1 ttl=61 time=17.6 ms
64 bytes from mrs09s13-in-f14.1e100.net (142.251.37.46): icmp_seq=2 ttl=61 time=17.2 ms
64 bytes from mrs09s13-in-f14.1e100.net (142.251.37.46): icmp_seq=3 ttl=61 time=22.1 ms
^C
--- google.com ping statistics ---
3 packets transmitted, 3 received, 0% packet loss, time 2002ms
rtt min/avg/max/mdev = 17.174/18.932/22.051/2.211 ms
```

## 3.1 Analyse et test

### ☀️ Déterminer sur quel port écoute le serveur NGINX
_[gab@Web ~]$ sudo ss -lnpt | grep 80_

```
LISTEN 0      511          0.0.0.0:80        0.0.0.0:*    users:(("nginx",pid=1861,fd=6),("nginx",pid=1860,fd=6))
LISTEN 0      511             [::]:80           [::]:*    users:(("nginx",pid=1861,fd=7),("nginx",pid=1860,fd=7))
```

### ☀️ Ouvrir ce port dans le firewall

_[gab@Web ~]$ curl http://10.6.2.11_
```
<!doctype html>
```

### 3. Serveur DHCP

_gab@Client2:~$ resolvectl status_
```
Global
         Protocols: -LLMNR -mDNS -DNSOverTLS DNSSEC=no/unsupported
  resolv.conf mode: stub

Link 2 (enp0s3)
    Current Scopes: DNS
         Protocols: +DefaultRoute -LLMNR -mDNS -DNSOverTLS DNSSEC=no/unsupported
Current DNS Server: 1.1.1.1
       DNS Servers: 1.1.1.1

```
_gab@Client2:~$ ip a_

```
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN group default qlen 1000
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
       valid_lft forever preferred_lft forever
    inet6 ::1/128 scope host noprefixroute 
       valid_lft forever preferred_lft forever
2: enp0s3: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc pfifo_fast state UP group default qlen 1000
    link/ether 08:00:27:35:c0:4f brd ff:ff:ff:ff:ff:ff
    inet 10.6.1.38/24 brd 10.6.1.255 scope global dynamic noprefixroute enp0s3
       valid_lft 42911sec preferred_lft 42911sec
    inet6 fe80::d58a:8ebb:fa2a:174e/64 scope link noprefixroute 
       valid_lft forever preferred_lft forever
```