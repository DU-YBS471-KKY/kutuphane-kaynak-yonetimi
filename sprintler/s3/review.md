# Sprint 3 Review ara kaydım

Mert Seçkin — 22 Kasım 2026  
Sprint 3: 18–25 Kasım 2026

Sprint aktif. Jira'da beş Story'nin tamamı In Progress; tamamlanan iş 0/5, tamamlanan puan 0/18. Trello'da beş kart Test/QA'da. Tasarım ve kontrol dosyaları hazır; ortak düzeltmeler, bağımsız onay ve PO kabulü bekleniyor. Nihai hedef gerçekleşmesini kapanışta kaydedeceğim.

## Teslimler ve açık kontroller

| İş | Sorumlu | Jira | İncelediğim çıktı | Kalan adım |
| --- | --- | --- | --- | --- |
| US-11 / KKY-10 / 5 SP | Kadir | In Progress | PR #40 | Rezerve kopyanın yalnızca ayrıldığı öğrenciye verilmesi; örnek aktif ödünç sayısı 1 → 2/3. |
| US-12 / KKY-11 / 3 SP | Kadir | In Progress | PR #40 | Aktif rezervasyonu olan sağlam iadede Rezerve durumu ve ilgili senaryolar. |
| US-13 / KKY-12 / 3 SP | Kadir | In Progress | PR #40 | Kitap B tarihlerinin US-15 ile 04.11.2026 / 19.11.2026 olarak eşitlenmesi. |
| US-14 / KKY-21 / 5 SP | Kübra | In Progress | PR #44 | Yeni rezervasyon kuralları işlendi; Kadir yeniden inceleyecek. |
| US-15 / KKY-22 / 2 SP | Kübra | In Progress | PR #44 | Ortak örnek veri ve geçmiş liste kuralları güncellendi; Kadir yeniden inceleyecek. |

Kadir'in dosyalarında 22, Kübra'nın dosyalarında 21 kontrol senaryosu var. Bunlar belge ve ekran akışı kontrolleridir; çalışan uygulama testi yürütülmedi. Sonuç sütunları henüz bağımsız kontrol sonucu olarak kapatılmadı.

Eray'ın 19 Kasım'daki beş kararı ve Durum sütunu Kadir tarafından işlenmiş; Kübra bunları karşılanmış olarak kaydetmiş. Eray'ın 21 Kasım'daki 48 saat rezervasyon kararı Kübra'nın dosyalarında var, Kadir'in US-11/12 güncellemesi bekleniyor. Kübra bu güncelleme ve örnek veri eşitlemesinden sonra #40'ı onaylayacağını yazmış. #44 için Kadir'in önceki incelemesi yorum niteliğinde; güncel sürüme nihai onay henüz yok. Eray'ın nihai PO kabulü de bekleniyor.

## Kendi tamamladıklarım

- Sprint 2 kapanış PR #41'imi, Kadir'in 21 Kasım onayından sonra 22 Kasım'da merge commit ile develop'a birleştirdim. Birleşme: `c67035ea257faab67e31a46987a0bf2d7215f994`.
- Ortak S3 raporunda Review'u ve kendi 21–22 Kasım günlüklerimi güncelledim. Diğer üyelerin günlüklerini korudum.
- Enes'in altı riskini koruyarak kategori alanlarını risk türüyle düzelttim; önem derecelerini skor alanına aldım. R02'nin önlemini, yapılan işe uygun olarak Azaltma şeklinde yazdım.
- R07 kararın ve uygulama kaydının doğrulanması, R08 önceki raporların teslim teyidi risklerini ekledim. Yeni olasılık ve etki puanları benim değerlendirmem; ekip takipte gözden geçirecek. Ortak defter artık sekiz kayıt içeriyor.
- 9. hafta 19. sayfadaki Kriz Simülasyonu #1 için kaynak, etki, seçenekler ve önerimi rapora yazdım. Ekip kararı ve gerçekleşen uygulama açık bırakıldı. Sınıftaki kurgusal talebi, ekipçe kabul edilip uygulanmış değişiklik olarak göstermedim.

## Sonraki takip

Kadir iki ortak düzeltmeyi tamamlar; Kübra tekrar kontrol eder; Eray nihai kabulü verir. Kadir güncel #44'ü de inceler. Esat'ın #42 Planning ve kendi #43 rapor incelemesi bekleniyor. Risk defterinin düzenli takibi Enes'te kalıyor; Eray ve Esat kriz senaryosuna verilecek ekip kararını ve S1/S2 teslim teyidini netleştirecek.

Sprint kapanışında Kadir'le Review'u tamamlayacağım. S3 Sprint Report, Burndown ve dal/tarih aralığı belirtilmiş Contributors görsellerini kapanış verileriyle alacağım. Retrospektif Kübra ve Enes'te.

## Kaynaklar

- [Jira panosu](https://dagdelen41.atlassian.net/jira/software/c/projects/KKY/boards/2)
- [Trello panosu](https://trello.com/b/BYmjSKQd/kutuphane-kaynak-yonetim-sistemi)
- [Kadir PR #40](https://github.com/DU-YBS471-KKY/kutuphane-kaynak-yonetimi/pull/40)
- [Birleşen PR #41](https://github.com/DU-YBS471-KKY/kutuphane-kaynak-yonetimi/pull/41)
- [Planning PR #42](https://github.com/DU-YBS471-KKY/kutuphane-kaynak-yonetimi/pull/42)
- [Rapor PR #43](https://github.com/DU-YBS471-KKY/kutuphane-kaynak-yonetimi/pull/43)
- [Kübra PR #44](https://github.com/DU-YBS471-KKY/kutuphane-kaynak-yonetimi/pull/44)
- [9. hafta sunumu](https://trello.com/c/dTBogw9W), sayfa 19–20
