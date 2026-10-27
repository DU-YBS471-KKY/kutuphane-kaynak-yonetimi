# Esat Kor (US-05, US-06, US-07) Gereksinim ve Kontrol Senaryoları
Sorumlu: Esat Kor (@esatkor9)

---

## US-05: Yazar, Başlık ve ISBN ile Kitap Arama
**Jira:** KKY-15 | **Puan:** 3 SP | **Sprint:** 1

### User Story
Öğrenci olarak kitabı yazar, başlık ya da ISBN ile aramak istiyorum, böylece aradığım kitabı hızla bulayım.

### Kabul Kriterleri
1. Arama kutusuna yazar adı, kitap başlığı veya ISBN (10 veya 13 haneli) girilebilir.
2. Sonuçlar kategoriye göre filtrelenebilir.
3. Her sonuçta kitap adı, yazar ve ISBN görünür.
4. Sonuç yoksa "Sonuç bulunamadı" mesajı gösterilir.

### Kontrol Senaryoları
| Senaryo | Beklenen Sonuç |
| :--- | :--- |
| Yazar adıyla arama | O yazarın kitapları listelenir |
| ISBN ile arama | Tek kitap listelenir |
| Kategori filtresi seçilir | Yalnızca o kategori listelenir |
| Olmayan bir başlık aranır | "Sonuç bulunamadı" mesajı çıkar |

---

## US-06: Kitap Raf Konumu ve Stok Durumu Görme
**Jira:** KKY-7 | **Puan:** 3 SP | **Sprint:** 2

### User Story
Öğrenci olarak kitabın raf konumunu ve stok durumunu görmek istiyorum, böylece kitabı kütüphanede kolayca bulayım.

### Kabul Kriterleri
1. Kitap detay sayfasında salon ve raf kodu açıkça görünür.
2. Kitabın anlık durumunu belirten "Müsait" veya "Ödünçte" etiketi gösterilir.
3. Stok bilgisi ödünç/iade işlemlerine göre anlık olarak güncel tutulur.

### Kontrol Senaryoları
| Senaryo | Beklenen Sonuç |
| :--- | :--- |
| Müsait kitap incelenir | "Müsait", salon ve raf kodu yeşil etiketle görünür |
| Ödünçte olan kitap incelenir | "Ödünçte" etiketi kırmızı renkle görünür |
| Rafta olmayan kitabın konumu | Konum yerine "Depoda/Kayıp" gibi geçerli durum yazar |

---

## US-07: Dijital Makale ve E-Kitap PDF İndirme
**Jira:** KKY-8 | **Puan:** 5 SP | **Sprint:** 2

### User Story
Üye olarak dijital makale ve e-kitapları PDF olarak indirmek istiyorum, böylece kütüphaneye gitmeden okuyabileyim.

### Kabul Kriterleri
1. İndirme butonu yalnızca dijital (e-kitap, makale) kaynakların detay sayfasında görünür.
2. Üye girişi yapmış kullanıcılar "PDF İndir" butonuna tıklayarak dosyaya doğrudan erişebilir.
3. Giriş yapmamış kullanıcılar indirmeye çalıştığında "Lütfen giriş yapın" uyarısı alır ve giriş ekranına yönlendirilir.

### Kontrol Senaryoları
| Senaryo | Beklenen Sonuç |
| :--- | :--- |
| Giriş yapmış üye indir derse | PDF dosyası cihaza iner / tarayıcıda açılır |
| Ziyaretçi (giriş yapmamış) indir derse | "Lütfen giriş yapın" uyarısı verir |
| Basılı (fiziksel) kitaba bakılırsa | Ekranda "PDF İndir" butonu hiç görünmez |
