# US 18 gecikmeli iade otomatik ceza hesaplama ekranı ve işlem akışı

**Sorumlu:** Enes Ulutaş | **Tarih:** 28 Kasım 2026 | **Güncelleme:** 28 Kasım 2026
**Jira:** KKY-16 | **Sprint 4** | **5 SP**
**Durum:** Sprint 4 kapsamında hazırlandı; inceleme ve ürün onayı bekleniyor.

İade işlemi sırasında son iade tarihi geçmiş kitaplar için gecikme gününe göre otomatik ceza tutarı hesaplanır ve aşağıdaki ekran/akışlarla gösterilir. Tablolar çalışan uygulama ekranı değildir; iade ve ceza hesabı kurallarını netleştirmek için hazırlanmıştır.

## U 01 İade kontrolü ve ceza hesaplama özeti

İADE VE CEZA HESAPLAMA         Durum: Görevli / Sistem
Kitap: Örnek Kitap A           Son İade Tarihi: 20.11.2026
İade Tarihi: 25.11.2026         Gecikme Süresi: 5 gün
Günlük Ceza Tutarı: 5 TL        Hesaplanan Ceza: 25 TL

Son iade tarihi geçmiş kayıtlarda gecikme süresi (`iade tarihi - son iade tarihi`, gün bazında) bulunur ve günlük ceza tutarıyla çarpılır (`5 gün × 5 TL = 25 TL`).

## U 02 Zamanında veya erken iade (ceza oluşmama durumu)

İADE VE CEZA HESAPLAMA         Durum: Görevli / Sistem
Kitap: Örnek Kitap B           Son İade Tarihi: 30.11.2026
İade Tarihi: 30.11.2026         Gecikme Süresi: 0 gün
Günlük Ceza Tutarı: 5 TL        Hesaplanan Ceza: 0 TL

Kitap son iade tarihinde veya öncesinde iade edildiyse gecikme günü `0` sayılır ve ceza oluşmaz (`0 TL`).

## U 03 İade anında cezanın kesinleşmesi ve öğrenci hesabına yansıması

CEZA KAYDI KESİNLEŞTİ         Öğrenci: Örnek Öğrenci (200000001)
Referans İşlem: İade #1042      Kitap: Örnek Kitap A
Kesinleşen Ceza: 25 TL          Hesap Durumu: Ödenmemiş Ceza Mevcut
Sonraki Adım: Tahsilat (US-19) ekranında görüntülenebilir.

Kitap iade edildiğinde hesaplanan ceza tutarı kesinleşir ve öğrencinin hesabında görünür hale gelir. Böylece sonraki adımdaki tahsilat ve makbuz akışı (`US-19` / `KKY-17`) bu kesinleşen tutar üzerinden ilerler.

## İşlem sırası

İade kaydı tetiklendiğinde -> Son iade tarihi ile iade tarihini karşılaştır
  -> İade tarihi <= Son iade tarihi mi? Evet: Gecikme = 0 gün, Ceza = 0 TL (ceza kaydı oluşmaz)
  -> Hayır: Gecikme gününü hesapla -> Günlük ceza tutarı ile çarp -> Kesinleşen cezayı öğrenci hesabına yaz

| Kabul kriteri veya kapsam kuralı | Tasarım kanıtı | Kontrol kaydı |
| :--- | :--- | :--- |
| 1. Son iade tarihinde veya öncesinde iade edilen kitapta ceza oluşmaz | U 02 ve İşlem sırası | KS-18.1 |
| 2. Gecikme gününe göre otomatik ceza tutarı hesaplanır | U 01 ve İşlem sırası | KS-18.2 |
| 3. İade anında ceza kesinleşir ve öğrenci hesabında görünür | U 03 ve İşlem sırası | KS-18.3 |

## PO kararları

Sprint 4 kapsam ve gereksinim dokümanlarına göre aşağıdaki kurallar esas alınır:

- Son iade tarihinde veya öncesinde yapılan iadelerde ceza tutarı oluşmaz (`0` gecikme, `0` ceza).
- İade tarihi geçmiş kayıtlarda gecikme günü ile günlük ceza tutarı çarpılarak ceza hesaplanır ve iade anında kesinleşerek öğrencinin hesabına yansır.

[Kontrol senaryoları](../test/us-18-kontrol.md) · [Gereksinimler](../docs/gereksinimler)
