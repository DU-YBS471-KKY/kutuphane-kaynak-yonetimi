# US 11 belge kontrol senaryoları

Hazırlayan: Abdülkadir Güneş | 18 Kasım 2026 | Güncelleme: 21 Kasım 2026  
Jira: [KKY-10](https://dagdelen41.atlassian.net/browse/KKY-10) | Sprint 3

Senaryoları gereksinim, ekran ve işlem akışı üzerinden hazırladım. Proje kod içermediği için bu bir belge kontrolüdür. Bir uygulamada ödünç işlemi çalıştırılmadı. Sonuç sütununu kendim doldurmadım. Kübra'nın bağımsız kontrolünden sonra işlenecek. KS-11-06 ile KS-11-09 arası Eray'ın 19 Kasım PO kararları için eklendi.

Örnek veriler gerçek kayıt değildir. Kitap "Örnek Kitap A", ISBN 9781234567897. Kopyalar K-001 Müsait, K-002 Ödünçte, K-003 Bakımda. Ödünç tarihi 18.11.2026. Öğrenciler şöyle:

- 2000000001 "Örnek Öğrenci", hesap aktif, gecikmiş kitabı yok, aktif ödünç 0.
- 2000000004, hesap pasif.
- 2000000005, hesap aktif, iade tarihi geçmiş 1 kitabı var.
- 2000000006, hesap aktif, gecikmiş kitabı yok, aktif ödünç 3.
- 2000000007, hesap aktif, gecikmiş kitabı yok, aktif ödünç 2.

KS-11-05 dışındaki her senaryo bu başlangıç durumundan değerlendirilir.

| Kod | Kriter | Kontrol girdisi ve adım | Beklenen sonuç | Belgedeki kanıt | Sonuç |
|---|---|---|---|---|---|
| KS-11-01 | 1 | 2000000001 okutulur, sonra K-001 okutulur. | Başlık, yazar, ISBN, kopya kodu ve "MUSAIT" durumu görünür. | O01 kopya bilgisi alanı | Bekliyor |
| KS-11-02 | 2 | 2000000001 okutulur, sonra K-002 okutulur. | "Bu kopya şu anda ödünçte" uyarısı çıkar. Ödünç ver düğmesi pasiftir. Kayıt oluşmaz. | O02 Kopya Ödünçte satırı | Bekliyor |
| KS-11-03 | 2 | 2000000001 okutulur, sonra K-003 okutulur. | "Bu kopya bakımda" uyarısı çıkar. Ödünç ver düğmesi pasiftir. Kayıt oluşmaz. | O02 Kopya Bakımda satırı, US-09 B02 | Bekliyor |
| KS-11-04 | 3 | 2000000001 ve K-001, 18.11.2026 tarihinde okutulur. | İade tarihi elle girilmeden 03.12.2026 olarak görünür. Ay geçişi doğru hesaplanır. | O01 iade tarihi alanı, işlem sırası | Bekliyor |
| KS-11-05 | 3 | KS-11-04'ten sonra Ödünç ver seçilir. | Kayıt özetinde öğrenci, kitap, ödünç ve iade tarihi görünür. K-001 Ödünçte olur, müsait kopya sayısı 1 azalır. Aktif ödünç 1 / 3 olur. | O03, US-06 KS-06-03 ile tutarlı | Bekliyor |
| KS-11-06 | PO kararı | 2000000004 okutulur. | "Öğrenci hesabı aktif değil" uyarısı çıkar. Kopya barkodu alanı açılmaz. Kayıt oluşmaz. | O02 Hesap pasif satırı, işlem sırası | Bekliyor |
| KS-11-07 | PO kararı | 2000000005 okutulur. | "Gecikmiş veya cezalı kitabı var" uyarısı çıkar. Kopya barkodu alanı açılmaz. Kayıt oluşmaz. | O02 gecikmiş veya cezalı satırı, işlem sırası | Bekliyor |
| KS-11-08 | PO kararı | 2000000006 okutulur. | "En fazla 3 kitap alabilir" uyarısı çıkar. Kopya barkodu alanı açılmaz. Kayıt oluşmaz. | O02 Aktif ödünç 3 / 3 satırı | Bekliyor |
| KS-11-09 | PO kararı | 2000000007 okutulur, K-001 okutulur, Ödünç ver seçilir. | Sınır dolmadığı için kayıt oluşur. Aktif ödünç 3 / 3 olur. | O01, O03 ve işlem sırası | Bekliyor |

Kontrol için [tasarım dosyasındaki](../tasarim/us-11-odunc-verme.md) O01–O03 bölümlerine bakılmalı. Rezervasyonlu kopya sorusu PO kararı gelince senaryoya eklenecek.
