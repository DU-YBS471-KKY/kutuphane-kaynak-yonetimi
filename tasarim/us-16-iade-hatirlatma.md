# US 16 iade tarihine 2 gün kala e-posta hatırlatması

Sorumlu: Kübra Şen | Tarih: 25 Kasım 2026  
Jira: [KKY-23](https://dagdelen41.atlassian.net/browse/KKY-23) | Sprint 4 | 3 SP  
Durum: Sprint 4 için taslak. Planning'de ekiple gözden geçirilecek.

Öğrencinin iade tarihine iki gün kala e-posta hatırlatması almasını aşağıdaki örnek ve kurallarla gösterdim. Bu aşamada gerçek e-posta gönderilmez; yalnızca mesaj örneği ve hatırlatma kuralları hazırlanır. İade tarihi US-15 L01'deki güncel iade tarihidir; US-13'te süre uzatılmışsa yeni tarih esas alınır.

## H 01 e-posta örneği

```text
Kime     : 2000000001@ogrenci.ornek.edu.tr
Konu     : Iade tarihiniz yaklasiyor: Ornek Kitap A

Merhaba,
Odunc aldiginiz "Ornek Kitap A" kitabinin iade tarihi 03.12.2026.
Kitabi bu tarihe kadar kutuphaneye iade edebilir ya da uygunsa
Odunc kayitlarim ekranindan sureyi uzatabilirsiniz.

Kutuphane Kaynak Yonetim Sistemi
```

Mesajda yalnızca bu ödünç kaydının kitap adı ve güncel iade tarihi bulunur. Başka öğrencilerin ya da öğrencinin diğer ödünçlerinin bilgisi yer almaz. Bu kriter 2'yi karşılar.

## H 02 hatırlatma zamanı ve tekrar kuralları

| Durum | Sonuç |
|---|---|
| Aktif ödünç, güncel iade tarihine 2 takvim günü kaldı | Kayıtlı e-posta için hatırlatma oluşur. 03.12.2026 iade için 01.12.2026'da. |
| Aynı ödünç kaydı ve aynı iade tarihi için ikinci değerlendirme | Yeni hatırlatma oluşmaz. |
| Süre US-13'te uzatıldı (03.12 → 10.12.2026) | Yeni tarih esas alınır; 08.12.2026'da yeni tarihle bir hatırlatma oluşur. |
| Kayıt iade edildi | Hatırlatma oluşmaz. |
| Kayıt iptal edildi | Hatırlatma oluşmaz. |
| İade tarihine 2 günden fazla var | Henüz hatırlatma oluşmaz. |

Hatırlatma, ödünç kaydı ve iade tarihi çiftiyle kaydedilir. Bu kriter 1 ve 3'ü karşılar.

## İşlem sırası

```text
Her gun aktif odunc kayitlari taranir
  -> Kayit iade veya iptal edildi mi? Evet: atla
  -> Guncel iade tarihi - bugun = 2 gun mu? Hayir: atla
  -> Bu kayit ve bu iade tarihi icin hatirlatma var mi? Evet: atla
  -> Hayir: H01 e-postasi olusturulur, kayit ve tarih kaydedilir
US-13 uzatma -> guncel iade tarihi degisir -> yeni tarih icin kural yeniden uygulanir
```

| Kabul kriteri | Tasarım kanıtı | Kontrol kaydı |
|---|---|---|
| 1 İade tarihinden 2 gün önce kayıtlı e-postaya hatırlatma | H01, H02 birinci satır | KS-16-01, KS-16-06 |
| 2 Kitap adı ve güncel iade tarihi var, başka bilgi yok | H01 | KS-16-02 |
| 3 Tekrar yok; iade/iptalde yok; uzatmada yeni tarih | H02, işlem sırası | KS-16-03, KS-16-04, KS-16-05 |

## Planning'de netleşecek noktalar

Kabul kriterlerinde yok, yeni kural eklemedim:

- Hatırlatmanın gün içindeki saati.
- E-posta geçersizse veya gönderim başarısız olursa ne yapılacağı.

[Kontrol senaryoları](../test/us-16-kontrol.md) · [Gereksinimler](../docs/gereksinimler/kubra-us-14-17-hazirlik.md)
