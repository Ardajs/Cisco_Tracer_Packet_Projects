# Project 2 - Static Routing Between Two Networks

## Proje Özeti
Bu projede iki farklı yerel ağ (LAN), iki router üzerinden birbirine bağlanmıştır.  
Router'lar arasında bağlantı kurularak farklı subnetlerdeki cihazların birbirleriyle iletişim kurması sağlanmıştır.

Bu proje, temel routing mantığını ve static route kullanımını göstermektedir.

---

## Topoloji

Projede aşağıdaki bileşenler kullanılmıştır:

- 2 adet Router (Cisco 1841)
- 2 adet Switch (2960)
- 4 adet PC

---

## IP Adresleme

### Routerlar arası bağlantı
- Router0 Fa0/0 → 192.168.1.2/24
- Router1 Fa0/0 → 192.168.1.4/24

---

### Sol ağ (Network 1)
- Router0 Fa0/1 → 192.168.2.3/24
- PC4 → 192.168.2.7/24
- PC5 → 192.168.2.9/24

Gateway:
- 192.168.2.3

---

### Sağ ağ (Network 2)
- Router1 Fa0/1 → 192.168.3.3/24
- PC6 → 192.168.3.5/24
- PC7 → 192.168.3.7/24

Gateway:
- 192.168.3.3

---

## Yapılandırma Adımları

### 1. Router IP ayarları

#### Router0
```bash
enable
conf t
interface fa0/0
ip address 192.168.1.2 255.255.255.0
no shutdown
exit

interface fa0/1
ip address 192.168.2.3 255.255.255.0
no shutdown
exit

#### Router1

enable
conf t
interface fa0/0
ip address 192.168.1.4 255.255.255.0
no shutdown
exit

interface fa0/1
ip address 192.168.3.3 255.255.255.0
no shutdown
exit



### 2. Static Routing

### Router0 üzerine:
ip route 192.168.3.0 255.255.255.0 192.168.1.4

### Router1 üzerine:
ip route 192.168.2.0 255.255.255.0 192.168.1.2



###Test Sonuçları

Ping testleri ile doğrulama yapılmıştır:

Aynı ağ içi iletişim başarılı
Farklı ağlar arası iletişim (routing sonrası) başarılı

Örnek:

PC4 → PC6 ping başarılı
PC5 → PC7 ping başarılı

