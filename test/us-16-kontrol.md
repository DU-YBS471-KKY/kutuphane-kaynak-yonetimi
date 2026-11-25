# US 16 belge kontrol senaryoları

Hazırlayan: Kübra Şen | 25 Kasım 2026  
Jira: [KKY-23](https://dagdelen41.atlassian.net/browse/KKY-23) | Sprint 4

Senaryoları kabul kriterleri ve tasarım dosyası üzerinden hazırladım. Bu bir belge kontrolüdür; gerçek e-posta gönderilmez. Sonuç sütunu bağımsız kontrolden sonra işlenecek.

Örnek veriler gerçek kayıt değildir. 2000000001 (US-11 ve US-15'teki öğrenci): Örnek Kitap A 18.11.2026'da ödünç, iade tarihi 03.12.2026. 2000000002: Örnek Kitap E ödünçte.

| Kod | Kriter | Kontrol girdisi ve adım | Beklenen sonuç | Belgedeki kanıt | Sonuç |
|---|---|---|---|---|---|
| KS-16-01 | 1 | 01.12.2026'da aktif kayıtlar değerlendirilir. | 2000000001'in kayıtlı e-postası için Örnek Kitap A hatırlatması oluşur. | H01, H02 birinci satır | Bekliyor |
| KS-16-02 | 2 | KS-16-01'deki e-posta incelenir. | Kitap adı ve 03.12.2026 vardır. 2000000002'nin Örnek Kitap E bilgisi yoktur. | H01 | Bekliyor |
| KS-16-03 | 3 | 01.12.2026'da aynı kayıt ikinci kez değerlendirilir. | İkinci hatırlatma oluşmaz. | H02 ikinci satır, işlem sırası | Bekliyor |
| KS-16-04 | 3 | Örnek Kitap A 30.11.2026'da iade edilir; 01.12.2026'da değerlendirme yapılır. | Hatırlatma oluşmaz. | H02 dördüncü satır | Bekliyor |
| KS-16-05 | 3 | 30.11.2026'da süre US-13'te 10.12.2026'ya uzatılır. 01.12 ve 08.12.2026'da değerlendirme yapılır. | 01.12'de hatırlatma oluşmaz. 08.12'de iade tarihi 10.12.2026 yazan bir hatırlatma oluşur. | H02 üçüncü satır, US-13 U02 | Bekliyor |
| KS-16-06 | 1 | 30.11.2026'da aktif kayıtlar değerlendirilir. | İade tarihine 3 gün olduğu için hatırlatma oluşmaz. | H02 altıncı satır | Bekliyor |

Kontrol için [tasarım dosyasındaki](../tasarim/us-16-iade-hatirlatma.md) H01–H02 bölümlerine bakılmalı.
