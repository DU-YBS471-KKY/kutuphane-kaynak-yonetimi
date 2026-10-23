# US-01: Bir Üye Olarak Kullanıcı Girişi Yapabilme — İş Kuralları

**Jira Kodu:** (KKY-3)
**Sorumlu:** Eray Yakup Dağdelen  
**Epic:** Kullanıcı ve Üye Yönetimi  
**Story Point:** 3 | **Sprint:** Sprint 1  

## Kullanıcı Hikayesi
Öğrenci (üye) olarak, kütüphane sistemine kullanıcı girişimi (hesap oluşturma işlemlerimi) yapabilmek istiyorum, böylece sisteme resmi bir üye olarak tanımlanabileyim.

## Kabul Kriterleri
1. Sisteme kullanıcı girişi yapılırken öğrenci numarası, ad, soyad ve kurumsal e-posta bilgileri zorunlu olarak doldurulmalıdır.
2. Sistem, daha önce girişi yapılmış (mevcut) bir öğrenci numarası veya e-posta ile tekrar kullanıcı girişi yapılmasına izin vermemelidir.
3. Kullanıcı tanımlama işlemi başarıyla tamamlandığında sistem onay mesajı göstermelidir.

## İş Kuralları ve Doğrulama Mantığı
* **İK-01.1 (Zorunlu Alanlar):** Kullanıcı tanımlama ekranında Öğrenci Numarası, Ad, Soyad, E-posta ve Şifre alanları boş bırakılamaz.
* **İK-01.2 (Format):** Öğrenci numarası sadece rakamlardan oluşmalı ve 9 haneli olmalıdır.
* **İK-01.3 (Mükerrer Kullanıcı Engeli):** Veritabanında aynı öğrenci numarasına sahip başka bir kullanıcı girişi varsa işlem reddedilir ve "Bu kullanıcı sisteme zaten girilmiş" uyarısı verilir.
* **İK-01.4 (Hesap Durumu):** Sisteme girişi yapılan yeni hesap varsayılan olarak `Doğrulama Bekliyor` statüsünde açılır.
