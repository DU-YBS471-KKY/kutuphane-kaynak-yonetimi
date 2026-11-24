# Sprint 3 Review ara kaydım

Mert Seçkin — 24 Kasım 2026  
Sprint 3: 18–25 Kasım 2026

Sprint aktif. Jira'da beş Story In Progress; tamamlanan iş 0/5, tamamlanan puan 0/18. Trello'da beş kart Test/QA'da. Teslim PR'ları develop'a birleşti. Kalan düzeltmeleri ve kontrol kayıtlarını aşağıda takip ediyorum; nihai sonucu sprint kapanışında yazacağım.

## Birleşen teslimler ve kalan kontroller

| İş | Sorumlu | Birleşen teslim | Kalan adım |
| --- | --- | --- | --- |
| US-11 / KKY-10 / 5 SP | Kadir | PR #40 | Rezerve kopyanın yalnızca sıradaki öğrenciye verilmesi; örnek aktif ödünç sayısının 1 → 2/3 olarak eşitlenmesi. |
| US-12 / KKY-11 / 3 SP | Kadir | PR #40 | Aktif rezervasyonlu sağlam iadede Rezerve durumu, bildirimden itibaren 48 saat ve ilgili senaryolar. |
| US-13 / KKY-12 / 3 SP | Kadir | PR #40 | Kitap B tarihlerinin US-15 ile 04.11.2026 / 19.11.2026 olarak eşitlenmesi. |
| US-14 / KKY-21 / 5 SP | Kübra | PR #44 | Kadir'in güncel belgeyi kontrol edip gözlenen sonuçları kaydetmesi. |
| US-15 / KKY-22 / 2 SP | Kübra | PR #44 | Kadir'in ortak veri ve liste akışını kontrol edip sonucu kaydetmesi. |

Kadir'in 22, Kübra'nın 21 kontrol senaryosunun Sonuç alanı hâlâ Bekliyor. Bunlar belge ve ekran akışı kontrolleridir. Yapılan kontrollerde bakılan bölüm ve gözlenen bulgu kaydedilmeli.

Eray, PR #40 ve #44'ü 24 Kasım'da güncel sürümleriyle onayladı; ikisi de develop'a birleşti. PR #40'ın birleşen sürümü `94a8cc25529aa3fbbf701be46ea845279b6f68f0`, PR #44'ünki `c99f595d692b64d90192b86b8aa397fb76a66d0a`. Birleşmeden sonra develop dosyalarını kontrol ettim: yukarıdaki iki ortak düzeltme #40 içinde hâlâ eksik. Kadir yeni düzeltme PR'ı açacak; Kübra kontrol edecek ve Eray düzeltilen sürümün kabulünü teyit edecek.

Eray Slack'te beş Jira kartına PO kabul yorumu eklediğini belirtti. 24 Kasım kontrolümde KKY-10, KKY-11, KKY-12, KKY-21 ve KKY-22'nin yorumlarında bu yeni kayıtları göremedim. GitHub onayları mevcut; Jira kabul kaydı ayrıca teyit edilecek. Pano durumlarını bu nedenle tamamlanmış olarak yazmadım.

## Kriz değişikliği ve risk takibi

Eray'ın PR #42'deki yazılı PO kararıyla paylaşım, kitap detayında yalnızca kitap adı ve yazar bilgisiyle ve kullanıcı onayıyla sınırlandırıldı. Hesap bağlama ve kişisel veri aktarımı kapsam dışında.

24 Kasım'da KKY-26 / US-21, üç kabul kriteriyle Sprint 4'e eklendi. Tarihleri 25 Kasım–2 Aralık. Kart Enes'e atanmış; açıklamadaki tasarım sorumlusu Kadir, bağımsız kontrol Kübra, PO kabulü Eray. Atama ile açıklama Eray tarafından eşitlenecek. Önerilen efor 2 SP, fakat Jira puan alanı boş. Sprint 4 şu an altı iş / 19 SP gösteriyor; puan girilince plan 21 SP olacak. Esat alan girişini takip edecek. Trello'da yeni işin karşılığı henüz yok.

Ortak defterde sekiz risk var. Enes 24 Kasım'da Slack'te R07–R08 puanlarını gözden geçirdiğini yazdı. Gerekçe ve Esat'ın teyidi risk takip kaydına eklenecek. S1/S2 teslim teyidi Eray ve Esat'ta; hocanın Trello kartı hâlâ Bekleniyor gösteriyor. Bu gösterge tek başına teslim edilmediğini kanıtlamıyor.

## Kendi tamamladıklarım

- PR #46'mın Eray'ın onayıyla 24 Kasım'da develop'a birleştiğini doğruladım. Bu PR için bekleyen incelemem kalmadı.
- Ortak S3 raporundaki Review'u, kalan işleri, risk takibini ve kriz planını güncelledim. Yalnızca kendi 24 Kasım Daily satırımı doldurdum; diğer üyelerin günlüklerini korudum.
- Birleşen Planning #42, Esat'ın bireysel yanıtı #45 ve Enes'in bireysel yanıtı #47'yi teslim takibine ekledim. Enes'in #48'i birleştirilmeden kapanmış; geçerli yanıt #47'de.
- Kadir ile Kübra'nın bireysel kriz yanıt bağlantıları ortak raporda henüz boş. Hazırladılarsa mevcut dosyalarını bağlamaları gerekiyor.

## Kapanış için takip

Kadir'in düzeltmesi, karşılıklı kontrol sonuçları ve Eray'ın düzeltilen sürüme kabul teyidinden sonra Jira/Trello durumları eşitlenecek. Esat Sprint 3'ü gerçek kapanış sonucu ile kapatacak. Ardından tamamlanan puanı ve hedef değerlendirmesini Review'a işleyeceğim.

Sprint 3 Sprint Report ve Burndown görüntülerini kapanıştan sonra; Contributors görüntüsünü dal, tarih aralığı ve çekim tarihini belirterek alacağım. Kriz öncesi/sonrası planı KKY-26 ile eşleştireceğim; paylaşım taslağı ve kontrolü Sprint 4'te üretildiğinde uygulama kanıtına bağlanacak. Kübra ile Enes, toplanan görüşleri retrospektife işleyecek.

## Kaynaklar

- [Jira panosu](https://dagdelen41.atlassian.net/jira/software/c/projects/KKY/boards/2)
- [Trello panosu](https://trello.com/b/BYmjSKQd/kutuphane-kaynak-yonetim-sistemi)
- [Kadir'in teslimi PR #40](https://github.com/DU-YBS471-KKY/kutuphane-kaynak-yonetimi/pull/40)
- [Kübra'nın teslimi PR #44](https://github.com/DU-YBS471-KKY/kutuphane-kaynak-yonetimi/pull/44)
- [Birleşen rapor PR #46](https://github.com/DU-YBS471-KKY/kutuphane-kaynak-yonetimi/pull/46)
- [Enes'in bireysel yanıtı PR #47](https://github.com/DU-YBS471-KKY/kutuphane-kaynak-yonetimi/pull/47)
- [Kriz işi KKY-26](https://dagdelen41.atlassian.net/browse/KKY-26)
- [9. hafta sunumu](https://trello.com/c/dTBogw9W), sayfa 19–20
