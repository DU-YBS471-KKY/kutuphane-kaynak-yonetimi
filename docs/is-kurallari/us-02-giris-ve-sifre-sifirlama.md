# US-02: Sisteme Giriş Yapma ve Şifre Sıfırlama — İş Kuralları

**Jira Kodu:** [KKY-4](https://dagdelen41.atlassian.net/browse/KKY-4)  
**Sorumlu:** Eray Yakup Dağdelen  
**Epic:** Kullanıcı ve Üye Yönetimi  
**Story Point:** 2 | **Sprint:** Sprint 1  

## Kullanıcı Hikayesi
Üye (öğrenci) olarak, e-posta ve şifremle sisteme güvenli giriş yapmak ve şifremi unuttuğumda sıfırlamak istiyorum, böylece kütüphane hesabıma sorunsuz erişebilirim.

## Kabul Kriterleri
1. Doğru e-posta ve şifre girildiğinde sistem kullanıcıyı anasayfaya yönlendirmelidir.
2. Hatalı giriş yapıldığında ekranda "Kullanıcı adı veya şifre hatalı" uyarısı çıkmalıdır.
3. "Şifremi Unuttum" butonuna tıklandığında kayıtlı e-posta adresine şifre sıfırlama bağlantısı gönderilmelidir.

## İş Kuralları ve Doğrulama Mantığı
* **İK-02.1 (Kimlik Doğrulama):** Giriş işlemi yalnızca `Aktif` statüsündeki kayıtlı e-posta ve eşleşen şifre ile gerçekleşir.
* **İK-02.2 (Güvenlik Mesajı):** Hatalı girişlerde hangi bilginin (e-posta mı şifre mi) yanlış olduğu açık edilmez; standart olarak "Kullanıcı adı veya şifre hatalı" mesajı gösterilir.
* **İK-02.3 (Hatalı Giriş Sınırı):** Ardışık 5 başarısız giriş denemesinde hesap 15 dakika süreyle geçici olarak kilitlenir.
* **İK-02.4 (Şifre Sıfırlama Bağlantısı):** Sıfırlama bağlantısı tek kullanımlıktır ve oluşturulduktan sonra 30 dakika boyunca geçerlidir.
