# US-05, US-06, US-07: Kitap Arama, Detay ve Durum Bilgisi (Tasarım ve Testler)

**Sorumlu:** Esat Kor  
**Kapsam:** KKY-15 (US-05), KKY-16 (US-06), KKY-17 (US-07)  
**Sprint:** Sprint 1  

---
## 1.Kitap Arama Ekranı Taslağı (US-05)
```text
+-------------------------------------------------------+
|             KÜTÜPHANE KAYNAK YÖNETİM SİSTEMİ          |
| [ Menü ] | Anasayfa | Kitap Arama | Profil | Çıkış    |
+-------------------------------------------------------+
| Kitap Arama:                                          |
| [ Yazar, Başlık veya ISBN giriniz... ] [ ARA ]        |
+-------------------------------------------------------+
| Sonuçlar:                                             |
|-------------------------------------------------------|
| ISBN          | Başlık        | Yazar       | Durum   |
|-------------------------------------------------------|
| 978-3-16-1... | Sefiller      | V. Hugo     | Mevcut  |
| 978-1-23-4... | 1984          | G. Orwell   | Ödünçte |
+-------------------------------------------------------+
| Uyarı/Bilgi Alanı:                                    |
| (!) "Aradığınız kriterlere uygun kitap bulunamadı."   |
+-------------------------------------------------------+
```
## 2.Kitap Detay Künyesi Taslağı (US-06)
```
+-------------------------------------------------------+
| [ < Aramaya Dön ]                                     |
+-------------------------------------------------------+
| KİTAP DETAY KÜNYESİ                                   |
|-------------------------------------------------------|
| Başlık   : 1984                                       |
| Yazar    : George Orwell                              |
| ISBN     : 978-1-23-456789-0                          |
| Kategori : Roman / Distopya                           |
| Yayın Evi: Can Yayınları                              |
+-------------------------------------------------------+
| Uyarı/Bilgi Alanı (Geçersiz/Silinmiş Kayıt):          |
| (!) "Kitap kaydı bulunamadı."                         |
+-------------------------------------------------------+
```
## 3.Stok ve Ödünç Durumu Taslağı (US-07)
```
+-------------------------------------------------------+
| STOK VE ÖDÜNÇ DURUMU                                  |
|-------------------------------------------------------|
| Durum: [ X ] Ödünç Verilmiş   [   ] Kütüphanede       |
|                                                       |
| İade Beklenen Tarih: 05.11.2026                       |
+-------------------------------------------------------+
