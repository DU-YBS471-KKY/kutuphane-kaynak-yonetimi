# US-06 ve US-07 Kontrol ve Kabul Test Senaryoları

**Sorumlu:** Esat Kor  
**Sprint:** Sprint 2  

---

## US-06: Raf Konumu ve Stok Durumu 
| Test Kodu | İlgili Kriter | Ön Koşul ve Test Adımları | Beklenen Sonuç | Durum |
| :--- | :--- | :--- | :--- | :---: |
| **KS-06-01** | Kriter 1 | Kütüphane kataloğundan rastgele bir fiziksel kitabın detay sayfasına girilir. | Ekranda kitabın bulunduğu salon ve raf kodunun (örn. B Salonu, Raf B-14) açıkça görünmesi. | **Bekliyor** |
| **KS-06-02** | Kriter 2 | Stokta olan ve olmayan iki farklı kitabın detay sayfaları incelenir. | Stoktaki kitapta yeşil "Müsait", stoğu biten kitapta kırmızı "Ödünçte" etiketinin görünmesi. | **Bekliyor** |
| **KS-06-03** | Kriter 3 | Sistem üzerinden bir kitap ödünç alınır ve sayfa yenilenir. | İlgili kitabın stok sayısının anında 1 eksilerek güncel durumu yansıtması. | **Bekliyor** |

---

## US-07: Dijital Kaynakları PDF Olarak İndirme
| Test Kodu | İlgili Kriter | Ön Koşul ve Test Adımları | Beklenen Sonuç | Durum |
| :--- | :--- | :--- | :--- | :---: |
| **KS-07-01** | Kriter 1 | Üye girişi yapılmış halde dijital bir eserin detay sayfasına girilir ve indirme butonuna basılır. | PDF dosyasının sorunsuz bir şekilde cihaza indirilmesi. | **Bekliyor** |
| **KS-07-02** | Kriter 2 | Ziyaretçi olarak (giriş yapmadan) dijital bir eserin sayfasına girilip indirme butonuna tıklanır. | Sistemin indirmeyi engelleyerek kullanıcıyı "Giriş Yap" sayfasına yönlendirmesi. | **Bekliyor** |
| **KS-07-03** | Kriter 3 | Sadece fiziksel (basılı) kopyası olan bir romanın detay sayfasına girilir. | Ekranda hiçbir şekilde "PDF İndir" butonunun görünmemesi. | **Bekliyor** |
