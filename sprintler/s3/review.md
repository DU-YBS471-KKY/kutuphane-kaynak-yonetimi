# Sprint 3 Review ara kaydım

Mert Seçkin — 25 Kasım 2026 akşam

| Sprint | Sprint 3 |
| :---- | :---- |
| **Planlanan tarih** | 18 Kasım - 25 Kasım 2026 |
| **Jira’da girilen başlangıç** | 18 Kasım 2026 |
| **Product Owner** | Eray Yakup Dağdelen |
| **Scrum Master** | Esat Kor |
| **Hazırlayanlar** | Mert Seçkin ve Abdülkadir Güneş |
| **Değerlendirme tarihi** | Sprint kapanışında eklenecek |

## 3.1. Sprint Hedefinin Değerlendirilmesi

25 Kasım akşam değerlendirmem: Sprint 3 Jira’da aktif; beş iş In Progress, tamamlanan Story 0/5 ve puan 0/18. Trello’da beş kart Test/QA’da. PR #51, #52, #53, #56 ve #57 develop’a birleşti. Kübra’nın US-11–13 için 24/25, Kadir’in US-14–15 için 21/21 uyumlu kontrolü kaydedilmiş; toplam 45/46. Açık konu, US-11’de Rezerve → Ödünçte geçişinde müsait sayının değişmemesi. Düzeltme ve yeniden kontrolden sonra Eray’ın kabulü ile Esat’ın kapanışını takip edeceğim. Nihai hedef sonucunu gerçek kapanış verileriyle yazacağım.

## 3.2. İşlerin Durumu ve Kapanış Kaydı

| Kod | Story | Sorumlu | SP | Jira durumu | Çıktı ve kontrol | PR |
| :---- | :---- | :---- | :---- | :---- | :---- | :---- |
| US-11 | Barkodla kitap ödünç verme | Kadir | 5 | In Progress | PR #40 ve #52 birleşti. Kübra’nın kontrolünde US-11 stok geçişi açık: Rezerve → Ödünçte işleminde müsait sayı değişmemeli. O03, işlem akışı ve KS-11-11 için yeni düzeltme gerekiyor. | #40, #52 |
| US-12 | İade edilen kitabın stok onayı | Kadir | 3 | In Progress | PR #40 ve #52 birleşti. I05 ve KS-12-06’daki 48 saat Rezerve kuralı Kübra’nın 25 Kasım kontrolünde uyumlu. Son PO kabulü ve pano kapanışı takipte. | #40, #52 |
| US-13 | Ödünç süresini 7 gün uzatma | Kadir | 3 | In Progress | PR #40 ve #52 birleşti. Kitap B tarihleri US-15 ile eşitlendi; Kübra’nın 25 Kasım kontrolünde ortak örnek veri uyumlu. Son PO kabulü ve pano kapanışı takipte. | #40, #52 |
| US-14 | Ödünçteki kitabı sırayla rezerve etme | Kübra | 5 | In Progress | PR #44, #53 ve #57 birleşti. Kadir’in kontrolünde 13/13 uyumlu; sonuçlar ve örnek öğrenci adı düzeltmesi dosyalara işlendi. PO kabulü ve pano kapanışı takipte. | PR #44, #53 |
| US-15 | Geçmiş ve aktif ödünç listesini görme | Kübra | 2 | In Progress | PR #44, #53 ve #57 birleşti. Kadir’in kontrolünde 8/8 uyumlu; sonuçlar ve öğrenci numarasıyla gösterim dosyalara işlendi. PO kabulü ve pano kapanışı takipte. | PR #44, #53 |

| Planlanan SP | 18 |
| :---- | :---- |
| **Tamamlanan SP** | Kapanışta hesaplanacak |
| **Tamamlanma oranı** | Kapanışta hesaplanacak |

## 3.3. İncelenen Çıktılar ve Demo Notları

25 Kasım akşamı PR #51–53, #56 ve #57’nin birleştiğini doğruladım. Kübra’nın güncel kontrol kaydı US-11–13’te 25 senaryodan 24’ünü uyumlu gösteriyor; açık KS-11-11 stok konusu. Kadir’in bağımsız kontrolü US-14’te 13/13, US-15’te 8/8 uyumlu; sonuçlar PR #57 ile ilgili dosyalara işlenmiş. Böylece toplam 46 senaryodan 45’i uyumlu. 48 saat Rezerve kuralı ve ortak örnek veri düzeltilmiş; Issue #50 ve #54 kapanmış. US-11 O03 ve işlem akışındaki her ödünçte müsait sayıyı 1 azaltan ifade ise develop’da hâlâ var. Yalnızca Müsait → Ödünçte geçişinde sayı azalmalı; Rezerve → Ödünçte geçişinde değişmemeli. PR #52 birleştiği için Kadir yeni düzeltme PR’ı açacak, Kübra yeniden kontrol edecek. Eray’ın 24 Kasım Jira yorumları mevcut; son düzeltmenin kabulü güncel çıktı ve kontrol sonucuna bağlanacak. Bunlar belge ve ekran akışı kontrolleridir. PR #56’m Eray’ın onayıyla birleşti; bu PR için bekleyen incelemem yok.

## 3.4. Geri Bildirimler ve Takip

