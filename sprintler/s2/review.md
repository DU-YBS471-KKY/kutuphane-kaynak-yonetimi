# Sprint 2 Review hazırlığım

Hazırlayan: Mert Seçkin  
Kontroller: 31 Ekim, 2 Kasım öğle, 2 Kasım akşam ve 3 Kasım (kapanış öncesi)  
Planlanan sprint: 28 Ekim–4 Kasım 2026

## Sprint hedefinin kapanış öncesi değerlendirmesi

Kitap konumu ve stok, dijital kaynak erişimi, kitap ekleme, bakım ve puan/yorum işlerinin kabul kriterlerine uygun belgelerle tamamlanmasını takip ediyorum. 2 Kasım akşam kontrolümde Jira'da Sprint 2 hâlâ aktif (bitiş alanı 4 Kasım 00.00) ve 5 Story / 18 SP kapsamının tamamı Tamam durumunda. US-08–10 işlerim (10 SP) 29 Ekim'de, Esat'ın US-06–07 işleri (8 SP) 1–2 Kasım'da tamamlandı.

Kübra'nın 2 Kasım kontrolünde açık kalan F-01 (iade sonrası stok), Esat'ın eklediği KS-06-04 senaryosuyla ([PR #36](https://github.com/DU-YBS471-KKY/kutuphane-kaynak-yonetimi/pull/36)) giderildi; Kübra PR #36'yı onayladı ve son kontrolünde ([PR #39](https://github.com/DU-YBS471-KKY/kutuphane-kaynak-yonetimi/pull/39)) 17 kriterin 17'sini Uyumlu olarak kaydetti. Eray 2 Kasım akşamı beş Story ve KKY-25 için Jira'da PO onayı yazdı, Sprint 2'yi PO olarak kabul ettiğini Slack'te paylaştı. Kapanış öncesi kayıtlara göre sprint hedefi karşılanmış görünüyor; gerçekleşen bitiş, Sprint Report ve Burndown kapanışta eklenecek.

## 2 Kasım akşam iş tablosu

| Story / Jira | Sorumlu | SP | Gözlediğim durum | Çıktı ve inceleme |
|---|---|---:|---|---|
| US-06 / [KKY-7](https://dagdelen41.atlassian.net/browse/KKY-7) | Esat | 3 | Tamam, PO onaylı | [Ekran taslağı](../../tasarim/esat-us-06-07-ekran-taslaklari.md), [4 kontrol, Geçti](../../test/us-06-07-kontrol-senaryolari.md), [PR #30](https://github.com/DU-YBS471-KKY/kutuphane-kaynak-yonetimi/pull/30), [PR #36](https://github.com/DU-YBS471-KKY/kutuphane-kaynak-yonetimi/pull/36) |
| US-07 / [KKY-8](https://dagdelen41.atlassian.net/browse/KKY-8) | Esat | 5 | Tamam, PO onaylı | [Ekran taslağı](../../tasarim/esat-us-06-07-ekran-taslaklari.md), [3 kontrol, Geçti](../../test/us-06-07-kontrol-senaryolari.md), [PR #30](https://github.com/DU-YBS471-KKY/kutuphane-kaynak-yonetimi/pull/30) |
| US-08 / [KKY-9](https://dagdelen41.atlassian.net/browse/KKY-9) | Mert | 5 | Tamam, PO onaylı | [Ekran/akış](../../tasarim/us-08-kitap-ekleme.md), [6 kontrol](../../test/us-08-kontrol.md), [PR #25](https://github.com/DU-YBS471-KKY/kutuphane-kaynak-yonetimi/pull/25) |
| US-09 / [KKY-19](https://dagdelen41.atlassian.net/browse/KKY-19) | Mert | 2 | Tamam, PO onaylı | [Ekran/akış](../../tasarim/us-09-bakim-durumu.md), [5 kontrol](../../test/us-09-kontrol.md), [PR #25](https://github.com/DU-YBS471-KKY/kutuphane-kaynak-yonetimi/pull/25) |
| US-10 / [KKY-20](https://dagdelen41.atlassian.net/browse/KKY-20) | Mert | 3 | Tamam, PO onaylı | [Ekran/akış](../../tasarim/us-10-puan-yorum.md), [7 kontrol](../../test/us-10-kontrol.md), [PR #25](https://github.com/DU-YBS471-KKY/kutuphane-kaynak-yonetimi/pull/25) |

Kapanış öncesi tamamlanma: **18/18 SP, %100** (Jira durumu ve PO kabulü). 31 Ekim ara değeri 10/18 SP idi. Sayı, kapanıştaki Sprint Report ile doğrulanacak.

Sprint içinde açılan hata kaydı: [KKY-25](https://dagdelen41.atlassian.net/browse/KKY-25) (F-01, Kadir açtı, Esat çözdü, Eray PO onayı verdi). İlgili GitHub kayıtları: [#34](https://github.com/DU-YBS471-KKY/kutuphane-kaynak-yonetimi/issues/34) ve [#35](https://github.com/DU-YBS471-KKY/kutuphane-kaynak-yonetimi/issues/35), ikisi de kapandı.

## İncelediğim çıktılar ve onay kaydı

US-08–10 teslimimdeki üç ekran/akış ve toplam 18 kontrol senaryosunu, Kübra'nın [29 Ekim bağımsız incelemesi](https://github.com/DU-YBS471-KKY/kutuphane-kaynak-yonetimi/pull/25#pullrequestreview-5695366811) ve [kriter listesi](kabul-kriteri-kontrolu.md) ile karşılaştırdım. Kübra, 11 kabul kriterinin kapsandığını belge incelemesi kapsamında onaylamış; PR #25 aynı gün Eray tarafından develop dalına birleştirilmiş.

US-06–07 için Esat, PR #30 ile ekran taslağını ve altı kontrol senaryosunu ekledi. Kübra'nın 2 Kasım kontrolü ([PR #33](https://github.com/DU-YBS471-KKY/kutuphane-kaynak-yonetimi/pull/33)) 17 kriterde 16 Uyumlu, 1 Fark var sonucunu verdi: F-02 kapandı, F-01 açık kaldı. PR #33'ü PR #30 dosyalarıyla karşılaştırıp onayladım; F-01'i #34, ekran taslağının ayrı `tasarım/` klasöründe durmasını #35 olarak kaydettim. Kadir F-01'i Jira'da KKY-25 olarak açtı. Esat PR #36 ile KS-06-04'ü (iade sonrası stok 1 artar) ekledi, ekran taslağını `tasarim/` klasörüne taşıdı ve yedi senaryonun durumunu "Geçti" yaptı; Kübra PR #36'yı onayladı.

Yedi US-06–07 senaryosu ile kendi 18 senaryomdaki sonuçlar çalışan uygulama testi değildir; gereksinim, ekran taslağı ve işlem akışı üzerinden yapılan belge kontrolüdür.

31 Ekim ara Review'um [PR #28](https://github.com/DU-YBS471-KKY/kutuphane-kaynak-yonetimi/pull/28) ile 1 Kasım'da, 2 Kasım güncellemem [PR #32](https://github.com/DU-YBS471-KKY/kutuphane-kaynak-yonetimi/pull/32) ile Kadir ve Eray'ın onayından sonra birleşti.

## Kalan işler ve takip

| İş | Gözlediğim açık nokta | Sonraki adım |
|---|---|---|
| Kriter listesi | Kübra'nın 2 Kasım akşam son kontrolü (PR #39, 3 Kasım'da birleşti): 17 kriterde 17 Uyumlu, F-01 kapandı, açık bulgu yok. | Kübra kapanışta son doğrulamasını yapacak. |
| Retrospektif | Kübra GitHub'daki [Retro dosyasını](retrospektif.md) 2 Kasım akşam durumuyla güncelledi (PR #39); ortak rapordaki Retro bölümü ve Enes'in katkısı bekleniyor. | Kübra ve Enes. |
| Sprint kapanışı | Jira'da Sprint 2 aktif. | Esat kapatır; Sprint Report, Burndown ve Contributors görüntülerini ekleyeceğim. |
| v0.2 sürümü | PO kabulünde hedef sürüm v0.2 geçiyor; GitHub'da sürüm oluşturulmadı. | Oluşturulursa bağlantısını ekleyeceğim. |

Review hazırlığını ve kendi günlük kaydımı sürdürmemi engelleyen bir durum yok. Nihai Review için sprint kapanışını bekliyorum.

## Kapanış ekleri

Kapanışta Jira Sprint Report ve Burndown görüntülerini; GitHub Contributors görünümünü ilgili dal ve tarih kapsamıyla kaydedeceğim. Her görüntünün kontrol tarihini yazacağım. Gerçekleşen bitiş, nihai sayılar ve varsa v0.2 sürüm bağlantısı eklenecek.

[Kriter kontrol listesi](kabul-kriteri-kontrolu.md) · [Teslim PR #25](https://github.com/DU-YBS471-KKY/kutuphane-kaynak-yonetimi/pull/25) · [Teslim PR #30](https://github.com/DU-YBS471-KKY/kutuphane-kaynak-yonetimi/pull/30) · [Düzeltme PR #36](https://github.com/DU-YBS471-KKY/kutuphane-kaynak-yonetimi/pull/36)
