# US-14–17: Gereksinim hazırlığı

Sorumlu: Kübra Şen  
Tarih: 22 Ekim 2026  
Durum: İncelemeye hazır gereksinim taslağı; Story teslimi değildir.

Bu belge, YBS 471 proje planının 5, 9, 10 ve 12. slaytları, 19 Ekim tarihli Ekip Rehberi ve 22 Ekim'de kontrol edilen Jira kayıtlarına dayanır. Story cümleleri ve kabul kriterleri aşağıda Jira ile aynı tutulmuştur. Ek kararlar PO onayı bekler. Çalışan yazılım, tamamlanmış ekran taslağı veya yürütülmüş test sonucu içermez.

## İş ve sprint eşlemesi

| Story | Jira | SP | Planlanan sprint | Trello |
| --- | --- | ---: | --- | --- |
| US-14: Ödünçteki kitabı sırayla rezerve etme | [KKY-21](https://dagdelen41.atlassian.net/browse/KKY-21) | 5 | Sprint 3, 4–11 Kasım | [Kart](https://trello.com/c/F8cdTUia) |
| US-15: Geçmiş ve aktif ödünç listesini görme | [KKY-22](https://dagdelen41.atlassian.net/browse/KKY-22) | 2 | Sprint 3, 4–11 Kasım | [Kart](https://trello.com/c/cMVx1Z6F) |
| US-16: İade tarihine 2 gün kala e-posta uyarısı | [KKY-23](https://dagdelen41.atlassian.net/browse/KKY-23) | 3 | Sprint 4, 11–24 Kasım | [Kart](https://trello.com/c/05d4cL7t) |
| US-17: Rezerve kitap iade edilince bildirim | [KKY-24](https://dagdelen41.atlassian.net/browse/KKY-24) | 3 | Sprint 4, 11–24 Kasım | [Kart](https://trello.com/c/nUgrBhiD) |

Toplam 13 SP: Sprint 3 için 7, Sprint 4 için 6. Tarihler plan hedefidir; Jira Sprint alanı Planning sırasında doldurulacaktır. Şimdilik Jira ve Trello kartları Backlog/Yapılacaklar durumunda kalır. Sprint 1–3 PO Eray, SM Esat; Sprint 4 ve finalde PO Kübra, SM Mert olur.

## US-14 / KKY-21

Öğrenci olarak tüm kopyaları ödünçte olan bir kitap için rezervasyon sırasına girmek istiyorum, böylece kitap iade edildiğinde bana sıra gelebilsin.

### Kabul kriterleri — Jira ile aynı

1. Giriş yapmış öğrenci, tüm kopyaları ödünçte olan kitap için rezervasyon oluşturabilir; talebin tarihi ve sıra numarası kaydedilir.
2. Aynı öğrencinin aynı kitap için ikinci bir aktif rezervasyonu oluşturulmaz; mevcut rezervasyon bilgisi gösterilir.
3. Rezervasyon sırası talep zamanına göre korunur. İade sonrası ilk aktif talep sahibi belirlenir; öğrenci kendi rezervasyonunu iptal ederse sıradan çıkarılır.

Sprint çıktısı: rezervasyon ekranı taslağı, sıra kuralları ve üç kabul kriterini kapsayan kontrol senaryoları.

## US-15 / KKY-22

Öğrenci olarak geçmiş ve aktif ödünç kayıtlarımı görmek istiyorum, böylece elimdeki kitapların iade tarihlerini ve önceki ödünçlerimi takip edebileyim.

### Kabul kriterleri — Jira ile aynı

1. Giriş yapmış öğrenci yalnızca kendi ödünç kayıtlarını görebilir; başka bir öğrencinin kayıtlarına erişemez.
2. Aktif listede kitap adı, ödünç tarihi, güncel iade tarihi ve durum gösterilir; iade edilen kayıt geçmiş listesine geçer.
3. Gecikmiş aktif kayıtlar açıkça işaretlenir. Hiç kayıt yoksa boş liste yerine açıklayıcı bir Kayıt bulunamadı mesajı gösterilir.

Sprint çıktısı: aktif/geçmiş ödünç ekranı taslağı, gösterilecek alanlar ve kabul kriterlerine göre kontrol senaryoları.

## US-16 / KKY-23

Öğrenci olarak ödünç aldığım kitabın iade tarihine iki gün kala e-posta hatırlatması almak istiyorum, böylece kitabı zamanında iade edebileyim.

### Kabul kriterleri — Jira ile aynı

1. Aktif ödünç kaydının güncel iade tarihinden iki takvim günü önce, öğrencinin kayıtlı e-posta adresi için bir hatırlatma oluşturulur.
2. Mesajda kitap adı ve güncel iade tarihi bulunur; başka öğrencilerin ödünç bilgileri yer almaz.
3. Aynı ödünç kaydı ve iade tarihi için tekrar hatırlatma üretilmez; iade edilmiş veya iptal edilmiş kayıtlar için mesaj gönderilmez. Süre uzatılmışsa yeni iade tarihi esas alınır.

Sprint çıktısı: e-posta örneği, hatırlatma zamanı/tekrar kuralları ve kontrol senaryoları; bu aşamada gerçek e-posta gönderimi yapılmayacaktır.

## US-17 / KKY-24

Öğrenci olarak rezerve ettiğim kitap iade edilip sıra bana geldiğinde bildirim almak istiyorum, böylece kitabı teslim almak için kütüphaneye gidebileyim.

### Kabul kriterleri — Jira ile aynı

1. Bir kopya iade edilip kullanılabilir olduğunda, rezervasyon sırasındaki ilk aktif talebin sahibi belirlenir ve bildirim bu öğrenci için oluşturulur.
2. Bildirim kitap adını ve kitabın teslim alınabilir olduğunu içerir; sıradaki diğer öğrencilere aynı kopya için eşzamanlı uygunluk bildirimi gönderilmez.
3. Aynı iade ve rezervasyon için tekrar bildirim oluşturulmaz; iptal edilmiş rezervasyonlar atlanır ve sıradaki aktif talep değerlendirilir.

Sprint çıktısı: bildirim metni örneği, rezervasyon/iade akışı ve kontrol senaryoları. Bu aşamada gerçek kullanıcıya mesaj gönderilmeyecektir.

## Kontrol senaryoları taslağı

Aşağıdaki sonuçlar beklenen davranıştır. Senaryolar henüz uygulanmadı; geçti/kaldı sonucu verilmemiştir. İlgili sprintte ekran/akış taslağı üzerinden kontrol edilip gerçek sonuç ve inceleme kanıtı test klasörüne eklenecektir. Örneklerde yalnızca varsayımsal öğrenci A/B ve kitap X kullanılır.

| Kod | Kriter | Ön koşul ve işlem | Beklenen sonuç |
| --- | --- | --- | --- |
| KS-14-01 | US-14/1 | A giriş yapar; X'in tüm kopyaları ödünçtedir; rezervasyon ister. | Talep tarihi ve sıra numarasıyla bir aktif rezervasyon oluşur. |
| KS-14-02 | US-14/2 | A'nın X için aktif talebi vardır; tekrar rezervasyon ister. | Yeni aktif talep oluşmaz; mevcut rezervasyon gösterilir. |
| KS-14-03 | US-14/3 | A, B'den önce talep oluşturmuştur; bir kopya iade edilir. | İlk aktif talep sahibi A seçilir. |
| KS-14-04 | US-14/3 | A kendi talebini iptal eder; B aktiftir; kopya iade edilir. | A sıradan çıkar; B ilk aktif talep sahibi olur. |
| KS-15-01 | US-15/1 | A kendi kayıtlarını açar; B'nin kaydına erişmeyi dener. | Yalnızca A'nın kayıtları görünür; B'nin bilgileri açılmaz. |
| KS-15-02 | US-15/2 | A aktif ödünç listesini açar, sonra iade kaydı işlenir. | Kitap adı, ödünç/güncel iade tarihi ve durum görünür; iade edilen kayıt geçmişe geçer. |
| KS-15-03 | US-15/3 | İade tarihi geçmiş aktif kayıt listelenir. | Gecikme açıkça işaretlenir. |
| KS-15-04 | US-15/3 | A'nın ödünç kaydı yoktur. | Kayıt bulunamadı mesajı görünür. |
| KS-16-01 | US-16/1 | İade tarihi 10 Kasım olan aktif kayıt için tarih 8 Kasım olarak değerlendirilir. | Kayıtlı e-posta için hatırlatma oluşturulur. |
| KS-16-02 | US-16/2 | A'nın hatırlatma içeriği incelenir. | X'in adı ve güncel iade tarihi vardır; B'nin bilgileri yoktur. |
| KS-16-03 | US-16/3 | Aynı ödünç ve iade tarihi tekrar değerlendirilir. | İkinci hatırlatma oluşmaz. |
| KS-16-04 | US-16/3 | Kayıt iade/iptal edilmiştir veya süre uzatılmıştır. | İade/iptalde mesaj oluşmaz; uzatmada yeni iade tarihi esas alınır. |
| KS-17-01 | US-17/1 | X'in bir kopyası iade edilip kullanılabilir olur; A ilk aktif talep sahibidir. | Bildirim A için oluşturulur. |
| KS-17-02 | US-17/2 | Aynı kopya için A ve B sıradadır; bildirim içeriği incelenir. | X'in adı ve teslim alınabilir bilgisi vardır; B'ye eşzamanlı uygunluk bildirimi oluşmaz. |
| KS-17-03 | US-17/3 | Aynı iade/rezervasyon olayı tekrar değerlendirilir. | Tekrar bildirim oluşmaz. |
| KS-17-04 | US-17/3 | A'nın rezervasyonu iptal edilmiştir; B'nin talebi aktiftir. | A atlanır; B değerlendirilir. |

## PO onayı bekleyen kararlar

Bunlar kabul edilmiş yeni kurallar değildir; Jira kriterlerini değiştirmez.

- US-14: Aynı zaman damgalı taleplerin sıralama ölçütü, kişi başı rezervasyon sınırı ve müsait kopya varken rezervasyon davranışı.
- US-17: Teslim alma için bekletme süresi ve süre dolunca sıradaki öğrenciye geçiş; bildirim kanalı ve tercihlerin etkisi.
- US-16: Hatırlatmanın gün içindeki saati/zaman dilimi, geçersiz e-posta ve gönderim hatasında tekrar deneme politikası.
- US-14/17: Birden fazla kopyanın aynı anda iadesinde tahsis sırası ve bakımdan çıkan kopya için rezervasyon bildirimini başlatacak olay.
- US-15: Geçmiş kayıtların sıralama, filtreleme ve saklama süresi.

## Bağımlılıklar ve teslim kontrolü

US-14 rezervasyon sırası, US-17'nin alıcı seçimine girdidir. [US-12 / KKY-11](https://dagdelen41.atlassian.net/browse/KKY-11) kriterlerine göre hasarlı iade Bakımda işaretlenir ve kullanılabilir stoğa eklenmez; [US-09 / KKY-19](https://dagdelen41.atlassian.net/browse/KKY-19) bakımdaki kopyanın ödünç verilemeyeceğini belirtir. Dolayısıyla US-17 bildirimi yalnızca iade edilen kopya kullanılabilir olduğunda oluşur. Bu mevcut bir bağımlılıktır, yeni PO kararı değildir. [US-13 / KKY-12](https://dagdelen41.atlassian.net/browse/KKY-12) için başka öğrencinin rezervasyonu varsa uzatma reddedilir; uzatma kabul edildiğinde US-15 ve US-16 güncel iade tarihini esas alır. US-02 oturum bilgisiyle yetki tutarlılığı ilgili Story sahipleriyle kontrol edilmelidir.

- [x] KKY-21–24'ün sorumlusu, Epic'i ve doğru Story Points alanındaki 5/2/3/3 puanları kontrol edildi.
- [x] Dört Story'nin Jira cümlesi ve üçer kabul kriteri bu belgede eşlendi.
- [x] Trello'da Kübra üyesi, Jira linki ve planlanan sprinti olan dört Backlog kartı oluşturuldu.
- [ ] Eray gereksinim belgesini inceleyip geri bildirim verecek.
- [ ] Bağımsız onay sonrası PR, Create a merge commit ile develop'a alınacak.
- [ ] Birleştirme sonrası Jira belge linkleri develop veya kalıcı commit bağlantısına güncellenecek.
- [ ] Sprint 3–4'te ekran/akış taslakları, mesaj örnekleri ve gerçek kontrol sonuçları eklenecek.
- [ ] Story kabul kriterleri ve tüm çıktılar incelenmeden Jira'da Tamamlandı yapılmayacak.
