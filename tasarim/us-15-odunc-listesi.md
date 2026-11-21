# US 15 geçmiş ve aktif ödünç listesi ekranı

Sorumlu: Kübra Şen | Tarih: 20 Kasım 2026 | Güncelleme: 21 Kasım 2026  
Jira: [KKY-22](https://dagdelen41.atlassian.net/browse/KKY-22) | Sprint 3 | 2 SP  
Durum: Eray'ın 21 Kasım PO kararları ve Kadir'in örnek veri notu işlendi. Bağımsız kontrol bekleniyor.

Öğrencinin kendi aktif ve geçmiş ödünç kayıtlarını görmesini aşağıdaki ekranlarla gösterdim. Taslaklar çalışan uygulama ekranı değildir. Bu liste, Kadir'in US-13 taslağındaki ödünç listesiyle aynı yerdir. Bu yüzden aktif listeye US-13'ün uzatma sütununu ve Süreyi uzat düğmesini de koydum. Örneklerde bugünün tarihi 20.11.2026'dır.

## L 01 aktif ödünçler

```text
ODUNC KAYITLARIM                        Oturum: Ogrenci (2000000001)
[ Aktif ]  [ Gecmis ]

Kitap          Odunc tarihi  Guncel iade  Durum            Uzatma  Islem
Ornek Kitap A  18.11.2026    03.12.2026   ODUNCTE          0 / 1   [Sureyi uzat]
Ornek Kitap B  04.11.2026    19.11.2026   ! GECIKMIS       0 / 1   -
```

Her satırda kitap adı, ödünç tarihi, güncel iade tarihi ve durum görünür. Güncel iade tarihi, US-13'te süre uzatıldıysa yeni tarihtir. Bu kriter 2'yi karşılar.

İade tarihi bugünden önce olan aktif kayıt kırmızı "! GECIKMIS" etiketiyle işaretlenir. İade tarihinin kendisi olan gün gecikmiş sayılmaz. Bu, Eray'ın US-13 için verdiği "iade günü henüz geçmemiştir" kararıyla aynıdır. Örnek Kitap B'nin iade tarihi 19.11.2026 olduğu için 18.11.2026'da öğrencinin gecikmiş kitabı yoktur; bu yüzden aynı öğrenci US-11'de o gün Örnek Kitap A'yı ödünç alabilir. 20.11.2026'da ise Örnek Kitap B gecikmiş görünür. Bu kriter 3'ün gecikme kısmını karşılar. Gecikmiş kayıtta süre uzatılamaz; bu da US-13 kriter 1 ile aynıdır.

## L 02 geçmiş ödünçler

```text
ODUNC KAYITLARIM                        Oturum: Ogrenci (2000000001)
[ Aktif ]  [ Gecmis ]

Kitap          Odunc tarihi  Iade edildigi tarih  Durum
Ornek Kitap D  20.10.2026    30.10.2026           IADE EDILDI
Ornek Kitap F  01.10.2026    10.10.2026           IADE EDILDI

Gecmis kayitlar en az 12 ay saklanir ve silinemez.
```

US-12'de iadesi tamamlanan kayıt aktif listeden çıkar ve geçmiş listesine iade edildiği tarihle geçer. Kopya hasarlı iade edilip Bakımda olsa da öğrencinin kaydı "İade edildi" olarak görünür. Bu kriter 2'nin geçmiş kısmını karşılar ve Kadir'in US-12 taslağındaki "ödünç kaydı aktif listeden çıkar" notuyla tutarlıdır.

Eray'ın 21 Kasım kararlarına göre geçmiş kayıtlar iade tarihine göre en yeniden en eskiye sıralanır. Kayıtlar öğrencinin aktif öğrencilik süresi boyunca, en az 12 ay, salt okunur olarak saklanır. Geçmiş listesinde silme ya da düzenleme seçeneği yoktur.

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
  -> Gecmis sekme (L02): US-12'de iadesi tamamlanan kayitlar, iade tarihine gore yeniden eskiye
Baska ogrencinin kaydi istenirse -> L04, bilgi gosterilmez
US-13 uzatma onaylanirsa -> L01'de guncel iade tarihi yenilenir
```

| Kabul kriteri veya PO kararı | Tasarım kanıtı | Kontrol kaydı |
|---|---|---|
| 1 Öğrenci yalnızca kendi kayıtlarını görür | L01 ve L04 | KS-15-01, KS-15-02 |
| 2 Aktif listede dört alan, iade edilen kayıt geçmişe geçer | L01 ve L02 | KS-15-03, KS-15-04 |
| 3 Gecikmiş kayıt işaretlenir, kayıt yoksa Kayıt bulunamadı mesajı | L01 ve L03 | KS-15-05, KS-15-06 |
| PO kararı, geçmiş liste iade tarihine göre yeniden eskiye | L02 ve işlem sırası | KS-15-07 |
| PO kararı, geçmiş kayıtlar en az 12 ay salt okunur saklanır | L02 | KS-15-08 |

## PO kararları

Eray 21 Kasım'da PR #44'te şu kararları verdi. Yukarıdaki ekrana ve senaryolara işledim.

- Geçmiş ödünç kayıtları iade tarihine göre en yeniden en eskiye listelenir.
- İade edilen kayıtlar öğrencinin aktif öğrencilik süresi boyunca, en az 12 ay, salt okunur olarak saklanır ve öğrenci tarafından silinemez.

## Bağlantılı işler

- US-13 (Kadir, KKY-12): Uzatma bu listeden yapılır ve yeni iade tarihi L01'de görünür. Kadir'in KS-13-05 senaryosu bu ekranı kullanır. Kadir 21 Kasım'da U01'in sütunlarını L01 ile eşitledi.
- US-11 (Kadir, KKY-10): L01'deki örnek öğrenci US-11'deki 2000000001 numaralı öğrencidir. Örnek Kitap B bu öğrencinin 18.11.2026'daki aktif ödüncüdür; US-11'deki aktif ödünç sayısı da buna göre eşleşmelidir.
- US-12 (Kadir, KKY-11): İadesi tamamlanan kayıt geçmiş listesine geçer.
- US-16 (benim, KKY-23, Sprint 4): Hatırlatma bu listedeki güncel iade tarihini kullanacak.

## Netleşmesi gereken nokta

Bu kabul kriterlerinde yok. Yeni kural eklemedim.

- Gecikmiş kayıtta kaç gün geciktiği gösterilecek mi? Gecikme cezası US-18'de, Enes'in işi. Gün sayısı oradaki hesapla birlikte netleşmeli.

[Kontrol senaryoları](../test/us-15-kontrol.md) · [Gereksinimler](../docs/gereksinimler/kubra-us-14-17-hazirlik.md)
