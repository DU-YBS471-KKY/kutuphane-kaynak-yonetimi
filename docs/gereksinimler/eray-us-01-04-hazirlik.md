# US-01: Bir Üye Olarak Sisteme Kayıt Olabilme

**Kullanıcı Hikayesi:**
Öğrenci (üye) olarak, kütüphane sistemine kullanıcı kayıtı (hesap oluşturma işlemlerimi) yapabilmek istiyorum, böylece sisteme resmi bir üye olarak tanımlanabileyim.

**Kabul Kriterleri:**
1. Sisteme kullanıcı kayıtı yapılırken öğrenci numarası, ad, soyad ve kurumsal e-posta bilgileri zorunlu olarak doldurulmalıdır.
2. Sistem, daha önce kayıt yapılmış (mevcut) bir öğrenci numarası veya e-posta ile tekrar kullanıcı kayıtı yapılmasına izin vermemeli ve uyarı vermelidir.
3. Kullanıcı tanımlama işlemi başarıyla tamamlandığında sistem ekranda bir onay mesajı göstermeli ve kullanıcının kurumsal e-posta adresine bir doğrulama e-postası göndermelidir.
4. Kullanıcı, e-postadaki bağlantıyı onayladığında "Doğrulama Bekliyor" statüsündeki hesabı "Aktif" duruma geçmeli ve sisteme giriş yapabilmelidir.
5. Belirlenen şifre en az 8 karakter uzunluğunda olmalıdır.

**İş Kuralları ve Doğrulama Mantığı:**
* İK-01.1: Öğrenci Numarası, Ad, Soyad, E-posta ve Şifre alanları boş bırakılamaz.
* İK-01.2: Öğrenci numarası sadece rakamlardan oluşmalı ve 9 haneli olmalıdır.
* İK-01.3: Veritabanında aynı öğrenci numarasına sahip kayıt varsa işlem reddedilir.
* İK-01.4: Hesap oluşturulduğunda varsayılan statü `Doğrulama Bekliyor` olur. E-posta onayı sonrası `Aktif` statüye geçer.

* # US-02: Sisteme Giriş Yapma ve Şifre Sıfırlama — İş Kuralları

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
4. Arka arkaya 3 kez hatalı giriş yapıldığında hesap geçici olarak kilitlenmeli ve kullanıcıya uyarı verilmelidir.

## İş Kuralları ve Doğrulama Mantığı
* **İK-02.1 (Kimlik Doğrulama):** Giriş işlemi yalnızca `Aktif` statüsündeki kayıtlı e-posta ve eşleşen şifre ile gerçekleşir.
* **İK-02.2 (Güvenlik Mesajı):** Hatalı girişlerde hangi bilginin (e-posta mı şifre mi) yanlış olduğu açık edilmez; standart olarak "Kullanıcı adı veya şifre hatalı" mesajı gösterilir.
* **İK-02.3 (Hatalı Giriş Sınırı):** 3. başarısız giriş denemesinde hesap 15 dakika süreyle geçici olarak kilitlenir.
* **İK-02.4 (Şifre Sıfırlama Bağlantısı):** Sıfırlama bağlantısı tek kullanımlıktır ve oluşturulduktan sonra 30 dakika boyunca geçerlidir.

* # US-03: Öğrenci Profil ve İletişim Bilgisi Güncelleme — İş Kuralları

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
4. Kullanıcı profil ekranından bildirim tercihlerini (örneğin e-posta ile bildirim) seçebilmeli ve kaydedebilmelidir.
## İş Kuralları ve Doğrulama Mantığı
* **İK-03.1 (Değiştirilebilir Alanlar):** Öğrenci yalnızca telefon numarası ve e-posta adresini güncelleyebilir; Öğrenci Numarası ve Ad/Soyad alanları salt okunurdur (değiştirilemez).
* **İK-03.2 (Format Kontrolü):** E-posta adresi `@` ve geçerli alan adı içermelidir. Telefon numarası 10 veya 11 haneli rakamlardan oluşmalıdır.
* **İK-03.3 (E-posta Tekilliği):** Güncellenmek istenen yeni e-posta adresi sistemde başka bir üyeye kayıtlıysa işlem reddedilir.

* # US-04: Admin Personel Hesabı Yetkilendirme — İş Kuralları

**Jira Kodu:** [KKY-6](https://dagdelen41.atlassian.net/browse/KKY-6)  
**Sorumlu:** Eray Yakup Dağdelen  
**Epic:** Kullanıcı ve Üye Yönetimi  
**Story Point:** 5 | **Sprint:** Sprint 1  

## Kullanıcı Hikayesi
Sistem yöneticisi (admin) olarak, kütüphane personeli hesaplarını yetkilendirmek istiyorum, böylece sadece yetkili görevliler kitap ekleme veya ödünç verme işlemlerini yapabilsin.

## Kabul Kriterleri
1. Admin, sistemdeki tüm kayıtlı personel hesaplarını yetki durumlarıyla birlikte listede görebilmelidir.
2. Admin, istediği bir hesaba "Görevli" yetkisi atayabilmeli veya mevcut yetkiyi geri alabilmelidir.
3. Yetkisiz bir personel görevli ekranlarına girmeye çalıştığında sistem "Yetkisiz Erişim" uyarısı vermelidir.

## İş Kuralları ve Doğrulama Mantığı
* **İK-04.1 (Rol Hiyerarşisi):** Sistemde `Öğrenci`, `Kütüphane Görevlisi` ve `Admin` olmak üzere 3 temel rol bulunur. Yetki atama/kaldırma ekranına yalnızca `Admin` rolü erişebilir.
* **İK-04.2 (Anlık Yetki Geçişi):** Görevli yetkisi geri alınan kullanıcının aktif oturumundaki yönetim izinleri anında kısıtlanır; kitap ekleme ve ödünç verme ekranlarına erişimi engellenir.
* **İK-04.3 (Kendi Yetkisini Kaldırma Engeli):** Sistemdeki son aktif Admin hesabı kendi Admin yetkisini kaldıramaz (sistemin yöneticisiz kalmasını önleme kuralı).
