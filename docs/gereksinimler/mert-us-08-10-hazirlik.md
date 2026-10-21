# US-08–US-10 Gereksinim ve Kabul Kriterleri

Sorumlu: Mert Seçkin (@mrts3c)  
Hazırlanma tarihi: 21 Ekim 2026

Bu belge, Mert’in üç işinin kapsamını ve daha sonra üretilecek çıktılarını netleştirir. Gereksinim hazırlığıdır; ekranların tamamlandığını veya testlerin çalıştırıldığını göstermez. İşler Backlog / Yapılacak durumundadır. Sprint 2, ekip planındaki hedef dönemdir; fiilî sprint ataması ve başlangıcı ekipçe yapılacaktır.

| İş | Jira | Puan | Hedef | Trello |
|---|---|---:|---|---|
| US-08 Kitap ekleme | [KKY-9](https://dagdelen41.atlassian.net/browse/KKY-9) | 5 | Sprint 2 | [Kart](https://trello.com/c/QXBJaDN2) |
| US-09 Bakım durumu | [KKY-19](https://dagdelen41.atlassian.net/browse/KKY-19) | 2 | Sprint 2 | [Kart](https://trello.com/c/UJwCmUw7) |
| US-10 Puan ve yorum | [KKY-20](https://dagdelen41.atlassian.net/browse/KKY-20) | 3 | Sprint 2 | [Kart](https://trello.com/c/I6QAP8HN) |

Üç iş de Kaynak ve Kitap Envanteri Epic’i kapsamındadır. Jira kayıtları ayrıntılı iş takibinin kaynağıdır.

## US-08 — Görevli barkod ile yeni kitap ekleme

**User Story:** Görevli olarak barkod/ISBN bilgisiyle sisteme yeni bir kitap eklemek istiyorum, böylece öğrenciler o kitabı katalogda bulabilsin.

### Kabul kriterleri

1. Kitap adı, yazar, ISBN ve kategori zorunludur. Eksik alan varken kayıt engellenir ve eksik alan belirtilir.
2. Barkoddan veya elle girilen ISBN, 13 haneli olma kuralına göre kontrol edilir; uygun olmayan giriş için uyarı gösterilir.
3. Kayıtlı ISBN tekrar girildiğinde yeni kitap kaydı oluşturulmaz ve mevcut ISBN uyarısı gösterilir.
4. Kapak bilgisi isteğe bağlıdır; kapak olmaması geçerli kitap kaydını engellemez.
5. Başarıyla kaydedilen kitap katalog aramasında bulunabilir.

### Sprint sırasında hazırlanacak çıktılar

- Kitap ekleme formu taslağı ve zorunlu/isteğe bağlı alan tablosu.
- Geçersiz ISBN ve tekrar kayıt uyarılarını içeren doğrulama akışı.
- Aşağıdaki senaryoların çıktı üzerinden değerlendirilmesi ve sonuçlarının kaydı.

| Senaryo | Beklenen sonuç |
|---|---|
| Zorunlu alanlardan biri boş | Kayıt oluşmaz; ilgili alan gösterilir. |
| ISBN 13 haneli değil | Uyarı gösterilir; kayıt oluşmaz. |
| ISBN zaten kayıtlı | Yeni kayıt oluşmaz; mevcut ISBN uyarısı gösterilir. |
| Geçerli alanlar, kapak yok | Kayıt oluşur; katalogda bulunur. |

**Önceki katkı:** Kadir’in kitap ekleme formu ve alan kuralları çalışması [PR #2](https://github.com/DU-YBS471-KKY/kutuphane-kaynak-yonetimi/pull/2) bu işin başlangıç kaynağıdır. Bu belge, ekip rehberindeki US-08 eşlemesine göre sonraki kapsamı ve kontrol senaryolarını düzenler; önceki katkının yazarlığı korunur.

## US-09 — Yıpranmış kitapları bakımda işaretleme

**User Story:** Görevli olarak yıpranmış bir kitap kopyasını bakımda işaretlemek istiyorum, böylece kullanılamayan kopya öğrencilere ödünç verilmesin.

### Kabul kriterleri

1. Görevli/admin kitap kopyasını Bakımda durumuna alabilir; öğrenci bu işlemi yapamaz.
2. Bakımdaki kopya ödünç verilemez ve müsait kopya sayısına katılmaz. Aynı kitabın diğer müsait kopyaları ödünç verilebilir.
3. Kopya yeniden Müsait durumuna alındığında müsait kopya sayısı güncellenir.

### Sprint sırasında hazırlanacak çıktılar

- Kopyayı Bakımda ve yeniden Müsait yapma akışı.
- Yetki ve müsait kopya sayısı kuralları.
- Aşağıdaki senaryoların değerlendirilmesi ve sonuç kaydı.

| Senaryo | Beklenen sonuç |
|---|---|
| Öğrenci bakım durumunu değiştirmek ister | İşleme izin verilmez. |
| İki müsait kopyadan biri bakımda yapılır | Müsait sayı 1 olur; bakımdaki kopya ödünç verilemez. |
| Bakımdaki kopya yeniden müsait yapılır | Müsait kopya sayısı güncellenir. |

## US-10 — Okunan kitaplara puan ve yorum bırakma

**User Story:** Öğrenci olarak okuduğum kitaba puan ve yorum bırakmak istiyorum, böylece deneyimimi diğer okuyucularla paylaşabileyim.

### Kabul kriterleri

1. Giriş yapmış öğrenci 1–5 arasında tam sayı puan verebilir. Aralık dışındaki veya tam sayı olmayan puan kabul edilmez.
2. Gönderilen yorum Onay bekliyor durumundadır; onay öncesi diğer kullanıcılara gösterilmez.
3. Görevli/admin onayladığında puan ve yorum yayımlanır; reddedilen yorum yayımlanmaz.

### Sprint sırasında hazırlanacak çıktılar

- Öğrenci için puan/yorum ekran taslağı.
- Onay bekliyor → Onaylandı / Reddedildi akışı ve görevli/admin onay taslağı.
- Aşağıdaki senaryoların değerlendirilmesi ve sonuç kaydı.

| Senaryo | Beklenen sonuç |
|---|---|
| Geçerli 1 veya 5 puan, yorum gönderimi | Kayıt onay bekler; diğer kullanıcılara henüz görünmez. |
| 0, 6 veya 2,5 puan | Giriş reddedilir; geçerli puan istenir. |
| Görevli/admin yorumu onaylar | Puan ve yorum yayımlanır. |
| Görevli/admin yorumu reddeder | Yorum yayımlanmaz. |

## İnceleme ve sonraki adım

Başka bir ekip üyesi Jira–US eşlemesini, kabul kriterlerini ve beklenen sonuçları kontrol eder. Geri bildirimler bu belge üzerinde düzeltilir. Ekran/akış çıktıları ve senaryo sonuçları ilgili işin sprintinde hazırlanır; PR açılmış olması bu üç işin tamamlandığı anlamına gelmez.

Tamamlandı durumuna geçiş için ekip Definition of Done’ı uygulanır: kabul kriterlerini karşılayan çıktı, başka bir üyenin incelemesi ve GitHub/Jira bağlantıları.
