- # US-18: Geciken Her Gün İçin Otomatik Ceza Hesabı — İş Kuralları

**Jira Kodu:** [KKY-16](https://dagdelen41.atlassian.net/browse/KKY-16)  
**Sorumlu:** Enes Ulutaş  
**Epic:** KKY-14 Ceza ve Rapor  
**Story Point:** 5 | **Sprint:** KKY Sprint 4  

## Kullanıcı Hikayesi
Kütüphane görevlisi olarak, iade tarihi geçen kitaplar için gecikme cezasının otomatik hesaplanmasını istiyorum, böylece cezaları elle hesaplamak zorunda kalmayayım.

## Kabul Kriterleri
1. İade tarihi geçen her ödünç kaydı için gecikme günü otomatik hesaplanmalıdır.
2. Ceza tutarı, gecikme günü ile yöneticinin belirlediği günlük ceza tutarının çarpımı olmalıdır.
3. Kitap iade edildiğinde ceza tutarı kesinleşmeli ve öğrencinin hesabında görünmelidir.
4. İade tarihinden önce veya o gün iade edilen kitap için ceza oluşmamalıdır.

## İş Kuralları ve Doğrulama Mantığı
- **İK-18.1 (Gecikme Günü Hesabı):** İade tarihi geçmiş ancak henüz iade edilmemiş veya gecikmeli iade edilmiş ödünç kayıtları için gecikme günü sistem tarafından otomatik olarak hesaplanır.
- **İK-18.2 (Ceza Tutarı Formülü):** Toplam ceza tutarı, hesaplanan gecikme günü sayısı ile yönetici tarafından tanımlanan güncel günlük ceza tutarının çarpımıyla belirlenir.
- **İK-18.3 (Ceza Oluşmama Koşulu):** Son iade tarihinde veya son iade tarihinden önce iade edilen kitaplar için sistem tarafından gecikme cezası oluşturulmaz.
- **İK-18.4 (Kesinleşme ve Görünürlük):** Kitap iade işlemi tamamlandığında hesaplanan ceza tutarı kesinleşir ve öğrencinin hesabına açık borç olarak işlenir.

- # US-19: Görevli Ceza Tahsilatı ve Makbuz Kaydı — İş Kuralları

**Jira Kodu:** [KKY-17](https://dagdelen41.atlassian.net/browse/KKY-17)  
**Sorumlu:** Enes Ulutaş  
**Epic:** KKY-14 Ceza ve Rapor  
**Story Point:** 3 | **Sprint:** KKY Sprint 4  

## Kullanıcı Hikayesi
Kütüphane görevlisi olarak, öğrencinin ödediği gecikme cezasını sisteme kaydetmek ve makbuz oluşturmak istiyorum, böylece tahsilatlar kayıt altında olsun.

## Kabul Kriterleri
1. Görevli, öğrencinin açık ceza borçlarını listede görebilmelidir.
2. Tahsilat kaydedildiğinde ceza "Ödendi" durumuna geçmeli ve makbuz numarası, tarih, tutar ve işlemi yapan görevli kaydedilmelidir.
3. Ödenmemiş cezası olan öğrenciye yeni ödünç verilmeden önce uyarı gösterilmelidir.

## İş Kuralları ve Doğrulama Mantığı
- **İK-19.1 (Ön Koşul ve Bağımlılık):** Ceza tahsilatı ve makbuz oluşturma işlemi, yalnızca `US-18 (KKY-16)` kapsamında kesinleşmiş açık gecikme cezası kayıtları üzerinden gerçekleştirilir.
- **İK-19.2 (Makbuz Zorunlu Alanları):** Tahsilat onaylandığında ilgili cezanın statüsü `Ödendi` olarak güncellenir; benzersiz makbuz numarası, tahsilat tarihi, tahsil edilen tutar ve işlemi yapan görevli bilgisi sisteme zorunlu olarak kaydedilir.
- **İK-19.3 (Açık Ceza Uyarısı):** Sistemde `Ödenmedi` statüsünde gecikme cezası bulunan bir öğrenci için yeni ödünç verme işlemi başlatılmak istendiğinde görevliye uyarı mesajı gösterilir.

- # US-20: Admin Aylık En Çok Okunanlar Raporu — İş Kuralları

**Jira Kodu:** [KKY-18](https://dagdelen41.atlassian.net/browse/KKY-18)  
**Sorumlu:** Enes Ulutaş  
**Epic:** KKY-14 Ceza ve Rapor  
**Story Point:** 5 | **Sprint:** KKY Sprint 4  

## Kullanıcı Hikayesi
Sistem yöneticisi (admin) olarak, aylık en çok ödünç alınan kitapların raporunu görmek istiyorum, böylece koleksiyon ve satın alma kararlarını veriye dayandırabileyim.

## Kabul Kriterleri
1. Yönetici ay ve yıl seçerek raporu görüntüleyebilmelidir.
2. Rapor, seçilen ayda en çok ödünç alınan kitapları ödünç sayısına göre sıralı listelemelidir (kitap adı, yazar, ödünç sayısı).
3. Seçilen ayda ödünç kaydı yoksa "Bu ay için kayıt bulunamadı" mesajı gösterilmelidir.
4. Raporu yalnızca yönetici rolü görebilmelidir.

## İş Kuralları ve Doğrulama Mantığı
- **İK-20.1 (Rol Yetkisi):** Aylık en çok okunanlar raporu ekranına yalnızca `Admin` rolüne sahip kullanıcılar erişebilir; `Öğrenci` ve `Kütüphane Görevlisi` rollerinin erişimi engellenir.
- **İK-20.2 (Filtreleme ve Sıralama):** Seçilen ay ve yıla ait ödünç kayıtları gruplanarak ödünç alınma sayısına göre azalan sırada listelenir; her satırda kitap adı, yazar ve toplam ödünç sayısı gösterilir.
- **İK-20.3 (Boş Kayıt Durumu):** Seçilen ay ve yıl aralığında sistemde herhangi bir ödünç işlemi bulunmuyorsa tablo yerine standart olarak "Bu ay için kayıt bulunamadı" mesajı gösterilir.

- # US-21: Kitap Detayında Sınırlı Paylaşım — İş Kuralları

**Jira Kodu:** [KKY-26](https://dagdelen41.atlassian.net/browse/KKY-26)  
**Sorumlu:** Enes Ulutaş  
**Epic:** Kriz / Değişiklik Yönetimi  
**Story Point:** 2 | **Sprint:** KKY Sprint 4  

## Kullanıcı Hikayesi
Öğrenci (üye) olarak, kitap detay ekranında seçtiğim kitabın temel bilgilerini onayım dahilinde sınırlı kapsamda paylaşmak istiyorum, böylece kişisel verilerim korunurken kitap bilgisini paylaşabileyim.

## Kabul Kriterleri
1. Kitap detay ekranında yalnızca herkese açık kitap adı ve yazar bilgisi paylaşım kapsamına dahil edilmelidir.
2. Paylaşım işlemi kullanıcının açık onayı olmadan gerçekleştirilmemelidir.
3. Sosyal medya hesabı bağlama, harici oturum açma ve kişisel veri aktarımı yapılmamalıdır.

## İş Kuralları ve Doğrulama Mantığı
- **İK-21.1 (Kapsam Sınırlandırması):** Paylaşım içeriği yalnızca herkese açık `Kitap Adı` ve `Yazar` bilgileriyle sınırlıdır; sosyal medya hesabı bağlama ve harici oturum açma özellikleri kapsam dışıdır.
- **İK-21.2 (Kişisel Veri Koruması):** Üyeye ait ad-soyad, öğrenci numarası ve ödünç geçmişi gibi hiçbir kişisel veri dışarı aktarılmaz.
- **İK-21.3 (Kullanıcı Onayı):** Paylaşım bağlantısı veya metni yalnızca kullanıcının açık onayı ile oluşturulur; onay verilmeden herhangi bir paylaşım tetiklenmez.
