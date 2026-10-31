# US-05: Kitap Arama Kontrol ve Kabul Test Senaryoları

**Sorumlu:** Esat Kor  
**Jira Kartı:** KKY-15  
**Sprint:** Sprint 1  
**Durum:** Kategori filtresi ve tüm kabul kriterleri üzerinden test edildi (Geçti).

---

| Test Kodu | İlgili Story / Kriter | Ön Koşul ve Test Adımları | Beklenen Sonuç | Durum |
| :--- | :--- | :--- | :--- | :---: |
| **KS-05-01** | US-05 / Kriter 1 | Arama çubuğuna kayıtlı bir "Yazar" adı veya "ISBN" numarası girilerek arama yapılır. | Sadece o yazar veya ISBN numarasına ait kayıtların listelenmesi. | **Geçti** |
| **KS-05-02** | US-05 / Kriter 2 | "Kategori Seç" filtresinden bir tür (ör. Roman) seçilip arama yapılır. | Tablodaki sonuçların sadece "Roman" kategorisindeki kitaplardan oluşması. | **Geçti** |
| **KS-05-03** | US-05 / Kriter 3 | Geçerli bir arama yapılıp sonuçlar ekranda listelenir. | Sonuç tablosunda Başlık, Yazar, ISBN ve Kategori sütunlarının (sonuç alanları) eksiksiz olarak gösterilmesi. | **Geçti** |
| **KS-05-04** | US-05 / Kriter 4 | Kütüphanede bulunmayan, rastgele bir kitap ismi veya ISBN girilir. | Ekranda "Aradığınız kriterlere uygun kitap bulunamadı." (Sonuç bulunamaması) uyarısının gösterilmesi. | **Geçti** |
