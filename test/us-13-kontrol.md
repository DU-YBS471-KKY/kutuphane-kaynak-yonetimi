# US 13 belge kontrol senaryoları

Hazırlayan: Abdülkadir Güneş | 18 Kasım 2026 | Güncelleme: 21 Kasım 2026  
Jira: [KKY-12](https://dagdelen41.atlassian.net/browse/KKY-12) | Sprint 3

Senaryoları gereksinim, ekran ve işlem akışı üzerinden hazırladım. Proje kod içermediği için bu bir belge kontrolüdür. Bir uygulamada uzatma işlemi çalıştırılmadı. Sonuç sütununu kendim doldurmadım. Kübra'nın bağımsız kontrolünden sonra işlenecek. KS-13-06 ile KS-13-08 arası Eray'ın 19 Kasım PO kararları için eklendi.

Örnek veriler gerçek kayıt değildir. "Örnek Öğrenci" 18.11.2026'da "Örnek Kitap A"yı ödünç almış, iade tarihi 03.12.2026. Talep tarihi aksi yazmadıkça 01.12.2026. KS-13-02 ve KS-13-05 dışındaki her senaryo bu başlangıç durumundan değerlendirilir.

| Kod | Kriter | Kontrol girdisi ve adım | Beklenen sonuç | Belgedeki kanıt | Sonuç |
|---|---|---|---|---|---|
| KS-13-01 | 3 | Hiç uzatılmamış, rezervasyonu olmayan kitap için 01.12.2026'da Süreyi uzat seçilir. | İade tarihi 10.12.2026 olur. Uzatma hakkı 1 / 1 kullanıldı görünür. | U02 | Bekliyor |
| KS-13-02 | 1 | KS-13-01'deki kitap için tekrar Süreyi uzat seçilir. | "Uzatma hakkınızı kullandınız" mesajı çıkar. İade tarihi 10.12.2026'da kalır. | U03 birinci satır | Bekliyor |
| KS-13-03 | 1 | İade tarihi 03.12.2026 olan kitap için 05.12.2026'da Süreyi uzat seçilir. | "İade tarihi geçtiği için süre uzatılamaz" mesajı çıkar. Tarih değişmez. | U03 ikinci satır | Bekliyor |
| KS-13-04 | 2 | Kitap için US-14'te başka bir öğrencinin aktif rezervasyonu var. 01.12.2026'da Süreyi uzat seçilir. | Uzatma reddedilir, rezervasyon sebebi yazılır. Rezerve edenin adı görünmez. Tarih değişmez. | U03 üçüncü satır, işlem sırası | Bekliyor |
| KS-13-05 | 3 | KS-13-01 sonrası öğrenci ödünç listesini yeniden açar. | Listede güncel iade tarihi 10.12.2026 olarak görünür. Durum ODUNCTE, uzatma 1 / 1. | U01 ve U02, US-15 L01 ile aynı sütunlar | Bekliyor |
| KS-13-06 | PO kararı | Rezervasyonu olmayan, hiç uzatılmamış kitap için iade günü olan 03.12.2026'da Süreyi uzat seçilir. | Uzatma kabul edilir. Yeni iade tarihi 10.12.2026 olur. | U03 açıklaması, işlem sırası | Bekliyor |
| KS-13-07 | PO kararı | Görevli, öğrencinin talebiyle 01.12.2026'da öğrenci kartını okutup Süreyi uzat seçer. | Yeni iade tarihi 10.12.2026 olur. Kayıtta uzatmayı yapan görevli görünür. | U04 | Bekliyor |
| KS-13-08 | PO kararı | Kitabın US-14'te başka öğrenci adına aktif rezervasyonu var. Görevli öğrenci adına Süreyi uzat seçer. | Öğrencinin kendi denemesindeki gibi uzatma reddedilir ve sebebi yazılır. Tarih değişmez. | U04 ve U03 üçüncü satır | Bekliyor |

Kontrol için [tasarım dosyasındaki](../tasarim/us-13-sure-uzatma.md) U01–U04 bölümlerine bakılmalı.
