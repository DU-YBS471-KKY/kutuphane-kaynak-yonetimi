# US-18 – US-21 Ekran/Akış Taslakları ve Kontrol Senaryoları

---

# US-18: Geciken Her Gün İçin Otomatik Ceza Hesabı — Ekran/Akış ve Kontrol Senaryoları

**Jira Kodu:** KKY-16 | **Sorumlu:** Enes Ulutaş | **Story Point:** 5 | **Sprint:** KKY Sprint 4

## Ekran ve Akış Taslağı
- **İlgili Ekran / Modül:** Ödünç / İade İşlemleri ve Gecikme Cezası Hesaplama Akışı
- **Görünen / İşlenen Alanlar:**
  - Öğrenci ve ödünç kaydı bilgisi
  - Son iade tarihi ve iade / kontrol tarihi
  - Gecikme günü sayısı (otomatik hesaplanan)
  - Günlük ceza tutarı (yöneticinin belirlediği tutar)
  - Toplam ceza tutarı (`Gecikme Günü × Günlük Ceza Tutarı`)
  - Ceza durumu (`Ceza Yok` / `Hesaplandı` / `Kesinleşti - Öğrenci Hesabında`)
- **Akış Adımları:**
  1. Sistem ödünç kaydının son iade tarihini kontrol eder.
  2. Kitap son iade tarihinde veya öncesinde iade edildiyse gecikme günü `0` olur ve ceza oluşmaz.
  3. İade tarihi geçtiyse gecikme günü otomatik hesaplanır ve günlük ceza tutarı ile çarpılır.
  4. İade işlemi tamamlandığında ceza tutarı kesinleşir ve öğrencinin hesabında görünür (US-19 tahsilat akışına zemin oluşturur).

## Kontrol Senaryoları
- **KS-18.1 (Zamanında / Erken İade):** Son iade tarihinde veya daha önce iade edilen kitap için gecikme günü ve ceza tutarı oluşmadığı doğrulanır.
- **KS-18.2 (Gecikme Günü ve Tutar Hesabı):** İade tarihi geçen kayıtta gecikme gününün doğru hesaplandığı ve günlük ceza tutarıyla çarpımının beklendiği gibi çalıştığı kontrol edilir.
- **KS-18.3 (İade Sonrası Kesinleşme):** Kitap iade edildiğinde cezanın kesinleştiği ve öğrencinin hesabında görüntülendiği doğrulanır.

---

# US-19: Görevli Ceza Tahsilatı ve Makbuz Kaydı — Ekran/Akış ve Kontrol Senaryoları

**Jira Kodu:** KKY-17 | **Sorumlu:** Enes Ulutaş | **Story Point:** 3 | **Sprint:** KKY Sprint 4

## Ekran ve Akış Taslağı
- **İlgili Ekran / Modül:** Görevli Ceza Tahsilat Ekranı, Makbuz Kaydı ve Ödünç Verme Kontrol Akışı
- **Görünen / İşlenen Alanlar:**
  - Öğrenci bilgisi ve açık ceza borçları listesi
  - Tahsilat tutarı ve ödeme onayı aksiyonu
  - Makbuz kayıt alanları: Makbuz numarası, tarih, tutar, işlemi yapan görevli
  - Ceza durumu (`Ödenmedi` / `Ödendi`)
  - Yeni ödünç verme öncesi açık ceza uyarı mesajı
- **Akış Adımları:**
  1. Görevli, öğrencinin açık ceza borçlarını listede görüntüler.
  2. Tahsilat kaydedildiğinde ilgili cezanın durumu `Ödendi` olur; makbuz numarası, tarih, tutar ve görevli bilgisi kaydedilir.
  3. Ödenmemiş cezası bulunan bir öğrenciye yeni ödünç verilmek istendiğinde sistem önce uyarı gösterir.

## Kontrol Senaryoları
- **KS-19.1 (Açık Borç Listeleme):** Görevlinin öğrencinin ödenmemiş ceza borçlarını eksiksiz görebildiği kontrol edilir.
- **KS-19.2 (Tahsilat ve Makbuz Kaydı):** Tahsilat yapıldığında durumun `Ödendi`ye geçtiği ve makbuz numarası, tarih, tutar ile görevli bilgisinin kaydedildiği doğrulanır.
- **KS-19.3 (Yeni Ödünç Uyarısı):** Ödenmemiş cezası olan öğrenci için yeni ödünç işleminde sistemin uyarı verdiği kontrol edilir.

