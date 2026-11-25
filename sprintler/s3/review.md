# Sprint 3 Review ara kaydım

Mert Seçkin — 25 Kasım 2026

| Sprint | Sprint 3 |
| :---- | :---- |
| **Planlanan tarih** | 18 Kasım \- 25 Kasım 2026 |
| **Jira’da girilen başlangıç** | 18 Kasım 2026 |
| **Product Owner** | Eray Yakup Dağdelen |
| **Scrum Master** | Esat Kor |
| **Hazırlayanlar** | Mert Seçkin ve Abdülkadir Güneş |
| **Değerlendirme tarihi** | Sprint kapanışında eklenecek |

## 3.1. Sprint Hedefinin Değerlendirilmesi

25 Kasım ara değerlendirmem: Jira’da Sprint 3 aktif; beş iş In Progress, tamamlanan Story 0/5 ve puan 0/18. Trello’da beş kart Test/QA’da. İlk teslimler develop’a birleşti. Kadir’in kural ve örnek veri düzeltmeleri PR \#52’de, US-14–15 için 21/21 uyumlu bağımsız kontrolü PR \#53’te; ikisi Kübra’nın incelemesini bekliyor. Kübra’nın PR \#51’i Kadir tarafından onaylandı, henüz birleşmedi. Yeni senaryolarla toplam 46 kontrol var; son üç senaryonun bağımsız kontrolü bekleniyor. Eray’ın beş Jira kartındaki 24 Kasım yorumlarını doğruladım. Nihai hedef sonucunu gerçek sprint kapanışında kaydedeceğim.

## 3.2. İşlerin Durumu ve Kapanış Kaydı

| Kod | Story | Sorumlu | SP | Jira durumu | Çıktı ve kontrol | PR |
| :---- | :---- | :---- | :---- | :---- | :---- | :---- |
| US-11 | Barkodla kitap ödünç verme | Kadir | 5 | In Progress | PR \#40 birleşti. 48 saat Rezerve kuralı ve ortak örnek veri PR \#52 ile işlendi, Kübra’nın kontrolü bekleniyor. | \#40, \#52 |
| US-12 | İade edilen kitabın stok onayı | Kadir | 3 | In Progress | PR \#40 birleşti. 48 saat Rezerve kuralı PR \#52 ile I05 ve KS-12-06’ya işlendi, Kübra’nın kontrolü bekleniyor. | \#40, \#52 |
| US-13 | Ödünç süresini 7 gün uzatma | Kadir | 3 | In Progress | PR \#40 birleşti. Ortak örnek veri PR \#52 ile US-15 L01’e eşitlendi, Kübra’nın kontrolü bekleniyor. | \#40, \#52 |
| US-14 | Ödünçteki kitabı sırayla rezerve etme | Kübra | 5 | In Progress | PR \#44 birleşti. Kadir’in bağımsız kontrolünde 13 senaryonun 13’ü uyumlu, kayıt PR \#53’te. | PR \#44, \#53 |
| US-15 | Geçmiş ve aktif ödünç listesini görme | Kübra | 2 | In Progress | PR \#44 birleşti. Kadir’in bağımsız kontrolünde 8 senaryonun 8’i uyumlu, kayıt PR \#53’te. | PR \#44, \#53 |

| Planlanan SP | 18 |
| :---- | :---- |
| **Tamamlanan SP** | Kapanışta hesaplanacak |
| **Tamamlanma oranı** | Kapanışta hesaplanacak |

## 3.3. İncelenen Çıktılar ve Demo Notları

25 Kasım’da birleşen teslimleri ve PR \#51–53’ü kontrol ettim. PR \#52, US-11 aktif ödünç sayısını 1 → 2/3; US-13 Kitap B tarihlerini 04.11.2026 / 19.11.2026 olarak eşitliyor ve US-11/12’ye 48 saat Rezerve kuralını ekliyor. Üç yeni senaryoyla Kadir’in kontrol sayısı 25, Kübra’nınki 21; toplam 46\. Kübra’nın 24 Kasım tarihli PR \#51 kaydı önceki 22 senaryoda 21 uyumlu ve bir düzeltme bulgusunu gösteriyor; güncel 25 senaryonun kontrolü ayrıca tamamlanacak. Kadir’in PR \#53 kaydında US-14 için 13/13, US-15 için 8/8 uyumlu sonuç ve dayanaklar var. Yeni bulgum: Rezerve kopya genel müsait stokta sayılmadığı hâlde US-11 O03 ve işlem akışı her ödünçte müsait sayıyı 1 azaltıyor. Azalma yalnızca Müsait → Ödünçte geçişine uygulanmalı; Rezerve → Ödünçte geçişinde sayı değişmemeli. Kadir düzeltir, Kübra kontrol eder. Eray’ın beş Jira kartındaki 24 Kasım “Her şey yolunda görünüyor” yorumlarını doğruladım; son düzeltmenin kabulü güncel çıktıyla eşleştirilecek. Bunlar belge ve ekran akışı kontrolleridir. Kendi PR \#49’um Eray’ın onayıyla 24 Kasım’da birleşmiş; bu PR için bekleyen incelemem yok.

