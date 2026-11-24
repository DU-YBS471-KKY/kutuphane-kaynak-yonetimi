# US 11 barkodla ödünç verme ekranı ve işlem akışı

Sorumlu: Abdülkadir Güneş | Tarih: 18 Kasım 2026 | Güncelleme: 21 Kasım 2026  
Jira: [KKY-10](https://dagdelen41.atlassian.net/browse/KKY-10) | Sprint 3 | 5 SP  
Durum: Eray'ın 19 Kasım PO kararları işlendi. Kübra'nın nihai kontrolü bekleniyor.

Görevlinin öğrenci kartını ve kitap kopyasının barkodunu okutup ödünç vermesini aşağıdaki ekranlarla gösterdim. Taslaklar çalışan uygulama ekranı değildir. Barkod, US-09'daki gibi kitabın tek bir fiziksel kopyasını gösterir. Böylece bir kopya ödünçte ya da bakımdayken aynı kitabın diğer kopyaları verilebilir.

## O 01 ödünç verme ekranı

```text
ODUNC VER                               Oturum: Gorevli
Ogrenci karti  [__________] [Barkod oku]

OGRENCI BILGISI
Ogrenci        Ornek Ogrenci  2000000001
Hesap          AKTIF
Gecikmis veya cezali kitap   Yok
Aktif odunc    0 / 3

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

İlk üç satır Eray'ın 19 Kasım kararlarıdır. Pasif ya da cezalı hesapta ve 3 kitap sınırı dolduğunda ödünç verilmez. Son üç satır kriter 2'yi karşılar. Yalnızca durumu Müsait olan kopya ödünç verilebilir. Bakımda durumunun adı ve anlamı US-09 ile aynıdır.

## O 03 başarılı ödünç kaydı

```text
Odunc kaydi olusturuldu.

Ogrenci        Ornek Ogrenci  2000000001
Kitap          Ornek Kitap A  K-001
Odunc tarihi   18.11.2026
Iade tarihi    03.12.2026
Kopya durumu   ODUNCTE
Aktif odunc    1 / 3
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
  -> Durum Musait mi? Hayir: O02 uyarisi, kayit yok, baska kopya okutulabilir
  -> Evet: Iade tarihi = odunc tarihi + 15 gun
  -> Odunc ver -> O03 kayit ozeti -> Kopya ODUNCTE, musait sayi 1 azalir
```

| Kabul kriteri veya PO kararı | Tasarım kanıtı | Kontrol kaydı |
|---|---|---|
| 1 Barkodla kitap bilgisi ve durum görünür | O01 | KS-11-01 |
| 2 Yalnızca müsait kitap verilir, diğerinde uyarı | O02 ve işlem sırası | KS-11-02, KS-11-03 |
| 3 Süre 15 gün, iade tarihi otomatik | O01 ve O03 | KS-11-04, KS-11-05 |
| PO kararı, pasif veya cezalı hesapta ödünç verilmez | O01, O02 ve işlem sırası | KS-11-06, KS-11-07 |
| PO kararı, aynı anda en fazla 3 kitap | O01, O02 ve O03 | KS-11-08, KS-11-09 |

## PO kararları

Eray 19 Kasım'da PR #40'ta şu kararları verdi. Yukarıdaki ekranlara ve senaryolara işledim.

- Öğrenci kartı okutulunca hesabın aktif olduğu ve gecikmiş ya da cezalı kitabı olmadığı kontrol edilir. Değilse uyarı çıkar ve ödünç verilmez.
- Bir öğrenci aynı anda en fazla 3 kitap ödünç alabilir. Sınır doluysa yeni ödünç kaydı oluşmaz.

## Açık kalan nokta

- İade edilen kopya US-14'te başka bir öğrenci için rezerve edildiyse sıradaki öğrenci teslim alana kadar başkasına verilebilir mi. Kübra ile birlikte Eray'a soruyoruz. Kübra da aynı soruyu US-14 taslağına yazdı.

[Kontrol senaryoları](../test/us-11-kontrol.md) · [Gereksinimler](../docs/gereksinimler/kadir-us-11-13-hazirlik.md)
