# US 20 raporlama ekranı ve özet akışı

**Sorumlu:** Enes Ulutaş | **Tarih:** 28 Kasım 2026 | **Güncelleme:** 28 Kasım 2026
**Jira:** KKY-18 | **Sprint 4** | **5 SP**
**Durum:** Sprint 4 kapsamında hazırlandı; kapsam/öncelik ve ürün onayı takibindedir.

Sistemdeki ödünç, iade, gecikme ve ceza/tahsilat verilerinin özetlenerek yönetici/sorumlu ekranında sunulması bu akışta kurgulanır. Tablolar taslak niteliğindedir; canlı rapor motoru veya dış servis çağrısı içermez.

## U 01 Rapor filtreleme ve özet görünümü

RAPORLAMA EKRANI                Durum: Yetkili / Görevli
Tarih Aralığı: 01.11.2026 - 28.11.2026   Tür: Özet Rapor
Özet Metrikler:
- Toplam Ödünç İşlemi: 48
- Zamanında İade: 39 | Gecikmeli İade: 9
- Oluşan Ceza Toplamı: 185 TL | Tahsil Edilen: 135 TL

Yetkili kullanıcı filtre kriterlerine göre özet metrikleri görüntüler.

## U 02 Rapor detayı ve dışa aktarım/çıktı taslağı

RAPOR DETAY VE ÇIKTI ÖZETİ      Durum: Yetkili / Görevli
Seçili Dönem: 01.11.2026 - 28.11.2026
Detay Kayıt Sayısı: 9 gecikmeli kayıt
Çıktı Durumu: Özet tablo hazır (Taslak)

Detay satırları ve dönem özeti tutarlı biçimde görüntülenir; veri bulunmayan dönemlerde boş/uyarı durumu gösterilir.

## İşlem sırası

Rapor ekranı açıldığında -> Filtre kriterlerini (tarih/tür) al
  -> İlgili kayıtları özetle -> Özet metrikleri ve detay listesini ekrana getir
  -> Kayıt yoksa -> "Kayıt bulunamadı" bilgisi göster

| Kabul kriteri veya kapsam kuralı | Tasarım kanıtı | Kontrol kaydı |
| :--- | :--- | :--- |
| 1. Filtrelenen döneme göre özet metrikler listelenir | U 01 ve İşlem sırası | KS-20.1 |
| 2. Detay görünümü ve boş sonuç durumu tutarlı çalışır | U 02 ve İşlem sırası | KS-20.2 |

## PO kararları

Sprint 4 kapsam ve gereksinim dokümanlarına göre aşağıdaki kurallar esas alınır:

- Rapor ekranında yalnızca tanımlı özet/kayıt verileri gösterilir ve kapsam dışı alan eklenmez.
- Güncel kapsam ve öncelik kararları PO tarafından teyit edilir.

[Kontrol senaryoları](../test/us-20-kontrol.md) · [Gereksinimler](../docs/gereksinimler)
