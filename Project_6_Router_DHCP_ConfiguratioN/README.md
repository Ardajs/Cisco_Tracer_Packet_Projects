## Project 6 - Router DHCP Configuration

##  Genel Bakış

Bu projede bir Cisco router üzerinde DHCP (Dynamic Host Configuration Protocol) yapılandırılmıştır.

DHCP sayesinde istemciler IP adreslerini manuel olarak girmek yerine otomatik olarak almıştır. Router üzerinde farklı ağlar için ayrı DHCP havuzları oluşturulmuştur.

---

##  Amaçlar

- DHCP yapılandırmasını öğrenmek
- İstemcilere otomatik IP dağıtmak
- Farklı ağlar için DHCP havuzları oluşturmak
- Default gateway yapılandırmasını anlamak
- DHCP işlemini test etmek

---

##  Ağ Topolojisi

Bu proje aşağıdaki bileşenleri içermektedir:

- 1 Cisco 1941 Router
- 2 PC


---

##  IP Adresleme

### Router Arayüzleri

| Arayüz | IP Adresi |
|----------|------------|
| GigabitEthernet0/0 | 10.0.0.1/8 |
| GigabitEthernet0/1 | 20.0.0.1/8 |

---

### DHCP Havuzları

| Havuz | Network | Gateway |
|---------|---------|----------|
| lan | 10.0.0.0/8 | 10.0.0.1 |
| lan_1 | 20.0.0.0/8 | 20.0.0.1 |

---

##  Yapılandırma

### Router DHCP Konfigürasyonu

```bash
enable
conf t

interface gig0/0
ip address 10.0.0.1 255.0.0.0
no shutdown

interface gig0/1
ip address 20.0.0.1 255.0.0.0
no shutdown

ip dhcp pool lan
network 10.0.0.0 255.0.0.0
default-router 10.0.0.1

ip dhcp pool lan_1
network 20.0.0.0 255.0.0.0
default-router 20.0.0.1
```

---

##  Test ve Doğrulama

### DHCP Testi

PC0:

 IP: 10.0.0.2  
 Gateway: 10.0.0.1

PC1:

 IP: 20.0.0.2  
 Gateway: 20.0.0.1

DHCP isteği başarılı şekilde tamamlandı.

---

##  Öğrenilen Kavramlar

- DHCP
- DHCP Pool
- Default Gateway
- Otomatik IP dağıtımı
- Router yapılandırması

---

##  Dosyalar

- `Router DHCP Configuration.pkt`
- `Router1_running-config.txt`
- `topology.png`
- DHCP test ekran görüntüleri

---

##  Sonuç

Bu proje ile router üzerinden DHCP yapılandırılarak istemcilere otomatik IP dağıtımı gerçekleştirilmiştir.

DHCP kullanımı ağ yönetimini kolaylaştırır ve manuel IP atama ihtiyacını azaltır.
