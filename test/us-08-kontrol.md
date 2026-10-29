# US 08 belge kontrol senaryoları

Hazırlayan ve belge kontrolü: Mert Seçkin | 29 Ekim 2026  
Jira: [KKY-9](https://dagdelen41.atlassian.net/browse/KKY-9) | Sprint 2

Gereksinim, ekran ve işlem akışını karşılaştırdım. Aşağıdaki “Uyumlu” sonuçları tasarımın ilgili beklenen sonucu açıkça tanımladığını gösterir. Bir uygulamada form çalıştırmadım veya veritabanı kaydı oluşturmadım. Bağımsız inceleme bekleniyor.

Örnek veriler gerçeğe ait katalog kayıtları değildir: Başlık “Örnek Kitap A”, yazar “Örnek Yazar”, kategori “Roman”, ISBN 9781234567897. Tekillik senaryosunda bu ISBN'nin mevcut olduğu varsayılır.

| Kod | Kriter | Kontrol girdisi ve adım | Beklenen sonuç | Belgede gözlediğim kanıt | Sonuç |
|---|---|---|---|---|---|
| KS-08-01 | 1 | Başlık, yazar, ISBN ve kategori sırayla boş bırakılarak Kaydet adımı değerlendirilir. | Her eksikte kayıt engellenir; ilgili alan belirtilir. | F01 dört alanı zorunlu işaretliyor; F02 eksik alan mesajını ve kayıt engelini tanımlıyor. | Uyumlu |
| KS-08-02 | 2 | Barkoddan veya elle 97812 girilir. | 13 rakam uyarısı; kayıt oluşmaz. | İki giriş yolu da aynı F02 kontrolüne gidiyor. | Uyumlu |
| KS-08-03 | 2 | ISBN olarak 978123456789X girilir. | Harf içeren değer reddedilir. | F02 hem uzunluk hem tüm karakterlerin rakam olmasını istiyor. | Uyumlu |
| KS-08-04 | 3 | Mevcut 9781234567897 ile kayıt denenir. | İkinci kayıt oluşmaz; mevcut ISBN uyarısı çıkar. | F02 tekillik kontrolü kayıt öncesinde; işlem sırası kayıt adımını durduruyor. | Uyumlu |
| KS-08-05 | 4 | Dört zorunlu alan geçerli, kapak boş olacak şekilde değerlendirilir. | Kapak eksikliği kayıt engeli oluşturmaz. | F01 isteğe bağlı etiketi ve F02 geçerli kayıt yolu açık. | Uyumlu |
| KS-08-06 | 5 | Geçerli yeni kitap kaydedilir; aynı ISBN katalogda aranır. | Yeni kitap başlık, yazar, ISBN ve kategoriyle bulunur. | F03 başarı ekranı ve aynı ISBN'li katalog satırı var. | Uyumlu |

Kontrolü [tasarım dosyasındaki](../tasarim/us-08-kitap-ekleme.md) F01–F03 bölümlerine göre yaptım. İnceleyen kişi ve varsa düzeltme kararı PR geçmişinde kaydedilecek.
