# US 12 belge kontrol senaryoları

Hazırlayan: Abdülkadir Güneş | 18 Kasım 2026 | Güncelleme: 25 Kasım 2026  
Jira: [KKY-11](https://dagdelen41.atlassian.net/browse/KKY-11) | Sprint 3

Senaryoları gereksinim, ekran ve işlem akışı üzerinden hazırladım. Proje kod içermediği için bu bir belge kontrolüdür. Bir uygulamada iade işlemi çalıştırılmadı. Sonuç sütununu kendim doldurmadım. Kübra'nın bağımsız kontrolünden sonra işlenecek. KS-12-05 Eray'ın 19 Kasım, KS-12-06 21 Kasım PO kararı için eklendi.

Örnek veriler gerçek kayıt değildir. Kitap "Örnek Kitap A" iki kopyalı. K-001, 18.11.2026'da "Örnek Öğrenci"ye ödünç verilmiş, K-002 Müsait. Başlangıçta ödünç verilebilir kopya sayısı 1. İade 25.11.2026'da "Örnek Görevli" tarafından alınıyor.

KS-12-06 için "Örnek Kitap C" kullanılır. US-14'teki gibi K-101 ve K-102 ödünçte, müsait kopya yok. Kitap için sırasıyla Örnek Öğrenci A 2000000011, B 2000000012 ve C 2000000013'ün aktif rezervasyonu var.

| Kod | Kriter | Kontrol girdisi ve adım | Beklenen sonuç | Belgedeki kanıt | Sonuç |
|---|---|---|---|---|---|
| KS-12-01 | 1 | K-001 okutulur, Sağlam seçilir, iade tamamlanır. | K-001 Müsait olur. Ödünç verilebilir kopya sayısı 1'den 2'ye çıkar. | I02, US-06 KS-06-04 ile tutarlı | Bekliyor |
| KS-12-02 | 2 | K-001 okutulur, Hasarlı seçilir, iade tamamlanır. | K-001 Bakımda olur. Ödünç verilebilir kopya sayısı 1'de kalır. | I03, US-09 B02 | Bekliyor |
| KS-12-03 | 3 | KS-12-01'deki sağlam iade tamamlanır. | Kayıtta iade tarihi 25.11.2026 ve işlemi yapan "Örnek Görevli" görünür. | I02 | Bekliyor |
| KS-12-04 | 3 | KS-12-02'deki hasarlı iade tamamlanır. | Kopya bakımda olsa da iade tarihi ve görevli kayıtta görünür. Ödünç kaydı kapanır. | I03 | Bekliyor |
| KS-12-05 | PO kararı | Aktif ödünç kaydı olmayan K-002 iade ekranında okutulur. | "Bu kopya için aktif ödünç kaydı bulunmamaktadır" uyarısı çıkar. İade başlamaz. K-002 Müsait kalır, verilebilir kopya sayısı 1'de kalır. | I04 ve işlem sırası | Bekliyor |
| KS-12-06 | PO kararı | 25.11.2026'da Örnek Kitap C'nin K-101 kopyası okutulur, Sağlam seçilir, iade tamamlanır. | K-101 Müsait değil Rezerve olur ve A'ya ayrılır. Teslim son zamanı bildirimden 48 saat sonra görünür. Ödünç verilebilir kopya sayısı 0'da kalır. İade tarihi ve görevli kayda geçer. B ve C sırada kalır. | I05, işlem sırası, US-14 KS-14-04 | Bekliyor |

Kontrol için [tasarım dosyasındaki](../tasarim/us-12-iade-stok-onayi.md) I01–I05 bölümlerine bakılmalı.
