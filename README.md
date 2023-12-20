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
#address 192.201.8.2
#netmask 255.255.248.0
#gateway 192.201.8.1

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
#address 192.201.4.3
#netmask 255.255.252.0
#gateway 192.201.4.1

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
#address 192.201.0.131
#netmask 255.255.255.128
#gateway 192.201.0.129

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
#address 192.201.2.2
#netmask 255.255.254.0
#gateway 192.201.2.1

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

Kemudian, dilakuka kongfigurasi untuk _set-up_ DHCP di beberapa node seperti berikut:

- **Revolte** - dhcpd.conf
```
#A1
subnet 192.201.0.0 netmask 255.255.255.252 {
}

#A2
subnet 192.201.8.0 netmask 255.255.248.0 {
    range 192.201.8.2 192.201.15.254;
    option routers 192.201.8.1;
    option broadcast-address 192.201.15.255;
    default-lease-time 180;
    max-lease-time 5760;
}

#A3
subnet 192.201.4.0 netmask 255.255.252.0 {
    range 192.201.4.3 192.201.7.254;
    option routers 192.201.4.1;
    option broadcast-address 192.201.7.255;
    default-lease-time 180;
    max-lease-time 5760;
}

#A4
subnet 192.201.0.4 netmask 255.255.255.252 {
}

#A5
subnet 192.201.0.8 netmask 255.255.255.252 {
}

#A6
subnet 192.201.0.12 netmask 255.255.255.252 {
}

#A7
subnet 192.201.2.0 netmask 255.255.254.0 {
    range 192.201.2.2 192.201.2.254;
    option routers 192.201.2.1;
    option broadcast-address 192.201.2.255;
    default-lease-time 180;
    max-lease-time 5760;
}

#A8
subnet 192.201.0.128 netmask 255.255.255.128 {
    range 192.201.0.131 192.201.0.254;
    option routers 192.201.0.129;
    option broadcast-address 192.201.0.255;
    default-lease-time 180;
    max-lease-time 5760;
}

#A9
subnet 192.201.0.16 netmask 255.255.255.252 {
}

#A10
subnet 192.201.0.20 netmask 255.255.255.252 {
}
```

- **DHCP Relay** - isc-dhcp-relay
```bash
SERVERS="192.201.0.22"

# On what interfaces should the DHCP relay (dhrelay) serve DHCP requests?
INTERFACES="eth0 eth1 eth2"

# Additional options that are passed to the DHCP relay daemon?
OPTIONS=""
```

## Soal 1  
> Agar topologi yang kalian buat dapat mengakses keluar, kalian diminta untuk mengkonfigurasi Aura menggunakan iptables, tetapi tidak ingin menggunakan MASQUERADE.
Pada `Aura` jalankan
```sh
ETH0_IP=$(ip -4 addr show eth0 | grep -oP '(?<=inet\s)\d+(\.\d+){3}')
iptables -t nat -A POSTROUTING -o eth0 -j SNAT --to-source $ETH0_IP
```
Berikut adalah penjelasan dari _syntax_ tersebut beserta masing-masing fungsinya:

`ip -4 addr show eth0:` Menampilkan informasi alamat IP untuk antarmuka jaringan eth0.

