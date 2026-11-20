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
