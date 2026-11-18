# US 13 ödünç süresini uzatma ekranı ve işlem akışı

Sorumlu: Abdülkadir Güneş | Tarih: 18 Kasım 2026  
Jira: [KKY-12](https://dagdelen41.atlassian.net/browse/KKY-12) | Sprint 3 | 3 SP  
Durum: Taslak hazır. Kübra'nın bağımsız kontrolü bekleniyor.

Öğrencinin kendi ödünç listesinden süreyi 7 gün uzatmasını aşağıdaki ekranlarla gösterdim. Taslaklar çalışan uygulama ekranı değildir. Liste, Kübra'nın US-15 aktif ödünç listesiyle aynı yerdir. Rezervasyon bilgisi US-14'teki kayıttan gelir.

## U 01 aktif ödünç listesi

```text
ODUNC ALDIKLARIM                        Oturum: Ogrenci
Kitap          Odunc tarihi  Iade tarihi  Uzatma   Islem
Ornek Kitap A  18.11.2026    03.12.2026   0 / 1    [Sureyi uzat]
Ornek Kitap B  10.11.2026    25.11.2026   1 / 1    [Sureyi uzat]
```

Her satırda kalan uzatma hakkı görünür. Öğrenci yalnızca kendi kayıtlarını görür. Bu US-15 kriter 1 ile aynıdır.

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

Uzatma yalnızca iade tarihi geçmeden ve bir kez yapılır. Bu kriter 1'i karşılar. Rezervasyon varsa uzatma reddedilir ve sebebi yazılır. Bu kriter 2'yi karşılar. Rezerve eden öğrencinin adı gösterilmez.

## İşlem sırası

```text
Listeyi ac -> Sureyi uzat
  -> Iade tarihi gecmis mi? Evet: U03 red
  -> Uzatma hakki kullanilmis mi? Evet: U03 red
  -> US-14'te aktif rezervasyon var mi? Evet: U03 red, sebep gosterilir
  -> Hayir: Iade tarihi + 7 gun -> U02 onay -> Listede yeni tarih
```

| Kabul kriteri | Tasarım kanıtı | Kontrol kaydı |
|---|---|---|
| 1 İade tarihi geçmeden ve bir kez | U01 ve U03 | KS-13-02, KS-13-03 |
| 2 Rezervasyon varsa red ve sebep | U03 ve işlem sırası | KS-13-04 |
| 3 Yeni tarih listede görünür | U02 | KS-13-01, KS-13-05 |

## Netleşmesi gereken noktalar

Bunlar kabul kriterlerinde yok. Yeni kural eklemedim.

- İade tarihinin tam günü uzatma yapılabilir mi. Kriter "geçmeden" diyor. Eray'a soracağım.
- Uzatmayı görevli de öğrenci adına yapabilir mi. Story öğrenci diyor. Eray'a soracağım.

[Kontrol senaryoları](../test/us-13-kontrol.md) · [Gereksinimler](../docs/gereksinimler/kadir-us-11-13-hazirlik.md)
