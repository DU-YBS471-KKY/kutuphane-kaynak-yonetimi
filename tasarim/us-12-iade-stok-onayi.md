# US 12 iade ve stok onayı ekranı ve işlem akışı

Sorumlu: Abdülkadir Güneş | Tarih: 18 Kasım 2026  
Jira: [KKY-11](https://dagdelen41.atlassian.net/browse/KKY-11) | Sprint 3 | 3 SP  
Durum: Taslak hazır. Kübra'nın bağımsız kontrolü bekleniyor.

Görevlinin iade gelen kopyayı okutup kontrol etmesini ve stoğa geri almasını aşağıdaki ekranlarla gösterdim. Taslaklar çalışan uygulama ekranı değildir. US-11'deki gibi işlem fiziksel kopya üzerinden yapılır. Bakımda durumu US-09 ile aynıdır.

## I 01 iade alma ekranı

```text
IADE AL                                 Oturum: Gorevli
Kopya barkodu  [__________] [Barkod oku]

AKTIF ODUNC KAYDI
Ogrenci        Ornek Ogrenci  2000000001
Kitap          Ornek Kitap A  K-001
Odunc tarihi   18.11.2026
Iade tarihi    03.12.2026

Kitap kontrolu
( ) Saglam  -> Musait yap
( ) Hasarli -> Bakimda yap
                              [Iptal] [Iadeyi tamamla]
```

Kopya okutulunca o kopyanın aktif ödünç kaydı görünür. Görevli kitabı kontrol edip iki seçenekten birini işaretler. Seçim yapılmadan iade tamamlanmaz.

## I 02 sağlam iade

```text
Iade alindi.
Kopya K-001    Durum MUSAIT
Odunc verilebilir kopya: 2

Iade tarihi       25.11.2026
Islemi yapan      Ornek Gorevli
```

Sağlam seçilince kopyanın durumu Müsait olur ve kitabın ödünç verilebilir kopya sayısı 1 artar. Bu kriter 1'i karşılar. Esat'ın US-06 KS-06-04 senaryosundaki iade sonrası stok artışıyla da tutarlıdır.

## I 03 hasarlı iade

```text
Iade alindi. Kopya bakima ayrildi.
Kopya K-001    Durum BAKIMDA
Odunc verilebilir kopya: 1

Iade tarihi       25.11.2026
Islemi yapan      Ornek Gorevli
```

Hasarlı seçilince kopya Bakımda olur ve ödünç verilebilir kopya sayısı artmaz. Bu kriter 2'yi karşılar. Bakım bitince kopyayı yeniden Müsait yapmak US-09 B03 ile olur.

Her iki durumda da iade tarihi ve işlemi yapan görevli kayıtta görünür. Bu kriter 3'ü karşılar. Ödünç kaydı aktif listeden çıkar, US-15'teki geçmiş listeye geçer.

## İşlem sırası

```text
Ekrani ac -> Kopya barkodunu okut -> Aktif odunc kaydi gorunur (I01)
  -> Kitabi kontrol et
  -> Saglam: Kopya MUSAIT, verilebilir sayi 1 artar (I02)
  -> Hasarli: Kopya BAKIMDA, sayi degismez (I03)
  -> Iade tarihi ve gorevli kayda yazilir -> Odunc kaydi kapanir
```

| Kabul kriteri | Tasarım kanıtı | Kontrol kaydı |
|---|---|---|
| 1 Sağlam iadede Müsait ve stok 1 artar | I01 ve I02 | KS-12-01 |
| 2 Hasarlı iadede Bakımda, stok değişmez | I01 ve I03 | KS-12-02 |
| 3 İade tarihi ve görevli kayda geçer | I02 ve I03 | KS-12-03, KS-12-04 |

## Netleşmesi gereken noktalar

Bunlar kabul kriterlerinde yok. Yeni kural eklemedim.

- Okutulan kopyanın aktif ödünç kaydı yoksa ne gösterilecek. Eray'a soracağım.
- İade tarihi geçmişse gecikme cezası bu ekranda hesaplanmıyor. Ceza US-18'de, Enes'in işi. Bu ekrandaki iade tarihi onun hesabına girdi olacak.
- Sağlam iade edilen kopyanın rezervasyonu varsa bildirim US-17'de oluşur. Kübra'nın belgesindeki bağlantıyla aynı.

[Kontrol senaryoları](../test/us-12-kontrol.md) · [Gereksinimler](../docs/gereksinimler/kadir-us-11-13-hazirlik.md)
