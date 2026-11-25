# US 12 iade ve stok onayı ekranı ve işlem akışı

Sorumlu: Abdülkadir Güneş | Tarih: 18 Kasım 2026 | Güncelleme: 25 Kasım 2026  
Jira: [KKY-11](https://dagdelen41.atlassian.net/browse/KKY-11) | Sprint 3 | 3 SP  
Durum: Eray'ın 19 ve 21 Kasım PO kararları işlendi. Kübra'nın kontrolü bekleniyor.

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
( ) Saglam  -> Musait, sira varsa Rezerve
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

## I 04 aktif ödünç kaydı olmayan kopya

```text
IADE AL                                 Oturum: Gorevli
Kopya barkodu  [K-002     ] [Barkod oku]

Bu kopya icin aktif odunc kaydi bulunmamaktadir.
                              [Yeni islem]
```

Okutulan kopyanın aktif ödünç kaydı yoksa iade başlatılmaz. Kitap kontrolü seçenekleri ve "Iadeyi tamamla" düğmesi gösterilmez. Kopyanın durumu ve stok sayısı değişmez. Bu, Eray'ın 19 Kasım kararıdır.

## I 05 rezervasyonlu kopyanın sağlam iadesi

```text
Iade alindi. Kopya rezervasyon sirasina ayrildi.
Kitap          Ornek Kitap C
Kopya K-101    Durum REZERVE
Ayrildigi ogrenci   Ornek Ogrenci A  2000000011  sira 1
Bildirim zamani     25.11.2026 10:00
Teslim son zamani   27.11.2026 10:00   48 saat
Odunc verilebilir kopya: 0

Iade tarihi       25.11.2026
Islemi yapan      Ornek Gorevli
```

Kitabın aktif rezervasyon sırası varsa sağlam iade edilen kopya Müsait olmaz, Rezerve olur. Kopya genel ödünç alıma açılmadığı için ödünç verilebilir kopya sayısı artmaz. Kopya sıradaki ilk öğrenci için bildirimden sonra 48 saat tutulur. Öğrenci gelirse US-11'de ona ödünç verilir. Gelmezse rezervasyon iptal olur ve kopya sıradaki öğrenciye, sıra boşsa Müsait durumuna geçer. Bu Eray'ın 21 Kasım kararıdır. Sıra ve 48 saat kuralı Kübra'nın US-14 R06 bölümüyle aynıdır. İade tarihi ve görevli I02'deki gibi kayda geçer.

## İşlem sırası

```text
Ekrani ac -> Kopya barkodunu okut
  -> Aktif odunc kaydi var mi? Hayir: I04 uyarisi, iade baslamaz
  -> Evet: Aktif odunc kaydi gorunur (I01)
  -> Kitabi kontrol et
  -> Saglam: Kitabin aktif rezervasyon sirasi var mi?
       Hayir: Kopya MUSAIT, verilebilir sayi 1 artar (I02)
       Evet: Kopya REZERVE, sira 1 icin 48 saat tutulur (I05), US-14 R06 ve US-17
  -> Hasarli: Kopya BAKIMDA, sayi degismez (I03)
  -> Iade tarihi ve gorevli kayda yazilir -> Odunc kaydi kapanir
```

| Kabul kriteri veya PO kararı | Tasarım kanıtı | Kontrol kaydı |
|---|---|---|
| 1 Sağlam iadede Müsait ve stok 1 artar | I01 ve I02 | KS-12-01 |
| 2 Hasarlı iadede Bakımda, stok değişmez | I01 ve I03 | KS-12-02 |
| 3 İade tarihi ve görevli kayda geçer | I02 ve I03 | KS-12-03, KS-12-04 |
| PO kararı, aktif kaydı olmayan kopyada uyarı | I04 ve işlem sırası | KS-12-05 |
| PO kararı, rezervasyonlu kopya sağlam iadede Rezerve olur | I05 ve işlem sırası | KS-12-06 |

## PO kararları

Eray 19 Kasım'da PR #40'ta şu kararı verdi. I04 ekranına ve KS-12-05 senaryosuna işledim.

- Okutulan kopyanın aktif ödünç kaydı yoksa iade başlatılmaz ve görevliye "Bu kopya için aktif ödünç kaydı bulunmamaktadır" uyarısı gösterilir.

Eray 21 Kasım'da PR #40 ve PR #44'te şu kararı verdi. I05 ekranına ve KS-12-06 senaryosuna işledim.

- Sağlam iade edilen kopyanın aktif rezervasyon sırası varsa kopya genel ödünç alıma açılmaz ve yalnızca sıradaki ilk öğrenciye verilir. Bildirimden sonra 48 saat bu öğrenci için tutulur.

## Bağlantılı işler

- İade tarihi geçmişse gecikme cezası bu ekranda hesaplanmıyor. Ceza US-18'de, Enes'in işi. Bu ekrandaki iade tarihi onun hesabına girdi olacak.
- Sağlam iade edilen kopya Rezerve olunca sıradaki öğrenciye bildirim US-17'de oluşur. 48 saat bildirim anından başlar. Kübra'nın US-14 R06 bölümüyle aynı.

[Kontrol senaryoları](../test/us-12-kontrol.md) · [Gereksinimler](../docs/gereksinimler/kadir-us-11-13-hazirlik.md)
