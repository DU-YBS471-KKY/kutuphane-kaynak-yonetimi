# US 11 barkodla ödünç verme ekranı ve işlem akışı

Sorumlu: Abdülkadir Güneş | Tarih: 18 Kasım 2026 | Güncelleme: 25 Kasım 2026  
Jira: [KKY-10](https://dagdelen41.atlassian.net/browse/KKY-10) | Sprint 3 | 5 SP  
Durum: Eray'ın 19 ve 21 Kasım PO kararları işlendi. Kübra'nın kontrolü bekleniyor.

Görevlinin öğrenci kartını ve kitap kopyasının barkodunu okutup ödünç vermesini aşağıdaki ekranlarla gösterdim. Taslaklar çalışan uygulama ekranı değildir. Barkod, US-09'daki gibi kitabın tek bir fiziksel kopyasını gösterir. Böylece bir kopya ödünçte ya da bakımdayken aynı kitabın diğer kopyaları verilebilir.

## O 01 ödünç verme ekranı

```text
ODUNC VER                               Oturum: Gorevli
Ogrenci karti  [__________] [Barkod oku]

OGRENCI BILGISI
Ogrenci        Ornek Ogrenci  2000000001
Hesap          AKTIF
Gecikmis veya cezali kitap   Yok
Aktif odunc    1 / 3

Kopya barkodu  [__________] [Barkod oku]

KOPYA BILGISI
Baslik   Ornek Kitap A
Yazar    Ornek Yazar
ISBN     9781234567897
Kopya    K-001        Durum  MUSAIT

Odunc tarihi   18.11.2026
Iade tarihi    03.12.2026   otomatik 15 gun
                              [Iptal] [Odunc ver]
```

Önce öğrenci kartı okutulur. Hesabın aktif olup olmadığı, gecikmiş veya cezalı kitabı olup olmadığı ve elindeki ödünç sayısı ekranda görünür. Öğrenci kontrolünden geçmeden kopya barkodu alanı açılmaz.

Kopya barkodu okutulunca kitap bilgisi ve kopyanın durumu ekranda görünür. Bu kriter 1'i karşılar. İade tarihi elle girilmez. Sistem ödünç tarihine 15 gün ekleyip gösterir. Bu kriter 3'ü karşılar.

## O 02 uyarı durumları

| Durum | Gösterilecek bilgi | Sonraki adım |
|---|---|---|
| Hesap pasif | "Öğrenci hesabı aktif değil. Ödünç verilemez." | Kopya barkodu alanı açılmaz. Kayıt oluşmaz. |
| Gecikmiş veya cezalı kitap var | "Öğrencinin gecikmiş veya cezalı kitabı var. Ödünç verilemez." | Kopya barkodu alanı açılmaz. Kayıt oluşmaz. |
| Aktif ödünç 3 / 3 | "Öğrenci aynı anda en fazla 3 kitap alabilir." | Kopya barkodu alanı açılmaz. Kayıt oluşmaz. |
| Kopya Müsait | Durum yeşil "MUSAIT" olarak görünür. | "Odunc ver" düğmesi aktiftir. |
| Kopya Ödünçte | "Bu kopya şu anda ödünçte. Ödünç verilemez." | "Odunc ver" düğmesi pasiftir. Kayıt oluşmaz. Görevli başka kopya okutabilir. |
| Kopya Bakımda | "Bu kopya bakımda. Ödünç verilemez." | "Odunc ver" düğmesi pasiftir. Kayıt oluşmaz. Görevli başka kopya okutabilir. |
| Kopya Rezerve, başka öğrenciye ayrılmış | "Bu kopya sıradaki öğrenci için ayrıldı. Ödünç verilemez." | "Odunc ver" düğmesi pasiftir. Kayıt oluşmaz. |
| Kopya Rezerve, okutulan öğrenciye ayrılmış | "Bu kopya size ayrıldı." | "Odunc ver" düğmesi aktiftir. Ödünç sonrası öğrencinin rezervasyonu Tamamlandı olur. |

İlk üç satır Eray'ın 19 Kasım kararlarıdır. Pasif ya da cezalı hesapta ve 3 kitap sınırı dolduğunda ödünç verilmez. Sonraki üç satır kriter 2'yi karşılar. Müsait kopya herkese, Rezerve kopya yalnızca ayrıldığı öğrenciye ödünç verilebilir. Bakımda durumunun adı ve anlamı US-09 ile aynıdır.

Son iki satır Eray'ın 21 Kasım kararıdır. Aktif rezervasyon sırası olan kitabın kopyası sağlam iade edilince US-12'de Rezerve olur. Kopya bildirimden sonra 48 saat sıradaki ilk öğrenci için tutulur. Bu sürede başka öğrenciye verilmez. Rezerve durum adı ve 48 saat kuralı Kübra'nın US-14 R06 bölümüyle aynıdır.

## O 03 başarılı ödünç kaydı

```text
Odunc kaydi olusturuldu.

Ogrenci        Ornek Ogrenci  2000000001
Kitap          Ornek Kitap A  K-001
Odunc tarihi   18.11.2026
Iade tarihi    03.12.2026
Kopya durumu   ODUNCTE
Aktif odunc    2 / 3
                              [Yeni islem]
```

Kayıt oluşunca iade tarihi kayıtta görünür. Kopyanın durumu Ödünçte olur ve kitabın müsait kopya sayısı 1 azalır. Bu US-06'daki stok bilgisiyle de tutarlıdır. Öğrencinin aktif ödünç sayısı 1 artar.

## İşlem sırası

```text
Ekrani ac -> Ogrenci kartini okut
  -> Hesap aktif mi? Hayir: O02 uyarisi, kayit yok
  -> Gecikmis veya cezali kitap var mi? Evet: O02 uyarisi, kayit yok
  -> Aktif odunc 3 mu? Evet: O02 uyarisi, kayit yok
  -> Kopya barkodunu okut -> Kitap bilgisi ve durum gorunur (O01)
  -> Durum Musait mi? Evet: devam
  -> Durum Rezerve mi? Okutulan ogrenciye ayrildiysa devam
     Baskasina ayrildiysa O02 uyarisi, kayit yok
  -> Oduncte ya da Bakimda: O02 uyarisi, kayit yok, baska kopya okutulabilir
  -> Iade tarihi = odunc tarihi + 15 gun
  -> Odunc ver -> O03 kayit ozeti -> Kopya ODUNCTE, musait sayi 1 azalir
  -> Kopya Rezerve idiyse ogrencinin rezervasyonu TAMAMLANDI olur
```

| Kabul kriteri veya PO kararı | Tasarım kanıtı | Kontrol kaydı |
|---|---|---|
| 1 Barkodla kitap bilgisi ve durum görünür | O01 | KS-11-01 |
| 2 Yalnızca müsait kitap verilir, diğerinde uyarı | O02 ve işlem sırası | KS-11-02, KS-11-03 |
| 3 Süre 15 gün, iade tarihi otomatik | O01 ve O03 | KS-11-04, KS-11-05 |
| PO kararı, pasif veya cezalı hesapta ödünç verilmez | O01, O02 ve işlem sırası | KS-11-06, KS-11-07 |
| PO kararı, aynı anda en fazla 3 kitap | O01, O02 ve O03 | KS-11-08, KS-11-09 |
| PO kararı, Rezerve kopya yalnızca ayrıldığı öğrenciye | O02 ve işlem sırası | KS-11-10, KS-11-11 |

## PO kararları

Eray 19 Kasım'da PR #40'ta şu kararları verdi.

- Öğrenci kartı okutulunca hesabın aktif olduğu ve gecikmiş ya da cezalı kitabı olmadığı kontrol edilir. Değilse uyarı çıkar ve ödünç verilmez.
- Bir öğrenci aynı anda en fazla 3 kitap ödünç alabilir. Sınır doluysa yeni ödünç kaydı oluşmaz.

Eray 21 Kasım'da PR #40 ve PR #44'te şu kararı verdi. Önceki sürümde açık kalan nokta buydu.

- Sağlam iade edilen kopyanın aktif rezervasyon sırası varsa kopya genel ödünç alıma açılmaz ve yalnızca sıradaki ilk öğrenciye verilir. Bildirimden sonra 48 saat bu öğrenci için tutulur. Teslim alınmazsa rezervasyon iptal edilir ve kopya sıradaki öğrenciye, sıra boşsa Müsait durumuna geçer.

Bu kararları yukarıdaki ekranlara ve senaryolara işledim. Örnek öğrenci 2000000001'in aktif ödünç sayısı Kübra'nın US-15 L01 örneğiyle aynı olacak şekilde 1'den başlar.

[Kontrol senaryoları](../test/us-11-kontrol.md) · [Gereksinimler](../docs/gereksinimler/kadir-us-11-13-hazirlik.md)