| Kimden | Geri bildirim | Yapılacak |
| :---- | :---- | :---- |
| Eray 19 Kasım | Beş PO kural kararı ve PR #40 değişiklik isteği | 21 Kasım’da işlendi ve kontrol edildi; 48 saat kararı ayrı takipte. |
| Kadir 18 Kasım | US-13 rezervasyon kontrolü US-14’e; liste US-15’e bağlı. | Durum sütunu ve ortak örnek veri eşitlendi. PR #52 birleşti; Kübra’nın 25 Kasım kontrolünde örnek veri uyumlu. Açık stok geçişi ayrı düzeltmeyle takip ediliyor. |
| Kübra 20 Kasım | US-11–13 ön kontrolünde 9/9 kriter uyumlu; beş PO kararı ve ortak liste sütunları takipte. | Eski beş karar, Durum sütunu, 48 saat kuralı ve örnek veri kontrol edildi. Kübra’nın güncel sonucu 24/25 uyumlu; KS-11-11 stok bulgusu yeni düzeltme ve yeniden kontrol bekliyor. |
| Kübra 25 Kasım | PR #52'de 25 senaryonun 24'ü uyumlu. Stok notu: Rezerve kopya ödünç verilince müsait sayı değişmemeli; US-11 O03 ve işlem sırasında her ödünçte 1 azalıyor yazıyor. | PR #52 birleşti. Kadir yeni PR’da O03, işlem akışı ve KS-11-11’i düzeltir; Kübra düzeltmeyi yeniden kontrol edip sonucu kaydeder. |

## 3.5. Kalan İşler ve Kontroller

| İş | 25 Kasım ara durumu | Sonraki adım |
| :---- | :---- | :---- |
| US-11-13 | PR #52 ve Kübra’nın PR #51 kontrol kaydı birleşti. 25 senaryonun 24’ü uyumlu; Rezerve kopyanın ödüncünde müsait sayının değişmemesi açık bulgu. | Kadir yeni düzeltme PR’ı açar; Kübra KS-11-11 stok kontrolünü ve ilgili akışı yeniden inceler. Onaylı düzeltmeden sonra Eray güncel çıktının kabulünü teyit eder. |
| US-14-15 | PR #53 ve #57 birleşti. 21/21 uyumlu bağımsız kontrol sonucu dosyalara işlendi; öğrenci adı çakışması düzeltildi ve Issue #54 kapandı. | Eray güncel çıktı ve kontrol kaydıyla kabulü teyit eder; Esat kabul edilen işleri Jira ve Trello’da eşitler. |
| Planning | PR #42 Esat’ın onayından sonra 24 Kasım’da develop’a birleşti. | Planning için bekleyen birleştirme kalmadı; yeni kriz işi Sprint 4 planında takip edilecek. |
| Risk ve kriz kayıtları | Sekiz risk hazır. KKY-26 Sprint 4’te Story türünde, Enes’e atanmış ve 2 SP; Trello kartı açılmış. Sprint 4 toplamı 6 iş / 21 SP. | Paylaşım taslağı Enes, bağımsız kontrol Kübra, PO kabulü Eray tarafından Sprint 4’te yapılacak. Enes ile Esat, backlog’daki KKY-30 kopyasının gerekçesini netleştirir. S1/S2 teslim teyidi Eray ve Esat’tadır. |

## 3.6. Ekler

Sprint kapanışında Sprint 3’e ait Sprint Report ve Burndown görüntülerini ekleyeceğim. GitHub Contributors görüntüsünde dalı, tarih aralığını ve çekim tarihini belirteceğim. Kriz öncesi ve sonrası planı KKY-26 kaydıyla eşleştireceğim; paylaşım taslağı ile kontrol sonucu Sprint 4’te üretildiğinde uygulama kanıtına bağlanacak.  
[Sprint 3 Jira panosu](https://dagdelen41.atlassian.net/jira/software/c/projects/KKY/boards/2)  
[US-11-13 teslim ve kontrol PR #40](https://github.com/DU-YBS471-KKY/kutuphane-kaynak-yonetimi/pull/40)  
[Sprint 3 Planning PR #42](https://github.com/DU-YBS471-KKY/kutuphane-kaynak-yonetimi/pull/42)  
Ek 1 Jira Sprint 3 Report ekran görüntüsü - kapanışta eklenecek  
Ek 2 Jira Sprint 3 Burndown ekran görüntüsü - kapanışta eklenecek  
Ek 3 GitHub Contributors ekran görüntüsü - kapanışta eklenecek  
Ek 4 Kriz öncesi ve sonrası plan ile uygulama kanıtları - gerçekleştiğinde eklenecek  

## Güncel inceleme kayıtları

- [Kübra’nın US-11–13 kontrol kaydı PR #51](https://github.com/DU-YBS471-KKY/kutuphane-kaynak-yonetimi/pull/51)
- [Kadir’in kural ve örnek veri düzeltmesi PR #52](https://github.com/DU-YBS471-KKY/kutuphane-kaynak-yonetimi/pull/52)
- [Kadir’in US-14–15 kontrol kaydı PR #53](https://github.com/DU-YBS471-KKY/kutuphane-kaynak-yonetimi/pull/53)
- [Birleşen Review güncellemem PR #56](https://github.com/DU-YBS471-KKY/kutuphane-kaynak-yonetimi/pull/56)
- [US-14–15 sonuç ve örnek veri güncellemesi PR #57](https://github.com/DU-YBS471-KKY/kutuphane-kaynak-yonetimi/pull/57)
