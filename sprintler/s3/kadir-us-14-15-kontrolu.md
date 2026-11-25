# US-14 ve US-15 bağımsız belge kontrolüm

Kontrol eden: Abdülkadir Güneş | 25 Kasım 2026  
Kontrol edilen: Kübra'nın PR #44 ile develop'a giren güncel dosyaları  
Jira: [KKY-21](https://dagdelen41.atlassian.net/browse/KKY-21) US-14 | [KKY-22](https://dagdelen41.atlassian.net/browse/KKY-22) US-15

Kübra'nın US-14 ve US-15 senaryolarını tasarım dosyalarıyla, Jira kabul kriterleriyle ve Eray'ın 21 Kasım PO kararlarıyla karşılaştırdım. Bu bir belge kontrolüdür. Bir uygulamada işlem çalıştırılmadı. Senaryodaki beklenen sonuç tasarım dosyasında aynı şekilde gösteriliyorsa Uyumlu yazdım.

Kübra da benim US-11, US-12 ve US-13 senaryolarımı kendi kaydında kontrol etti. Böylece Sprint 3'teki 43 senaryonun hepsi karşılıklı kontrol edilmiş oluyor.

## US-14 rezervasyon

Kontrol edilen dosyalar `tasarim/us-14-rezervasyon.md` ve `test/us-14-kontrol.md`.

| Kod | Kriter | Karşılaştırdığım yer | Gözlediğim | Sonuç |
|---|---|---|---|---|
| KS-14-01 | 1 | R01, R03 | Talep tarihi, sıra no 1 ve 2 / 2 aktif rezervasyon R03'te aynı. | Uyumlu |
| KS-14-02 | 2 | R04, işlem sırası | Aynı kitap kontrolü 2 rezervasyon sınırından önce yapılıyor, sınır uyarısı çıkmıyor. | Uyumlu |
| KS-14-03 | 3 | R03, R06 | Sıra talep zamanına göre A, B, C. | Uyumlu |
| KS-14-04 | 3 | R06, US-12 | Sağlam iadede K-101 Rezerve olup A'ya ayrılıyor. Benim US-12 I05 ve KS-12-06 ile aynı. | Uyumlu |
| KS-14-05 | 3 | R05, R06 | İptal eden sıradan çıkıyor, B 1'e geçiyor, iade sonrası B'ye ayrılıyor. | Uyumlu |
| KS-14-06 | PO kararı | R02 birinci satır | Müsait kopya varken düğme yok, uyarı metni aynı. | Uyumlu |
| KS-14-07 | PO kararı | R02 ikinci satır | Tüm kopyalar bakımdayken rezervasyon yok. | Uyumlu |
| KS-14-08 | PO kararı | R02 beşinci satır, R05 | 2 aktif rezervasyon sınırı ve mevcut kayıtların değişmemesi aynı. | Uyumlu |
| KS-14-09 | PO kararı | R02 üçüncü satır | Pasif hesap 2000000004 benim US-11 verimle aynı. | Uyumlu |
| KS-14-10 | PO kararı | R02 dördüncü satır | Gecikmiş kitabı olan 2000000005 benim US-11 verimle aynı. | Uyumlu |
| KS-14-11 | PO kararı | R06, US-11 | Rezerve K-101 B'ye verilmiyor, A'ya veriliyor ve rezervasyon Tamamlandı. Benim KS-11-10 ve KS-11-11 ile aynı. | Uyumlu |
| KS-14-12 | PO kararı | R06, işlem sırası | 48 saat dolunca A iptal, kopya B için Rezerve kalıyor ve süre yeniden başlıyor. | Uyumlu |
| KS-14-13 | PO kararı | R06, işlem sırası | Sırada başka talep yoksa kopya Müsait oluyor. | Uyumlu |

US-14 sonucu 13 senaryonun 13'ü uyumlu.

## US-15 ödünç listesi

Kontrol edilen dosyalar `tasarim/us-15-odunc-listesi.md` ve `test/us-15-kontrol.md`.

| Kod | Kriter | Karşılaştırdığım yer | Gözlediğim | Sonuç |
|---|---|---|---|---|
| KS-15-01 | 1 | L01, L02 | A yalnızca kendi dört kaydını görüyor. | Uyumlu |
| KS-15-02 | 1 | L04 | Başka öğrencinin kaydında yetki uyarısı var, bilgi gösterilmiyor. | Uyumlu |
| KS-15-03 | 2 | L01 | Dört alan ve tarihler aynı. Benim US-13 U01 ile sütunlar aynı. | Uyumlu |
| KS-15-04 | 2 | L02, US-12 | İade edilen kayıt geçmişe geçiyor. Benim US-12 I02 ile aynı. | Uyumlu |
| KS-15-05 | 3 | L01 | Kitap B 19.11.2026'dan sonra gecikmiş, iade günü gecikmiş sayılmıyor. Benim US-13 kararıyla aynı. | Uyumlu |
| KS-15-06 | 3 | L03 | Kaydı olmayan öğrenciye "Kayıt bulunamadı" mesajı çıkıyor. | Uyumlu |
| KS-15-07 | PO kararı | L02, işlem sırası | Geçmiş liste iade tarihine göre yeniden eskiye. | Uyumlu |
| KS-15-08 | PO kararı | L02 | Silme ve düzenleme yok, saklama bilgisi yazıyor. | Uyumlu |

US-15 sonucu 8 senaryonun 8'i uyumlu.

## Not

Sonucu etkilemeyen bir isim benzerliği var. US-14'te "Örnek Öğrenci A" 2000000011, US-15'te "Örnek Öğrenci A" 2000000001. Numaralar farklı olduğu için senaryolar karışmıyor. Final raporunda örnek öğrencilerin numarayla anılması daha net olur.

Ortak örnek veri çelişkisi 25 Kasım'da benim tarafımda da düzeltildi. US-11'de 2000000001'in aktif ödüncü artık Kübra'nın US-15 L01 örneğiyle aynı.

## Özet

| İş | Senaryo | Uyumlu |
|---|---:|---:|
| US-14 | 13 | 13 |
| US-15 | 8 | 8 |
| Toplam | 21 | 21 |

Kübra'nın test dosyalarındaki Sonuç sütunu bu kayda göre işlenebilir.
