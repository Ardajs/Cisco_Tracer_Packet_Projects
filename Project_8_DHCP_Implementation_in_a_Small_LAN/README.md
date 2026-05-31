#  Project 8 - Router DHCP Configuration with Multiple Clients

##  Genel Bakış

Bu projede bir Cisco router üzerinde DHCP servisi yapılandırılmış ve aynı yerel ağdaki birden fazla istemcinin otomatik IP adresi alması sağlanmıştır.

Router, DHCP sunucusu olarak çalışmakta ve bağlı cihazlara IP adresi, default gateway ve DNS bilgilerini otomatik olarak dağıtmaktadır.

---

##  Amaçlar

- Router üzerinde DHCP yapılandırmak
- Birden fazla istemciye otomatik IP adresi dağıtmak
- Default gateway ve DNS dağıtımını öğrenmek
- DHCP istemci doğrulaması yapmak
- Ping testleri ile ağ içi iletişimi kontrol etmek

---

##  Ağ Topolojisi

Bu proje aşağıdaki bileşenleri içermektedir:

- 1 Cisco 2901 Router
- 1 Cisco 2960 Switch
- 3 PC
- 2 Laptop
- 1 Server


---

##  IP Adresleme

### Router

| Arayüz | IP Adresi | Subnet Mask |
|--------|-----------|-------------|
| GigabitEthernet0/0 | 192.168.1.1 | 255.255.255.0 |

---

### DHCP Pool

| Pool Name | Network | Default Gateway | DNS Server |
|----------|---------|-----------------|------------|
| ABC-POOL | 192.168.1.0/24 | 192.168.1.1 | 192.168.1.254 |

---

### DHCP İstemcileri

| Cihaz | Alınan IP Adresi | Gateway | DNS |
|------|------------------|---------|-----|
| Laptop1 | 192.168.1.2 | 192.168.1.1 | 192.168.1.254 |
| PC0 | 192.168.1.3 | 192.168.1.1 | 192.168.1.254 |
| PC1 | 192.168.1.4 | 192.168.1.1 | 192.168.1.254 |
| PC2 | 192.168.1.5 | 192.168.1.1 | 192.168.1.254 |
| Laptop0 | 192.168.1.6 | 192.168.1.1 | 192.168.1.254 |

---

##  Router DHCP Yapılandırması

```bash
enable
conf t

interface gigabitEthernet0/0
ip address 192.168.1.1 255.255.255.0
no shutdown

ip dhcp pool ABC-POOL
network 192.168.1.0 255.255.255.0
default-router 192.168.1.1
dns-server 192.168.1.254
```

---

##  Test ve Doğrulama

### DHCP Testi

Tüm istemciler DHCP üzerinden başarılı şekilde IP adresi almıştır.

- Laptop1 → 192.168.1.2 
- PC0 → 192.168.1.3 
- PC1 → 192.168.1.4 
- PC2 → 192.168.1.5 
- Laptop0 → 192.168.1.6 

### Ping Testi

Laptop0 üzerinden diğer istemcilere ping testi yapılmıştır.

- Laptop0 → Laptop1 başarılı 
- Laptop0 → PC0 başarılı 


##  Dosyalar

- `project_8.pkt` → Packet Tracer proje dosyası
- `configs/Router0_running-config.txt` → Router yapılandırması
- `configs/Switch0_running-config.txt` → Switch yapılandırması
- `topology/topology.png` → Ağ topolojisi
- `pc-configs/` → DHCP istemci ekran görüntüleri
- `tests/ping-test.png` → Ping testi

---

##  Öğrenilen Kavramlar

- DHCP
- DHCP Pool
- Default Gateway
- DNS dağıtımı
- Router üzerinden IP dağıtımı
- LAN içi bağlantı testi

---

##  Sonuç
Bu proje ile router üzerinde DHCP yapılandırılarak aynı ağdaki birden fazla istemciye otomatik IP adresi dağıtılmıştır.

DHCP kullanımı, ağ yönetimini kolaylaştırır ve manuel IP adresi verme ihtiyacını azaltır.
