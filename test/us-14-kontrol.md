# US 14 belge kontrol senaryoları

Hazırlayan: Kübra Şen | 20 Kasım 2026 | Güncelleme: 25 Kasım 2026  
Jira: [KKY-21](https://dagdelen41.atlassian.net/browse/KKY-21) | Sprint 3

Senaryoları gereksinim, ekran ve sıra kuralları üzerinden hazırladım. Proje kod içermediği için bu bir belge kontrolüdür. Bir uygulamada rezervasyon işlemi çalıştırılmadı. Sonuç sütununu Kadir'in 25 Kasım bağımsız kontrolüne göre işledim (PR #53). KS-14-06 ile KS-14-13 arası Eray'ın 21 Kasım PO kararları için eklendi.

Örnek veriler gerçek kayıt değildir. Başlangıç durumu:

- "Örnek Kitap C", ISBN 9781234567800, iki kopyalı. K-101 ve K-102 ödünçte, müsait kopya yok, rezervasyon yok.
- "Örnek Kitap A": K-001 Müsait (US-11'deki kitap).
- "Örnek Kitap H": K-301 ve K-302 Bakımda.
- "Örnek Kitap J": tüm kopyaları ödünçte, rezervasyon yok.
- Örnek Öğrenci A (2000000011), B (2000000012) ve C (2000000013): hesap aktif, gecikmiş veya cezalı kitap yok. A'nın 17.11.2026 14:00'te "Örnek Kitap G" için 1 aktif rezervasyonu var; B ve C'nin rezervasyonu yok.
- 2000000004: hesap pasif. 2000000005: hesap aktif, iade tarihi geçmiş 1 kitabı var. İkisi de US-11 kontrol dosyasındaki öğrencilerdir.

Tüm öğrenciler giriş yapmış. Her senaryo bu başlangıç durumundan değerlendirilir; önceki bir senaryoya bağlıysa adımda yazılıdır.

| Kod | Kriter | Kontrol girdisi ve adım | Beklenen sonuç | Belgedeki kanıt | Sonuç |
|---|---|---|---|---|---|
| KS-14-01 | 1 | A, 19.11.2026 10:05'te Örnek Kitap C'nin detayını açar ve Rezerve et seçer. | Rezervasyon oluşur. Kayıtta talep tarihi 19.11.2026 10:05 ve sıra no 1 görünür. Durum Aktif olur. A'nın aktif rezervasyonu 2 / 2 olur. | R01, R03 | Uyumlu |
| KS-14-02 | 2 | KS-14-01'den sonra A aynı kitap için tekrar Rezerve et seçer. | Yeni rezervasyon oluşmaz. "Bu kitap için aktif rezervasyonunuz var" mesajıyla mevcut talep tarihi ve sıradaki yer gösterilir. 2 rezervasyon sınırı uyarısı çıkmaz. | R04, işlem sırası | Uyumlu |
| KS-14-03 | 3 | KS-14-01'den sonra B 19.11.2026 11:20'de, C 20.11.2026 09:00'da aynı kitabı rezerve eder. | B sıra no 2, C sıra no 3 alır. Sıra talep zamanına göre A, B, C'dir. | R03, R06 | Uyumlu |
| KS-14-04 | 3 | KS-14-03'ten sonra K-101, 25.11.2026'da US-12'de sağlam iade edilir. | İlk aktif talep sahibi olarak A belirlenir. K-101 Rezerve olur ve A'ya ayrılır. B ve C sırada kalır. | R06, işlem sırası, US-12 I02 | Uyumlu |
| KS-14-05 | 3 | KS-14-03'ten sonra, K-101 iade edilmeden A Rezervasyonlarım ekranından Örnek Kitap C rezervasyonunu iptal eder. Sonra K-101 sağlam iade edilir. | A'nın kaydı İptal olur ve sıradan çıkar. B'nin sıradaki yeri 1, C'ninki 2 olur. İade sonrası ilk aktif talep sahibi B'dir ve K-101 B'ye ayrılır. | R05, R06 | Uyumlu |
| KS-14-06 | PO kararı | B, Örnek Kitap A'nın detayını açar. | "Rafta müsait kopyası var" uyarısı görünür. Rezerve et düğmesi gösterilmez. Kayıt oluşmaz. | R02 birinci satır | Uyumlu |
| KS-14-07 | PO kararı | B, Örnek Kitap H'nin detayını açar. | "Tüm kopyalar bakımda olduğu için rezervasyon yapılamaz" uyarısı görünür. Rezerve et düğmesi gösterilmez. Kayıt oluşmaz. | R02 ikinci satır | Uyumlu |
| KS-14-08 | PO kararı | KS-14-01'den sonra A, 19.11.2026 12:00'de Örnek Kitap J için Rezerve et seçer. | "En fazla 2 aktif rezervasyonunuz olabilir" uyarısı çıkar. Kayıt oluşmaz. A'nın Örnek Kitap C ve G rezervasyonları değişmez. | R02 beşinci satır, R05 | Uyumlu |
| KS-14-09 | PO kararı | 2000000004, Örnek Kitap C için Rezerve et seçer. | "Hesabınız aktif olmadığı için rezervasyon yapamazsınız" uyarısı çıkar. Kayıt oluşmaz. | R02 üçüncü satır, işlem sırası | Uyumlu |
| KS-14-10 | PO kararı | 2000000005, Örnek Kitap C için Rezerve et seçer. | "Gecikmiş veya cezalı kitabınız olduğu için rezervasyon yapamazsınız" uyarısı çıkar. Kayıt oluşmaz. | R02 dördüncü satır, işlem sırası | Uyumlu |
| KS-14-11 | PO kararı | KS-14-04'ten sonra, A'ya bildirim 25.11.2026 10:00'da gider. 26.11.2026'da görevli K-101'i B'ye ödünç vermeye çalışır; sonra A gelir ve K-101 ona verilir. | K-101 B'ye verilemez. A'ya ödünç verilir, A'nın rezervasyonu Tamamlandı olur ve sıradan çıkar. B'nin sıradaki yeri 1 olur. | R06, US-11 ödünç işlemi | Uyumlu |
| KS-14-12 | PO kararı | KS-14-04'ten sonra, A'ya bildirim 25.11.2026 10:00'da gider. A, 27.11.2026 10:00'a kadar gelmez. | A'nın rezervasyonu İptal olur. K-101 Rezerve kalır ve ilk aktif talep sahibi B için ayrılır. B için 48 saat bildirimden itibaren yeniden başlar. | R06, işlem sırası | Uyumlu |
| KS-14-13 | PO kararı | Örnek Kitap C için yalnızca A'nın aktif talebi vardır. K-101 sağlam iade edilir, A'ya bildirim gider ve A 48 saat içinde gelmez. | A'nın rezervasyonu İptal olur. Sırada başka aktif talep olmadığı için K-101 Müsait olur. | R06, işlem sırası | Uyumlu |

Kontrol için [tasarım dosyasındaki](../tasarim/us-14-rezervasyon.md) R01–R06 bölümlerine bakılmalı. Bildirimin gönderilmesi US-17'nin konusu olduğu için burada yalnızca bildirim zamanı veri olarak kullanıldı.
