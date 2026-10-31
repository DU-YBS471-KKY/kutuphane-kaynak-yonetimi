# Sprint 2 Review hazırlığım

Hazırlayan: Mert Seçkin  
Ara kontrol: 31 Ekim 2026  
Planlanan sprint: 28 Ekim–4 Kasım 2026

## Sprint hedefinin ara değerlendirmesi

Kitap konumu ve stok, dijital kaynak erişimi, kitap ekleme, bakım ve puan/yorum işlerinin kabul kriterlerine uygun belgelerle tamamlanmasını takip ediyorum. Jira'da Sprint 2 aktif ve planlanan bitiş 4 Kasım. Kontrolümde 5 Story / 18 SP kapsamının 3 Story / 10 SP bölümü tamam, 2 Story / 8 SP bölümü yapılacaklar durumunda. Bu, sprint sürerken aldığım ara kayıttır. Nihai hedef sonucu, PO kabul görüşü ve gerçekleşen bitiş kapanışta eklenecek.

## 31 Ekim iş tablosu

| Story / Jira | Sorumlu | SP | Gözlediğim durum | Çıktı ve inceleme |
|---|---|---:|---|---|
| US-06 / [KKY-7](https://dagdelen41.atlassian.net/browse/KKY-7) | Esat | 3 | Yapılacaklar | Gereksinim hazırlığı mevcut; ekran/akış ve sonuç teslimini bekliyorum. |
| US-07 / [KKY-8](https://dagdelen41.atlassian.net/browse/KKY-8) | Esat | 5 | Yapılacaklar | Gereksinim hazırlığı mevcut; ekran/akış ve sonuç teslimini bekliyorum. |
| US-08 / [KKY-9](https://dagdelen41.atlassian.net/browse/KKY-9) | Mert | 5 | Tamam | [Ekran/akış](../../tasarim/us-08-kitap-ekleme.md), [6 kontrol](../../test/us-08-kontrol.md), [PR #25](https://github.com/DU-YBS471-KKY/kutuphane-kaynak-yonetimi/pull/25) |
| US-09 / [KKY-19](https://dagdelen41.atlassian.net/browse/KKY-19) | Mert | 2 | Tamam | [Ekran/akış](../../tasarim/us-09-bakim-durumu.md), [5 kontrol](../../test/us-09-kontrol.md), [PR #25](https://github.com/DU-YBS471-KKY/kutuphane-kaynak-yonetimi/pull/25) |
| US-10 / [KKY-20](https://dagdelen41.atlassian.net/browse/KKY-20) | Mert | 3 | Tamam | [Ekran/akış](../../tasarim/us-10-puan-yorum.md), [7 kontrol](../../test/us-10-kontrol.md), [PR #25](https://github.com/DU-YBS471-KKY/kutuphane-kaynak-yonetimi/pull/25) |

Ara tamamlanma: **10/18 SP, %55,6**. Kapanıştaki tamamlanan/devreden işler ve oran yeniden hesaplanacak.

## İncelediğim çıktılar ve onay kaydı

US-08–10 teslimimdeki üç ekran/akış ve toplam 18 kontrol senaryosunu, Kübra'nın [29 Ekim bağımsız incelemesi](https://github.com/DU-YBS471-KKY/kutuphane-kaynak-yonetimi/pull/25#pullrequestreview-5695366811) ve [kriter listesi](kabul-kriteri-kontrolu.md) ile karşılaştırdım. Kübra, 11 kabul kriterinin kapsandığını belge incelemesi kapsamında onaylamış; PR #25 aynı gün Eray tarafından develop dalına birleştirilmiş. Jira ve Trello'da üç işim tamamlandı durumunda.

Kontrolün dayanağı gereksinim, ekran taslağı ve işlem akışı karşılaştırmasıdır. Çalışan uygulama testi sonucu kaydetmedim. Kontrol dosyalarımda kalan eski “bağımsız inceleme bekleniyor” notlarını gerçekleşen onay bağlantısıyla güncelledim.

## Kalan işler ve takip

| İş | Gözlediğim açık nokta | Sonraki kontrol |
|---|---|---|
| US-06 / F-01 | Ödünç/iade öncesi ve sonrası stok değerini karşılaştıran senaryo ile ekran/sonuç kanıtı eksik. | Esat'ın tesliminden sonra Kübra kriteri yeniden kontrol edecek; sonucu Review'a ekleyeceğim. |
| US-07 / F-02 | Oturumsuz PDF erişiminin engellenmesi ve giriş yönlendirmesi beklenen sonuçta açıkça kontrol edilmeli. | Esat'ın tesliminden sonra Kübra dijital/basılı kaynak ve oturum yollarını yeniden karşılaştıracak. |
| PO kabul görüşü | Sprint 2'nin nihai kabul sonucu henüz kaydedilmedi. | Eray'ın değerlendirmesini tarih ve kaynakla ekleyeceğim. |
| Review kapanışı | Sprint devam ediyor. | Abdülkadir ile son iş/puan durumunu, devreden işleri ve teslim kanıtlarını kapanışta kontrol edeceğim. |

Review hazırlığını ve kendi günlük kaydımı sürdürmemi engelleyen bir durum yok. Sprint hedefinin tamamını değerlendirebilmem için kalan iki işin teslim ve inceleme sonuçlarını takip edeceğim.

## Kapanış ekleri

4 Kasım için planlanan kapanışta Jira Sprint Report ve Burndown görüntülerini; GitHub Contributors görünümünü ilgili dal ve tarih kapsamıyla kaydedeceğim. Her görüntünün kontrol tarihini yazacağım. Nihai sonuç, PO görüşü, varsa devreden işler ve gerçekleştiğinde v0.2 sürüm bağlantısı eklenecek.

[Ortak Sprint 2 raporu](https://docs.google.com/document/d/1dovKZWNX8STAj2aNgCt0hlEapiJboS2mtfXGcQEtI4o/edit) · [Kriter kontrol listesi](kabul-kriteri-kontrolu.md) · [Teslim PR #25](https://github.com/DU-YBS471-KKY/kutuphane-kaynak-yonetimi/pull/25)
