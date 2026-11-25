# KKY 29 iade sonrası aktif ve geçmiş liste kontrolü

Hazırlayan: Mert Seçkin — 25 Kasım 2026  
Jira: [KKY-29](https://dagdelen41.atlassian.net/browse/KKY-29) | Sprint 4 hazırlığı  
Durum: Çözüm akışı ve kontrol senaryoları hazır; bağımsız kontrol bekleniyor.

## Sorun ve hazırladığım düzeltme

Ders senaryosunda "İade alındı" mesajı görünen kitap öğrencinin Aktif listesinde kalıyor. US-12 ile US-15'i karşılaştırdım: iade edilen kaydın geçmişe geçmesi zaten tanımlı; başarı mesajının ne zaman gösterileceği ve listenin hangi kayıt durumuna göre ayrılacağı ayrıca netleştirilmeli. Çalışan uygulama bulunmadığı için hatanın teknik kök nedeni doğrulanmadı.

US-12'ye iadenin tamamlanması ile başarı mesajının sırasını; US-15'e aktif/geçmiş ayrımının öğrencinin ödünç kaydı üzerinden yapılmasını ekledim. Kopyanın Müsait, Bakımda veya Rezerve olması öğrencinin kapanmış ödüncünü aktif tutmamalı.

## Ortak örnek veri

Veriler ders örneğidir. Öğrenci 2000000091'in Dönüşüm / K-291 kopyası için bir aktif ödünç kaydı vardır. Kayıt 18.11.2026'da açılmıştır; planlanan son gün 03.12.2026'dır. Senaryodaki iade 25.11.2026'da yapılır. Başlangıçta bu kayıt geçmiş listesinde yoktur. Her senaryo başlangıç verisinden ayrı değerlendirilir; diğer öğrenci örnekleri değiştirilmez.

## Yeniden kontrol senaryoları

| Kod | Adımlar | Beklenen sonuç | Kontrol edilecek bölüm | Sonuç |
|---|---|---|---|---|
| KKY29-01 | Görevli K-291'i okutur, Sağlam seçer ve iadeyi tamamlar. Öğrenci Aktif ve Geçmiş sekmelerini yeniler. | Başarı mesajı işlem tamamlanınca görünür. Kayıt Aktif'ten çıkar; Geçmiş'te 25.11.2026 ve İade edildi bilgisiyle bir kez görünür. | US-12 I02 ve KKY-29 eki; US-15 L02 ve KKY-29 eki | Bağımsız kontrol bekleniyor |
| KKY29-02 | KKY29-01'den sonra öğrenci listeyi kapatıp yeniden açar ve iki sekmeyi kontrol eder. | Kayıt Aktif'e dönmez; Geçmiş'te ikinci bir kayıt oluşmaz. | US-15 KKY-29 eki | Bağımsız kontrol bekleniyor |
| KKY29-03 | Başlangıçtaki K-291 Hasarlı seçilerek iade edilir, listeler yenilenir. | Kopya Bakımda olur; öğrencinin ödünç kaydı kapanır ve Geçmiş'e geçer. Aktif'te görünmez. | US-12 I03; US-15 L02 ve KKY-29 ekleri | Bağımsız kontrol bekleniyor |
| KKY29-04 | K-291 için başka öğrencinin aktif rezervasyonu olduğu varsayılır; sağlam iade tamamlanır, listeler yenilenir. | Kopya Rezerve olur; iade eden öğrencinin kaydı Geçmiş'e geçer. Rezerve olması kaydı Aktif'te bırakmaz. | US-12 I05 ve US-15 KKY-29 eki | Bağımsız kontrol bekleniyor |
| KKY29-05 | İade tamamlanmadan işlem başarısız olur; öğrenci listeleri yeniler. | Başarı mesajı gösterilmez. Kayıt Aktif'te kalır; tamamlanmış iade gibi Geçmiş'e eklenmez. | US-12 ve US-15 KKY-29 ekleri | Bağımsız kontrol bekleniyor |

## İnceleme ve kapanış

Kübra'dan US-15 liste akışıyla birlikte bağımsız kontrol isteyeceğim. Kontrol eden kişi baktığı bölümü, gözlediği sonucu ve varsa düzeltme isteğini kaydeder. Sonuçlar henüz Geçti veya Uyumlu olarak doldurulmadı. Bu senaryolar Sprint 3'ün tamamlanan 46 kontrolünden ayrıdır ve Sprint 4 bug takibine aittir.

Bağımsız kontrol ve PO kabulü kaydedildikten sonra Jira durumunu buna göre güncelleyeceğim. Bu çalışma uygulama üzerinde hata giderildiği iddiası içermez; dersin belge ve akış çalışması kapsamında hazırlanmıştır.
