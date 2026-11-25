# US 17 belge kontrol senaryoları

Hazırlayan: Kübra Şen | 25 Kasım 2026  
Jira: [KKY-24](https://dagdelen41.atlassian.net/browse/KKY-24) | Sprint 4

Senaryoları kabul kriterleri ve tasarım dosyası üzerinden hazırladım. Bu bir belge kontrolüdür; gerçek bildirim gönderilmez. Sonuç sütunu bağımsız kontrolden sonra işlenecek.

Örnek veriler US-14 kontrol dosyasıyla aynıdır ve gerçek kayıt değildir. "Örnek Kitap C" iki kopyalı, K-101 ve K-102 ödünçte. Kitap için sırasıyla Örnek Öğrenci A (2000000011), B (2000000012) ve C (2000000013)'nin aktif rezervasyonu var.

| Kod | Kriter | Kontrol girdisi ve adım | Beklenen sonuç | Belgedeki kanıt | Sonuç |
|---|---|---|---|---|---|
| KS-17-01 | 1 | K-101, 25.11.2026 10:00'da US-12'de sağlam iade edilir. | K-101 Rezerve olur. A için bildirim oluşur, teslim son zamanı 27.11.2026 10:00. | N02 birinci satır, US-12 I05, US-14 KS-14-04 | Bekliyor |
| KS-17-02 | 2 | KS-17-01'deki bildirim incelenir; B ve C'nin bildirimlerine bakılır. | Bildirimde "Örnek Kitap C" ve teslim alınabilir bilgisi var. B ve C'ye bu kopya için bildirim oluşmaz. | N01, N02 ikinci satır | Bekliyor |
| KS-17-03 | 3 | KS-17-01'deki aynı iade ve rezervasyon tekrar değerlendirilir. | A için ikinci bildirim oluşmaz. | N02 üçüncü satır | Bekliyor |
| KS-17-04 | 3 | A, K-101 iade edilmeden rezervasyonunu iptal eder; sonra K-101 sağlam iade edilir. | A atlanır. Bildirim B için oluşur. | N02 dördüncü satır, US-14 KS-14-05 | Bekliyor |
| KS-17-05 | 3 | KS-17-01'den sonra A, 27.11.2026 10:00'a kadar gelmez. | A'nın rezervasyonu iptal olur. B için yeni bildirim oluşur, teslim son zamanı yeni bildirimden 48 saat sonra. | N02 beşinci satır, US-14 KS-14-12 | Bekliyor |
| KS-17-06 | 1 | K-101 hasarlı iade edilir. | K-101 Bakımda olur. Kimseye bildirim oluşmaz; A, B ve C sırada kalır. | N02 altıncı satır, US-12 I03 | Bekliyor |

Kontrol için [tasarım dosyasındaki](../tasarim/us-17-rezervasyon-bildirimi.md) N01–N02 bölümlerine bakılmalı.
