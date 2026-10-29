# US 09 bakım durumu ekranı ve işlem akışı

Sorumlu: Mert Seçkin | Tarih: 29 Ekim 2026  
Jira: [KKY-19](https://dagdelen41.atlassian.net/browse/KKY-19) | Sprint 2 | 2 SP  
Durum: Belge kontrolü yapıldı; bağımsız incelemeye sunuluyor.

Bakım durumunu kitap başlığının tamamı yerine fiziksel kopya üzerinde gösterdim. Böylece bir kopya bakımdayken aynı kitabın sağlam kopyaları kullanılabilir kalır.

## B 01 görevli ve yönetici ekranı

```text
KITAP KOPYALARI                     Oturum: Gorevli / Admin
Kitap: Ornek Kitap A         Odunc verilebilir kopya: 2

Kopya       Durum       Islem
K-001       Musait     [Bakimda yap]
K-002       Musait     [Bakimda yap]
```

Öğrenci görünümünde durumlar ve müsait sayı okunabilir; durum değiştirme düğmeleri bulunmaz. Öğrencinin doğrudan durum değiştirme isteği de “Bu işlem için yetkiniz yok.” bilgisiyle reddedilir (kriter 1).

## B 02 bakımda kopya

```text
KITAP KOPYALARI              Odunc verilebilir kopya: 1
Kopya       Durum       Islem
K-001       Bakimda    [Musait yap] [Odunc ver: kapali]
K-002       Musait     [Bakimda yap] [Odunc ver]

Bilgi: K-001 bakimda oldugu icin odunc verilemez.
```

Müsait sayı yalnızca durumu Müsait olan kopyalardan hesaplanır. Bakımda kopya ödünç işlemine gönderilse de işlem reddedilir; diğer müsait kopya seçilebilir (kriter 2).

## B 03 yeniden müsait yapma

Görevli/admin K-001 için “Müsait yap” seçtiğinde durum Müsait olur ve sayı yeniden 2'ye çıkar. Ekranda “Kopya durumu güncellendi.” mesajı görünür (kriter 3).

```text
Yetki kontrolu -> Kopyayi sec -> Bakimda yap
  -> Kopya Bakimda -> Musait sayiyi yeniden hesapla
  -> Bu kopyanin odunc verilmesini engelle
Bakim bitti -> Musait yap -> Sayiyi yeniden hesapla
```

| Kabul kriteri | Tasarım kanıtı | Kontrol kaydı |
|---|---|---|
| 1 Yetkili rol | B01 | KS-09-01, KS-09-02 |
| 2 Bakımda kopya ve diğer kopyalar | B02 | KS-09-03, KS-09-04 |
| 3 Yeniden müsait olma | B03 | KS-09-05 |

[Kontrol sonuçları](../test/us-09-kontrol.md) · [Gereksinimler](../docs/gereksinimler/mert-us-08-10-hazirlik.md)
