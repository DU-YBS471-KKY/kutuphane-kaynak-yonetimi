# US 15 belge kontrol senaryoları

Hazırlayan: Kübra Şen | 20 Kasım 2026 | Güncelleme: 21 Kasım 2026  
Jira: [KKY-22](https://dagdelen41.atlassian.net/browse/KKY-22) | Sprint 3

Senaryoları gereksinim ve ekran taslağı üzerinden hazırladım. Proje kod içermediği için bu bir belge kontrolüdür. Bir uygulamada liste açılmadı. Sonuç sütununu kendim doldurmadım; bağımsız kontrolden sonra işlenecek. KS-15-07 ve KS-15-08 Eray'ın 21 Kasım PO kararları için eklendi.

Örnek veriler gerçek kayıt değildir. Bugünün tarihi 20.11.2026. Örnek Öğrenci A (2000000001, US-11'deki öğrenci): Örnek Kitap A 18.11.2026'da ödünç, iade tarihi 03.12.2026; Örnek Kitap B 04.11.2026'da ödünç, iade tarihi 19.11.2026; Örnek Kitap D 20.10.2026'da ödünç, 30.10.2026'da iade edildi; Örnek Kitap F 01.10.2026'da ödünç, 10.10.2026'da iade edildi. Örnek Öğrenci B (2000000002) Örnek Kitap E'yi ödünç almış. Örnek Öğrenci C (2000000003) hiç ödünç almamış.

| Kod | Kriter | Kontrol girdisi ve adım | Beklenen sonuç | Belgedeki kanıt | Sonuç |
|---|---|---|---|---|---|
| KS-15-01 | 1 | A giriş yapıp Ödünç kayıtlarım ekranını açar. | Yalnızca Örnek Kitap A, B, D ve F kayıtları görünür. B'nin Örnek Kitap E kaydı görünmez. | L01, L02 | Bekliyor |
| KS-15-02 | 1 | A, B'nin Örnek Kitap E kaydını bağlantısını değiştirerek açmaya çalışır. | "Bu kayda erişim yetkiniz yok" uyarısı çıkar. B'nin kaydına ait hiçbir bilgi görünmez. | L04 | Bekliyor |
| KS-15-03 | 2 | A aktif sekmeyi açar. | Örnek Kitap A satırında kitap adı, ödünç tarihi 18.11.2026, güncel iade tarihi 03.12.2026 ve durum Ödünçte görünür. | L01 | Bekliyor |
| KS-15-04 | 2 | Örnek Kitap A, 25.11.2026'da US-12'de iade edilir. A listeyi yeniden açar. | Örnek Kitap A aktif listeden çıkar. Geçmiş sekmesinde iade edildiği tarih 25.11.2026 ve durum İade edildi olarak görünür. | L02, US-12 I02 | Bekliyor |
| KS-15-05 | 3 | 20.11.2026'da A aktif sekmeyi açar. | İade tarihi 19.11.2026 olan Örnek Kitap B kırmızı "Gecikmiş" etiketiyle işaretlidir. İade tarihi 03.12.2026 olan Örnek Kitap A işaretli değildir. | L01 | Bekliyor |
| KS-15-06 | 3 | C giriş yapıp Ödünç kayıtlarım ekranını açar. | Boş tablo yerine "Kayıt bulunamadı" mesajı ve açıklaması görünür. | L03 | Bekliyor |
| KS-15-07 | PO kararı | A geçmiş sekmesini açar. | Önce 30.10.2026'da iade edilen Örnek Kitap D, sonra 10.10.2026'da iade edilen Örnek Kitap F görünür. | L02, işlem sırası | Bekliyor |
| KS-15-08 | PO kararı | A geçmiş sekmesindeki Örnek Kitap D kaydını silmeye veya düzenlemeye çalışır. | Silme ya da düzenleme seçeneği yoktur. Kayıt değişmeden görünür; listede en az 12 ay saklandığı bilgisi yazar. | L02 | Bekliyor |

Kontrol için [tasarım dosyasındaki](../tasarim/us-15-odunc-listesi.md) L01–L04 bölümlerine bakılmalı. US-13 uzatması sonrası güncel tarihin listede görünmesi Kadir'in KS-13-05 senaryosunda kontrol ediliyor; aynı şeyi burada ikinci kez senaryo yapmadım. 12 aylık saklama süresi bir belge kontrolüyle ölçülemediği için KS-15-08 yalnızca kaydın salt okunur olduğunu ve saklama bilgisinin gösterildiğini kontrol eder.
