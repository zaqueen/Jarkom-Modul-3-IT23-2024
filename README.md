# Jarkom-Modul-3-IT23-2024
**Praktikum Jaringan Komputer Modul 3 Tahun 2024**

# Laporan Resmi
| Nama | NRP |
| ---- | ---- |
| Etha Felisya Br Purba | 5027221017 |
| Rahmad Aji Wicaksono | 5027221034 |

## Daftar Isi
1. [Laporan Resmi](#Laporan-Resmi)
2. [Daftar Isi](#Daftar-Isi)
3. [Topologi](#Topologi)
4. [Config](#Config)
5. [Bashrc](#Bashrc)
6. [Soal 1](#Soal-1)
7. [Soal 2](#Soal-2)
8. [Soal 3](#Soal-3)
9. [Soal 4](#Soal-4)
10. [Soal 5](#Soal-5)
11. [Soal 6](#Soal-6)
12. [Soal 7](#Soal-7)
13. [Soal 8](#Soal-8)
14. [Soal 9](#Soal-9)
15. [Soal 10](#Soal-10)
16. [Soal 11](#Soal-11)
17. [Soal 12](#Soal-12)
18. [Soal 13](#Soal-13)
18. [Soal 14](#Soal-14)
18. [Soal 15](#Soal-15)
18. [Soal 16](#Soal-16)
18. [Soal 17](#Soal-17)
18. [Soal 18](#Soal-18)
18. [Soal 19](#Soal-19)
18. [Soal 20](#Soal-20)

## Topologi
 <img src="attachment/topologii.jpeg">

## Konfigurasi
* Arakis (DHCP Relay)
```
# DHCP config for eth0
auto eth0
iface eth0 inet dhcp

auto eth1
iface eth1 inet static
	address 10.75.1.0
	netmask 255.255.255.0

auto eth2
iface eth2 inet static
	address 10.75.2.0
	netmask 255.255.255.0

auto eth3
iface eth3 inet static
	address 10.75.3.0
	netmask 255.255.255.0

auto eth4
iface eth4 inet static
	address 10.75.4.0
	netmask 255.255.255.0
```
* Irulan (DNS Server)
```
auto eth0
iface eth0 inet static
	address 10.75.3.3
	netmask 255.255.255.0
	gateway 10.75.3.0
```
* Mohiam (DHCP Server)
```
auto eth0
iface eth0 inet static
	address 10.75.3.2
	netmask 255.255.255.0
	gateway 10.75.3.0
```
* Stilgar (Load Balancer)
```
auto eth0
iface eth0 inet static
	address 10.75.4.3
	netmask 255.255.255.0
	gateway 10.75.4.0
```
* Chani (Databse Server)
```
auto eth0
iface eth0 inet static
	address 10.75.4.2
	netmask 255.255.255.0
	gateway 10.75.4.0
```
* Leto (Laravel Worker)
```
auto eth0
iface eth0 inet static
	address 10.75.2.4
	netmask 255.255.255.0
	gateway 10.75.2.0
```
* Duncan (Laravel Worker)
```
auto eth0
iface eth0 inet static
	address 10.75.2.3
	netmask 255.255.255.0
	gateway 10.75.2.0

```
* Jessica (Laravel Worker)
```
auto eth0
iface eth0 inet static
	address 10.75.2.2
	netmask 255.255.255.0
	gateway 10.75.2.0
```
* Vladimir (PHP Worker)
```
auto eth0
iface eth0 inet static
	address 10.75.1.4
	netmask 255.255.255.0
	gateway 10.75.1.0
```
* Rabban (PHP Worker)
```
auto eth0
iface eth0 inet static
	address 10.75.1.3
	netmask 255.255.255.0
	gateway 10.75.1.0
```
* Feyd (PHP Worker)
```
auto eth0
iface eth0 inet static
	address 10.75.1.2
	netmask 255.255.255.0
	gateway 10.75.1.0
```
* Dmitri, Paul (Client)
```
auto eth0
iface eth0 inet dhcp
```

## Install Depedencies
* Arakis (DHCP Relay)
```
apt-get update
apt-get install isc-dhcp-relay -y
```
* Irulan (DNS Server)
```
apt-get update
apt-get install bind9 -y
```
* Mohiam (DHCP Server)
```
apt-get update
apt-get install isc-dhcp-server -y
```
* Stilgar (Load Balancer)
```
apt-get update
apt-get install apache2-utils -y
apt-get install nginx -y
apt-get install lynx -y
```
* Chani (Databse Server)
```
apt-get update
apt-get install mariadb-server -y
```
* Leto, Duncan, Jessica (Laravel Worker)
* Vladimir, Rabban, Feyd (PHP Worker)
* Dmitri, Paul (Client)
```
apt-get update
apt-get install lynx -y
apt-get install htop -y
apt-get install apache2-utils -y
apt-get install jq -y
```
## Nomor 0
> Planet Caladan sedang mengalami krisis karena kehabisan spice, klan atreides berencana untuk melakukan eksplorasi ke planet arakis dipimpin oleh duke leto mereka meregister domain name atreides.yyy.com untuk worker Laravel mengarah pada Leto Atreides .
> Namun ternyata tidak hanya klan atreides yang berusaha melakukan eksplorasi, Klan harkonen sudah mendaftarkan domain name harkonen.yyy.com untuk worker PHP (0) mengarah pada Vladimir Harkonen