## 3.4. Geri Bildirimler ve Takip

| Kimden | Geri bildirim | Yapılacak |
| :---- | :---- | :---- |
| Eray 19 Kasım | Beş PO kural kararı ve PR \#40 değişiklik isteği | 21 Kasım’da işlendi ve kontrol edildi; 48 saat kararı ayrı takipte. |
| Kadir 18 Kasım | US-13 rezervasyon kontrolü US-14’e; liste US-15’e bağlı. | Durum sütunu eşitlendi; ortak örnek veri tarihleri ve sayıları PR \#52’de düzeltildi, Kübra’nın kontrolü bekleniyor. |
| Kübra 20 Kasım | US-11–13 ön kontrolünde 9/9 kriter uyumlu; beş PO kararı ve ortak liste sütunları takipte. | Eski beş karar ve Durum sütunu karşılandı. 48 saat kuralı ve örnek veri PR \#52’de işlendi; Kübra güncel 25 senaryoyu kontrol edecek. Stok geçişi bulgusu da aynı incelemede kapanacak. |

## 3.5. Kalan İşler ve Kontroller

| İş | 25 Kasım ara durumu | Sonraki adım |
| :---- | :---- | :---- |
| US-11-13 | PR \#40 birleşti. 48 saat kuralı ve ortak örnek veri PR \#52’de düzeltildi. Rezerve kopya ödüncünde müsait stok sayısının değişmemesi açık bulgu olarak kaydedildi. | Kadir PR \#52’de stok geçişi ifadesini netleştirir; Kübra güncel 25 senaryoyu ve PR \#52’yi inceler. Onaylı değişiklik birleşince Eray güncel çıktının kabulünü teyit eder. |
| US-14-15 | PR \#44 birleşti. Kadir’in 21/21 uyumlu bağımsız kontrolü PR \#53’te; inceleme ve birleşme bekliyor. | Kübra PR \#53’teki kontrol kaydını inceler. Örnek öğrenci adlarının farklı numaralarla kullanılması Issue \#54’te izleniyor; kabul kaydı ve Jira/Trello kapanışı güncel sonuçla eşleştirilir. |
| Planning | PR \#42 Esat’ın onayından sonra 24 Kasım’da develop’a birleşti. | Planning için bekleyen birleştirme kalmadı; yeni kriz işi Sprint 4 planında takip edilecek. |
| Risk ve kriz kayıtları | Sekiz risk hazır. KKY-26 Sprint 4’e açıldı. Enes puanları gözden geçirdiğini Slack’te belirtti; takip gerekçesi henüz kaydedilmedi. | KKY-26’da atama ve tasarım sorumlusu Enes olarak eşitlendi. Esat önerilen 2 SP’yi girer; Enes Trello karşılığını ve risk takip gerekçesini tamamlar. S1/S2 teslim teyidi Eray ve Esat’tadır. |

## 3.6. Ekler

Sprint kapanışında Sprint 3’e ait Sprint Report ve Burndown görüntülerini ekleyeceğim. GitHub Contributors görüntüsünde dalı, tarih aralığını ve çekim tarihini belirteceğim. Kriz öncesi ve sonrası planı KKY-26 kaydıyla eşleştireceğim; paylaşım taslağı ile kontrol sonucu Sprint 4’te üretildiğinde uygulama kanıtına bağlanacak.  
[Sprint 3 Jira panosu](https://dagdelen41.atlassian.net/jira/software/c/projects/KKY/boards/2)  
[US-11-13 teslim ve kontrol PR \#40](https://github.com/DU-YBS471-KKY/kutuphane-kaynak-yonetimi/pull/40)  
[Sprint 3 Planning PR \#42](https://github.com/DU-YBS471-KKY/kutuphane-kaynak-yonetimi/pull/42)  
Ek 1 Jira Sprint 3 Report ekran görüntüsü \- kapanışta eklenecek  
Ek 2 Jira Sprint 3 Burndown ekran görüntüsü \- kapanışta eklenecek  
Ek 3 GitHub Contributors ekran görüntüsü \- kapanışta eklenecek  
Ek 4 Kriz öncesi ve sonrası plan ile uygulama kanıtları \- gerçekleştiğinde eklenecek

## Güncel inceleme kayıtları

- [PR #49 birleşen rapor güncellemem](https://github.com/DU-YBS471-KKY/kutuphane-kaynak-yonetimi/pull/49)
- [PR #51 Kübra’nın kontrol ve bireysel yanıt kaydı](https://github.com/DU-YBS471-KKY/kutuphane-kaynak-yonetimi/pull/51)
- [PR #52 Kadir’in kural ve örnek veri düzeltmesi](https://github.com/DU-YBS471-KKY/kutuphane-kaynak-yonetimi/pull/52)
- [PR #53 Kadir’in bağımsız kontrol ve bireysel yanıt kaydı](https://github.com/DU-YBS471-KKY/kutuphane-kaynak-yonetimi/pull/53)
