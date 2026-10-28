# US-01 – US-04: Kontrol ve Kabul Test Senaryoları

**Sorumlu:** Eray Yakup Dağdelen  
**Tarih:** 23 Ekim 2026  
**Sprint:** Sprint 1  
**Durum:** Ekran taslakları ve iş kuralları üzerinden doğrulandı (Geçti).

| Test Kodu | İlgili Story / Kriter | Ön Koşul ve Test Adımları | Beklenen Sonuç | Durum |
| :--- | :--- | :--- | :--- | :---: |
| **KS-01-01** | US-01 / Kriter 1 & 3 | Sistemde kayıtlı olmayan geçerli öğrenci no, ad, soyad, e-posta ve şifre girilerek "Kayıt Ol" butonuna basılır. | Kayıt oluşturulur ve doğrulama e-postası gönderildi bilgisi gösterilir. | **Geçti** |
| **KS-01-02** | US-01 / Kriter 2 | Sistemde mevcut olan bir öğrenci numarası veya e-posta ile ikinci kez kayıt formu gönderilir. | Kayıt engellenir; "Bu kullanıcı zaten kayıtlı" uyarısı gösterilir. | **Geçti** |
| **KS-02-01** | US-02 / Kriter 1 | Kayıtlı ve aktif öğrenci geçerli e-posta ve şifresini girerek giriş yapar. | Kullanıcı başarılı şekilde kütüphane anasayfasına yönlendirilir. | **Geçti** |
| **KS-02-02** | US-02 / Kriter 2 | Kullanıcı yanlış şifre veya kayıtlı olmayan e-posta ile giriş yapmayı dener. | Giriş reddedilir; "Kullanıcı adı veya şifre hatalı" uyarısı çıkar. | **Geçti** |
| **KS-02-03** | US-02 / Kriter 3 | Giriş ekranında "Şifremi Unuttum" tıklanır ve kayıtlı e-posta girilir. | Kayıtlı e-posta adresine şifre sıfırlama bağlantısı gönderilir. | **Geçti** |
| **KS-03-01** | US-03 / Kriter 1 & 3 | Öğrenci profil ayarlarından geçerli yeni telefon ve e-posta girip kaydeder. | Bilgiler güncellenir ve "Bilgileriniz başarıyla güncellendi" mesajı çıkar. | **Geçti** |
| **KS-03-02** | US-03 / Kriter 2 | Öğrenci e-posta alanına `@` işareti olmayan geçersiz bir metin girip kaydetmeyi dener. | İşlem kaydedilmez ve geçersiz e-posta formatı hatası gösterilir. | **Geçti** |
| **KS-03-03** | US-03 / Bildirim Tercihi | Kullanıcı profil ayarlarından 'Bildirimleri e-posta ile al' seçeneğini işaretleyip kaydeder. | Tercih başarıyla güncellenir ve ekranda 'Bilgileriniz güncellendi' mesajı çıkar. | **Geçti** |
| **KS-04-01** | US-04 / Kriter 1 & 2 | Admin yetki panelini açar, listedeki bir personele "Görevli" yetkisi verir ve ardından geri alır. | Liste görüntülenir; yetki durumu anlık olarak güncellenir. | **Geçti** |
| **KS-04-02** | US-04 / Kriter 3 | Görevli yetkisi olmayan bir hesap kitap ekleme/ödünç verme ekranına erişmeye çalışır. | Erişim engellenir ve "Yetkisiz Erişim" uyarısı gösterilir. | **Geçti** |
