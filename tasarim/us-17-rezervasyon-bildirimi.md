# US 17 rezerve kitap iade edilince bildirim

Sorumlu: Kübra Şen | Tarih: 25 Kasım 2026  
Jira: [KKY-24](https://dagdelen41.atlassian.net/browse/KKY-24) | Sprint 4 | 3 SP  
Durum: Sprint 4 için taslak. Planning'de ekiple gözden geçirilecek.

Rezerve edilen kitabın kopyası iade edilip sıra öğrenciye geldiğinde oluşacak bildirimi aşağıdaki örnek ve kurallarla gösterdim. Bu aşamada gerçek kullanıcıya mesaj gönderilmez. Alıcı, US-14 R06'daki ilk aktif talep sahibidir. Kopyanın Rezerve olması US-12 I05'teki sağlam iadeyle olur. 48 saat kuralı Eray'ın 21 Kasım kararıdır ve bildirim anından başlar.

## N 01 bildirim örneği

```text
Kime     : Ornek Ogrenci A (2000000011)
Konu     : Rezerve ettiginiz kitap teslim alinabilir

"Ornek Kitap C" kitabinin bir kopyasi sizin icin ayrildi.
Kitabi 27.11.2026 10:00'a kadar kutuphaneden teslim alabilirsiniz.
Bu sure icinde teslim alinmazsa rezervasyonunuz iptal edilir.
```

Bildirimde kitap adı ve teslim alınabilir olduğu bilgisi bulunur. Teslim son zamanı bildirimden 48 saat sonradır. Bu kriter 2'nin içerik kısmını karşılar.

## N 02 alıcı ve tekrar kuralları

| Durum | Sonuç |
|---|---|
| Kopya sağlam iade edildi, kitabın aktif rezervasyon sırası var | Kopya Rezerve olur; yalnızca ilk aktif talep sahibi için bildirim oluşur. |
| Sıradaki diğer öğrenciler | Aynı kopya için eşzamanlı bildirim almazlar. |
| Aynı iade ve aynı rezervasyon için ikinci değerlendirme | Yeni bildirim oluşmaz. |
| İlk talep sahibinin rezervasyonu iptal edilmiş | Atlanır; sıradaki aktif talep sahibi için bildirim oluşur. |
| İlk talep sahibi 48 saat içinde teslim almadı | Rezervasyonu iptal olur; sıradaki aktif talep sahibi için yeni bildirim oluşur. |
| Kopya hasarlı iade edildi (Bakımda) | Kopya kullanılabilir olmadığı için bildirim oluşmaz. |

Bu kriter 1, 2 ve 3'ü karşılar.

## İşlem sırası

```text
US-12 iade -> Kopya saglam mi? Hayir: Bakimda, bildirim yok
  -> Kitabin aktif rezervasyon sirasi var mi? Hayir: Musait, bildirim yok
  -> Evet: Iptal edilmis talepler atlanir, ilk aktif talep sahibi belirlenir (US-14 R06)
  -> Bu iade ve bu rezervasyon icin bildirim var mi? Evet: yeni bildirim yok
  -> Hayir: N01 bildirimi olusur, 48 saat baslar
48 saat doldu, teslim alinmadi -> rezervasyon IPTAL -> siradaki aktif talep icin N01
```

| Kabul kriteri | Tasarım kanıtı | Kontrol kaydı |
|---|---|---|
| 1 Kullanılabilir kopyada ilk aktif talep sahibi için bildirim | N02 birinci satır, işlem sırası | KS-17-01, KS-17-06 |
| 2 Kitap adı ve teslim bilgisi; diğerlerine eşzamanlı bildirim yok | N01, N02 ikinci satır | KS-17-02 |
| 3 Tekrar yok; iptal edilen atlanır, sıradaki değerlendirilir | N02, işlem sırası | KS-17-03, KS-17-04, KS-17-05 |

## Planning'de netleşecek noktalar

Kabul kriterlerinde yok, yeni kural eklemedim:

- Bildirim kanalı (e-posta, uygulama içi ya da ikisi) ve öğrencinin tercihinin etkisi.
- Aynı anda birden fazla kopya iade edilirse tahsis sırası.

[Kontrol senaryoları](../test/us-17-kontrol.md) · [US-14 rezervasyon](us-14-rezervasyon.md) · [Gereksinimler](../docs/gereksinimler/kubra-us-14-17-hazirlik.md)
