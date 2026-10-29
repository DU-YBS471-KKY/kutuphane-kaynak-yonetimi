# US 08 09 10 gereksinim ve teslim takibi

**Sorumlu:** Mert Seçkin (@mrts3c)  
**İlk hazırlık:** 21 Ekim 2026 | **Güncelleme:** 29 Ekim 2026  
**Sprint:** 2 | **Epic:** Kaynak ve Kitap Envanteri

Üç işimin Jira kabul kriterlerini ekran, işlem akışı ve kontrol belgeleriyle eşleştirdim. Çalışmalar belge ve ekran taslağı kapsamındadır; çalışan uygulama testi kaydetmedim. Kübra’nın bağımsız incelemesinden sonra PR #25, Eray tarafından 29 Ekim’de develop dalına birleştirildi. Üç işimi tamamlanma koşullarına göre Tamam durumuna aldım.

| İş | Jira | SP | Tasarım | Kontrol |
|---|---|---:|---|---|
| US-08 Kitap ekleme | [KKY-9](https://dagdelen41.atlassian.net/browse/KKY-9) | 5 | [Ekran ve akış](../../tasarim/us-08-kitap-ekleme.md) | [Senaryolar](../../test/us-08-kontrol.md) |
| US-09 Bakım durumu | [KKY-19](https://dagdelen41.atlassian.net/browse/KKY-19) | 2 | [Ekran ve akış](../../tasarim/us-09-bakim-durumu.md) | [Senaryolar](../../test/us-09-kontrol.md) |
| US-10 Puan ve yorum | [KKY-20](https://dagdelen41.atlassian.net/browse/KKY-20) | 3 | [Ekran ve akış](../../tasarim/us-10-puan-yorum.md) | [Senaryolar](../../test/us-10-kontrol.md) |

## US 08 kitap ekleme

Görevli olarak barkod/ISBN bilgisiyle kitap eklemek istiyorum; böylece öğrenciler kitabı katalogda bulabilsin.

1. Başlık, yazar, ISBN ve kategori zorunludur; eksikte kayıt yapılmaz ve alan belirtilir.
2. Barkoddan veya elle girilen ISBN 13 rakam olmalıdır; uygun olmayan giriş reddedilir.
3. Aynı ISBN ikinci kitap kaydı oluşturmaz; mevcut ISBN uyarısı gösterilir.
4. Kapak isteğe bağlıdır; boş olması geçerli kaydı engellemez.
5. Kaydedilen kitap katalog aramasında görünür.

Alan kurallarında Kadir'in [PR #2](https://github.com/DU-YBS471-KKY/kutuphane-kaynak-yonetimi/pull/2) hazırlığından yararlandım. Bu işin ekranını, doğrulama akışını ve kriter kontrolünü ben hazırladım.

## US 09 bakım durumu

Görevli olarak yıpranmış bir kitap kopyasını bakımda işaretlemek istiyorum; böylece kullanılamayan kopya ödünç verilmesin.

1. Görevli/admin kopyayı Bakımda yapabilir; öğrenci yapamaz.
2. Bakımdaki kopya ödünç verilemez, müsait sayıya katılmaz; sağlam kopyalar kullanılabilir kalır.
3. Kopya yeniden Müsait yapıldığında müsait sayı güncellenir.

## US 10 puan ve yorum

Öğrenci olarak okuduğum kitaba puan ve yorum bırakmak istiyorum; böylece deneyimimi paylaşabileyim.

1. Giriş yapmış öğrenci 1–5 arasında tam sayı puan verebilir; diğer değerler reddedilir.
2. Gönderilen yorum Onay bekliyor olur; diğer öğrencilere gösterilmez.
3. Görevli/admin onayladığında puan ve yorum görünür; reddedilen yorum yayımlanmaz.

## İnceleme ve durum

29 Ekim'de her kriteri tasarım ve kontrol dosyalarına bağladım. Tablolardaki sonuçlar belge tutarlılığı kontrolüdür. [PR #25](https://github.com/DU-YBS471-KKY/kutuphane-kaynak-yonetimi/pull/25), Kübra'nın 29 Ekim 12.18 tarihli [inceleme onayını](https://github.com/DU-YBS471-KKY/kutuphane-kaynak-yonetimi/pull/25#pullrequestreview-5695366811) aldı; Eray 12.32'de develop dalına birleştirdi. KKY-9, KKY-19 ve KKY-20'nin Jira/Trello kapanışlarını ve kanıt bağlantılarını güncelledim. Sprint 2'nin ortak başlangıç ve kapanış kaydını Esat/Eray yönetecek.
