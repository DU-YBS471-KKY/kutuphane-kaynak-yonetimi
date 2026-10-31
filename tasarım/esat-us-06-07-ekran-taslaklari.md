# KKY Projesi - Sprint 2 Görev Belgeleri

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
|  |    GÖRSELİ ]  |  Puan     : ⭐⭐⭐⭐⭐ (4.8/5)            |
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
|                     [ 🔖 Favorilere Ekle ]  [ 📖 Rezerve Et ]  |
+-----------------------------------------------------------------+
```
## 2. US-07: Dijital Kaynakları PDF Olarak İndirme

### 2.1. Gereksinimler
**Kullanıcı Hikayesi:** Üye olarak dijital makale ve e-kitapları PDF olarak indirmek istiyorum, böylece kütüphaneye gitmeden okuyabileyim.

**Kabul Kriterleri:**
1. Üye girişi yapan kullanıcı PDF'e doğrudan erişir.
2. Giriş yapmayan kullanıcı PDF'i indiremez.
3. İndirme butonu yalnızca dijital kaynaklarda görünür.

### 2.2. Ekran Tasarımı (Wireframe)
**Tasarım Amacı:** Eserin sadece dijital olduğunu vurgulamak ve oturum yönetimine bağlı dinamik buton yapısını net bir şekilde göstermek.

```text
+-----------------------------------------------------------------+
|  [ 🏠 Anasayfa ] > [ 💻 E-Kaynaklar ] > [ Yapay Zeka... ]       |
+-----------------------------------------------------------------+
|                                                                 |
|  +---------------+  Yapay Zeka ve Gelecek                       |
|  |               |  Yazar    : Alan Turing                      |
|  |   [ DİJİTAL   |  Kategori : Akademik Makale                  |
|  |    KAYNAK     |  Format   : 💻 Dijital Eser (PDF)            |
|  |    GÖRSELİ ]  |                                              |
|  |               |  +----------------------------------------+  |
|  +---------------+  | 📁 DOSYA DETAYLARI                     |  |
|                     |  Boyut: 2.4 MB  |  Sayfa: 142          |  |
|                     +----------------------------------------+  |
|                                                                 |
|                                                                 |
|   >> [DURUM 1] EĞER KULLANICI ÜYE GİRİŞİ YAPMIŞSA:              |
|   +----------------------------------------------------------+  |
|   |  📥 DİJİTAL KOPYAYI İNDİR (PDF)                          |  |
|   +----------------------------------------------------------+  |
|                                                                 |
|   >> [DURUM 2] EĞER ZİYARETÇİ İSE (GİRİŞ YAPMAMIŞSA):           |
|   +----------------------------------------------------------+  |
|   |  🔒 İndirmek İçin Lütfen Üye Girişi Yapın                |  |
|   +----------------------------------------------------------+  |
|                                                                 |
+-----------------------------------------------------------------+
