# Sprint 1 — Review hazırlığı ve ön inceleme

Hazırlayan: Mert Seçkin  
Kontrol tarihi: 23 Ekim 2026  
Ortak değerlendirme: Abdülkadir Güneş’in kontrolü bekleniyor  
Planlanan sprint: 21–28 Ekim 2026  
Gerçek başlangıç ve bitiş: Jira’da henüz girilmemiş  
Sprint sonu Review tarihi: Henüz gerçekleşmedi

Bu notu, Sprint 1 sonunda Kadir’le hazırlayacağımız Review raporuna başlangıç olarak yazdım. Aşağıdaki durumlar 23 Ekim’deki kontrolümü gösteriyor. Sprint sonundaki teslimleri, ekip görüşlerini ve kabul kararlarını gerçekleştiğinde bu dosyaya ekleyeceğim.

## 1. Sprintin hedefi ve kapsamı

Öğrenci kaydı, giriş ve şifre sıfırlama, profil güncelleme, personel yetkilendirme ve kitap arama için iş kurallarını, ekran taslaklarını ve kontrol senaryolarını hazırlamak hedefleniyor. Jira’da doğru beş iş ve toplam 15 Story Point seçilmiş.

| İş | Sorumlu | SP | Jira durumu | 23 Ekim’de gördüğüm çıktı |
|---|---|---:|---|---|
| [US-01 / KKY-3](https://dagdelen41.atlassian.net/browse/KKY-3): öğrenci kaydı | Eray | 3 | Yapılacaklar | İş kuralı, ekran taslağı ve senaryolar PR #7’de; onay bekliyor. |
| [US-02 / KKY-4](https://dagdelen41.atlassian.net/browse/KKY-4): giriş ve şifre sıfırlama | Eray | 2 | Yapılacaklar | Aynı PR’da; onay bekliyor. |
| [US-03 / KKY-5](https://dagdelen41.atlassian.net/browse/KKY-5): profil güncelleme | Eray | 2 | Yapılacaklar | Aynı PR’da; onay bekliyor. |
| [US-04 / KKY-6](https://dagdelen41.atlassian.net/browse/KKY-6): personel yetkilendirme | Eray | 5 | Yapılacaklar | Aynı PR’da; onay bekliyor. |
| [US-05 / KKY-15](https://dagdelen41.atlassian.net/browse/KKY-15): kitap arama | Esat | 3 | Yapılacaklar | Bu iş için açık PR veya develop dalında teslim dosyası görmedim. |

Kontrol sırasında sprint henüz başlatılmamıştı. Jira’da tamamlanan iş 0/5, tamamlanan puan 0/15 görünüyor. Sprint sonu tamamlanma oranını ve Velocity sonucunu kapanışta yeniden kontrol edeceğim.

## 2. İncelediğim belgeler ve açık noktalar

- [PR #6 — Planning](https://github.com/DU-YBS471-KKY/kutuphane-kaynak-yonetimi/pull/6): Hedef, beş Story, 15 puan ve ekip görevleri var. Esat’ın incelemesi bekleniyor. Belgede 21–28 Ekim ekip planı yazıyor; bu aralık hocanın verdiği kesin teslim tarihi değil. Gerçek başlangıç ve bitiş ayrıca kaydedilmeli.
- [PR #7 — Eray’ın US-01–04 çıktıları](https://github.com/DU-YBS471-KKY/kutuphane-kaynak-yonetimi/pull/7): Dört ayrı iş kuralı belgesi, ortak ekran taslağı ve dokuz kontrol senaryosu var. Esat henüz inceleme göndermemiş; PR birleşmemiş.
- Eray’ın US-01 işinin Jira başlığı hâlâ “kullanıcı girişi” diyor; açıklama ve belge öğrenci kaydını anlatıyor. Eray, kendi işinin Jira, Planning ve iş kuralı başlıklarını öğrenci kaydı olarak eşleştirmeli.
- US-05 Esat’ın işi. Planning’de katalog Epic’i altında; Jira’da üyelik Epic’ine bağlı. Esat, Jira’daki üst öğeyi Kaynak ve Kitap Envanteri olarak düzeltmeli; bu Eray’ın kişisel Story görevi değil.
- Test tablosunda dokuz senaryo “Geçti” olarak işaretli ve başlıkta ekran taslakları ile iş kuralları üzerinden doğrulandığı açıkça yazıyor. Kodlama zorunlu olmadığı için bu kontrol yöntemi proje kapsamına uygun. Gözlenen bulgu ve kontrol eden kişi bilgisini eklemek benim izlenebilirlik önerim; hocanın yönergesinde zorunlu bir sütun şartı değil. Bu ayrıntıların yokluğunu tek başına hatalı test sonucu veya kabul engeli saymıyorum.
- Eray’ın dört Jira kaydında PR #7 ve çıktı bağlantılarını göremedim. Onay ve birleştirme sonrasında bu bağlantılar da eklenmeli.

## 3. Kabul durumu

Bu ön incelemede hiçbir Story için nihai kabul vermedim. Kabul için README’deki üç koşulu her işte kontrol edeceğim: çıktı kabul kriterlerini karşılıyor mu; başka bir üye inceleyip kritik eksikleri gidermiş mi; dosya ve inceleme bağlantıları Jira’da var mı? Bir gereksinim belgesinin birleşmesi tek başına Story’nin tamamlandığını göstermiyor.

## 4. Sprint sonunda Kadir’le tamamlayacaklarım

| Sıra | Kontrol | Sorumluluk |
|---|---|---|
| 1 | US-01–05’in son dosya, PR ve Jira bağlantılarını bu tabloya işlemek | Mert ve Abdülkadir |
| 2 | Her Story için kabul edilen, eksik kalan ve sonraki sprinte önerilen işi gerekçesiyle yazmak | Mert ve Abdülkadir; kabul görüşü Eray |
| 3 | Gerçek başlangıç/bitiş, tamamlanan SP ve Jira rapor bağlantılarını eklemek | Mert; sprint kaydı Esat |
| 4 | Review tarihi, katılımcılar ve gerçek geri bildirimleri kaydetmek; Kadir’in kontrolünü almak | Mert ve Abdülkadir |

Bu dört adım tamamlandıktan sonra raporu sprint sonu değerlendirmesi olarak güncelleyeceğim. Henüz gerçekleşmeyen toplantı, onay veya test sonucu kaydetmedim.

Kaynaklar: [Jira Sprint Backlog](https://dagdelen41.atlassian.net/jira/software/c/projects/KKY/boards/2/backlog), [ekip rolleri ve Definition of Done](https://github.com/DU-YBS471-KKY/kutuphane-kaynak-yonetimi/blob/8cae630d77893f454a24e6637c7e576aab1dd853/README.md), PR #6 ve PR #7. Bu dosyanın kapsamı US-01–05’tir; benim US-08–10 ve Kübra’nın US-14–17 gereksinim hazırlıkları Sprint 1 teslim puanına eklenmedi.

