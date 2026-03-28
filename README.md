# Cisco_Tracer_Packet_Projects
Cisco Packet Tracer network projects from basic to advanced, including VLANs, routing, switching, and network security labs.

# Cisco Packet Tracer Projects

Bu repo, Cisco Packet Tracer üzerinde yaptığım ağ projelerini içermektedir.  
Projeler temel ağ kavramlarından başlayarak daha ileri seviye switch, router, VLAN, routing ve network security yapılarına doğru ilerleyecektir.

## İçerik

### Project 1 - Basic VLAN Segmentation
Bu projede tek bir switch üzerinde iki farklı VLAN oluşturularak ağ segmentasyonu yapılmıştır.

- **VLAN 2**: Office
- **VLAN 3**: Home

Bağlı istemciler ilgili VLAN'lara atanmıştır ve iletişim testleri `ping` komutu ile doğrulanmıştır.

## Amaç
Bu projenin amacı aşağıdaki temel ağ kavramlarını uygulamalı olarak göstermektir:

- VLAN oluşturma
- Switch portlarını VLAN’lara atama
- Aynı VLAN içindeki cihazların haberleşmesi
- Farklı VLAN’lardaki cihazların yönlendirme olmadan haberleşememesi
- Ağ segmentasyonu mantığını anlama

## Kullanılan Araçlar
- Cisco Packet Tracer
- 2960 Switch
- PC-PT istemciler


### Project 2 - Static Routing Between Two Networks
İki farklı LAN ağı, iki router üzerinden static routing kullanılarak birbirine bağlandı.  
Farklı subnetlerdeki cihazlar arasında başarılı iletişim sağlandı.

## Topoloji

Projede aşağıdaki bileşenler kullanılmıştır:

- 2 adet Router (Cisco 1841)
- 2 adet Switch (2960)
- 4 adet PC

---

### Project 3 - Dynamic Routing (RIP v2)
Bu projede iki farklı yerel ağ, routerlar arasında dinamik yönlendirme kullanılarak birbirine bağlanmıştır.

RIP v2 protokolü sayesinde routerlar ağ bilgilerini otomatik olarak öğrenmiş ve farklı subnetlerdeki cihazlar arasında iletişim sağlanmıştır.

Bağlı istemciler farklı ağlarda olmasına rağmen `ping` testleri ile başarılı şekilde haberleşmiştir.

## Amaç
Bu projenin amacı aşağıdaki temel ağ kavramlarını uygulamalı olarak göstermektir:

- Dinamik routing (RIP v2)
- Routerlar arası otomatik route öğrenme
- Farklı subnetler arasında iletişim
- Routing table mantığını anlama
- Convergence (yakınsama) sürecini gözlemleme

## Kullanılan Araçlar
- Cisco Packet Tracer
- Cisco 1841 Router
- 2960 Switch
- PC-PT istemciler

### Proje 3'ü önümüzdeki hafta ekleyeceğim.


## Not
Bu repo zamanla yeni Cisco projeleriyle genişletilecektir.
