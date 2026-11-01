# Sprint 2 - Kabul kriteri kontrol listem

Hazırlayan: Kübra Şen  
İlk kontrol: 29 Ekim 2026  
Kapsam: US-06-10, 5 Story, 18 SP, 17 kabul kriteri  
Planlanan sprint: 28 Ekim-4 Kasım 2026  
Son kontrol hedefim: 4 Kasım 2026  
Planladığım kapasite: Sprint 2 için toplam 4 saat (planlama tahminim).

Jira'daki 17 kriteri plan, gereksinim, ekran/akış ve kontrol senaryolarıyla eşleştirdim. Mert'in güncel PR #25 teslimini 4f74bf0 sürümünde sekiz dosyasıyla inceledim ve [bağımsız belge incelememi onay olarak kaydettim][M-ONAY]. Esat'ın mevcut gereksinim ve senaryo hazırlığını 78a4c23 sürümünde kontrol ettim. Çalışan uygulama testi yürütmedim; aşağıdaki sonuçlar belge tutarlılığı ve kapsam kontrolümü gösterir.

## Durumları nasıl kullandım?

- **Uyumlu:** İncelediğim gereksinim, ekran/akış ve kontrol kaydı ilgili Jira koşulunu birlikte açıklıyor.
- **Fark var:** Hazırlıkta bir kriterin beklenen sonucu veya senaryo kapsamı açık kalıyor. Bunları belge düzeltme notu olarak kaydettim.
- **Kanıt bekleniyor:** Gereksinim/senaryo taslağı var; ilgili Sprint 2 ekran/akış ve sonuç kaydıyla eşleştirmeyi henüz tamamlayamadım.

Bu ilk kontrolde **11 Uyumlu, 2 Fark var, 4 Kanıt bekleniyor** sonucu kaydettim. US-06-07'nin altı kriteri için teslim kanıtı takibim sürüyor; bunların ikisinde ayrıca aşağıdaki senaryo notlarım var.

## Kaynaklarım

