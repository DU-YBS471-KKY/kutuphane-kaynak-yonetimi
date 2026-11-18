# US 11 barkodla ödünç verme ekranı ve işlem akışı

Sorumlu: Abdülkadir Güneş | Tarih: 18 Kasım 2026  
Jira: [KKY-10](https://dagdelen41.atlassian.net/browse/KKY-10) | Sprint 3 | 5 SP  
Durum: Taslak hazır. Kübra'nın bağımsız kontrolü bekleniyor.

Görevlinin öğrenci kartını ve kitap kopyasının barkodunu okutup ödünç vermesini aşağıdaki ekranlarla gösterdim. Taslaklar çalışan uygulama ekranı değildir. Barkod, US-09'daki gibi kitabın tek bir fiziksel kopyasını gösterir. Böylece bir kopya ödünçte ya da bakımdayken aynı kitabın diğer kopyaları verilebilir.

## O 01 ödünç verme ekranı

```text
ODUNC VER                               Oturum: Gorevli
Ogrenci karti  [__________] [Barkod oku]
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

Kopya barkodu okutulunca kitap bilgisi ve kopyanın durumu ekranda görünür. Bu kriter 1'i karşılar. İade tarihi elle girilmez. Sistem ödünç tarihine 15 gün ekleyip gösterir. Bu kriter 3'ü karşılar.

## O 02 uyarı durumları

| Kopyanın durumu | Gösterilecek bilgi | Sonraki adım |
|---|---|---|
| Müsait | Durum yeşil "MUSAIT" olarak görünür. | "Odunc ver" düğmesi aktiftir. |
| Ödünçte | "Bu kopya şu anda ödünçte. Ödünç verilemez." | "Odunc ver" düğmesi pasiftir. Kayıt oluşmaz. Görevli başka kopya okutabilir. |
| Bakımda | "Bu kopya bakımda. Ödünç verilemez." | "Odunc ver" düğmesi pasiftir. Kayıt oluşmaz. Görevli başka kopya okutabilir. |

Yalnızca durumu Müsait olan kopya ödünç verilebilir. Diğer durumlarda uyarı çıkar ve kayıt oluşmaz. Bu kriter 2'yi karşılar. Bakımda durumunun adı ve anlamı US-09 ile aynıdır.

## O 03 başarılı ödünç kaydı

```text
Odunc kaydi olusturuldu.

Ogrenci        Ornek Ogrenci  2000000001
Kitap          Ornek Kitap A  K-001
Odunc tarihi   18.11.2026
Iade tarihi    03.12.2026
Kopya durumu   ODUNCTE
                              [Yeni islem]
```

Kayıt oluşunca iade tarihi kayıtta görünür. Kopyanın durumu Ödünçte olur ve kitabın müsait kopya sayısı 1 azalır. Bu US-06'daki stok bilgisiyle de tutarlıdır.

## İşlem sırası

```text
Ekrani ac -> Ogrenci kartini okut -> Kopya barkodunu okut
  -> Kitap bilgisi ve durum gorunur (O01)
  -> Durum Musait mi? Hayir: O02 uyarisi, kayit yok, baska kopya okutulabilir
  -> Evet: Iade tarihi = odunc tarihi + 15 gun
  -> Odunc ver -> O03 kayit ozeti -> Kopya ODUNCTE, musait sayi 1 azalir
```

| Kabul kriteri | Tasarım kanıtı | Kontrol kaydı |
|---|---|---|
| 1 Barkodla kitap bilgisi ve durum görünür | O01 | KS-11-01 |
| 2 Yalnızca müsait kitap verilir, diğerinde uyarı | O02 ve işlem sırası | KS-11-02, KS-11-03 |
| 3 Süre 15 gün, iade tarihi otomatik | O01 ve O03 | KS-11-04, KS-11-05 |

## Netleşmesi gereken noktalar

Bunlar kabul kriterlerinde yok. Yeni kural eklemedim, PO kararına bırakıyorum.

- Öğrenci kartı okutulunca hesabın geçerli olup olmadığı kontrol edilecek mi. Eray'a soracağım.
- Bir öğrencinin aynı anda alabileceği kitap sayısı için sınır olacak mı. Eray'a soracağım.
- İade edilen kopya US-14'te başka bir öğrenci için rezerve edildiyse sıradaki öğrenci dışında birine verilebilir mi. Kübra ile birlikte bakacağız, çünkü US-14 ve US-17'deki sıra kuralına bağlı.

[Kontrol senaryoları](../test/us-11-kontrol.md) · [Gereksinimler](../docs/gereksinimler/kadir-us-11-13-hazirlik.md)
