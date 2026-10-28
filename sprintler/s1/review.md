# Sprint 1 Review Raporu

**Hazırlayan:** Mert Seçkin  
**Kontrol tarihi:** 28 Ekim 2026, sprint kapanmadan önce  
**Planlanan tarih:** 21–28 Ekim 2026  
**Gerçek başlangıç:** 23 Ekim 2026  
**Gerçek bitiş:** Sprint Jira’da hâlâ açık  
**PO:** Eray Yakup Dağdelen | **SM:** Esat Kor

## 1. Sprint hedefi ve mevcut sonuç

Öğrenci kaydı, giriş ve şifre sıfırlama, profil güncelleme, personel yetkilendirme ve kitap arama için gereksinimleri, ekran taslaklarını ve kontrol senaryolarını inceledim. Jira’da ilk dört iş Done, kitap arama In Progress durumunda. Mevcut sonuç 4/5 iş ve 12/15 SP (%80). Bu değer kapanış öncesindeki Jira durumudur; nihai sprint sonucu henüz oluşmadı.

## 2. İşler ve çıktı bağlantıları

| İş | Sorumlu | SP | Jira durumu | İncelediğim çıktı |
|---|---|---:|---|---|
| [US-01 / KKY-3](https://dagdelen41.atlassian.net/browse/KKY-3) Öğrenci kaydı | Eray | 3 | Done | Kayıt, e-posta aktivasyonu ve kısa şifre kontrolü; [PR #7](https://github.com/DU-YBS471-KKY/kutuphane-kaynak-yonetimi/pull/7), [#12](https://github.com/DU-YBS471-KKY/kutuphane-kaynak-yonetimi/pull/12), [#13](https://github.com/DU-YBS471-KKY/kutuphane-kaynak-yonetimi/pull/13) birleşti. |
| [US-02 / KKY-4](https://dagdelen41.atlassian.net/browse/KKY-4) Giriş ve şifre sıfırlama | Eray | 2 | Done | Giriş, sıfırlama ve üç hatalı girişte kilit senaryoları ortak depoda; kriter atıflarında düzeltme gerekiyor. |
| [US-03 / KKY-5](https://dagdelen41.atlassian.net/browse/KKY-5) Profil güncelleme | Eray | 2 | Done | Bildirim tercihi kriteri ve senaryosu eklendi; ekran kutusu [PR #16](https://github.com/DU-YBS471-KKY/kutuphane-kaynak-yonetimi/pull/16) ile birleşti. |
| [US-04 / KKY-6](https://dagdelen41.atlassian.net/browse/KKY-6) Personel yetkilendirme | Eray | 5 | Done | Yetki verme, geri alma ve yetkisiz erişim kuralları, ekranı ve senaryoları ortak depoda. |
| [US-05 / KKY-15](https://dagdelen41.atlassian.net/browse/KKY-15) Kitap arama | Esat | 3 | In Progress | Kategori filtresi, sonuç alanları ve dört senaryo [PR #15](https://github.com/DU-YBS471-KKY/kutuphane-kaynak-yonetimi/pull/15) ile birleşti. Sonuç bulunamama senaryosu sonradan dala eklendi; henüz yeni PR’a alınmadı. |

US-01–04 dosyalarının güncel sürümü: [gereksinimler](https://github.com/DU-YBS471-KKY/kutuphane-kaynak-yonetimi/blob/dd6b86035a3986a986ad6bcaf3e572f8dc341408/docs/gereksinimler/eray-us-01-04-hazirlik.md), [ekran taslakları](https://github.com/DU-YBS471-KKY/kutuphane-kaynak-yonetimi/blob/dd6b86035a3986a986ad6bcaf3e572f8dc341408/tasarim/us-01-04-kullanici-yonetimi-ekran-taslaklari.md), [kontrol senaryoları](https://github.com/DU-YBS471-KKY/kutuphane-kaynak-yonetimi/blob/dd6b86035a3986a986ad6bcaf3e572f8dc341408/test/us-01-04-kontrol-senaryolari.md).

US-05: [gereksinimler](https://github.com/DU-YBS471-KKY/kutuphane-kaynak-yonetimi/blob/dd6b86035a3986a986ad6bcaf3e572f8dc341408/docs/gereksinimler/esat-us-05-07-hazirlik.md), [ekran](https://github.com/DU-YBS471-KKY/kutuphane-kaynak-yonetimi/blob/dd6b86035a3986a986ad6bcaf3e572f8dc341408/tasarim/us-05-kitap-arama-ekran-taslaklari.md), [birleşen senaryolar](https://github.com/DU-YBS471-KKY/kutuphane-kaynak-yonetimi/blob/dd6b86035a3986a986ad6bcaf3e572f8dc341408/test/us-05-kontrol-senaryolari.md), [dalda bekleyen ek senaryo](https://github.com/DU-YBS471-KKY/kutuphane-kaynak-yonetimi/blob/c50176fe713619d3a7176f37708b2db7b2239473/test/us-05-kontrol-senaryolari.md).

## 3. İnceleme ve demo notları

Kontrolümü gereksinimler, metin tabanlı ekran taslakları, senaryo tabloları ve PR geçmişi üzerinden yaptım. Çalışan bir uygulamada test yürütmedim. Kayıt ve aktivasyon, hatalı giriş, profil bildirimi ve yetkilendirme akışlarının belgelerini karşılaştırdım. Kitap arama ekranında yazar/başlık/ISBN alanı, kategori filtresi ve sonuç sütunları bulunuyor. Test dosyalarında yazan “Geçti” sonuçları dosya sahiplerinin belge kontrolü kayıtlarıdır.

PR #13 ve #16 Esat’ın, PR #15 Eray’ın onayıyla birleşmiş. Planning PR #6 da 27 Ekim’de birleşti. Trello’da dört iş Tamamlandı, kitap arama Geliştirmede; Jira ile durumlar eşleşiyor. Review toplantısına ilişkin katılımcı veya yeni ekip geri bildirimi kaydı henüz yok.

## 4. Geri bildirimler ve takip

| Kaynak | Geri bildirim ve sonuç |
|---|---|
| Abdülkadir, PR #8, 25 Ekim | İş tablosunu ve puanları uyumlu buldu; gerçek başlangıç ve US-05 Epic bilgisinin güncellenmesini istedi. Başlangıcı 23 Ekim olarak işledim; US-05 Kaynak ve Kitap Envanteri altında. |
| Mert, 28 Ekim kontrolü | Aktivasyon ve bildirim eksikleri giderilmiş. US-02’de şifre sıfırlama senaryosunun kriter atfı, US-05’te kriter eşleştirmesi ve son senaryonun ortak depoya alınması açık. |

## 5. Kalan işler

- **Eray:** US-02 kriterlerini sıralayıp KS-02-03 şifre sıfırlama atfını doğru kritere bağlayacak.
- **Esat:** US-05’te yazar/ISBN aramasını kriter 1’e, sonuç alanlarını kriter 3’e, sonuç bulunamamasını kriter 4’e bağlayacak. Dalındaki son senaryoyu yeni PR ile incelemeye sunacak; inceleme ve düzeltmelerden sonra Jira durumunu güncelleyecek.
- **Mert:** Bu Review güncellemesini bağımsız incelemeye sunacağım. PO’nun kabul görüşünü ve gerçek ekip geri bildirimlerini geldiğinde ekleyeceğim. Abdülkadir’in önceki incelemesi yukarıda korunuyor; bugünkü kontrolü ben yaptım.
- **Sprint kapanışı:** Esat kapattığında gerçek bitişi, son puanı ve Jira Sprint Report/Burndown bağlantılarını ekleyeceğim. US-05 yetişmezse PO/SM’nin sonraki sprint planına aldığı karar rapora işlenecek; bugün tamamlanan puana eklenmeyecek.

## 6. Kapanış ekleri

Sprint Report ve Burndown görselleri sprint kapandıktan sonra eklenecek. Ortak rapordaki GitHub Contributors eki de aynı aşamada hazırlanacak. Bu kontrolde nihai grafik veya toplantı katılımı kaydı oluşturmadım.

[Jira panosu](https://dagdelen41.atlassian.net/jira/software/c/projects/KKY/boards/2) · [Jira raporları](https://dagdelen41.atlassian.net/jira/software/c/projects/KKY/boards/2/reports) · [Ortak Sprint 1 raporu](https://docs.google.com/document/d/1IX7KqhIBBCtKO-QIxZ8Pj1QFw0yYov0M2tPioCW0bQs/edit)
