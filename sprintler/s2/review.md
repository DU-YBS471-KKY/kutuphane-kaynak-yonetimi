# Sprint 2 Review hazırlığım

Hazırlayan: Mert Seçkin  
Ara kontroller: 31 Ekim ve 2 Kasım 2026  
Planlanan sprint: 28 Ekim–4 Kasım 2026

## Sprint hedefinin ara değerlendirmesi

Kitap konumu ve stok, dijital kaynak erişimi, kitap ekleme, bakım ve puan/yorum işlerinin kabul kriterlerine uygun belgelerle tamamlanmasını takip ediyorum. 2 Kasım kontrolümde Jira'da Sprint 2 aktif, planlanan bitiş 4 Kasım ve 5 Story / 18 SP kapsamının tamamı Tamam durumunda. US-08–10 işlerim 29 Ekim'de onaylanıp tamamlandı (10 SP). Esat, US-06–07 teslimini 1 Kasım'da PR #30 ile ekledi; Kübra PR'ı onayladı ve iki iş Jira'da Tamam'a alındı (8 SP).

US-06–07 kontrol senaryolarının sonuç sütunu henüz "Bekliyor" ve Kübra'nın F-01/F-02 yeniden kontrolü kayıtlı değil. Bu yüzden 18/18 SP'yi Jira durumu olarak yazıyorum; nihai hedef sonucu, PO kabul görüşü ve gerçekleşen bitiş kapanışta eklenecek.

## 2 Kasım iş tablosu

