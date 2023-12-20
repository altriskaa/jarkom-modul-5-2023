# Laporan Resmi Praktikum Jaringan Komputer Modul 5 D20  2023

## Author
| Nama | NRP |Github |
|---------------------------|------------|--------|
|Khairuddin Nasty | 5025201041 | https://github.com/khairuddin-n |
|Altriska Izzati Khairunnisa H | 5025211187 | https://github.com/altriskaa |

## Topologi
![image](https://github.com/altriskaa/jarkom-modul-5-d20-2023/assets/114663340/913958c1-6f89-41cc-bd32-b33e07ee4df5)

## Subnet dan Prefix IP 
![image](https://github.com/altriskaa/jarkom-modul-5-d20-2023/assets/114663340/63069f21-aa21-4060-9857-33d83d34c96a)
Dengan menggunakan prefix IP `192.201`
## Route
![image](https://github.com/altriskaa/jarkom-modul-5-d20-2023/assets/114663340/6520c0a9-f6d8-4404-9b79-687678bf3759)

## Pembagian IP
### VLSM Tree
![image](https://github.com/altriskaa/jarkom-modul-5-d20-2023/assets/114663340/4b30a72a-fa36-4523-94f4-1cc2cc211c23)
### IP
![image](https://github.com/altriskaa/jarkom-modul-5-d20-2023/assets/114663340/5eee1223-5a5d-4f1b-ae4a-35168f61c50d)

## Network Configuration
- Aura
```
auto eth0
iface eth0 inet static

# A1
auto eth1
iface eth1 inet static
address 192.201.0.1
netmask 255.255.255.252

# A4
auto eth2
iface eth2 inet static
address 192.201.0.5
netmask 255.255.255.252

up echo nameserver 192.168.122.1 > /etc/resolv.conf
```
- Heiter
```
#A1
auto eth0
iface eth0 inet static
address 192.201.0.2
netmask 255.255.255.252
gateway 192.201.0.1

#A2
auto eth1
iface eth1 inet static
address 192.201.8.1
netmask 255.255.248.0

#A3
auto eth2
iface eth2 inet static
address 192.201.4.1
netmask 255.255.252.0

up echo nameserver 192.168.122.1 > /etc/resolv.conf
```
- Turk Region (A2)
```
auto eth0
iface eth0 inet dhcp
address 192.201.8.2
netmask 255.255.248.0
gateway 192.201.8.1

up echo nameserver 192.168.122.1 > /etc/resolv.conf
```
- Sein (A3)
```
auto eth0
iface eth0 inet static
address 192.201.4.2
netmask 255.255.252.0
gateway 192.201.4.1

up echo nameserver 192.168.122.1 > /etc/resolv.conf
```
- Grobe Forest (A3)
```
auto eth0
iface eth0 inet dhcp
address 192.201.4.3
netmask 255.255.252.0
gateway 192.201.4.1

up echo nameserver 192.168.122.1 > /etc/resolv.conf
```
- Frieren
```
#A4
auto eth0
iface eth0 inet static
address 192.201.0.6
netmask 255.255.255.252
gateway 192.201.0.5

#A5
auto eth1
iface eth1 inet static
address 192.201.0.9
netmask 255.255.255.252

#A6
auto eth2
iface eth2 inet static
address 192.201.0.13
netmask 255.255.255.252

up echo nameserver 192.168.122.1 > /etc/resolv.conf
```
- Himmel
```
#A6
auto eth0
iface eth0 inet static
address 192.201.0.14
netmask 255.255.255.252
gateway 192.201.0.13

#A7
auto eth1
iface eth1 inet static
address 192.201.2.1
netmask 255.255.254.0

#A8
auto eth2
iface eth2 inet static
address 192.201.0.129
netmask 255.255.255.128

up echo nameserver 192.168.122.1 > /etc/resolv.conf
```
- Schwer Mountain (A8)
```
auto eth0
iface eth0 inet dhcp
address 192.201.0.131
netmask 255.255.255.128
gateway 192.201.0.129

up echo nameserver 192.168.122.1 > /etc/resolv.conf
```
- Fern
```
#A8
auto eth0
iface eth0 inet static
address 192.201.0.130
netmask 255.255.255.128
gateway 192.201.0.129

#A9
auto eth1
iface eth1 inet static
address 192.201.0.17
netmask 255.255.255.252

#A10
auto eth2
iface eth2 inet static
address 192.201.0.21
netmask 255.255.255.252

up echo nameserver 192.168.122.1 > /etc/resolv.conf
```
- Richter (A9)
```
auto eth0
iface eth0 inet static
address 192.201.0.18
netmask 255.255.255.252
gateway 192.201.0.17

up echo nameserver 192.168.122.1 > /etc/resolv.conf
```
- Revolte (A10)
```
auto eth0
iface eth0 inet static
address 192.201.0.22
netmask 255.255.255.252
gateway 192.201.0.21

up echo nameserver 192.168.122.1 > /etc/resolv.conf
```
- Stark (A5)
```
auto eth0
iface eth0 inet static
address 192.201.0.10
netmask 255.255.255.252
gateway 192.201.0.9

up echo nameserver 192.168.122.1 > /etc/resolv.conf
```
- Laub Hills (A7)
```
auto eth0
iface eth0 inet dhcp
address 192.201.2.2
netmask 255.255.254.0
gateway 192.201.2.1

up echo nameserver 192.168.122.1 > /etc/resolv.conf
```

## Routing
- Aura
```
up route add -net 192.201.8.0 netmask 255.255.248.0 gw 192.201.0.2
up route add -net 192.201.4.0 netmask 255.255.252.0 gw 192.201.0.2

up route add -net 192.201.0.4 netmask 255.255.255.252 gw 192.201.0.6
up route add -net 192.201.0.8 netmask 255.255.255.252 gw 192.201.0.6
up route add -net 192.201.2.0 netmask 255.255.254.0 gw 192.201.0.6
up route add -net 192.201.0.128 netmask 255.255.255.128 gw 192.201.0.6
up route add -net 192.201.0.16 netmask 255.255.255.252 gw 192.201.0.6
up route add -net 192.201.0.20 netmask 255.255.255.252 gw 192.201.0.6
```
- Frieren
```
up route add -net 192.201.2.0 netmask 255.255.254.0 gw 192.201.0.13
up route add -net 192.201.0.128 netmask 255.255.255.128 gw 192.201.0.13
up route add -net 192.201.0.16 netmask 255.255.255.252 gw 192.201.0.13
up route add -net 192.201.0.20 netmask 255.255.255.252 gw 192.201.0.13
```
- Himmel
```
up route add -net 192.201.0.16 netmask 255.255.255.252 gw 192.201.0.130
up route add -net 192.201.0.20 netmask 255.255.255.252 gw 192.201.0.130
```


