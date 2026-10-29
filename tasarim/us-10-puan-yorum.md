# US 10 puan yorum ve onay ekranları

Sorumlu: Mert Seçkin | Tarih: 29 Ekim 2026  
Jira: [KKY-20](https://dagdelen41.atlassian.net/browse/KKY-20) | Sprint 2 | 3 SP  
Durum: Belge kontrolü yapıldı; bağımsız incelemeye sunuluyor.

Öğrencinin puan/yorum göndermesini ve görevli/adminin yayın kararını ayrı ekranlarda gösterdim. Örnek akış çalışan uygulama testi değildir.

## Y 01 öğrenci ekranı

```text
KITAP: Ornek Kitap A                  Oturum: Ogrenci A
Puan * [1] [2] [3] [4] [5]
Yorum  [____________________________________________]
       [____________________________________________]
                                           [Gonder]
```

Puan seçenekleri 1, 2, 3, 4 ve 5 tam sayılarıdır. İstek içindeki puan da doğrulanır; 0, 6, 2.5 gibi değerlerde “1–5 arasında tam sayı puan seçin.” uyarısı gösterilir ve kayıt oluşturulmaz. Oturum yoksa gönderim yerine “Puan ve yorum için giriş yapın.” bilgisi gösterilir (kriter 1).

## Y 02 gönderim sonrası ve herkese açık görünüm

```text
Gonderim alindi. Durum: Onay bekliyor.
Ogrenci A kendi gonderimini bu durumla gorur.

Diger ogrencilerin kitap detayi:
ONAYLI YORUMLAR
Yalnizca onaylanmis puan ve yorumlar listelenir.
```

Yeni gönderim Onay bekliyor durumuna alınır. Diğer öğrencilere, onay öncesinde gönderimin puanı ve yorumu gösterilmez (kriter 2).

## Y 03 görevli ve yönetici onayı

```text
YORUM INCELEME                         Oturum: Gorevli / Admin
Kitap: Ornek Kitap A   Gonderen: Ogrenci A
Puan: 5               Durum: Onay bekliyor
Yorum: [Ornek yorum metni]
                                  [Reddet] [Onayla]
```

```text
Oturum ve puan kontrolu -> Gonder -> Onay bekliyor
  -> Gorevli/Admin Onayla -> Onaylandi -> Puan ve yorumu yayinla
  -> Gorevli/Admin Reddet -> Reddedildi -> Yayinlama
```

Öğrencinin onay verme isteğine izin verilmez. Onaylanan gönderim kitap detayında görünür; reddedilen gönderim yayımlanmaz (kriter 3). Onay kararı puan ile yorum için birlikte uygulanır.

| Kabul kriteri | Tasarım kanıtı | Kontrol kaydı |
|---|---|---|
| 1 Oturum ve puan aralığı | Y01 | KS-10-01, KS-10-02, KS-10-03 |
| 2 Onay bekliyor görünürlüğü | Y02 | KS-10-04 |
| 3 Onay ve ret | Y03 | KS-10-05, KS-10-06, KS-10-07 |

[Kontrol sonuçları](../test/us-10-kontrol.md) · [Gereksinimler](../docs/gereksinimler/mert-us-08-10-hazirlik.md)
