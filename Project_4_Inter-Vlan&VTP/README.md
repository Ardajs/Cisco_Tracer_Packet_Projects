# Cisco Inter-VLAN Routing & VTP Project

Bu proje, Cisco Packet Tracer kullanılarak tasarlanmış bir ağ altyapısı çalışmasıdır. Proje kapsamında VLAN hiyerarşisi, VTP yönetimi ve Router-on-a-Stick yöntemiyle yönlendirme yapılandırmaları gerçekleştirilmiştir.

## Özellikler
- **VLAN Yapılandırması:** Faculty, Student ve Guest ağları için izolasyon.
- **VTP (VLAN Trunking Protocol):** VLAN bilgilerinin switchler arasında otomatik senkronizasyonu.
- **Router-on-a-Stick:** Tek bir fiziksel arayüz üzerinden çoklu VLAN yönlendirmesi.
- **Güvenlik:** Ayrıcalıklı mod şifreleme ve VTY/Console güvenliği.

## Ağ Detayları
| VLAN | Adı | IP Aralığı | Gateway |
| :--- | :--- | :--- | :--- |
| 10 | Faculty-Staff | 172.17.10.0/24 | 172.17.10.1 |
| 20 | Students | 172.17.20.0/24 | 172.17.20.1 |
| 30 | Guest | 172.17.30.0/24 | 172.17.30.1 |
| 99 | Management | 172.17.99.0/24 | 172.17.99.1 |

##  Yapılandırma Dosyaları
Cihazların detaylı `running-config` dökümlerine `configs/` klasöründen ulaşabilirsiniz.

##  Test Sonuçları
Tüm VLAN'lar arası ping testleri ve Server erişimi başarıyla doğrulanmıştır.


##  Nasıl Kullanılır?
1. Bu repoyu bilgisayarınıza indirin (`git clone`).
2. Bilgisayarınızda **Cisco Packet Tracer** (v8.x ve üzeri önerilir) yüklü olduğundan emin olun.
3. `.pkt` uzantılı dosyalardan birini açın.
4. Terminal/CLI üzerinden cihazların `running-config` dökümlerini inceleyebilir veya simülasyon modunda trafiği gözlemleyebilirsiniz.

### Proje X - Inter-VLAN Routing & Router-on-a-Stick
Bu proje, tek bir Router bacağı üzerinden birden fazla VLAN'ın haberleşmesini (inter-vlan routing) ve VTP protokolü ile VLAN yönetimini kapsamaktadır.

- **Kullanılan Protokoller:** VTP (Server/Client), IEEE 802.1Q (Dot1q), STP (Spanning Tree).
- **Yönetim:** VLAN 99 (Management VLAN) üzerinden uzaktan yönetim IP'leri atanmıştır.
- **Güvenlik:** Console, VTY ve Privileged mode şifrelemeleri yapılmıştır.

  