- YBS 471 Kütüphane Sistemi Proje Planı, slayt 8: US-06-10 kapsamı, kabul özeti ve 3/5/5/2/3 SP.
- Jira: [KKY-7][J6], [KKY-8][J7], [KKY-9][J8], [KKY-19][J9], [KKY-20][J10]. AK numaralarını her karttaki kriter sırasına göre verdim.
- [Esat'ın gereksinim ve senaryo hazırlığı, 78a4c23][E-G].
- [Mert'in güncel gereksinim ve teslim takibi, 4f74bf0][M-G]; [PR #25][M-PR].
- [US-08 ekran/akış][M8-E], [US-08 kontrolü][M8-K]; [US-09 ekran/akış][M9-E], [US-09 kontrolü][M9-K]; [US-10 ekran/akış][M10-E], [US-10 kontrolü][M10-K]. Mert'in bütün bağlantılarını incelediğim aynı 4f74bf0 sürümüne sabitledim.

## Kriter eşleştirme tablom

| İzleme kimliğim / Jira | Kontrol ettiğim koşul | Gereksinim ve senaryo eşleşmesi | Ekran/sonuç kanıtı ve sonraki kontrolüm | Durum |
| --- | --- | --- | --- | --- |
| S2-06-AK1 / KKY-7 | Kitap detayında salon ve raf kodu | [E-G] US-06 kriter 1; “Müsait kitap incelenir” taslağı | US-06 detay ekranı ve kriter bazlı sonuç bağlantısını bekliyorum. | Kanıt bekleniyor |
| S2-06-AK2 / KKY-7 | Müsait / Ödünçte etiketi | [E-G] US-06 kriter 2; müsait ve ödünçte kitap senaryoları | İki durumun ekran/akış ve sonuç kaydını kontrol edeceğim. | Kanıt bekleniyor |
| S2-06-AK3 / KKY-7 | Stok bilgisi güncel tutulur | [E-G] US-06 kriter 3 ödünç/iade sonrası güncellemeyi söylüyor; mevcut üç senaryoda stok değişimi adımı yok. | **F-01:** Ödünç ve iade öncesi/sonrası stok değerini karşılaştıran senaryo ve kanıt istemem gerekiyor. | Fark var |
| S2-07-AK1 / KKY-8 | Giriş yapmış üye PDF'e doğrudan erişir | [E-G] US-07 kriter 2; giriş yapmış üye senaryosu | Dijital kaynak ekranı, erişim akışı ve sonuç kaydını bekliyorum. | Kanıt bekleniyor |
| S2-07-AK2 / KKY-8 | Giriş yapmayan kullanıcı PDF indiremez | [E-G] US-07 kriter 3; ziyaretçi senaryosu yalnızca uyarı sonucunu yazıyor. | **F-02:** PDF erişiminin engellendiği ve belgedeki giriş ekranına yönlendirmenin beklenen sonuçta açıkça kontrol edilmesini isteyeceğim. | Fark var |
| S2-07-AK3 / KKY-8 | İndirme düğmesi yalnızca dijital kaynaklarda görünür | [E-G] US-07 kriter 1; fiziksel kitapta düğmenin görünmemesi senaryosu | Dijital ve basılı kaynak ekranlarını birlikte kontrol edeceğim. | Kanıt bekleniyor |
| S2-08-AK1 / KKY-9 | Başlık, yazar, ISBN ve kategori zorunludur | [M-G] US-08/1; [M8-K] KS-08-01 | [M8-E] F01-F02 dört alanı, uyarıyı ve kayıt engelini açıklıyor. | Uyumlu |
| S2-08-AK2 / KKY-9 | Barkoddan veya elle girilen ISBN 13 rakamdır; uygunsuz giriş reddedilir | [M-G] US-08/2; [M8-K] KS-08-02, KS-08-03 | [M8-E] F02 ve işlem sırası iki giriş yoluna aynı uzunluk/rakam kontrolünü uyguluyor. | Uyumlu |
| S2-08-AK3 / KKY-9 | Aynı ISBN ile ikinci kayıt oluşmaz; uyarı gösterilir | [M-G] US-08/3; [M8-K] KS-08-04 | [M8-E] F02 tekilliği kayıt öncesinde kontrol ediyor. | Uyumlu |
| S2-08-AK4 / KKY-9 | Kapak isteğe bağlıdır; boş olması geçerli kaydı engellemez | [M-G] US-08/4; [M8-K] KS-08-05 | [M8-E] F01-F02 isteğe bağlı kapağı ve geçerli kayıt yolunu gösteriyor. | Uyumlu |
| S2-08-AK5 / KKY-9 | Kaydedilen kitap katalog aramasında görünür | [M-G] US-08/5; [M8-K] KS-08-06 | [M8-E] F03 aynı ISBN ile katalog sonucunu gösteriyor. | Uyumlu |
| S2-09-AK1 / KKY-19 | Görevli/admin bakım durumunu değiştirebilir; öğrenci değiştiremez | [M-G] US-09/1; [M9-K] KS-09-01, KS-09-02 | [M9-E] B01 iki yetkili rolü, düğme görünürlüğünü ve doğrudan yetkisiz işlem engelini açıklıyor. | Uyumlu |
| S2-09-AK2 / KKY-19 | Bakımdaki kopya ödünç verilemez, müsait sayıya katılmaz; sağlam kopya kullanılabilir | [M-G] US-09/2; [M9-K] KS-09-03, KS-09-04 | [M9-E] B02 K-001 için bakım/ödünç engelini, K-002 için kullanılabilirliği ve sayının 2'den 1'e inişini gösteriyor. | Uyumlu |
| S2-09-AK3 / KKY-19 | Yeniden Müsait yapılan kopya müsait sayıyı günceller | [M-G] US-09/3; [M9-K] KS-09-05 | [M9-E] B03 sayının yeniden 2 olmasını açıklıyor. | Uyumlu |
| S2-10-AK1 / KKY-20 | Giriş yapmış öğrenci 1-5 tam sayı puan verebilir; geçersiz değer reddedilir | [M-G] US-10/1; [M10-K] KS-10-01, KS-10-02, KS-10-03 | [M10-E] Y01 alt/üst sınırı, 0/6/2.5 girdilerini ve oturum koşulunu açıklıyor. | Uyumlu |
| S2-10-AK2 / KKY-20 | Yorum Onay bekliyor olur; onay öncesi diğer öğrencilere gösterilmez | [M-G] US-10/2; [M10-K] KS-10-04 | [M10-E] Y02 kişisel durum ve onaylı yorum listesini ayırıyor; puan ile yorum birlikte gizli kalıyor. | Uyumlu |
| S2-10-AK3 / KKY-20 | Görevli/admin onayında puan ve yorum yayımlanır; ret durumunda yayımlanmaz | [M-G] US-10/3; [M10-K] KS-10-05, KS-10-06, KS-10-07 | [M10-E] Y03 onay, ret ve öğrencinin yetkisiz onay isteğini kapsıyor. | Uyumlu |

US-07 için Jira ve Esat belgesindeki kriter sıraları farklı: Jira 1 → belge 2, Jira 2 → belge 3, Jira 3 → belge 1. Eşleştirmeyi bu sırayla yaptım; yalnızca numara farkını hata saymadım.

## Açık notlarım ve yeniden kontrolüm

| Notum | İlgili iş | İstediğim tamamlayıcı kayıt | Sonraki kontrolüm |
| --- | --- | --- | --- |
| F-01 | US-06 / KKY-7, Esat | Ödünç/iade sonrası stok güncellemesi için açık ön koşul, işlem ve beklenen sonuç; ekran/akış ve sonuç bağlantısı | Yeni belge/PR geldiğinde stok değerlerini ve kriter bağlantısını yeniden karşılaştıracağım. |
| F-02 | US-07 / KKY-8, Esat | Ziyaretçinin PDF erişiminin engellenmesi; mevcut gereksinimdeki uyarı ve giriş yönlendirmesinin açık beklenen sonucu | Dijital ve basılı kaynak, oturumlu ve oturumsuz kullanıcı yollarını birlikte kontrol edeceğim. |

Bu iki notu hazırlık senaryolarındaki kapsam açıklığı için açtım. PO adına yeni bir kural eklemedim. US-06'daki “Depoda/Kayıp” örneğini Jira'daki Müsait/Ödünçte etiketlerinin yerine geçecek onaylı yeni durum olarak değerlendirmedim; ekran tesliminde kapsamını ayrıca soracağım.

## Takvim ve çalışma kaydım

29 Ekim'de ilk listeyi ve Mert'in 18 senaryolu tesliminin bağımsız incelemesini tamamladım. Yeni kanıt/karar geldiğinde ilgili satırın kaynağını, sonucunu ve kontrol tarihini güncelleyeceğim. 4 Kasım'da 17 satırın tamamı için son durumu ve açık not sayısını kaydedeceğim. Story durumunu veya sprint başlangıcını bu listeyle değiştirmedim.

Jira'yı kontrol ettiğim anda Sprint 2'de “Sprint'i başlat” düğmesi vardı; Esat'ın iki işi Yapılacaklar (8 SP), Mert'in üç işi Devam Ediyor (10 SP) görünüyordu. Başlangıç/kapanış kaydını Esat ve PO'nun yönetiminde takip edeceğim.

[E-G]: https://github.com/DU-YBS471-KKY/kutuphane-kaynak-yonetimi/blob/78a4c238fc65ebcf1abe85fbb318499bac00dba8/docs/gereksinimler/esat-us-05-07-hazirlik.md
[M-G]: https://github.com/DU-YBS471-KKY/kutuphane-kaynak-yonetimi/blob/4f74bf0f0218e6a1f48cda5db698a8cd38cafbbb/docs/gereksinimler/mert-us-08-10-hazirlik.md
[M8-E]: https://github.com/DU-YBS471-KKY/kutuphane-kaynak-yonetimi/blob/4f74bf0f0218e6a1f48cda5db698a8cd38cafbbb/tasarim/us-08-kitap-ekleme.md
[M8-K]: https://github.com/DU-YBS471-KKY/kutuphane-kaynak-yonetimi/blob/4f74bf0f0218e6a1f48cda5db698a8cd38cafbbb/test/us-08-kontrol.md
[M9-E]: https://github.com/DU-YBS471-KKY/kutuphane-kaynak-yonetimi/blob/4f74bf0f0218e6a1f48cda5db698a8cd38cafbbb/tasarim/us-09-bakim-durumu.md
[M9-K]: https://github.com/DU-YBS471-KKY/kutuphane-kaynak-yonetimi/blob/4f74bf0f0218e6a1f48cda5db698a8cd38cafbbb/test/us-09-kontrol.md
[M10-E]: https://github.com/DU-YBS471-KKY/kutuphane-kaynak-yonetimi/blob/4f74bf0f0218e6a1f48cda5db698a8cd38cafbbb/tasarim/us-10-puan-yorum.md
[M10-K]: https://github.com/DU-YBS471-KKY/kutuphane-kaynak-yonetimi/blob/4f74bf0f0218e6a1f48cda5db698a8cd38cafbbb/test/us-10-kontrol.md
[M-PR]: https://github.com/DU-YBS471-KKY/kutuphane-kaynak-yonetimi/pull/25
[M-ONAY]: https://github.com/DU-YBS471-KKY/kutuphane-kaynak-yonetimi/pull/25#pullrequestreview-5695366811
[J6]: https://dagdelen41.atlassian.net/browse/KKY-7
[J7]: https://dagdelen41.atlassian.net/browse/KKY-8
[J8]: https://dagdelen41.atlassian.net/browse/KKY-9
[J9]: https://dagdelen41.atlassian.net/browse/KKY-19
[J10]: https://dagdelen41.atlassian.net/browse/KKY-20


## 31 Ekim 2026 ara kontrolüm

[PR #26](https://github.com/DU-YBS471-KKY/kutuphane-kaynak-yonetimi/pull/26) için Eray'ın onayını ve develop'a birleşme kaydını doğruladım (f713532). İlk kontrol listem ve 29 Ekim günlüğüm artık birleşmiş durumda.

Jira'da Sprint 2'nin etkin olduğunu gördüm. Planlanan aralık 28 Ekim–4 Kasım; beş Story ve 18 SP. US-08–10 Tamam (10 SP), US-06–07 Yapılacaklar (8 SP). Bu ara durum, yukarıdaki 29 Ekim pano gözlemimden sonraki kaydımdır.

US-06–07 için yeni ekran/akış ve kriter bazlı sonuç teslimi göremedim. KKY-7'deki F-01 stok güncellemesi ve KKY-8'deki F-02 oturumsuz PDF erişimi notlarıma yeni yanıt bulunmuyor. Bu nedenle 17 kriter için son belge kontrolümün dağılımını **11 Uyumlu, 2 Fark var, 4 Kanıt bekleniyor** olarak korudum. US-06–07'nin altı kriterini henüz tamamlanmış teslim olarak değerlendirmiyorum.

Mert'in [PR #28](https://github.com/DU-YBS471-KKY/kutuphane-kaynak-yonetimi/pull/28) açıklamasında üç kontrol tablosunun korunduğunu ve eski inceleme bekleyişi notlarının güncellendiğini gördüm. Yeni bir yazılım testi veya US-06–07 teslim incelemesi yapmadım.

Yeni belge/PR geldiğinde F-01/F-02 ile dört bekleyen kriterin kanıtını yeniden karşılaştıracağım. Son değerlendirmemi **4 Kasım** için planladım. O tarihte açık kalan koşulları ve bekleme gerekçelerini de yazacağım.
