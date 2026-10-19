# KUT-05: Kitap ekleme – Kayıt formu ve alan kuralları

**Sorumlu:** Kadir · **Kontrol:** Esat · **Sprint:** 1 · **Epic:** E1 Katalog

## Story
Görevli olarak sisteme yeni bir kitap eklemek istiyorum, böylece öğrenciler o kitabı katalogda bulabilsin.

## Kim kullanır?
Yalnızca **Görevli** ve **Yönetici**. Öğrenci bu formu göremez.

## Form alanları

| Alan | Zorunlu mu? | Kural |
|---|---|---|
| Başlık | Evet | En fazla 200 karakter |
| Yazar | Evet | Birden fazla yazar virgülle ayrılır |
| ISBN | Evet | 13 haneli sayı, sistemde tekrar edemez |
| Kategori | Evet | Hazır listeden seçilir (Roman, Bilim, Tarih, Ders kitabı…) |
| Yayınevi | Hayır | En fazla 100 karakter |
| Basım yılı | Hayır | 4 haneli yıl, bu yıldan büyük olamaz |
| Kopya sayısı | Evet | En az 1 |

## Akış
1. Görevli "Kitap ekle" ekranını açar.
2. Alanları doldurur ve **Kaydet**'e basar.
3. Kurallar sağlanıyorsa kitap kaydedilir ve "Kitap eklendi" mesajı görünür.
4. Kitap katalogda arama sonuçlarında görünür.

## Hata durumları

| Durum | Gösterilecek mesaj |
|---|---|
| Zorunlu alan boş | "Lütfen [alan adı] alanını doldurun." |
| ISBN 13 hane değil | "ISBN 13 haneli olmalıdır." |
| ISBN zaten kayıtlı | "Bu ISBN zaten kayıtlı." |
| Basım yılı gelecekte | "Basım yılı geçerli değil." |

Hata olduğunda kayıt yapılmaz, girilen bilgiler silinmez.

## Kabul kriterleri ve karşılığı

| Kabul kriteri | Bu belgede nerede? |
|---|---|
| Zorunlu alan boşsa kayıt yapılmaz, eksik alan gösterilir | Form alanları, Hata durumları |
| Aynı ISBN ikinci kez eklenemez | Hata durumları |
| Kaydedilen kitap katalogda görünür | Akış, 4. adım |
