# US 15 belge kontrol senaryoları

Hazırlayan: Kübra Şen | 20 Kasım 2026 | Güncelleme: 25 Kasım 2026  
Jira: [KKY-22](https://dagdelen41.atlassian.net/browse/KKY-22) | Sprint 3

Senaryoları gereksinim ve ekran taslağı üzerinden hazırladım. Proje kod içermediği için bu bir belge kontrolüdür. Bir uygulamada liste açılmadı. Sonuç sütununu Kadir'in 25 Kasım bağımsız kontrolüne göre işledim (PR #53). KS-15-07 ve KS-15-08 Eray'ın 21 Kasım PO kararları için eklendi.

Örnek veriler gerçek kayıt değildir. Bugünün tarihi 20.11.2026. 2000000001 (US-11'deki "Örnek Öğrenci"): Örnek Kitap A 18.11.2026'da ödünç, iade tarihi 03.12.2026; Örnek Kitap B 04.11.2026'da ödünç, iade tarihi 19.11.2026; Örnek Kitap D 20.10.2026'da ödünç, 30.10.2026'da iade edildi; Örnek Kitap F 01.10.2026'da ödünç, 10.10.2026'da iade edildi. 2000000002 Örnek Kitap E'yi ödünç almış. 2000000003 hiç ödünç almamış. Öğrencileri numarayla yazdım; US-14'teki Örnek Öğrenci A, B ve C (2000000011–13) ile karışmasın (#54).

| Kod | Kriter | Kontrol girdisi ve adım | Beklenen sonuç | Belgedeki kanıt | Sonuç |
|---|---|---|---|---|---|
| KS-15-01 | 1 | 2000000001 giriş yapıp Ödünç kayıtlarım ekranını açar. | Yalnızca Örnek Kitap A, B, D ve F kayıtları görünür. 2000000002'nin Örnek Kitap E kaydı görünmez. | L01, L02 | Uyumlu |
| KS-15-02 | 1 | 2000000001, 2000000002'nin Örnek Kitap E kaydını bağlantısını değiştirerek açmaya çalışır. | "Bu kayda erişim yetkiniz yok" uyarısı çıkar. 2000000002'nin kaydına ait hiçbir bilgi görünmez. | L04 | Uyumlu |
| KS-15-03 | 2 | 2000000001 aktif sekmeyi açar. | Örnek Kitap A satırında kitap adı, ödünç tarihi 18.11.2026, güncel iade tarihi 03.12.2026 ve durum Ödünçte görünür. | L01 | Uyumlu |
| KS-15-04 | 2 | Örnek Kitap A, 25.11.2026'da US-12'de iade edilir. 2000000001 listeyi yeniden açar. | Örnek Kitap A aktif listeden çıkar. Geçmiş sekmesinde iade edildiği tarih 25.11.2026 ve durum İade edildi olarak görünür. | L02, US-12 I02 | Uyumlu |
| KS-15-05 | 3 | 20.11.2026'da 2000000001 aktif sekmeyi açar. | İade tarihi 19.11.2026 olan Örnek Kitap B kırmızı "Gecikmiş" etiketiyle işaretlidir. İade tarihi 03.12.2026 olan Örnek Kitap A işaretli değildir. | L01 | Uyumlu |
| KS-15-06 | 3 | 2000000003 giriş yapıp Ödünç kayıtlarım ekranını açar. | Boş tablo yerine "Kayıt bulunamadı" mesajı ve açıklaması görünür. | L03 | Uyumlu |
| KS-15-07 | PO kararı | 2000000001 geçmiş sekmesini açar. | Önce 30.10.2026'da iade edilen Örnek Kitap D, sonra 10.10.2026'da iade edilen Örnek Kitap F görünür. | L02, işlem sırası | Uyumlu |
| KS-15-08 | PO kararı | 2000000001 geçmiş sekmesindeki Örnek Kitap D kaydını silmeye veya düzenlemeye çalışır. | Silme ya da düzenleme seçeneği yoktur. Kayıt değişmeden görünür; listede en az 12 ay saklandığı bilgisi yazar. | L02 | Uyumlu |

Kontrol için [tasarım dosyasındaki](../tasarim/us-15-odunc-listesi.md) L01–L04 bölümlerine bakılmalı. US-13 uzatması sonrası güncel tarihin listede görünmesi Kadir'in KS-13-05 senaryosunda kontrol ediliyor; aynı şeyi burada ikinci kez senaryo yapmadım. 12 aylık saklama süresi bir belge kontrolüyle ölçülemediği için KS-15-08 yalnızca kaydın salt okunur olduğunu ve saklama bilgisinin gösterildiğini kontrol eder.
