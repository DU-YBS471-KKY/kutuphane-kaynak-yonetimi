# US 15 geçmiş ve aktif ödünç listesi ekranı

Sorumlu: Kübra Şen | Tarih: 20 Kasım 2026  
Jira: [KKY-22](https://dagdelen41.atlassian.net/browse/KKY-22) | Sprint 3 | 2 SP  
Durum: Taslak hazır. Bağımsız kontrol bekleniyor.

Öğrencinin kendi aktif ve geçmiş ödünç kayıtlarını görmesini aşağıdaki ekranlarla gösterdim. Taslaklar çalışan uygulama ekranı değildir. Bu liste, Kadir'in US-13 taslağındaki "Ödünç aldıklarım" listesiyle aynı yerdir. Bu yüzden aktif listeye US-13'ün uzatma sütununu ve Süreyi uzat düğmesini de koydum. Örneklerde bugünün tarihi 20.11.2026'dır.

## L 01 aktif ödünçler

```text
ODUNC KAYITLARIM                        Oturum: Ogrenci (2000000001)
[ Aktif ]  [ Gecmis ]

Kitap          Odunc tarihi  Guncel iade  Durum            Uzatma  Islem
Ornek Kitap A  18.11.2026    03.12.2026   ODUNCTE          0 / 1   [Sureyi uzat]
Ornek Kitap B  01.11.2026    16.11.2026   ! GECIKMIS       0 / 1   -
```

Her satırda kitap adı, ödünç tarihi, güncel iade tarihi ve durum görünür. Güncel iade tarihi, US-13'te süre uzatıldıysa yeni tarihtir. Bu kriter 2'yi karşılar.

İade tarihi bugünden önce olan aktif kayıt kırmızı "! GECIKMIS" etiketiyle işaretlenir. İade tarihinin kendisi olan gün gecikmiş sayılmaz. Bu, Eray'ın US-13 için verdiği "iade günü henüz geçmemiştir" kararıyla aynıdır. Bu kriter 3'ün gecikme kısmını karşılar. Gecikmiş kayıtta süre uzatılamaz; bu da US-13 kriter 1 ile aynıdır.

## L 02 geçmiş ödünçler

```text
ODUNC KAYITLARIM                        Oturum: Ogrenci (2000000001)
[ Aktif ]  [ Gecmis ]

Kitap          Odunc tarihi  Iade edildigi tarih  Durum
Ornek Kitap D  20.10.2026    30.10.2026           IADE EDILDI
```

US-12'de iadesi tamamlanan kayıt aktif listeden çıkar ve geçmiş listesine iade edildiği tarihle geçer. Kopya hasarlı iade edilip Bakımda olsa da öğrencinin kaydı "İade edildi" olarak görünür. Bu kriter 2'nin geçmiş kısmını karşılar ve Kadir'in US-12 taslağındaki "ödünç kaydı aktif listeden çıkar" notuyla tutarlıdır.

## L 03 kayıt bulunamadı

```text
ODUNC KAYITLARIM                        Oturum: Ogrenci (2000000003)
[ Aktif ]  [ Gecmis ]

Kayit bulunamadi.
Henuz odunc aldiginiz bir kitap yok.
```

Öğrencinin hiç ödünç kaydı yoksa boş tablo yerine bu açıklayıcı mesaj görünür. Bu kriter 3'ün boş liste kısmını karşılar.

## L 04 yalnızca kendi kayıtları

```text
Bu kayda erisim yetkiniz yok.
Yalnizca kendi odunc kayitlarinizi gorebilirsiniz.
                                         [Kayitlarima don]
```

Liste, US-02 oturumundaki öğrenci numarasına göre açılır. Öğrenci başka bir öğrencinin kaydını açmaya çalışırsa (örneğin kayıt bağlantısını değiştirerek) o kaydın hiçbir bilgisi gösterilmez ve bu uyarı çıkar. Bu kriter 1'i karşılar.

## İşlem sırası

```text
Odunc kayitlarim ekranini ac -> Oturumdaki ogrencinin kayitlari getirilir
  -> Hic kayit yok mu? Evet: L03
  -> Aktif sekme (L01): iade tarihi bugunden once mi? Evet: GECIKMIS etiketi
  -> Gecmis sekme (L02): US-12'de iadesi tamamlanan kayitlar
Baska ogrencinin kaydi istenirse -> L04, bilgi gosterilmez
US-13 uzatma onaylanirsa -> L01'de guncel iade tarihi yenilenir
```

| Kabul kriteri | Tasarım kanıtı | Kontrol kaydı |
|---|---|---|
| 1 Öğrenci yalnızca kendi kayıtlarını görür | L01 ve L04 | KS-15-01, KS-15-02 |
| 2 Aktif listede dört alan, iade edilen kayıt geçmişe geçer | L01 ve L02 | KS-15-03, KS-15-04 |
| 3 Gecikmiş kayıt işaretlenir, kayıt yoksa Kayıt bulunamadı mesajı | L01 ve L03 | KS-15-05, KS-15-06 |

## Bağlantılı işler

- US-13 (Kadir, KKY-12): Uzatma bu listeden yapılır ve yeni iade tarihi L01'de görünür. Kadir'in KS-13-05 senaryosu bu ekranı kullanır. Kadir'in U01 taslağında Durum sütunu yok; aynı liste olduğu için iki taslağın sütunlarını birlikte eşitlemeyi önereceğim.
- US-12 (Kadir, KKY-11): İadesi tamamlanan kayıt geçmiş listesine geçer.
- US-16 (benim, KKY-23, Sprint 4): Hatırlatma bu listedeki güncel iade tarihini kullanacak.

## Netleşmesi gereken noktalar

Bunlar kabul kriterlerinde yok. Yeni kural eklemedim.

- Geçmiş listesinin sıralaması, filtrelenmesi ve kaç yıl saklanacağı. Eray'a soracağım.
- Gecikmiş kayıtta kaç gün geciktiği gösterilecek mi? Gecikme cezası US-18'de, Enes'in işi. Gün sayısı oradaki hesapla birlikte netleşmeli.

[Kontrol senaryoları](../test/us-15-kontrol.md) · [Gereksinimler](../docs/gereksinimler/kubra-us-14-17-hazirlik.md)
