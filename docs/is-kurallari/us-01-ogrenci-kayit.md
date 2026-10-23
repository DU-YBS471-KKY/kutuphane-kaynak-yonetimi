# US-01: Bir Üye Olarak Kullanıcı Girişi / Öğrenci Numarasıyla Kayıt Olabilme — İş Kuralları

**Jira Kodu:** [KKY-3](https://dagdelen41.atlassian.net/browse/KKY-3)  
**Sorumlu:** Eray Yakup Dağdelen  
**Epic:** Kullanıcı ve Üye Yönetimi  
**Story Point:** 3 | **Sprint:** Sprint 1  

## Kullanıcı Hikayesi
Öğrenci olarak, öğrenci numaramla sisteme kayıt olmak istiyorum, böylece kütüphane hizmetlerinden yararlanmaya başlayabileyim.

## Kabul Kriterleri
1. Sisteme kayıt olurken geçerli bir öğrenci numarası, ad, soyad, kurumsal e-posta adresi ve şifre girilmelidir.
2. Aynı öğrenci numarası veya e-posta adresi ile ikinci bir kayıt oluşturulamamalı, sistem "Bu kullanıcı zaten kayıtlı" uyarısı vermelidir.
3. Kayıt başarıyla tamamlandığında e-posta adresine bir doğrulama bağlantısı gönderilmelidir.

## İş Kuralları ve Doğrulama Mantığı
* **İK-01.1 (Zorunlu Alanlar):** Öğrenci Numarası, Ad, Soyad, E-posta ve Şifre alanları boş bırakılamaz. Boş bırakıldığında form gönderimi engellenir.
* **İK-01.2 (Öğrenci Numarası Formatı):** Öğrenci numarası 9 haneli sayısal bir değer olmalıdır. Harf veya özel karakter içeremez.
* **İK-01.3 (Tekillik Kuralı):** Sistem veritabanında girilen öğrenci numarası veya e-posta adresi mevcutsa yeni kayıt reddedilir.
* **İK-01.4 (Hesap Durumu):** Yeni oluşturulan hesap varsayılan olarak `Doğrulama Bekliyor` statüsünde açılır; e-posta onayından sonra `Aktif` olur.
