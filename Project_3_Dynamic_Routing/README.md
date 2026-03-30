#  Proje 3 - RIP v2 ile Dinamik Yönlendirme

##  Genel Bakış

Bu projede, iki farklı yerel ağ (LAN), routerlar arasında **RIP v2 dinamik yönlendirme protokolü** kullanılarak birbirine bağlanmıştır.

Statik yönlendirmeden farklı olarak, routerlar ağ bilgilerini otomatik olarak paylaşır ve ağ yollarını dinamik şekilde öğrenir.

---

##  Amaçlar

- RIP v2 kullanarak dinamik yönlendirme yapılandırmak  
- Farklı subnetler arasında iletişimi sağlamak  
- Routing convergence (yakınsama) sürecini anlamak  
- Ping testleri ile bağlantıyı doğrulamak  

---

##  Ağ Topolojisi

Bu proje aşağıdaki bileşenleri içermektedir:

- 2 adet Router (Cisco 1841)  
- 2 adet Switch (2960)  
- 4 adet PC  

---

##  IP Adresleme

### Router Arayüzleri

#### Router0
- Fa0/0 → 192.168.1.2/24  
- Fa0/1 → 192.168.2.3/24  

#### Router1
- Fa0/0 → 192.168.1.4/24  
- Fa0/1 → 192.168.3.3/24  

---

### PC'ler

| Cihaz | IP Adresi | Subnet Mask | Varsayılan Ağ Geçidi |
|------|-----------|------------|----------------------|
| PC0 | 192.168.2.7 | 255.255.255.0 | 192.168.2.3 |
| PC1 | 192.168.2.9 | 255.255.255.0 | 192.168.2.3 |
| PC2 | 192.168.3.5 | 255.255.255.0 | 192.168.3.3 |
| PC3 | 192.168.3.7 | 255.255.255.0 | 192.168.3.3 |

---

##  Yapılandırma

###  Router0 Yapılandırması

```bash
enable
conf t

interface fa0/0
ip address 192.168.1.2 255.255.255.0
no shutdown

interface fa0/1
ip address 192.168.2.3 255.255.255.0
no shutdown

router rip
version 2
no auto-summary
network 192.168.1.0
network 192.168.2.0


### Router1 Yapılandırması

enable
conf t

interface fa0/0
ip address 192.168.1.4 255.255.255.0
no shutdown

interface fa0/1
ip address 192.168.3.3 255.255.255.0
no shutdown

router rip
version 2
no auto-summary
network 192.168.1.0
network 192.168.3.0



### Test ve Doğrulama
# Bağlantı Testleri
PC0 → PC2 ✅
PC1 → PC3 ✅
Farklı ağlar arası iletişim başarılı
# Router Bağlantısı
Router0 ↔ Router1 ping başarılı


###Yakınsama (Convergence) Notu

İlk ping denemelerinde küçük bir paket kaybı gözlemlenmiştir.

Bu durum RIP protokolünün yakınsama süresinden (convergence time) kaynaklanmaktadır.
Routing tabloları güncellendikten sonra tam bağlantı sağlanmıştır.


