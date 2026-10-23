# US-01: Bir Üye Olarak Kullanıcı Girişi Yapabilme

**Kullanıcı Hikayesi:**
Öğrenci (üye) olarak, kütüphane sistemine kullanıcı girişimi (hesap oluşturma işlemlerimi) yapabilmek istiyorum, böylece sisteme resmi bir üye olarak tanımlanabileyim.

**Kabul Kriterleri:**
1. Sisteme kullanıcı girişi yapılırken öğrenci numarası, ad, soyad ve kurumsal e-posta bilgileri zorunlu olarak doldurulmalıdır.
2. Sistem, daha önce girişi yapılmış (mevcut) bir öğrenci numarası veya e-posta ile tekrar kullanıcı girişi yapılmasına izin vermemeli ve uyarı vermelidir.
3. Kullanıcı tanımlama işlemi başarıyla tamamlandığında sistem ekranda bir onay mesajı göstermeli ve kullanıcının kurumsal e-posta adresine bir doğrulama e-postası göndermelidir.
4. Kullanıcı, e-postadaki bağlantıyı onayladığında "Doğrulama Bekliyor" statüsündeki hesabı "Aktif" duruma geçmeli ve sisteme giriş yapabilmelidir.

**İş Kuralları ve Doğrulama Mantığı:**
* İK-01.1: Öğrenci Numarası, Ad, Soyad, E-posta ve Şifre alanları boş bırakılamaz.
* İK-01.2: Öğrenci numarası sadece rakamlardan oluşmalı ve 9 haneli olmalıdır.
* İK-01.3: Veritabanında aynı öğrenci numarasına sahip kayıt varsa işlem reddedilir.
* İK-01.4: Hesap oluşturulduğunda varsayılan statü `Doğrulama Bekliyor` olur. E-posta onayı sonrası `Aktif` statüye geçer.
