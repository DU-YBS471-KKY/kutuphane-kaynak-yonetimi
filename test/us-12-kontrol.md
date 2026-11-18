# US 12 belge kontrol senaryoları

Hazırlayan: Abdülkadir Güneş | 18 Kasım 2026  
Jira: [KKY-11](https://dagdelen41.atlassian.net/browse/KKY-11) | Sprint 3

Senaryoları gereksinim, ekran ve işlem akışı üzerinden hazırladım. Proje kod içermediği için bu bir belge kontrolüdür. Bir uygulamada iade işlemi çalıştırılmadı. Sonuç sütununu kendim doldurmadım. Kübra'nın bağımsız kontrolünden sonra işlenecek.

Örnek veriler gerçek kayıt değildir. Kitap "Örnek Kitap A" iki kopyalı. K-001, 18.11.2026'da "Örnek Öğrenci"ye ödünç verilmiş, K-002 Müsait. Başlangıçta ödünç verilebilir kopya sayısı 1. İade 25.11.2026'da "Örnek Görevli" tarafından alınıyor.

| Kod | Kriter | Kontrol girdisi ve adım | Beklenen sonuç | Belgedeki kanıt | Sonuç |
|---|---|---|---|---|---|
| KS-12-01 | 1 | K-001 okutulur, Sağlam seçilir, iade tamamlanır. | K-001 Müsait olur. Ödünç verilebilir kopya sayısı 1'den 2'ye çıkar. | I02, US-06 KS-06-04 ile tutarlı | Bekliyor |
| KS-12-02 | 2 | K-001 okutulur, Hasarlı seçilir, iade tamamlanır. | K-001 Bakımda olur. Ödünç verilebilir kopya sayısı 1'de kalır. | I03, US-09 B02 | Bekliyor |
| KS-12-03 | 3 | KS-12-01'deki sağlam iade tamamlanır. | Kayıtta iade tarihi 25.11.2026 ve işlemi yapan "Örnek Görevli" görünür. | I02 | Bekliyor |
| KS-12-04 | 3 | KS-12-02'deki hasarlı iade tamamlanır. | Kopya bakımda olsa da iade tarihi ve görevli kayıtta görünür. Ödünç kaydı kapanır. | I03 | Bekliyor |

Kontrol için [tasarım dosyasındaki](../tasarim/us-12-iade-stok-onayi.md) I01–I03 bölümlerine bakılmalı.