`grep -oP '(?<=inet\s)\d+(\.\d+){3}'`: Menggunakan grep untuk mengambil alamat IP dari baris yang mengandung "inet" pada output sebelumnya.`

`iptables -t nat -A POSTROUTING`: Menambahkan aturan ke chain POSTROUTING pada tabel nat.

`-o eth0`: Menentukan antarmuka keluar (outgoing) sebagai eth0.

`-j SNAT`: Menyatakan bahwa _rules_ tersebut adalah Source Network Address Translation.

`--to-source $ETH0_IP`: Menentukan alamat IP sumber untuk melakukan SNAT, menggunakan alamat IP yang telah diperoleh sebelumnya dari eth0.

_Output_ dari nomor 1 adalah tiap _route_ dapat melakukan ping keluar (misalnya: google.com) seperti pada gambar berikut:

Lalu untuk testing buka client dan lakukan `ping google.com`

## Soal 2
> Kalian diminta untuk melakukan drop semua TCP dan UDP kecuali port 8080 pada TCP.
```sh
iptables -F
iptables -A INPUT -p icmp -j ACCEPT
iptables -A INPUT -p tcp --dport 8080 -j ACCEPT
iptables -A INPUT -p tcp -j DROP
iptables -A INPUT -p udp -j DROP
```
Dari _syntax_ tersebut dapat dilihat bahwa _node_ tersebut hanya menerima koneksi dari port 8080 dengan koneksi TCP. Berikut adalah hasil _testing_ yang sudah dilakukan:

![image](https://github.com/altriskaa/jarkom-modul-5-d20-2023/assets/114663340/24211f64-d95e-4811-9e52-80b82e88e3bc)

Dari gambar tersebut dapat dilihat bahwa koneksi yang menggunakan port 8080 dapat mengirim dan menerima pesa, sedangkan untuk koneksi dengan port 8000 tidak bisa berkomunikasi.



## Soal 3
> Kepala Suku North Area meminta kalian untuk membatasi DHCP dan DNS Server hanya dapat dilakukan ping oleh maksimal 3 device secara bersamaan, selebihnya akan di drop.
- Revolte
```sh
iptables -A INPUT -m state --state ESTABLISHED,RELATED -j ACCEPT
iptables -A INPUT -p icmp -m connlimit --connlimit-above 3 --connlimit-mask 0 -j DROP
```
- Richter   
```sh
iptables -A INPUT -m state --state ESTABLISHED,RELATED -j ACCEPT
iptables -A INPUT -p icmp -m connlimit --connlimit-above 3 --connlimit-mask 0 -j DROP
```

Kemudian dilakukan testing dengan cara melakukan ping menuju node tersebut dengan 4 node. Berikut adalah hasil testing yang telah dilakukan:

![image](https://github.com/altriskaa/jarkom-modul-5-d20-2023/assets/114663340/43aa4fcc-6eed-49c6-a161-0545e5117b33)

Dapat dilihat bahwa node keempat yang melakukan ping akan gagal dan tidak bisa tersambung dengan node tujuan.


## Soal 4
> Lakukan pembatasan sehingga koneksi SSH pada Web Server hanya dapat dilakukan oleh masyarakat yang berada pada GrobeForest.
- Sein dan Stark
```sh
iptables -A INPUT -p tcp --dport 22 -s 192.201.4.0/22 -j ACCEPT
iptables -A INPUT -p tcp --dport 22 -j DROP
```
Dalam syntax tersebut dilakukan pembatasan untuk subnet dari GrobeForest, serta hanya bisa diakses oleh ip 22 atau SSH. Berikut adalah hasil testing untuk nomor 4:

![image](https://github.com/altriskaa/jarkom-modul-5-d20-2023/assets/114663340/2cc90876-7783-46f5-9657-df3ae68f2e7f)

Dapat dilihat bahwa untuk GrobeForest menunjukkan hasil open, sedangkan untuk node lain filtered atau tidak berhasil tersambung.


## Soal 5
> Selain itu, akses menuju WebServer hanya diperbolehkan saat jam kerja yaitu Senin-Jumat pada pukul 08.00-16.00. 
- Sein dan Stark  
Tambahkan rules pada iptables seperti berikut:
```sh
iptables -A INPUT -p tcp --dport 22 -s 192.201.4.0/22 -m time --timestart 08:00 --timestop 16:00 --weekdays Mon,Tue,Wed,Thu,Fri -j ACCEPT
iptables -A INPUT -p tcp --dport 22 -j DROP
``` 
## Soal 6
> Lalu, karena ternyata terdapat beberapa waktu di mana network administrator dari WebServer tidak bisa stand by, sehingga perlu ditambahkan rule bahwa akses pada hari Senin - Kamis pada jam 12.00 - 13.00 dilarang (istirahat maksi cuy) dan akses di hari Jumat pada jam 11.00 - 13.00 juga dilarang (maklum, Jumatan rek).   
- Sein dan Stark  
Tambahkan rules pada iptables seperti berikut:
```sh
iptables -A INPUT -p tcp --dport 22 -s 192.201.4.0/22 -m time --timestart 12:00 --timestop 13:00 --weekdays Mon,Tue,Wed,Thu -j DROP
iptables -A INPUT -p tcp --dport 22 -s 192.201.4.0/22 -m time --timestart 11:00 --timestop 13:00 --weekdays Fri -j DROP
``` 
## Soal 7
> Karena terdapat 2 WebServer, kalian diminta agar setiap client yang mengakses Sein dengan Port 80 akan didistribusikan secara bergantian pada Sein dan Stark secara berurutan dan request dari client yang mengakses Stark dengan port 443 akan didistribusikan secara bergantian pada Sein dan Stark secara berurutan.
- Heiter dan Frieren  
Tambahkan rules pada iptables di router yang terhubung dengan webserver seperti berikut:
```sh
iptables -A PREROUTING -t nat -p tcp --dport 80 -d 192.201.4.2 -m statistic --mode nth --every 2 --packet 0 -j DNAT --to-destination 192.201.4.2
iptables -A PREROUTING -t nat -p tcp --dport 80 -d 192.201.4.2 -j DNAT --to-destination 192.201.0.10
iptables -A PREROUTING -t nat -p tcp --dport 443 -d 192.201.0.10 -m statistic --mode nth --every 2 --packet 0 -j DNAT --to-destination 192.201.0.10
iptables -A PREROUTING -t nat -p tcp --dport 443 -d 192.201.0.10 -j DNAT --to-destination 192.201.4.2
```
- Sein dan Stark  
Tuliskan syntax berikut pada webserver:
```sh
while true; do nc -l -p 80 -c 'echo "ini sein"'; done #sein
while true; do nc -l -p 443 -c 'echo "ini dari stark"'; done #stark
while true; do nc -l -p 443 -c 'echo "ini sein"'; done #sein
while true; do nc -l -p 443 -c 'echo "ini stark"'; done #stark
```
## Soal 8
> Karena berbeda koalisi politik, maka subnet dengan masyarakat yang berada pada Revolte dilarang keras mengakses WebServer hingga masa pencoblosan pemilu kepala suku 2024 berakhir. Masa pemilu (hingga pemungutan dan penghitungan suara selesai) kepala suku bersamaan dengan masa pemilu Presiden dan Wakil Presiden Indonesia 2024.
- Sein dan Stark  
Tambahkan rules pada iptables seperti berikut:
```sh
Revolte_Subnet="192.201.0.22/30"
Pemilu_Start=$(date -d "2023-10-19T00:00" +"%Y-%m-%dT%H:%M")
Pemilu_End=$(date -d "2024-02-15T00:00" +"%Y-%m-%dT%H:%M")
iptables -A INPUT -p tcp -s $Revolte_Subnet --dport 80 -m time --datestart "$Pemilu_Start" --datestop "$Pemilu_End" -j DROP
```
## Soal 9
> Sadar akan adanya potensial saling serang antar kubu politik, maka WebServer harus dapat secara otomatis memblokir  alamat IP yang melakukan scanning port dalam jumlah banyak (maksimal 20 scan port) di dalam selang waktu 10 menit. 
(clue: test dengan nmap)
- Sein dan Stark  
Tambahkan rules pada iptables seperti berikut:
```sh
iptables -N scan_port
iptables -A INPUT -m recent --name scan_port --update --seconds 600 --hitcount 20 -j DROP
iptables -A FORWARD -m recent --name scan_port --update --seconds 600 --hitcount 20 -j DROP
iptables -A INPUT -m recent --name scan_port --set -j ACCEPT
iptables -A FORWARD -m recent --name scan_port --set -j ACCEPT
```
## Soal 10
> Karena kepala suku ingin tau paket apa saja yang di-drop, maka di setiap node server dan router ditambahkan logging paket yang di-drop dengan standard syslog level.

