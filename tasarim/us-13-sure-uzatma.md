# US 13 ödünç süresini uzatma ekranı ve işlem akışı

Sorumlu: Abdülkadir Güneş | Tarih: 18 Kasım 2026 | Güncelleme: 25 Kasım 2026  
Jira: [KKY-12](https://dagdelen41.atlassian.net/browse/KKY-12) | Sprint 3 | 3 SP  
Durum: Eray'ın 19 Kasım PO kararları işlendi. Liste sütunları Kübra'nın US-15 L01 taslağıyla eşitlendi. Kübra'nın nihai kontrolü bekleniyor.

Öğrencinin kendi ödünç listesinden süreyi 7 gün uzatmasını aşağıdaki ekranlarla gösterdim. Taslaklar çalışan uygulama ekranı değildir. Liste, Kübra'nın US-15 aktif ödünç listesiyle aynı yerdir. Rezervasyon bilgisi US-14'teki kayıttan gelir. Örneklerde bugünün tarihi 20.11.2026'dır.

## U 01 aktif ödünç listesi

```text
ODUNC KAYITLARIM                        Oturum: Ogrenci (2000000001)
[ Aktif ]  [ Gecmis ]

Kitap          Odunc tarihi  Guncel iade  Durum            Uzatma  Islem
Ornek Kitap A  18.11.2026    03.12.2026   ODUNCTE          0 / 1   [Sureyi uzat]
Ornek Kitap B  04.11.2026    19.11.2026   ! GECIKMIS       0 / 1   -
```

Sütunlar ve örnek kayıtlar US-15 L01 ile aynıdır. Her satırda kitap adı, ödünç tarihi, güncel iade tarihi, durum ve uzatma hakkı görünür. Öğrenci yalnızca kendi kayıtlarını görür. Bu US-15 kriter 1 ile aynıdır. İade tarihi geçmiş kayıtta "Sureyi uzat" düğmesi gösterilmez.

## U 02 onaylanan uzatma

```text
Sure uzatildi.
Ornek Kitap A
Eski iade tarihi   03.12.2026
Yeni iade tarihi   10.12.2026
Uzatma hakki       1 / 1 kullanildi
```

Uzatma onaylanınca iade tarihi 7 gün ileri alınır ve listede yeni tarih görünür. Bu kriter 3'ü karşılar. US-15 listesi ve US-16 hatırlatması bu yeni tarihi kullanır.

## U 03 reddedilen uzatma

| Durum | Gösterilecek bilgi | Sonuç |
|---|---|---|
| Uzatma hakkı kullanılmış | "Bu kitap için uzatma hakkınızı kullandınız." | İade tarihi değişmez. |
| İade tarihi geçmiş | "İade tarihi geçtiği için süre uzatılamaz." | İade tarihi değişmez. |
| Başka öğrenci rezerve etmiş | "Bu kitap başka bir öğrenci tarafından rezerve edildiği için süre uzatılamaz." | İade tarihi değişmez. |

Uzatma yalnızca iade tarihi geçmeden ve bir kez yapılır. Bu kriter 1'i karşılar. İade tarihinin kendisi olan gün henüz geçmiş sayılmaz, o gün uzatma yapılabilir. Bu Eray'ın 19 Kasım kararıdır ve US-15'teki gecikme etiketiyle aynıdır. Rezervasyon varsa uzatma reddedilir ve sebebi yazılır. Bu kriter 2'yi karşılar. Rezerve eden öğrencinin adı gösterilmez.

## U 04 görevlinin öğrenci adına uzatması

```text
SURE UZAT                               Oturum: Gorevli
Ogrenci karti  [__________] [Barkod oku]

Ornek Ogrenci  2000000001
Kitap          Guncel iade  Durum      Uzatma  Islem
Ornek Kitap A  03.12.2026   ODUNCTE    0 / 1   [Sureyi uzat]

Sure uzatildi. Yeni iade tarihi 10.12.2026
Uzatmayi yapan   Ornek Gorevli, ogrencinin talebiyle
```

Öğrenci isterse görevli de öğrencinin kartını okutup süreyi uzatabilir. Kurallar öğrencinin kendi yaptığı uzatmayla aynıdır. Rezervasyon varsa, hak kullanılmışsa ya da iade tarihi geçmişse U03'teki uyarılar çıkar. Uzatmayı yapan görevli kayda geçer. Bu Eray'ın 19 Kasım kararıdır.

## İşlem sırası

```text
Ogrenci kendi listesinden ya da gorevli ogrenci kartiyla -> Sureyi uzat
  -> Iade tarihi bugunden once mi? Evet: U03 red
     Iade gunu ise gecmis sayilmaz, devam
  -> Uzatma hakki kullanilmis mi? Evet: U03 red
  -> US-14'te aktif rezervasyon var mi? Evet: U03 red, sebep gosterilir
  -> Hayir: Iade tarihi + 7 gun -> U02 onay -> Listede yeni tarih
  -> Gorevli yaptiysa uzatmayi yapan gorevli kayda yazilir
```

| Kabul kriteri veya PO kararı | Tasarım kanıtı | Kontrol kaydı |
|---|---|---|
| 1 İade tarihi geçmeden ve bir kez | U01 ve U03 | KS-13-02, KS-13-03 |
| 2 Rezervasyon varsa red ve sebep | U03 ve işlem sırası | KS-13-04 |
| 3 Yeni tarih listede görünür | U02 | KS-13-01, KS-13-05 |
| PO kararı, iade gününde uzatma yapılabilir | U03 ve işlem sırası | KS-13-06 |
| PO kararı, görevli öğrenci adına uzatabilir | U04 | KS-13-07, KS-13-08 |

## PO kararları

Eray 19 Kasım'da PR #40'ta şu kararları verdi. Yukarıdaki ekranlara ve senaryolara işledim.

- İade tarihinin son günü henüz geçmiş sayılmaz. Rezervasyon yoksa ve uzatma hakkı kullanılmadıysa o gün de 7 gün uzatma yapılabilir.
- Öğrencinin talebiyle görevli de aynı kurallarla öğrenci adına uzatma yapabilir.

[Kontrol senaryoları](../test/us-13-kontrol.md) · [Gereksinimler](../docs/gereksinimler/kadir-us-11-13-hazirlik.md)
