# US-05: Kitap Arama Kontrol ve Kabul Test Senaryoları

**Sorumlu:** Esat Kor  
**Jira Kartı:** KKY-15  
**Sprint:** Sprint 1  
**Durum:** Kategori filtresi ve tüm kabul kriterleri üzerinden test edildi (Geçti).

---

| Test Kodu | İlgili Story / Kriter | Ön Koşul ve Test Adımları | Beklenen Sonuç | Durum |
| :--- | :--- | :--- | :--- | :---: |
| **KS-05-01** | US-05 / Kriter 1 | Arama çubuğuna kayıtlı bir "Başlık" girilip "Ara" butonuna basılır. | Sadece o başlığı içeren kitapların Başlık, Yazar, ISBN ve Kategori sütunlarıyla listelenmesi. | **Geçti** |
| **KS-05-02** | US-05 / Kriter 2 | "Kategori Seç" filtresinden bir tür (ör. Roman) seçilip arama yapılır. | Tablodaki sonuçların sadece "Roman" kategorisindeki kitaplardan oluşması. | **Geçti** |
| **KS-05-03** | US-05 / Kriter 3 | Arama çubuğuna kayıtlı bir "Yazar" adı girilip "Ara" butonuna basılır. | O yazara ait kitapların eksiksiz olarak sonuç tablosunda listelenmesi. | **Geçti** |
| **KS-05-04** | US-05 / Kriter 4 | Arama çubuğuna doğru bir "ISBN" numarası girilerek arama yapılır. | Sadece o ISBN numarasına ait tek bir kitap kaydının listelenmesi. | **Geçti** |
| **KS-05-05** | US-05 / BR-05-03 (İş Kuralı) | Kütüphanede bulunmayan, rastgele bir kitap ismi veya ISBN girilir. | Ekranda "Aradığınız kriterlere uygun kitap bulunamadı." uyarısının gösterilmesi. | **Geçti** |
