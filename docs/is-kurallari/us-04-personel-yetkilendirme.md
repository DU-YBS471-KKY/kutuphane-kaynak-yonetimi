# US-04: Admin Personel Hesabı Yetkilendirme — İş Kuralları

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
