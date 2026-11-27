# US 19 ceza tahsilatı ve makbuz kaydı ekranı ve işlem akışı

**Sorumlu:** Enes Ulutaş | **Tarih:** 28 Kasım 2026 | **Güncelleme:** 28 Kasım 2026
**Jira:** KKY-17 | **Sprint 4** | **3 SP**
**Durum:** Sprint 4 kapsamında hazırlandı; US-18 ceza hesabı kuralına dayanır, inceleme ve ürün onayı bekleniyor.

Öğrencinin hesabında kesinleşen gecikme cezalarının görevli tarafından tahsil edilmesi ve makbuz/durum kaydının tutulması bu akışta gösterilir. Ekranlar taslak niteliğindedir; gerçek ödeme altyapısı veya canlı finansal entegrasyon yapılmaz.

## U 01 Ödenmemiş ceza listesi ve tahsilat ekranı

CEZA TAHSİLAT EKRANI           Durum: Görevli
Öğrenci: Örnek Öğrenci (200000001)
Aktif / Ödenmemiş Cezalar:
- Ceza #C-101 | Kitap: Örnek Kitap A | Gecikme: 5 gün | Tutar: 25 TL | Durum: Ödenmedi [Tahsil Et]

Görevli, öğrencinin ödenmemiş cezalarını görüntüler ve ilgili kayıt için **Tahsil Et** işlemini başlatır.

## U 02 Tahsilat onayı ve makbuz kaydı

TAHSİLAT ONAYI VE MAKBUZ KAYDI   Durum: Görevli
Makbuz No: MKZ-2026-0018        Öğrenci: Örnek Öğrenci (200000001)
Tahsil Edilen Tutar: 25 TL      Ödeme Yöntemi: Nakit (Kayıt Taslağı)
Ceza Durumu: Ödendi             İşlem Zamanı: 28.11.2026

Tahsilat onaylandığında ceza kaydı **Ödendi** durumuna geçer, makbuz numarası üretilir ve işlem kaydı oluşturulur.

## U 03 Borç/ceza uyarısı kontrolü

UYARI KONTROLÜ                  Durum: Sistem / Görevli
Öğrenci: Örnek Öğrenci (200000002)
Ödenmemiş Ceza: Yok (0 TL)      Makbuz Durumu: İşlem Bekleniyor

Ödenmemiş ceza bulunmadığında tahsilat işlemi başlatılmaz ve ilgili uyarı/bilgi mesajı gösterilir.

## İşlem sırası

Tahsilat ekranı açıldığında -> Öğrencinin kesinleşmiş/ödenmemiş cezalarını listele
  -> Tahsil edilecek kayıt seçildiğinde -> Tahsilatı onayla -> Durumu "Ödendi" yap ve makbuz kaydı oluştur
  -> Tahsil edilecek borç yoksa -> Uyarı mesajı göster ve tahsilat kaydı açma

| Kabul kriteri veya kapsam kuralı | Tasarım kanıtı | Kontrol kaydı |
| :--- | :--- | :--- |
| 1. Kesinleşmiş cezalar listelenir ve tahsilatla "Ödendi" olur | U 01, U 02 ve İşlem sırası | KS-19.1 |
| 2. Tahsilat sonrası makbuz/işlem kaydı tutulur | U 02 ve İşlem sırası | KS-19.2 |
| 3. Ödenmemiş ceza yoksa uygun uyarı verilir | U 03 ve İşlem sırası | KS-19.3 |

## PO kararları

Sprint 4 kapsam ve gereksinim dokümanlarına göre aşağıdaki kurallar esas alınır:

- Tahsilat akışı US-18 ile kesinleşen ceza tutarlarına dayanır.
- Tahsilat tamamlandığında ceza durumu güncellenir ve makbuz kaydı saklanır.

[Kontrol senaryoları](../test/us-19-kontrol.md) · [Gereksinimler](../docs/gereksinimler)
