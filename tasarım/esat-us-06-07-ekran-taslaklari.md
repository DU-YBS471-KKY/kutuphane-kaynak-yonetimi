# KKY Projesi - Sprint 2 Görev Belgeleri (US-06)

**Sorumlu:** Esat Kor  
**Sprint:** Sprint 2  

---

## 1. US-06: Raf Konumu ve Stok Durumu 

### 1.1. Gereksinimler
**Kullanıcı Hikayesi:** Öğrenci olarak kitabın raf konumunu ve stok durumunu görmek istiyorum, böylece kitabı kütüphanede kolayca bulayım.

**Kabul Kriterleri:**
1. Kitap detayında salon ve raf kodu görünür.
2. Müsaitlik etiketi (Müsait / Ödünçte) gösterilir.
3. Stok bilgisi güncel tutulur.

### 1.2. Ekran Tasarımı (Wireframe)
**Tasarım Amacı:** Fiziksel bir kitabın kütüphane içerisindeki navigasyonunu kolaylaştırmak, stok ve raf bilgisini temiz bir "bilgi kartı" içinde sunmak.

```text
+-----------------------------------------------------------------+
|  [ 🏠 Anasayfa ] > [ 📚 Katalog ] > [ Sefiller ]                |
+-----------------------------------------------------------------+
|                                                                 |
|  +---------------+  Sefiller                                    |
|  |               |  Yazar    : Victor Hugo                      |
|  |    [ KİTAP    |  Kategori : Dünya Klasikleri                 |
|  |     KAPAĞI    |  ISBN     : 978-605-222-111                  |
|  |    GÖRSELİ ]  |  Puan     : ⭐⭐⭐⭐⭐ (4.8/5)                      |
|  |               |                                              |
|  +---------------+  +----------------------------------------+  |
|                     | 🟢 DURUM: MÜSAİT         Stok: [ 3/5 ] |  |
|                     +----------------------------------------+  |
|                     | 📍 KÜTÜPHANE KONUM KARTI               |  |
|                     |  • Bina  : Merkez Kütüphane            |  |
|                     |  • Salon : B Blok Okuma Salonu         |  |
|                     |  • Kat   : 2. Kat                      |  |
|                     |  • Raf   : B-14 (Klasikler Bölümü)     |  |
|                     +----------------------------------------+  |
|                                                                 |
|                     [ 🔖 Favorilere Ekle ]  [ 📖 Rezerve Et ]   |
+-----------------------------------------------------------------+
