# Sprint 3 kabul kriteri kontrolüm

Hazırlayan: Kübra Şen  
Sprint 3: 18–25 Kasım 2026

Bu kayıtta ekip arkadaşlarımın Sprint 3 teslimlerini Jira kabul kriterleriyle karşılaştırıyorum. Kontrolüm bir belge kontrolüdür; çalışan bir uygulamada test yapılmadı. Teslim sahiplerinin kontrol dosyalarındaki "Sonuç" sütunlarını ben doldurmuyorum. Benim karşılaştırmam bu dosyada ayrı tutulur.

## 20 Kasım 2026: PR #40 ön kontrolüm (US-11, US-12, US-13)

Kontrol ettiğim sürüm: [PR #40](https://github.com/DU-YBS471-KKY/kutuphane-kaynak-yonetimi/pull/40), `feature/odunc-verme` dalı, 18 Kasım'daki 4 commit (son commit 54f4794). Jira kriterlerini [KKY-10](https://dagdelen41.atlassian.net/browse/KKY-10), [KKY-11](https://dagdelen41.atlassian.net/browse/KKY-11) ve [KKY-12](https://dagdelen41.atlassian.net/browse/KKY-12) kayıtlarından 20 Kasım'da yeniden okudum.

Eray 5 PO kararını PR'a yazdı ama 20 Kasım itibarıyla dosyalara henüz işlenmedi. Bu yüzden bu bir ön kontroldür. Kadir kararları işleyince nihai kontrolümü yapıp PR'ı onaylayacağım.

### Kriter karşılaştırmam

| Story | Kriter | Tasarım kanıtı | Senaryo | Gözlemim | Sonucum |
|---|---|---|---|---|---|
| US-11 | 1 Barkodla kitap bilgisi ve müsaitlik görünür | O01 | KS-11-01 | Başlık, yazar, ISBN, kopya kodu ve durum ekranda var. | Uyumlu |
| US-11 | 2 Yalnızca müsait kitap verilir, diğerinde uyarı | O02, işlem sırası | KS-11-02, KS-11-03 | Ödünçte ve Bakımda için ayrı uyarı var, düğme pasif, kayıt oluşmuyor. | Uyumlu |
| US-11 | 3 Süre 15 gün, iade tarihi otomatik ve kayıtta | O01, O03 | KS-11-04, KS-11-05 | 18.11.2026 + 15 gün = 03.12.2026; hesabı kontrol ettim, doğru. | Uyumlu |
| US-12 | 1 Sağlam iadede Müsait, stok 1 artar | I01, I02 | KS-12-01 | Verilebilir kopya 1'den 2'ye çıkıyor. US-06 KS-06-04 ile tutarlı. | Uyumlu |
| US-12 | 2 Hasarlıda Bakımda, stoğa eklenmez | I01, I03 | KS-12-02 | Sayı 1'de kalıyor. US-09 ile tutarlı. | Uyumlu |
| US-12 | 3 İade tarihi ve görevli kayda geçer | I02, I03 | KS-12-03, KS-12-04 | İki iade türünde de iki bilgi kayıtta. | Uyumlu |
| US-13 | 1 İade tarihi geçmeden ve bir kez | U01, U03 | KS-13-02, KS-13-03 | İkinci uzatma ve süresi geçmiş kayıt reddediliyor. | Uyumlu |
| US-13 | 2 Rezervasyon varsa red ve sebep | U03, işlem sırası | KS-13-04 | Benim US-14 taslağımdaki Aktif rezervasyonla aynı kural. Rezerve edenin adı gösterilmiyor. | Uyumlu |
| US-13 | 3 Yeni tarih ödünç listesinde görünür | U02 | KS-13-01, KS-13-05 | 03.12.2026 + 7 gün = 10.12.2026; doğru. Liste benim US-15 taslağımla aynı yer. | Uyumlu |

Dağılımım: 9 kriterde 9 Uyumlu. Açık kriter farkı yok.

### Nihai kontrolden önce görmem gerekenler

Bunlar Jira kriter farkı değil. Eray'ın PR #40'taki kararlarının dosyalara işlenmesini bekliyorum:

| No | Dosya | Beklediğim güncelleme |
|---|---|---|
| B-01 | US-11 | Pasif veya cezalı hesapta ödünç engeli ve uyarısı, ekran ve senaryo olarak. |
| B-02 | US-11 | Aynı anda en fazla 3 kitap sınırı ve limit doluysa ret, ekran ve senaryo olarak. |
| B-03 | US-12 | Aktif ödünç kaydı olmayan kopyada "Bu kopya için aktif ödünç kaydı bulunmamaktadır" uyarısı. |
| B-04 | US-13 | İade tarihinin son gününde uzatmanın kabul edildiği senaryo. |
| B-05 | US-13 | Görevlinin öğrenci adına aynı kurallarla uzatma yapabildiği ekran ve senaryo. |

### Kadir ile birlikte netleştireceklerimiz

- N-01: US-11'deki rezervasyonlu kopya sorusu. İade edilen kopyanın, US-14'teki ilk aktif talep sahibi teslim alana kadar başka birine verilip verilemeyeceği. Kadir ile birlikte Eray'a soracağız. Ben de US-14 taslağıma aynı soruyu yazdım.
- N-02: US-13 U01 ile US-15 L01 aynı liste. Kadir'in U01'inde Durum sütunu yok, US-15 kriter 2 ise durumu istiyor. İki taslağın sütunlarını birlikte eşitlemeyi öneriyorum.

Kontrol senaryolarının sonuç sütunları Kadir'in dosyalarında "Bekliyor" olarak duruyor. Onlara dokunmadım.

## 21 Kasım 2026: PR #40 nihai kontrolüm

Kontrol ettiğim sürüm: Kadir'in 21 Kasım'daki iki commit'i ("US-11 12 13 taslaklarına PO kararları ve Durum sütunu işlendi" ve "US-11 12 13 senaryolarına PO kararları eklendi"). Jira kriterleri değişmemiş; 9 kriterin 9'u yine Uyumlu.

### Beklediğim güncellemeler

| No | Beklediğim | Gördüğüm | Sonucum |
|---|---|---|---|
| B-01 | US-11 pasif veya cezalı hesapta ödünç engeli | O01'de hesap ve gecikmiş kitap alanları, O02'de iki uyarı satırı, KS-11-06 ve KS-11-07 | Karşılandı |
| B-02 | US-11 aynı anda en fazla 3 kitap | O01 ve O03'te aktif ödünç sayısı, O02'de 3 / 3 uyarısı, KS-11-08 ve KS-11-09 | Karşılandı |
| B-03 | US-12 aktif kaydı olmayan kopyada uyarı | I04 ekranı ve KS-12-05; stok değişmiyor | Karşılandı |
| B-04 | US-13 iade gününde uzatma | U03 açıklaması, işlem sırası ve KS-13-06 (03.12.2026 → 10.12.2026, hesap doğru) | Karşılandı |
| B-05 | US-13 görevlinin öğrenci adına uzatması | U04 ekranı, KS-13-07 ve rezervasyonlu durumda KS-13-08 | Karşılandı |
| N-02 | US-13 U01 ile US-15 L01 sütunları | U01'e Durum sütunu eklenmiş; sütunlar L01 ile aynı | Karşılandı |

### Onaydan önce kalan iki nokta

- N-01, rezervasyonlu kopya: Eray kararı 21 Kasım'da, Kadir'in commit'lerinden sonra verdi. Bu yüzden henüz dosyalarda yok. Beklediğim: US-12'de sağlam iade edilen kopyanın aktif rezervasyon sırası varsa Müsait değil Rezerve olması ve genel ödünç alıma açılmaması; US-11'de Rezerve kopyanın yalnızca ayrıldığı öğrenciye verilmesi ve bunun için senaryolar. US-11'deki "Açık kalan nokta" da karar olarak güncellenmeli. Ben kendi tarafımı US-14 R06 ve KS-14-11…13'e işledim; durum adı olarak Rezerve kullanıyorum.
- Örnek veri: Kadir'in PR #44'teki notu üzerine US-15'te 2000000001 numaralı öğrencinin Örnek Kitap B'sini 04.11.2026 ödünç, 19.11.2026 iade tarihi olarak değiştirdim. Bu öğrencinin 18.11.2026'da 1 aktif ödüncü var. US-11'de aynı öğrencinin başlangıçtaki aktif ödüncü 0 ve O03'te 1 / 3 yazıyor; bunlar 1 ve 2 / 3 olmalı. US-13 U01'deki Örnek Kitap B satırı da 04.11.2026 / 19.11.2026 olmalı.

Bu iki nokta işlenince PR #40'ı onaylayacağım. Kadir'in dosyalarındaki "Sonuç" sütunlarına dokunmadım.

## 24 Kasım 2026: PR #40 birleşme sonrası senaryo kontrolüm

Kontrol ettiğim sürüm: PR #40'ın Eray tarafından birleştirilmesinden sonraki `develop` dalı; `test/us-11-kontrol.md`, `test/us-12-kontrol.md`, `test/us-13-kontrol.md` ve ilgili tasarım dosyaları. Senaryoları Kadir'in yazdığı beklenen sonuçlarla ve tasarım dosyalarındaki kanıtlarla karşılaştırdım. Bu da bir belge kontrolüdür; çalışan bir uygulamada test yapılmadı. Kadir'in dosyalarındaki "Sonuç" sütunlarına dokunmadım.

### Senaryo karşılaştırmam

| Senaryo | Kriter | Kontrol ettiğim | Belgedeki kanıt | Sonucum |
|---|---|---|---|---|
| KS-11-01 | US-11 / 1 | Öğrenci ve K-001 okutulunca başlık, yazar, ISBN, kopya kodu ve MUSAIT durumu görünür. | O01 | Uyumlu |
| KS-11-02 | US-11 / 2 | K-002 için "ödünçte" uyarısı, pasif düğme, kayıt oluşmaması. | O02 | Uyumlu |
| KS-11-03 | US-11 / 2 | K-003 için "bakımda" uyarısı, pasif düğme, kayıt oluşmaması. | O02, US-09 B02 | Uyumlu |
| KS-11-04 | US-11 / 3 | 18.11.2026 + 15 gün = 03.12.2026; ay geçişi doğru. | O01, işlem sırası | Uyumlu |
| KS-11-05 | US-11 / 3 | Kayıt özeti ve stok azalması doğru. Ancak senaryoda aktif ödünç 1 / 3 yazıyor; 2000000001'in 18.11.2026'da zaten 1 aktif ödüncü olduğu için işlem sonrası 2 / 3 olmalı. | O03 | Düzeltme bekliyor (#50) |
| KS-11-06 | PO kararı | Pasif hesapta uyarı, kopya alanı açılmıyor, kayıt yok. | O02, işlem sırası | Uyumlu |
| KS-11-07 | PO kararı | Gecikmiş veya cezalı kitapta uyarı, kayıt yok. | O02, işlem sırası | Uyumlu |
| KS-11-08 | PO kararı | 3 / 3 dolu hesapta limit uyarısı, kayıt yok. | O02 | Uyumlu |
| KS-11-09 | PO kararı | 2 aktif ödünçlü öğrencide kayıt oluşur, 3 / 3 olur. | O01, O03 | Uyumlu |
| KS-12-01 | US-12 / 1 | Sağlam iadede K-001 Müsait, verilebilir kopya 1'den 2'ye çıkar. | I02, US-06 KS-06-04 | Uyumlu |
| KS-12-02 | US-12 / 2 | Hasarlı iadede K-001 Bakımda, sayı 1'de kalır. | I03, US-09 B02 | Uyumlu |
| KS-12-03 | US-12 / 3 | Sağlam iadede iade tarihi 25.11.2026 ve görevli kayıtta. | I02 | Uyumlu |
| KS-12-04 | US-12 / 3 | Hasarlı iadede de tarih ve görevli kayıtta, ödünç kaydı kapanır. | I03 | Uyumlu |
| KS-12-05 | PO kararı | Aktif kaydı olmayan kopyada uyarı, iade başlamaz, stok değişmez. | I04, işlem sırası | Uyumlu |
| KS-13-01 | US-13 / 3 | 03.12.2026 + 7 gün = 10.12.2026; hak 1 / 1 kullanıldı. | U02 | Uyumlu |
| KS-13-02 | US-13 / 1 | İkinci uzatma reddedilir, tarih 10.12.2026'da kalır. | U03 | Uyumlu |
| KS-13-03 | US-13 / 1 | İade tarihi geçmiş kayıtta uzatma reddedilir. | U03 | Uyumlu |
| KS-13-04 | US-13 / 2 | Aktif rezervasyonda red ve sebep; rezerve edenin adı görünmez. US-14 ile aynı kural. | U03, işlem sırası | Uyumlu |
| KS-13-05 | US-13 / 3 | Listede 10.12.2026, ODUNCTE, uzatma 1 / 1; sütunlar US-15 L01 ile aynı. | U01, U02 | Uyumlu |
| KS-13-06 | PO kararı | İade gününde (03.12.2026) uzatma kabul edilir, yeni tarih 10.12.2026. | U03, işlem sırası | Uyumlu |
| KS-13-07 | PO kararı | Görevli öğrenci adına uzatır, yeni tarih 10.12.2026 ve görevli kayıtta. | U04 | Uyumlu |
| KS-13-08 | PO kararı | Rezervasyonlu kitapta görevli denemesi de reddedilir. | U04, U03 | Uyumlu |

### Özet

- 22 senaryodan 21'i uyumlu. KS-11-05 düzeltme bekliyor.
- Jira kabul kriterleri: 9 kriterin 9'u uyumlu.

### Issue #50'de açık kalan maddeler

Bu maddeleri [Issue #50](https://github.com/DU-YBS471-KKY/kutuphane-kaynak-yonetimi/issues/50) ile Kadir'e ilettim. Düzeltmeler gelince yeniden kontrol edip sonucumu bu dosyaya ekleyeceğim.

1. US-12 ve US-11: Eray'ın 21 Kasım'daki 48 saat kararı dosyalarda yok. Sağlam iade edilen kopyanın aktif sırası varsa Rezerve olması, yalnızca sıradaki öğrenciye verilmesi ve 48 saat içinde alınmazsa sıradakine veya Müsait durumuna geçmesi için ekran ve senaryolar eklenmeli.
2. US-11: 2000000001'in başlangıçtaki aktif ödüncü 0 değil 1 olmalı; O01'de 1 / 3, O03'te ve KS-11-05'te 2 / 3 yazmalı.
3. US-13: U01'deki Örnek Kitap B satırı 04.11.2026 ödünç, 19.11.2026 iade olarak güncellenmeli (US-15 ile aynı örnek veri).

## 25 Kasım 2026: PR #52 kontrolüm (#50 düzeltmesi)

Kadir'in [PR #52](https://github.com/DU-YBS471-KKY/kutuphane-kaynak-yonetimi/pull/52) dalındaki US-11, US-12 ve US-13 dosyalarını kontrol ettim. Toplam 25 senaryo: KS-11-01..11, KS-12-01..06, KS-13-01..08.

| Konu | Gördüğüm | Sonucum |
|---|---|---|
| 48 saat Rezerve kuralı | US-12 I05 ve KS-12-06; US-11 O02'de iki yeni satır, KS-11-10 ve KS-11-11. Benim KS-14-04 ve KS-14-11 ile aynı veri. | Uyumlu |
| Ortak örnek veri | US-11'de 2000000001 aktif ödünç 1 ile başlıyor; O01 1 / 3, O03 ve KS-11-05 2 / 3. US-13 U01'de Kitap B 04.11.2026 / 19.11.2026. | Uyumlu |
| Rezerve kopyanın ödüncünde stok | O03 ve işlem sırasında her ödünçte "müsait sayı 1 azalır" yazıyor. Rezerve → Ödünçte geçişinde sayı değişmemeli (I05'te zaten 0). KS-11-11'de stok kontrolü yok. Mert'in bulgusunu doğruluyorum. | Düzeltme bekliyor |

Özet: 25 senaryonun 24'ü uyumlu. KS-11-11, O03 ve işlem sırasındaki stok ifadesi düzelince uyumlu olacak. Bu düzeltme gelince PR #52'yi onaylayacağım.
