# US-03: Öğrenci Profil ve İletişim Bilgisi Güncelleme — İş Kuralları

**Jira Kodu:** [KKY-5](https://dagdelen41.atlassian.net/browse/KKY-5)  
**Sorumlu:** Eray Yakup Dağdelen  
**Epic:** Kullanıcı ve Üye Yönetimi  
**Story Point:** 2 | **Sprint:** Sprint 1  

## Kullanıcı Hikayesi
Öğrenci olarak, profilimdeki telefon numarası ve e-posta gibi iletişim bilgilerimi güncellemek istiyorum, böylece kütüphaneden gelen iade ve ceza bildirimlerini doğru adreslerden alabilirim.

## Kabul Kriterleri
1. Öğrenci, profil ayarları sekmesinden telefon numarası ve e-posta alanlarını değiştirebilmelidir.
2. Geçersiz bir e-posta formatı girildiğinde sistem kaydetmemeli ve hata vermelidir.
3. Değişiklikler kaydedildiğinde ekranda "Bilgileriniz başarıyla güncellendi" onay mesajı çıkmalıdır.

## İş Kuralları ve Doğrulama Mantığı
* **İK-03.1 (Değiştirilebilir Alanlar):** Öğrenci yalnızca telefon numarası ve e-posta adresini güncelleyebilir; Öğrenci Numarası ve Ad/Soyad alanları salt okunurdur (değiştirilemez).
* **İK-03.2 (Format Kontrolü):** E-posta adresi `@` ve geçerli alan adı içermelidir. Telefon numarası 10 veya 11 haneli rakamlardan oluşmalıdır.
* **İK-03.3 (E-posta Tekilliği):** Güncellenmek istenen yeni e-posta adresi sistemde başka bir üyeye kayıtlıysa işlem reddedilir.
