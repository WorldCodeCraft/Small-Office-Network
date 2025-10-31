# 🖧 Small Office Network Simulation — VLAN Bölümlendirme Projesi  

## 🔹 Proje Hakkında  
Bu proje, Cisco Packet Tracer üzerinde tasarlanmış küçük ölçekli bir ofis ağını simüle eder.  
Ağ yapısında **4 departman (VLAN)** bulunur ve her biri kendi içinde iletişim kurarken diğer VLAN’lardan izole edilmiştir.  
Merkezi bir **Core Switch** üzerinden VLAN yönetimi ve trunk bağlantıları sağlanmıştır.  
Amaç; **ağ segmentasyonu, güvenlik ve yönetim prensiplerini** uygulamalı olarak göstermek.  

---

## 🏢 Ağ Topolojisi  

| Departman | VLAN ID | IP Aralığı | Switch | PC Sayısı |
|------------|----------|-------------|----------|------------|
| IT | 10 | 192.168.10.0/24 | SW-IT | 10 |
| HR (İnsan Kaynakları) | 20 | 192.168.20.0/24 | SW-HR | 10 |
| Finance (Finans) | 30 | 192.168.30.0/24 | SW-FINANCE | 10 |
| Sales (Satış) | 40 | 192.168.40.0/24 | SW-SALES | 10 |
| Core Switch | - | 192.168.99.0/24 | SW-CORE | - |
| Router | - | 192.168.99.1/24 | R1 | - |

---

## ⚙️ Kullanılan Cihazlar
- **1× Router:** Cisco 2811  
- **1× Core Switch:** Cisco 2960  
- **4× Access Switch:** Cisco 2960  
- **40× Bilgisayar (her VLAN’da 10 adet)**  

---

## 🎯 Temel Özellikler
- VLAN segmentasyonu ile departmanlar arası izolasyon  
- Trunk bağlantılar üzerinden VLAN taşıma  
- Yönetim VLAN’ı (99) ile merkezi kontrol  
- Şifreli erişim ve güvenlik önlemleri  
- Kolay anlaşılır yapı ve profesyonel topoloji düzeni  

---
