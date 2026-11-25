# US 14 ödünçteki kitabı sırayla rezerve etme ekranı ve sıra kuralları

Sorumlu: Kübra Şen | Tarih: 20 Kasım 2026 | Güncelleme: 25 Kasım 2026  
Jira: [KKY-21](https://dagdelen41.atlassian.net/browse/KKY-21) | Sprint 3 | 5 SP  
Durum: Eray'ın 21 Kasım PO kararları işlendi. Kadir'in 25 Kasım bağımsız kontrolünde 13 senaryonun 13'ü uyumlu (PR #53).

Öğrencinin tüm kopyaları ödünçte olan bir kitap için rezervasyon sırasına girmesini, aynı kitap için ikinci kez sıraya girememesini ve sıranın nasıl korunduğunu aşağıdaki ekranlarla gösterdim. Taslaklar çalışan uygulama ekranı değildir. Rezervasyon kitabın kendisi için yapılır, tek bir kopya için yapılmaz. Kopya ve durum adları (Müsait, Ödünçte, Bakımda) US-09, US-11 ve US-12 ile aynıdır. Eray'ın 21 Kasım kararıyla kopyalar için bir durum daha ekledim: Rezerve. Rezerve Et düğmesi Esat'ın US-06 kitap detayı taslağındaki düğmedir.

## R 01 kitap detayında rezervasyon

```text
KITAP DETAYI                            Oturum: Ogrenci
Ornek Kitap C
Yazar    Ornek Yazar          ISBN  9781234567800

DURUM: TUM KOPYALAR ODUNCTE        Musait: 0 / 2
Kopya  K-101  ODUNCTE   Iade tarihi 28.11.2026
Kopya  K-102  ODUNCTE   Iade tarihi 02.12.2026

Bekleyen rezervasyon: 0
                                   [Rezerve et]
```

Kitabın ödünç verilebilir kopyalarının hepsi ödünçteyken giriş yapmış öğrenci Rezerve et düğmesini görür. Öğrenci girişi US-02 oturumuyla yapılır. Oturum yoksa düğme yerine "Rezervasyon için giriş yapın" bağlantısı görünür. Bakımdaki kopyalar ödünç verilebilir sayılmaz. Bu yüzden bazı kopyalar Bakımda, diğerleri Ödünçteyse ve müsait kopya yoksa rezervasyon yapılabilir.

## R 02 rezervasyon yapılamayan durumlar

| Durum | Gösterilecek bilgi | Sonuç |
|---|---|---|
| En az bir kopya Müsait | "Bu kitabın rafta müsait kopyası var. Rezervasyon yapmadan doğrudan ödünç alabilirsiniz." | Rezerve et düğmesi gösterilmez. Kayıt oluşmaz. |
| Tüm kopyalar Bakımda | "Tüm kopyalar bakımda olduğu için rezervasyon yapılamaz." | Rezerve et düğmesi gösterilmez. Kayıt oluşmaz. |
| Hesap pasif | "Hesabınız aktif olmadığı için rezervasyon yapamazsınız." | Kayıt oluşmaz. |
| Gecikmiş veya cezalı kitap var | "Gecikmiş veya cezalı kitabınız olduğu için rezervasyon yapamazsınız." | Kayıt oluşmaz. |
| 2 aktif rezervasyon var | "Aynı anda en fazla 2 aktif rezervasyonunuz olabilir." | Kayıt oluşmaz. Mevcut rezervasyonlar Rezervasyonlarım ekranında görünür. |

Bu beş satır Eray'ın 21 Kasım kararlarıdır. Hesap kontrolü, Kadir'in US-11'deki ödünç kontrolüyle aynı kuraldır. Pasif hesap ve gecikmiş kitap örneklerinde US-11 kontrol dosyasındaki 2000000004 ve 2000000005 numaralı öğrencileri kullandım.

## R 03 oluşturulan rezervasyon

```text
Rezervasyonunuz olusturuldu.

Kitap          Ornek Kitap C
Talep tarihi   19.11.2026 10:05
Sira no        1
Durum          AKTIF
Aktif rezervasyon  2 / 2
                                   [Rezervasyonlarim]
```

Talep tarihi ve saati ile sıra numarası rezervasyon kaydına yazılır. Sıra numarası, o kitap için aktif talepler arasında talep zamanına göre verilir. Bu kriter 1'i karşılar.

## R 04 aynı kitap için ikinci talep

```text
Bu kitap icin aktif rezervasyonunuz var.

Kitap          Ornek Kitap C
Talep tarihi   19.11.2026 10:05
Siradaki yeriniz 1
                        [Rezervasyonu iptal et] [Kapat]
```

Öğrencinin aynı kitap için aktif rezervasyonu varsa yeni kayıt oluşmaz. Ekranda mevcut rezervasyonun bilgisi gösterilir. Bu kontrol, 2 rezervasyon sınırından önce yapılır. Bu kriter 2'yi karşılar.

## R 05 rezervasyonlarım ve iptal

```text
REZERVASYONLARIM                        Oturum: Ogrenci
Kitap          Talep tarihi       Siradaki yeriniz  Durum   Islem
Ornek Kitap C  19.11.2026 10:05   1                 AKTIF   [Iptal et]
Ornek Kitap G  17.11.2026 14:00   2                 AKTIF   [Iptal et]
Aktif rezervasyon  2 / 2

Iptal onayi: "Ornek Kitap C rezervasyonunuz iptal edilecek ve siradan cikacaksiniz."
                                         [Vazgec] [Iptal et]
```

Öğrenci kendi rezervasyonunu iptal edince kaydın durumu İptal olur ve sıradan çıkar. Arkasındaki öğrencilerin sıradaki yeri bir öne geçer. Öğrenci yalnızca kendi rezervasyonlarını görür. Bu kriter 3'ün iptal kısmını karşılar.

## R 06 sıra kuralı ve iade sonrası teslim

| Talep zamanı | Öğrenci | Sıra no | Durum | A iptal ettikten sonra sıradaki yer |
|---|---|---|---|---|
| 19.11.2026 10:05 | Örnek Öğrenci A | 1 | Aktif → İptal | Sırada değil |
| 19.11.2026 11:20 | Örnek Öğrenci B | 2 | Aktif | 1 |
| 20.11.2026 09:00 | Örnek Öğrenci C | 3 | Aktif | 2 |

Sıra yalnızca talep zamanına göre belirlenir. Bir kopya US-12'de sağlam iade edildiğinde, aktif talepler arasında talep zamanı en erken olan öğrenci ilk aktif talep sahibi olarak belirlenir. İptal edilmiş talepler atlanır. Bu kriter 3'ü karşılar.

```text
Iade sonrasi (Ornek Kitap C, K-101 saglam iade edildi)
Kopya K-101    Durum REZERVE
Ayrildigi ogrenci   Ornek Ogrenci A (sira 1)
Bildirim zamani     25.11.2026 10:00
Teslim son zamani   27.11.2026 10:00   (48 saat)
```

Eray'ın 21 Kasım kararına göre aktif rezervasyon sırası olan kitabın kopyası sağlam iade edilince Müsait olmaz, Rezerve olur. Kopya genel ödünç alıma açılmaz ve yalnızca ilk aktif talep sahibine ödünç verilebilir. Kopya bu öğrenci için bildirimden sonra 48 saat ayrılır.

- Öğrenci 48 saat içinde gelirse kopya US-11'deki ödünç işlemiyle ona verilir. Rezervasyonun durumu Tamamlandı olur ve sıradan çıkar.
- 48 saat içinde teslim alınmazsa rezervasyon iptal edilir. Kopya sıradaki bir sonraki aktif talep sahibi için Rezerve kalır ve onun için 48 saat yeniden başlar.
- Sırada başka aktif talep yoksa kopya Müsait olur.

Bildirimin kendisi US-17'nin işidir ve Sprint 4'te hazırlanacak. 48 saat bildirim anından başlar. Hasarlı iade edilip Bakımda olan kopya US-12 kriter 2 gereği kullanılabilir olmadığı için ilk aktif talep sahibi belirlenmez ve kopya Rezerve olmaz.

## İşlem sırası

```text
Kitap detayini ac (R01)
  -> Oturum var mi? Hayir: "Rezervasyon icin giris yapin"
  -> Hesap aktif mi, gecikmis veya cezali kitap var mi? Sorun varsa: R02, kayit yok
  -> En az bir kopya Musait mi? Evet: R02, kayit yok
  -> Tum kopyalar Bakimda mi? Evet: R02, kayit yok
  -> Ogrencinin bu kitap icin aktif rezervasyonu var mi? Evet: R04, yeni kayit yok
  -> Ogrencinin 2 aktif rezervasyonu var mi? Evet: R02, kayit yok
  -> Hayir: Talep tarihi ve sira no kaydedilir (R03)
Iptal: Rezervasyonlarim (R05) -> Iptal et -> Kayit IPTAL, siradan cikar
Iade:  US-12 saglam iade -> Aktif sira var mi?
         Evet: Kopya REZERVE, ilk aktif talep sahibi belirlenir (R06) -> US-17 bildirim -> 48 saat
               Teslim alindi: US-11 odunc, rezervasyon TAMAMLANDI
               48 saat doldu: rezervasyon IPTAL, siradaki talep sahibi icin 48 saat
         Hayir: Kopya MUSAIT (US-12 I02)
```

| Kabul kriteri veya PO kararı | Tasarım kanıtı | Kontrol kaydı |
|---|---|---|
| 1 Tüm kopyaları ödünçte kitap için rezervasyon, talep tarihi ve sıra no kaydedilir | R01 ve R03 | KS-14-01 |
| 2 Aynı kitap için ikinci aktif rezervasyon oluşmaz, mevcut bilgi gösterilir | R04 | KS-14-02 |
| 3 Sıra talep zamanına göre korunur, iade sonrası ilk aktif talep sahibi belirlenir, iptal eden sıradan çıkar | R05, R06 ve işlem sırası | KS-14-03, KS-14-04, KS-14-05 |
| PO kararı, müsait kopya varken veya tüm kopyalar bakımdayken rezervasyon yapılamaz | R01, R02 | KS-14-06, KS-14-07 |
| PO kararı, en fazla 2 aktif rezervasyon | R02, R05 | KS-14-08 |
| PO kararı, pasif veya cezalı hesap rezervasyon yapamaz | R02 | KS-14-09, KS-14-10 |
| PO kararı, iade edilen kopya sıradaki öğrenciye 48 saat ayrılır | R06 ve işlem sırası | KS-14-11, KS-14-12, KS-14-13 |

## PO kararları

Eray 21 Kasım'da PR #44 ve PR #40'ta şu kararları verdi. Yukarıdaki ekranlara ve senaryolara işledim.

- Kitabın en az bir Müsait kopyası varsa rezervasyon yapılamaz, öğrenciye rafta mevcut olduğu ve doğrudan ödünç alabileceği söylenir. Tüm kopyalar Bakımda ise de rezervasyon yapılamaz. Rezervasyon yalnızca ödünç verilebilir kopyaların hepsi Ödünçteyken yapılabilir.
- Bir öğrencinin aynı anda en fazla 2 aktif rezervasyonu olabilir. Aynı kitap için ikinci rezervasyon yapılamaz.
- Hesabı pasif olan ya da gecikmiş veya cezalı kitabı olan öğrenci rezervasyon yapamaz.
- Sağlam iade edilen kopyanın aktif rezervasyon sırası varsa kopya genel ödünç alıma açılmaz ve yalnızca sıradaki ilk öğrenciye verilir. Bildirimden sonra 48 saat bu öğrenci için tutulur. Teslim alınmazsa rezervasyon iptal edilir ve kopya sıradaki öğrenciye, sıra boşsa Müsait durumuna geçer.

## Bağlantılı işler

- US-11 ve US-12 (Kadir, KKY-10 ve KKY-11): 48 saat kuralı iki dosyaya da girecek. US-12'de sağlam iade edilen kopyanın aktif rezervasyonu varsa durum Müsait değil Rezerve olur. US-11'de Rezerve kopya yalnızca ayrıldığı öğrenciye verilir. Rezerve durum adını Kadir ile aynı kullanıyoruz.
- US-13 (Kadir, KKY-12): Kitap için başka öğrencinin aktif rezervasyonu varsa süre uzatma reddedilir. Kadir'in KS-13-04 ve KS-13-08 senaryoları bu belgedeki Aktif durumdaki rezervasyonu kullanır. İptal edilmiş ya da tamamlanmış rezervasyon uzatmayı engellemez.
- US-17 (benim, KKY-24, Sprint 4): Bildirim, R06'da belirlenen ilk aktif talep sahibi için oluşturulacak. 48 saat bildirim anından başlar.

## Netleşmesi gereken nokta

Bu kabul kriterlerinde yok. Yeni kural eklemedim.

- Aynı saniyede gelen iki talebin sırası. US-17 ile birlikte Sprint 4'te netleşecek.

Örnek Öğrenci A, B ve C adları yalnızca 2000000011–2000000013 için kullanılır. Kadir'in US-11 ve US-12 rezerve senaryoları da aynı öğrencileri kullanır. US-15'teki öğrenciler (2000000001–2000000003) numarayla anılır (#54).

[Kontrol senaryoları](../test/us-14-kontrol.md) · [Gereksinimler](../docs/gereksinimler/kubra-us-14-17-hazirlik.md)
