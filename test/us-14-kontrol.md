# US 14 belge kontrol senaryoları

Hazırlayan: Kübra Şen | 20 Kasım 2026  
Jira: [KKY-21](https://dagdelen41.atlassian.net/browse/KKY-21) | Sprint 3

Senaryoları gereksinim, ekran ve sıra kuralları üzerinden hazırladım. Proje kod içermediği için bu bir belge kontrolüdür. Bir uygulamada rezervasyon işlemi çalıştırılmadı. Sonuç sütununu kendim doldurmadım; bağımsız kontrolden sonra işlenecek.

Örnek veriler gerçek kayıt değildir. Kitap "Örnek Kitap C", ISBN 9781234567800, iki kopyalı. K-101 ve K-102 ödünçte, müsait kopya yok. Öğrenciler: Örnek Öğrenci A (2000000001), Örnek Öğrenci B (2000000002), Örnek Öğrenci C (2000000003). Tüm öğrenciler giriş yapmış.

| Kod | Kriter | Kontrol girdisi ve adım | Beklenen sonuç | Belgedeki kanıt | Sonuç |
|---|---|---|---|---|---|
| KS-14-01 | 1 | A, 19.11.2026 10:05'te Örnek Kitap C'nin detayını açar ve Rezerve et seçer. | Rezervasyon oluşur. Kayıtta talep tarihi 19.11.2026 10:05 ve sıra no 1 görünür. Durum Aktif olur. | R01, R02 | Bekliyor |
| KS-14-02 | 2 | KS-14-01'den sonra A aynı kitap için tekrar Rezerve et seçer. | Yeni rezervasyon oluşmaz. "Bu kitap için aktif rezervasyonunuz var" mesajıyla mevcut talep tarihi ve sıradaki yer gösterilir. | R03 | Bekliyor |
| KS-14-03 | 3 | B 19.11.2026 11:20'de, C 20.11.2026 09:00'da aynı kitabı rezerve eder. | B sıra no 2, C sıra no 3 alır. Sıra talep zamanına göre A, B, C'dir. | R02, R05 | Bekliyor |
| KS-14-04 | 3 | A, B ve C aktifken K-101 US-12'de sağlam iade edilir ve Müsait olur. | İlk aktif talep sahibi olarak A belirlenir. B ve C sırada kalır. | R05, işlem sırası, US-12 I02 | Bekliyor |
| KS-14-05 | 3 | K-101 iade edilmeden önce A, Rezervasyonlarım ekranından rezervasyonunu iptal eder. Sonra K-101 sağlam iade edilir. | A'nın kaydı İptal olur ve sıradan çıkar. B'nin sıradaki yeri 1, C'ninki 2 olur. İade sonrası ilk aktif talep sahibi B'dir. | R04, R05 | Bekliyor |

Kontrol için [tasarım dosyasındaki](../tasarim/us-14-rezervasyon.md) R01–R05 bölümlerine bakılmalı. Müsait kopya varken rezervasyon, kişi başı sınır ve hesap durumu PO kararına bağlı olduğu için senaryolara eklenmedi. PO kararı gelince senaryolar güncellenecek.
