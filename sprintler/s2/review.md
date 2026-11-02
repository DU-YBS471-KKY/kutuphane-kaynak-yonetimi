# Sprint 2 Review hazırlığım

Hazırlayan: Mert Seçkin  
Ara kontroller: 31 Ekim ve 2 Kasım 2026  
Planlanan sprint: 28 Ekim–4 Kasım 2026

## Sprint hedefinin ara değerlendirmesi

Kitap konumu ve stok, dijital kaynak erişimi, kitap ekleme, bakım ve puan/yorum işlerinin kabul kriterlerine uygun belgelerle tamamlanmasını takip ediyorum. 2 Kasım kontrolümde Jira'da Sprint 2 aktif, planlanan bitiş 4 Kasım ve 5 Story / 18 SP kapsamının tamamı Tamam durumunda. US-08–10 işlerim 29 Ekim'de onaylanıp tamamlandı (10 SP). Esat, US-06–07 teslimini 1 Kasım'da PR #30 ile ekledi; Kübra PR'ı onayladı ve iki iş Jira'da Tamam'a alındı (8 SP).

Kübra 2 Kasım yeniden kontrolünde ([PR #33](https://github.com/DU-YBS471-KKY/kutuphane-kaynak-yonetimi/pull/33)) 17 kriterden 16'sını Uyumlu, 1'ini Fark var olarak kaydetti: F-02 kapandı, F-01 (iade sonrası stok) açık. US-06–07 kontrol senaryolarının sonuç sütunu da henüz "Bekliyor". Bu yüzden 18/18 SP'yi Jira durumu olarak yazıyorum; nihai hedef sonucu, PO kabul görüşü ve gerçekleşen bitiş kapanışta eklenecek.

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

Esat'ın US-06–07 teslimini (PR #30) Kübra'nın açık bulgularıyla karşılaştırdım. Ekran taslakları ve altı kontrol senaryosu (3/3) eklenmiş; senaryoların sonuç sütunu "Bekliyor". KS-07-02 artık ziyaretçinin indirmesinin engellenip giriş sayfasına yönlendirilmesini beklenen sonuç olarak yazıyor. KS-06-03 ödünç sonrası stok düşüşünü kapsıyor; iade sonrası stok artışı için senaryo yok. Kübra'nın 2 Kasım kontrolü de aynı sonuca ulaştı; PR #33'ü inceleyip onayladım. F-01'i [#34](https://github.com/DU-YBS471-KKY/kutuphane-kaynak-yonetimi/issues/34), ekran taslağının ayrı `tasarım/` klasöründe durmasını [#35](https://github.com/DU-YBS471-KKY/kutuphane-kaynak-yonetimi/issues/35) olarak kaydettim.

31 Ekim ara Review'um ve kontrol dosyalarımdaki onay notu düzeltmelerim [PR #28](https://github.com/DU-YBS471-KKY/kutuphane-kaynak-yonetimi/pull/28) ile 1 Kasım'da Eray'ın onayından sonra birleşti.

## Kalan işler ve takip

| İş | Gözlediğim açık nokta | Sonraki kontrol |
|---|---|---|
| US-06 / F-01 ([#34](https://github.com/DU-YBS471-KKY/kutuphane-kaynak-yonetimi/issues/34)) | Kübra'nın 2 Kasım kontrolünde açık: iade sonrası stok değerini karşılaştıran senaryo yok; senaryo sonuçları "Bekliyor". | Esat iade senaryosunu ve sonuçları ekler; Kübra 4 Kasım'da yeniden kontrol eder; sonucu Review'a ekleyeceğim. |
| US-07 / F-02 | Kübra 2 Kasım'da kapattı (PR #33); senaryo sonuçları "Bekliyor". | Esat senaryo sonuçlarını doldurur. |
| Kriter listesi | Kübra'nın 2 Kasım bölümü: 16 Uyumlu, 1 Fark var, 0 Kanıt bekleniyor; PR #33'te; onayladım, birleşmesi bekleniyor. | Kübra'nın 4 Kasım son değerlendirmesi. |
| Klasör adı ([#35](https://github.com/DU-YBS471-KKY/kutuphane-kaynak-yonetimi/issues/35)) | US-06–07 ekran taslağı `tasarım/` klasöründe, diğerleri `tasarim/` altında. | Esat dosyayı taşıyınca bu dosyadaki bağlantıyı güncelleyeceğim. |
| PO kabul görüşü | Sprint 2'nin nihai kabul sonucu henüz kaydedilmedi. | Eray'ın değerlendirmesini tarih ve kaynakla ekleyeceğim. |
| Review kapanışı | Sprint devam ediyor. | Abdülkadir ile son iş/puan durumunu, devreden işleri ve teslim kanıtlarını kapanışta kontrol edeceğim. |

Review hazırlığını ve kendi günlük kaydımı sürdürmemi engelleyen bir durum yok. Nihai sonucu yazabilmem için Esat'ın F-01 senaryosunu ve senaryo sonuçlarını, Kübra'nın son kontrolünü ve Eray'ın PO görüşünü takip ediyorum.

## Kapanış ekleri

4 Kasım için planlanan kapanışta Jira Sprint Report ve Burndown görüntülerini; GitHub Contributors görünümünü ilgili dal ve tarih kapsamıyla kaydedeceğim. Her görüntünün kontrol tarihini yazacağım. Nihai sonuç, PO görüşü, varsa devreden işler ve gerçekleştiğinde v0.2 sürüm bağlantısı eklenecek.

[Kriter kontrol listesi](kabul-kriteri-kontrolu.md) · [Teslim PR #25](https://github.com/DU-YBS471-KKY/kutuphane-kaynak-yonetimi/pull/25) · [Teslim PR #30](https://github.com/DU-YBS471-KKY/kutuphane-kaynak-yonetimi/pull/30)
