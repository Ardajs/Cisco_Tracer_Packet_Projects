# Project 1 - Basic VLAN Segmentation

## Proje Özeti
Bu projede Cisco Packet Tracer kullanılarak tek bir switch üzerinde iki farklı VLAN yapılandırılmıştır.  
Amaç, ağ segmentasyonu yaparak aynı VLAN içindeki cihazların birbiriyle haberleşmesini sağlamak ve farklı VLAN’lardaki cihazların birbirinden izole olduğunu göstermektir.

## Topoloji
Projede toplam 1 switch ve 4 PC kullanılmıştır.

### VLAN Yapısı
- **VLAN 2 - Office**
  - PC2 → 10.0.0.3/8
  - PC3 → 10.0.0.4/8

- **VLAN 3 - Home**
  - PC0 → 10.0.0.1/8
  - PC1 → 10.0.0.2/8

## Port Atamaları
- **FastEthernet 0/1** → VLAN 2
- **FastEthernet 0/2** → VLAN 2
- **FastEthernet 0/3** → VLAN 3
- **FastEthernet 0/4** → VLAN 3

## Yapılandırma Adımları

### 1. VLAN oluşturma
Switch üzerinde iki VLAN oluşturuldu:
- VLAN 2 → office
- VLAN 3 → home

### 2. Portları VLAN’lara atama
İlgili switch portları access port olarak uygun VLAN’lara bağlandı.

### 3. IP adresleme
Her PC’ye manuel IP adresi verildi:

- PC0 → 10.0.0.1/8
- PC1 → 10.0.0.2/8
- PC2 → 10.0.0.3/8
- PC3 → 10.0.0.4/8

## Test Sonuçları

### VLAN yapılandırmasından önce
Aynı fiziksel switch üzerinde bulunan cihazlar birbirleriyle haberleşebiliyordu.

### VLAN yapılandırmasından sonra
- **PC0 ↔ PC1** iletişimi başarılı
- **PC2 ↔ PC3** iletişimi başarılı
- **PC0 ↔ PC2 / PC3** başarısız
- **PC1 ↔ PC2 / PC3** başarısız

Bu sonuç, farklı VLAN’ların Layer 2 seviyesinde birbirinden ayrıldığını göstermektedir.

## Öğrenilen Kavramlar
Bu proje ile aşağıdaki konular uygulamalı olarak öğrenilmiştir:

- VLAN nedir?
- Neden VLAN kullanılır?
- Switch üzerinde VLAN oluşturma
- Access port yapılandırması
- Broadcast domain ayrımı
- Ağ segmentasyonu

## Kullanılan Komutlar

```bash
enable
conf t
vlan 2
name office
exit
vlan 3
name home
exit

interface fastEthernet 0/1
switchport access vlan 2
exit

interface fastEthernet 0/2
switchport access vlan 2
exit

interface fastEthernet 0/3
switchport access vlan 3
exit

interface fastEthernet 0/4
switchport access vlan 3
exit