| Story / Jira | Sorumlu | SP | Gözlediğim durum | Çıktı ve inceleme |
|---|---|---:|---|---|
| US-06 / [KKY-7](https://dagdelen41.atlassian.net/browse/KKY-7) | Esat | 3 | Jira'da Tamam | [Ekran taslağı](../../tasar%C4%B1m/esat-us-06-07-ekran-taslaklari.md), [3 kontrol](../../test/us-06-07-kontrol-senaryolari.md), [PR #30](https://github.com/DU-YBS471-KKY/kutuphane-kaynak-yonetimi/pull/30); senaryo sonuçları bekleniyor. |
| US-07 / [KKY-8](https://dagdelen41.atlassian.net/browse/KKY-8) | Esat | 5 | Jira'da Tamam | [Ekran taslağı](../../tasar%C4%B1m/esat-us-06-07-ekran-taslaklari.md), [3 kontrol](../../test/us-06-07-kontrol-senaryolari.md), [PR #30](https://github.com/DU-YBS471-KKY/kutuphane-kaynak-yonetimi/pull/30); senaryo sonuçları bekleniyor. |
| US-08 / [KKY-9](https://dagdelen41.atlassian.net/browse/KKY-9) | Mert | 5 | Tamam | [Ekran/akış](../../tasarim/us-08-kitap-ekleme.md), [6 kontrol](../../test/us-08-kontrol.md), [PR #25](https://github.com/DU-YBS471-KKY/kutuphane-kaynak-yonetimi/pull/25) |
| US-09 / [KKY-19](https://dagdelen41.atlassian.net/browse/KKY-19) | Mert | 2 | Tamam | [Ekran/akış](../../tasarim/us-09-bakim-durumu.md), [5 kontrol](../../test/us-09-kontrol.md), [PR #25](https://github.com/DU-YBS471-KKY/kutuphane-kaynak-yonetimi/pull/25) |
| US-10 / [KKY-20](https://dagdelen41.atlassian.net/browse/KKY-20) | Mert | 3 | Tamam | [Ekran/akış](../../tasarim/us-10-puan-yorum.md), [7 kontrol](../../test/us-10-kontrol.md), [PR #25](https://github.com/DU-YBS471-KKY/kutuphane-kaynak-yonetimi/pull/25) |

Ara tamamlanma: **18/18 SP, %100 (Jira durumu)**. 31 Ekim'deki ara değer 10/18 SP idi. Kapanıştaki tamamlanan/devreden işler ve oran kontrol sonuçlarıyla yeniden hesaplanacak.

## İncelediğim çıktılar ve onay kaydı

US-08–10 teslimimdeki üç ekran/akış ve toplam 18 kontrol senaryosunu, Kübra'nın [29 Ekim bağımsız incelemesi](https://github.com/DU-YBS471-KKY/kutuphane-kaynak-yonetimi/pull/25#pullrequestreview-5695366811) ve [kriter listesi](kabul-kriteri-kontrolu.md) ile karşılaştırdım. Kübra, 11 kabul kriterinin kapsandığını belge incelemesi kapsamında onaylamış; PR #25 aynı gün Eray tarafından develop dalına birleştirilmiş. Kontrolün dayanağı gereksinim, ekran taslağı ve işlem akışı karşılaştırmasıdır; çalışan uygulama testi sonucu kaydetmedim.

Esat'ın US-06–07 teslimini (PR #30) Kübra'nın açık bulgularıyla karşılaştırdım. Ekran taslakları ve altı kontrol senaryosu (3/3) eklenmiş; senaryoların sonuç sütunu "Bekliyor". KS-07-02 artık ziyaretçinin indirmesinin engellenip giriş sayfasına yönlendirilmesini beklenen sonuç olarak yazıyor. KS-06-03 ödünç sonrası stok düşüşünü kapsıyor; iade sonrası stok artışı için senaryo yok.

31 Ekim ara Review'um ve kontrol dosyalarımdaki onay notu düzeltmelerim [PR #28](https://github.com/DU-YBS471-KKY/kutuphane-kaynak-yonetimi/pull/28) ile 1 Kasım'da Eray'ın onayından sonra birleşti.

## Kalan işler ve takip

| İş | Gözlediğim açık nokta | Sonraki kontrol |
|---|---|---|
| US-06 / F-01 | İade sonrası stok değerini karşılaştıran senaryo yok; senaryo sonuçları "Bekliyor". | Esat iade senaryosunu ve sonuçları ekler; Kübra kriteri yeniden kontrol eder; sonucu Review'a ekleyeceğim. |
| US-07 / F-02 | Engel ve giriş yönlendirmesi beklenen sonuçta yazıyor; senaryo sonuçları "Bekliyor". | Kübra yeniden kontrol eder; sonucu Review'a ekleyeceğim. |
| Kriter listesi | [Kriter listesi](kabul-kriteri-kontrolu.md) 31 Ekim'de, PR #30'dan önce yazıldı (11 Uyumlu, 2 Fark var, 4 Kanıt bekleniyor). | Kübra'nın 4 Kasım hedefli son değerlendirmesi. |
| PO kabul görüşü | Sprint 2'nin nihai kabul sonucu henüz kaydedilmedi. | Eray'ın değerlendirmesini tarih ve kaynakla ekleyeceğim. |
| Review kapanışı | Sprint devam ediyor. | Abdülkadir ile son iş/puan durumunu, devreden işleri ve teslim kanıtlarını kapanışta kontrol edeceğim. |

Review hazırlığını ve kendi günlük kaydımı sürdürmemi engelleyen bir durum yok. Nihai sonucu yazabilmem için Kübra'nın yeniden kontrolünü ve Esat'ın senaryo sonuçlarını takip ediyorum.

## Kapanış ekleri

4 Kasım için planlanan kapanışta Jira Sprint Report ve Burndown görüntülerini; GitHub Contributors görünümünü ilgili dal ve tarih kapsamıyla kaydedeceğim. Her görüntünün kontrol tarihini yazacağım. Nihai sonuç, PO görüşü, varsa devreden işler ve gerçekleştiğinde v0.2 sürüm bağlantısı eklenecek.

[Kriter kontrol listesi](kabul-kriteri-kontrolu.md) · [Teslim PR #25](https://github.com/DU-YBS471-KKY/kutuphane-kaynak-yonetimi/pull/25) · [Teslim PR #30](https://github.com/DU-YBS471-KKY/kutuphane-kaynak-yonetimi/pull/30)
