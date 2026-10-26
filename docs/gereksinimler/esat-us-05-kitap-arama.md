# US-05 Kitap Arama
Sorumlu: Esat Kor (@esatkor9)
Jira: KKY-15 | 3 SP
Gereksinim ve Kontrol Senaryoları
Sprint 1

## User Story
Öğrenci olarak kitabı yazar, başlık ya da ISBN ile aramak istiyorum, böylece aradığım kitabı hızla bulayım.

## Kabul kriterleri
1. Arama kutusuna yazar adı, kitap başlığı veya ISBN girilebilir.
2. Sonuçlar kategoriye göre filtrelenebilir.
3. Her sonuçta kitap adı, yazar ve ISBN görünür.
4. Sonuç yoksa "Sonuç bulunamadı" mesajı gösterilir.

## Ekran taslağı
- Üst kısımda yazar, başlık veya ISBN girilebilen bir arama çubuğu bulunur.
- Arama çubuğunun hemen yanında kategori seçimi yapılabilen bir açılır menü (filtre) yer alır.
- Alt kısımda arama sonuçları liste veya kart formatında sıralanır; her kartta kitap kapağı, adı, yazarı ve ISBN bilgisi yer alır.

## Kontrol senaryoları
| Senaryo | Beklenen sonuç |
| :--- | :--- |
| Yazar adıyla arama | O yazarın kitapları listelenir |
| ISBN ile arama | Tek kitap listelenir |
| Kategori filtresi seçilir | Yalnızca o kategori listelenir |
| Olmayan bir başlık aranır | "Sonuç bulunamadı" mesajı çıkar |
