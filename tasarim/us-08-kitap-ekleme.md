# US 08 kitap ekleme ekranı ve işlem akışı

Sorumlu: Mert Seçkin | Tarih: 29 Ekim 2026  
Jira: [KKY-9](https://dagdelen41.atlassian.net/browse/KKY-9) | Sprint 2 | 5 SP  
Durum: Belge kontrolü yapıldı; bağımsız incelemeye sunuluyor.

Görevlinin barkod/ISBN ile kitap eklemesini, hatalı girdiyi düzeltmesini ve kaydı katalogda görmesini aşağıdaki ekranlarla gösterdim. Taslaklar çalışan uygulama ekranı değildir.

## F 01 kitap ekleme formu

```text
KITAP EKLE                         Oturum: Gorevli
ISBN / Barkod * [_____________] [Barkod oku]
Baslik *       [___________________________]
Yazar *        [___________________________]
Kategori *     [Seciniz                  v]
Kapak          [Dosya sec]  (istege bagli)

Alan mesaji: [ilgili alanin altinda]
                         [Iptal] [Kaydet]
```

Yıldızlı dört alan zorunludur (kriter 1). Barkoddan gelen değer ve elle yazılan ISBN aynı kontrolden geçer: tam 13 karakter ve her karakter rakam olmalıdır (kriter 2). Bu sprintte ISBN kontrol basamağı hesabını ek bir kabul şartı olarak tanımlamadım; Jira'daki 13 rakam kuralını uyguladım.

## F 02 doğrulama ve hata durumları

| Durum | Gösterilecek bilgi | Sonraki adım |
|---|---|---|
| Başlık, yazar, ISBN veya kategori boş | Her eksik alanın altında “Bu alan zorunludur.” | Kayıt oluşmaz; formdaki diğer değerler korunur. |
| ISBN kısa, uzun veya harf içeriyor | “ISBN 13 rakamdan oluşmalıdır.” | Kayıt oluşmaz; ISBN düzeltilir. |
| ISBN zaten kayıtlı | “Bu ISBN zaten kayıtlı.” | İkinci kitap kaydı oluşmaz; formdan çıkılabilir veya ISBN düzeltilebilir. |
| Kapak boş, diğer alanlar geçerli | Kapak için zorunluluk hatası gösterilmez. | Kayıt adımına geçilir. |

Tekillik kontrolü kayıt tamamlanmadan yapılır (kriter 3). Kapak isteğe bağlıdır (kriter 4).

## F 03 başarılı kayıt ve katalog

```text
Kitap kaydedildi.  [Katalogda gor]

KATALOG  ISBN [9781234567897] [Ara]
Baslik          Yazar          ISBN           Kategori
Ornek Kitap A   Ornek Yazar    9781234567897   Roman
```

Başarılı kayıt sonrası aynı ISBN ile arama yapıldığında yeni kitap sonuçlarda bulunur (kriter 5). Kitap adı, yazar ve ISBN yukarıda yalnızca örnek veri olarak kullanıldı.

## İşlem sırası

```text
Formu ac -> Barkod oku / ISBN yaz -> Alanlari doldur
  -> Eksik alan? Evet: F02 uyarisi, formda kal
  -> ISBN 13 rakam mi? Hayir: F02 uyarisi, formda kal
  -> ISBN mevcut mu? Evet: F02 tekrar kayit uyarisi
  -> Kaydet -> F03 basari bilgisi -> Katalogda ayni ISBN ile ara
```

| Kabul kriteri | Tasarım kanıtı | Kontrol kaydı |
|---|---|---|
| 1 Zorunlu alanlar | F01 ve F02 | KS-08-01 |
| 2 ISBN doğrulama | F02 ve işlem sırası | KS-08-02, KS-08-03 |
| 3 Tekil ISBN | F02 | KS-08-04 |
| 4 Kapak isteğe bağlı | F01 ve F02 | KS-08-05 |
| 5 Katalogda görünme | F03 | KS-08-06 |

[Kontrol sonuçları](../test/us-08-kontrol.md) · [Gereksinimler](../docs/gereksinimler/mert-us-08-10-hazirlik.md)
