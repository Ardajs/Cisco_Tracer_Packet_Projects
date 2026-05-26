#  Project 7 - Switch DHCP Configuration

##  Genel Bakış

Bu projede bir Cisco switch üzerinde DHCP servisi yapılandırılmıştır.

Switch üzerinden istemcilere otomatik IP dağıtımı gerçekleştirilmiş ve DHCP yapılandırması test edilmiştir.

Bu proje, Layer 2 cihazlar üzerinde temel ağ servislerinin kullanımını göstermektedir.

---

##  Amaçlar

- Switch üzerinde DHCP yapılandırmak
- İstemcilere otomatik IP dağıtmak
- Management IP yapılandırmasını öğrenmek
- DHCP çalışma mantığını anlamak
- DHCP istemci doğrulaması yapmak

---

##  Ağ Topolojisi

Bu proje aşağıdaki bileşenleri içermektedir:

- 1 Cisco 2960 Switch
- 2 PC

---

##  IP Adresleme

### Switch

| Arayüz | IP Adresi |
|---------|-----------|
| VLAN1 | 10.0.0.1/8 |

---

### DHCP İstemcileri

| Cihaz | IP Adresi | Gateway |
|--------|-----------|----------|
| PC0 | 10.0.0.2 | 10.0.0.1 |
| PC1 | 10.0.0.3 | 10.0.0.1 |

---

##  Yapılandırma

### Switch DHCP Yapılandırması

```bash
enable
conf t

interface vlan 1
ip address 10.0.0.1 255.0.0.0
no shutdown

ip dhcp pool LAN
network 10.0.0.0 255.0.0.0
default-router 10.0.0.1
```

---

##  Test ve Doğrulama

### DHCP Testi

PC0:

 IP Adresi: 10.0.0.2  
 Gateway: 10.0.0.1

PC1:

 IP Adresi: 10.0.0.3  
 Gateway: 10.0.0.1

DHCP istekleri başarılı şekilde tamamlandı.

---

##  Öğrenilen Kavramlar

- DHCP
- DHCP Pool
- Switch management IP
- Otomatik IP dağıtımı
- Layer 2 cihaz yapılandırması

---



---

##  Dosyalar

- `switch_dhcp_conf.pkt`
- `Switch0_running-config.txt`
- `topology.png`
- `pc_0.png`
- `pc_1.png`

---

##  Sonuç

Bu proje ile switch üzerinde DHCP yapılandırılarak istemcilere otomatik IP dağıtımı gerçekleştirilmiştir.

DHCP kullanımı ağ yönetimini kolaylaştırır ve manuel IP yapılandırma ihtiyacını azaltır.

