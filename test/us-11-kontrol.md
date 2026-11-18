# US 11 belge kontrol senaryoları

Hazırlayan: Abdülkadir Güneş | 18 Kasım 2026  
Jira: [KKY-10](https://dagdelen41.atlassian.net/browse/KKY-10) | Sprint 3

Senaryoları gereksinim, ekran ve işlem akışı üzerinden hazırladım. Proje kod içermediği için bu bir belge kontrolüdür. Bir uygulamada ödünç işlemi çalıştırılmadı. Sonuç sütununu kendim doldurmadım. Kübra'nın bağımsız kontrolünden sonra işlenecek.

Örnek veriler gerçek kayıt değildir. Kitap "Örnek Kitap A", ISBN 9781234567897. Kopyalar K-001 Müsait, K-002 Ödünçte, K-003 Bakımda. Öğrenci "Örnek Öğrenci", numara 2000000001. Ödünç tarihi 18.11.2026.

| Kod | Kriter | Kontrol girdisi ve adım | Beklenen sonuç | Belgedeki kanıt | Sonuç |
|---|---|---|---|---|---|
| KS-11-01 | 1 | Öğrenci kartı okutulur, sonra K-001 okutulur. | Başlık, yazar, ISBN, kopya kodu ve "MUSAIT" durumu görünür. | O01 kopya bilgisi alanı | Bekliyor |
| KS-11-02 | 2 | K-002 okutulur. | "Bu kopya şu anda ödünçte" uyarısı çıkar. Ödünç ver düğmesi pasiftir. Kayıt oluşmaz. | O02 Ödünçte satırı | Bekliyor |
| KS-11-03 | 2 | K-003 okutulur. | "Bu kopya bakımda" uyarısı çıkar. Ödünç ver düğmesi pasiftir. Kayıt oluşmaz. | O02 Bakımda satırı, US-09 B02 | Bekliyor |
| KS-11-04 | 3 | K-001, 18.11.2026 tarihinde okutulur. | İade tarihi elle girilmeden 03.12.2026 olarak görünür. Ay geçişi doğru hesaplanır. | O01 iade tarihi alanı, işlem sırası | Bekliyor |
| KS-11-05 | 3 | K-001 için Ödünç ver seçilir. | Kayıt özetinde öğrenci, kitap, ödünç ve iade tarihi görünür. K-001 Ödünçte olur, müsait kopya sayısı 1 azalır. | O03, US-06 KS-06-03 ile tutarlı | Bekliyor |

Kontrol için [tasarım dosyasındaki](../tasarim/us-11-odunc-verme.md) O01–O03 bölümlerine bakılmalı. Netleşmesi gereken üç nokta tasarım dosyasının sonunda yazıyor. PO kararı gelince senaryolar güncellenecek.
