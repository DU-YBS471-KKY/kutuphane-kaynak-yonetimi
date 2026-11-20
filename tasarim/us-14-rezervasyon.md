# US 14 ödünçteki kitabı sırayla rezerve etme ekranı ve sıra kuralları

Sorumlu: Kübra Şen | Tarih: 20 Kasım 2026  
Jira: [KKY-21](https://dagdelen41.atlassian.net/browse/KKY-21) | Sprint 3 | 5 SP  
Durum: Taslak hazır. Bağımsız kontrol bekleniyor.

Öğrencinin tüm kopyaları ödünçte olan bir kitap için rezervasyon sırasına girmesini, aynı kitap için ikinci kez sıraya girememesini ve sıranın nasıl korunduğunu aşağıdaki ekranlarla gösterdim. Taslaklar çalışan uygulama ekranı değildir. Rezervasyon kitabın kendisi için yapılır, tek bir kopya için yapılmaz. Kopya ve durum adları (Müsait, Ödünçte, Bakımda) US-09, US-11 ve US-12 ile aynıdır. Rezerve Et düğmesi Esat'ın US-06 kitap detayı taslağındaki düğmedir.

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

Kitabın tüm kopyaları ödünçteyken giriş yapmış öğrenci Rezerve et düğmesini görür. Öğrenci girişi US-02 oturumuyla yapılır. Oturum yoksa düğme yerine "Rezervasyon için giriş yapın" bağlantısı görünür.

## R 02 oluşturulan rezervasyon

```text
Rezervasyonunuz olusturuldu.

Kitap          Ornek Kitap C
Talep tarihi   19.11.2026 10:05
Sira no        1
Durum          AKTIF
                                   [Rezervasyonlarim]
```

Talep tarihi ve saati ile sıra numarası rezervasyon kaydına yazılır. Sıra numarası, o kitap için aktif talepler arasında talep zamanına göre verilir. Bu kriter 1'i karşılar.

## R 03 aynı kitap için ikinci talep

```text
Bu kitap icin aktif rezervasyonunuz var.

Kitap          Ornek Kitap C
Talep tarihi   19.11.2026 10:05
Siradaki yeriniz 1
                        [Rezervasyonu iptal et] [Kapat]
```

Öğrencinin aynı kitap için aktif rezervasyonu varsa yeni kayıt oluşmaz. Ekranda mevcut rezervasyonun bilgisi gösterilir. Bu kriter 2'yi karşılar.

## R 04 rezervasyonlarım ve iptal

```text
REZERVASYONLARIM                        Oturum: Ogrenci
Kitap          Talep tarihi       Siradaki yeriniz  Durum   Islem
Ornek Kitap C  19.11.2026 10:05   1                 AKTIF   [Iptal et]

Iptal onayi: "Ornek Kitap C rezervasyonunuz iptal edilecek ve siradan cikacaksiniz."
                                         [Vazgec] [Iptal et]
```

Öğrenci kendi rezervasyonunu iptal edince kaydın durumu İptal olur ve sıradan çıkar. Arkasındaki öğrencilerin sıradaki yeri bir öne geçer. Öğrenci yalnızca kendi rezervasyonlarını görür. Bu kriter 3'ün iptal kısmını karşılar.

## R 05 sıra kuralı örneği

| Talep zamanı | Öğrenci | Sıra no | Durum | A iptal ettikten sonra sıradaki yer |
|---|---|---|---|---|
| 19.11.2026 10:05 | Örnek Öğrenci A | 1 | Aktif → İptal | Sırada değil |
| 19.11.2026 11:20 | Örnek Öğrenci B | 2 | Aktif | 1 |
| 20.11.2026 09:00 | Örnek Öğrenci C | 3 | Aktif | 2 |

Sıra yalnızca talep zamanına göre belirlenir. Bir kopya US-12'de sağlam iade edilip Müsait olduğunda, aktif talepler arasında talep zamanı en erken olan öğrenci ilk aktif talep sahibi olarak belirlenir. İptal edilmiş talepler atlanır. Bu kriter 3'ü karşılar. Belirlenen öğrenciye bildirim gönderilmesi US-17'nin işidir ve Sprint 4'te hazırlanacak. Hasarlı iade edilip Bakımda olan kopya US-12 kriter 2 gereği kullanılabilir olmadığı için ilk aktif talep sahibi belirlenmez.

## İşlem sırası

```text
Kitap detayini ac (R01)
  -> Tum kopyalar oduncte mi? Hayir: Rezerve et dugmesi yok (PO karari bekliyor, asagida)
  -> Evet: Rezerve et
  -> Ogrencinin bu kitap icin aktif rezervasyonu var mi?
       Evet: R03, yeni kayit yok, mevcut bilgi gosterilir
       Hayir: Talep tarihi ve sira no kaydedilir (R02)
Iptal: Rezervasyonlarim (R04) -> Iptal et -> Kayit IPTAL, siradan cikar
Iade:  US-12 saglam iade -> Kopya MUSAIT -> Ilk aktif talep sahibi belirlenir (R05) -> US-17
```

| Kabul kriteri | Tasarım kanıtı | Kontrol kaydı |
|---|---|---|
| 1 Tüm kopyaları ödünçte kitap için rezervasyon, talep tarihi ve sıra no kaydedilir | R01 ve R02 | KS-14-01 |
| 2 Aynı kitap için ikinci aktif rezervasyon oluşmaz, mevcut bilgi gösterilir | R03 | KS-14-02 |
| 3 Sıra talep zamanına göre korunur, iade sonrası ilk aktif talep sahibi belirlenir, iptal eden sıradan çıkar | R04, R05 ve işlem sırası | KS-14-03, KS-14-04, KS-14-05 |

## Bağlantılı işler

- US-13 (Kadir, KKY-12): Kitap için başka öğrencinin aktif rezervasyonu varsa süre uzatma reddedilir. Kadir'in KS-13-04 senaryosu bu belgedeki Aktif durumdaki rezervasyonu kullanır. İptal edilmiş rezervasyon uzatmayı engellemez.
- US-12 (Kadir, KKY-11): Sağlam iade kopyayı Müsait yapar. İlk aktif talep sahibi bu olaydan sonra belirlenir.
- US-17 (benim, KKY-24, Sprint 4): Bildirim, R05'te belirlenen ilk aktif talep sahibi için oluşturulacak.

## Netleşmesi gereken noktalar

Bunlar kabul kriterlerinde yok. Yeni kural eklemedim, PO kararına bırakıyorum.

- Kitabın müsait kopyası varken rezervasyon yapılabilir mi? Taslakta düğmeyi yalnızca tüm kopyalar ödünçteyken gösterdim. Bir kopya Bakımda, diğerleri Ödünçteyse ne olacağını da Eray'a soracağım.
- Bir öğrencinin aynı anda kaç kitap için rezervasyonu olabilir? US-11'deki 3 kitaplık ödünç sınırı rezervasyon için de geçerli mi? Eray'a soracağım.
- Pasif veya cezalı hesap rezervasyon yapabilir mi? Eray US-11 için bu hesaplarda ödünç vermeyi engelledi. Aynı kural rezervasyona da uygulanacak mı? Eray'a soracağım.
- İade edilen kopya, ilk aktif talep sahibi teslim alana kadar başka bir öğrenciye ödünç verilebilir mi? Bu, Kadir'in US-11 dosyasındaki ortak sorudur. Kadir ile birlikte Eray'a soracağız.
- Aynı saniyede gelen iki talebin sırası ve teslim alma için bekleme süresi. Bekleme süresi US-17'ye bağlı olduğu için Sprint 4'te netleşecek.

[Kontrol senaryoları](../test/us-14-kontrol.md) · [Gereksinimler](../docs/gereksinimler/kubra-us-14-17-hazirlik.md)