---

# US-20: Admin Aylık En Çok Okunanlar Raporu — Ekran/Akış ve Kontrol Senaryoları

**Jira Kodu:** KKY-18 | **Sorumlu:** Enes Ulutaş | **Story Point:** 5 | **Sprint:** KKY Sprint 4

## Ekran ve Akış Taslağı
- **İlgili Ekran / Modül:** Yönetici (Admin) Aylık En Çok Okunanlar Rapor Ekranı
- **Görünen / İşlenen Alanlar:**
  - Ay ve yıl seçim filtreleri
  - Rapor listesi / tablosu: Kitap adı, yazar, ödünç sayısı (ödünç sayısına göre sıralı)
  - Boş kayıt durumu mesajı: `"Bu ay için kayıt bulunamadı"`
  - Rol yetki kontrolü (yalnızca yönetici rolü)
- **Akış Adımları:**
  1. Sistem yöneticisi raporu açar ve ay ile yıl seçer.
  2. Seçilen dönemde ödünç kaydı varsa kitaplar ödünç sayısına göre sıralı olarak (kitap adı, yazar, ödünç sayısı) listelenir.
  3. Seçilen ayda ödünç kaydı yoksa `"Bu ay için kayıt bulunamadı"` mesajı gösterilir.
  4. Yönetici rolü dışındaki kullanıcıların rapora erişimi engellenir.

## Kontrol Senaryoları
- **KS-20.1 (Ay/Yıl Filtresi ve Sıralama):** Seçilen ay ve yıla göre kitapların ödünç sayısına göre sıralı (kitap adı, yazar, ödünç sayısı) listelendiği kontrol edilir.
- **KS-20.2 (Kayıt Yoksa Mesaj):** Seçilen ayda ödünç kaydı bulunmadığında `"Bu ay için kayıt bulunamadı"` mesajının göründüğü doğrulanır.
- **KS-20.3 (Yetki Kısıtı):** Yönetici rolü dışındaki kullanıcıların raporu görüntüleyemediği kontrol edilir.

---

# US-21: Kitap Detayından Güvenli Sosyal Medya Paylaşımı (Kriz Değişikliği) — Ekran/Akış ve Kontrol Senaryoları

**Jira Kodu:** KKY-26 | **Sorumlu:** Enes Ulutaş | **Story Point:** 2 | **Sprint:** KKY Sprint 4

## Ekran ve Akış Taslağı
- **İlgili Ekran / Modül:** Kitap Detay Ekranı — Sınırlı Paylaşım Onay Akışı
- **Görünen / İşlenen Alanlar:**
  - `Paylaş` aksiyonu
  - Paylaşım onay adımı / penceresi
  - Kapsam içi veriler: Yalnızca kitap adı ve yazar bilgisi
  - Kapsam dışı / aktarılmayanlar: Sosyal medya hesabı bağlama ekranı yok; öğrenci bilgisi veya ödünç geçmişi aktarılmaz
- **Akış Adımları:**
  1. Kullanıcı kitap detay ekranında `Paylaş` aksiyonunu tetikler.
  2. Paylaşım öncesinde kullanıcıdan açık onay alınır.
  3. Onay verildiğinde yalnızca kitap adı ve yazar bilgisi paylaşılır; sosyal medya hesabı bağlama yapılmaz ve kişisel veri / ödünç geçmişi aktarılmaz.

## Kontrol Senaryoları
- **KS-21.1 (Açık Onay ve Sınırlı Veri):** Paylaşım öncesi açık onay alındığı ve yalnızca kitap adı ile yazar bilgisinin aktarıldığı kontrol edilir.
- **KS-21.2 (Kişisel Veri ve Harici Hesap Koruması):** Öğrenci bilgisi veya ödünç geçmişinin paylaşılmadığı ve harici sosyal medya hesabı bağlama ekranının bulunmadığı doğrulanır.
