# US-05, US-06, US-07: Kontrol ve Kabul Test Senaryoları

**Sorumlu:** Esat Kor  
**Tarih:** 27 Ekim 2026  
**Sprint:** Sprint 1  
**Durum:** Ekran taslakları ve iş kuralları üzerinden doğrulandı (Geçti).

| Test Kodu | İlgili Story / Kriter | Ön Koşul ve Test Adımları | Beklenen Sonuç | Durum |
| :--- | :--- | :--- | :--- | :---: |
| **KS-05-01** | US-05 / Kriter 1 | Arama çubuğuna kayıtlı bir "Başlık" girilip "Ara" butonuna basılır. | İlgili başlığa sahip kitap listelenir. | **Geçti** |
| **KS-05-02** | US-05 / Kriter 2 | Arama çubuğuna kayıtlı bir "Yazar" adı girilip "Ara" butonuna basılır. | O yazara ait tüm kitaplar listelenir. | **Geçti** |
| **KS-05-03** | US-05 / Kriter 3 | Arama çubuğuna doğru bir "ISBN" numarası girilerek arama yapılır. | O ISBN numarasına ait tekil kitap listelenir. | **Geçti** |
| **KS-05-04** | US-05 / Kriter 4 | Sistemde kayıtlı olmayan rastgele bir kelime ile arama yapılması denenir. | "Aradığınız kriterlere uygun kitap bulunamadı" uyarısı gösterilir. | **Geçti** |
| **KS-05-05** | US-05 / Kriter 5 | Arama çubuğu tamamen boş bırakılarak arama butonuna tıklanır. | Sisteme kayıtlı tüm kitap arşivi liste olarak getirilir. | **Geçti** |
| **KS-06-01** | US-06 / Kriter 1 | Arama sonucundaki listeden bir kitaba tıklanır. | Kitabın yazar, başlık ve ISBN bilgileri eksiksiz açılır. | **Geçti** |
| **KS-06-02** | US-06 / Kriter 2 | Veritabanından silinmiş bir kitabın eski linkine tıklanır. | "Kitap kaydı bulunamadı" hatası gösterilir. | **Geçti** |
| **KS-07-01** | US-07 / Kriter 1 | Kütüphanede mevcut olan bir kitabın detayına bakılır. | Stok durumu "Kütüphanede" olarak işaretli gösterilir. | **Geçti** |
| **KS-07-02** | US-07 / Kriter 2 | Önceden ödünç verilmiş bir kitabın detayına bakılır. | Durum "Ödünç Verilmiş" görünür ve iade tarihi belirtilir. | **Geçti** |
