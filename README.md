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

# Cisco Packet Tracer Projects 

Cisco Packet Tracer üzerinde gerçekleştirdiğim, temel ağ kavramlarından ileri seviye yapılandırmalara kadar uzanan ağ projeleri koleksiyonudur.

##  Genel Bakış
Bu depo, ağ tasarımı, VLAN yönetimi, yönlendirme protokolleri ve ağ güvenliği konularında yaptığım laboratuvar çalışmalarını ve yapılandırma dosyalarını içermektedir.

---

### Project 4 - Inter-VLAN Routing (Router-on-a-Stick) & VTP
Kurumsal bir ağ yapısını simüle eden en kapsamlı projedir.
- **VTP (VLAN Trunking Protocol):** S1 'Server', diğer switchler 'Client' modunda yapılandırılarak merkezi VLAN yönetimi sağlandı.
- **Router-on-a-Stick:** Tek bir fiziksel router arayüzü, sub-interface'lere (Dot1Q) bölünerek tüm VLAN'lar arası iletişim sağlandı.
- **Management VLAN:** Ağ cihazlarının yönetimi için VLAN 99 üzerinden IP atamaları yapıldı.

| VLAN | Departman | Subnet | Gateway |
| :--- | :--- | :--- | :--- |
| 10 | Faculty-Staff | 172.17.10.0/24 | 172.17.10.1 |
| 20 | Students | 172.17.20.0/24 | 172.17.20.1 |
| 30 | Guest | 172.17.30.0/24 | 172.17.30.1 |
| 99 | Management | 172.17.99.0/24 | 172.17.99.1 |

---

##  Uygulanan Güvenlik Standartları
Tüm projelerde aşağıdaki "Hardening" adımları uygulanmıştır:
- **Enable Secret:** Ayrıcalıklı mod şifresi MD5 algoritması ile şifrelendi.
- **Console & VTY Security:** Cihazlara fiziksel ve uzaktan erişim şifre ile korundu.
- **Password Encryption:** `service password-encryption` ile tüm şifreler config dosyalarında gizlendi.

---

##  Nasıl Kullanılır?
1. Bu repoyu indirin: `git clone https://github.com/Arda.js/Cisco_Tracer_Packet_Projects.git`
2. `.pkt` uzantılı dosyaları **Cisco Packet Tracer (v8.x+)** ile açın.
3. Cihaz konfigürasyonlarını incelemek için `configs/` klasöründeki `.txt` dosyalarına göz atın.
4. **Cihaz Şifreleri:**
   - Console/VTY: `cisco`
   - Enable Secret: `class`

---


## Not
Bu repo zamanla yeni Cisco projeleriyle genişletilecektir.
