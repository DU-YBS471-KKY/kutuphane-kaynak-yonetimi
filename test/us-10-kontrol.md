# US 10 belge kontrol senaryoları

Hazırlayan ve belge kontrolü: Mert Seçkin | 29 Ekim 2026  
Jira: [KKY-20](https://dagdelen41.atlassian.net/browse/KKY-20) | Sprint 2

Öğrenci gönderimi ile görevli/admin yayın kararını tasarım üzerinde karşılaştırdım. Sonuçlar belge tutarlılığı kontrolüdür; uygulamada oturum açıp yorum yayımlamadım. Bağımsız incelemem 29 Ekim 2026'da Kübra Şen tarafından [PR #25'te onaylandı](https://github.com/DU-YBS471-KKY/kutuphane-kaynak-yonetimi/pull/25#pullrequestreview-5695366811); PR aynı gün develop dalına birleştirildi.

Örnekler: Oturumu açık Öğrenci A, başka bir okuyucu Öğrenci B ve görevli/admin. “Örnek Kitap A” ve “Örnek yorum” yalnızca senaryo verisidir.

| Kod | Kriter | Kontrol adımı | Beklenen sonuç | Belgede gözlediğim kanıt | Sonuç |
|---|---|---|---|---|---|
| KS-10-01 | 1 | Oturum açıkken alt ve üst sınır 1 ve 5 puan ile gönderim incelenir. | Her iki tam sayı kabul edilir; kayıt onay bekler. | Y01 düğmeleri ve Y02 gönderim sonucu birbiriyle uyumlu. | Uyumlu |
| KS-10-02 | 1 | 0, 6 ve 2.5 değerleriyle gönderim isteği değerlendirilir. | Kayıt oluşmaz; geçerli tam sayı uyarısı gösterilir. | Y01 yalnızca düğmeleri değil istek değerini de doğruluyor. | Uyumlu |
| KS-10-03 | 1 | Oturumu olmayan kullanıcı gönderim yapmak ister. | Giriş istenir; gönderim oluşturulmaz. | Y01 oturum koşulunu ve giriş mesajını tanımlıyor. | Uyumlu |
| KS-10-04 | 2 | Öğrenci A yorum gönderir; Öğrenci B'nin kitap detayı incelenir. | A'nın kaydı Onay bekliyor; B'ye puan ve yorum görünmez. | Y02 kişisel durum ekranı ile onaylı yorum listesini ayırıyor. | Uyumlu |
| KS-10-05 | 3 | Görevli ve Admin için Onayla yolu ayrı ayrı değerlendirilir. | Gönderim Onaylandı; puan ve yorum kitap detayında görünür. | Y03 iki rolü ve yayın geçişini tanımlıyor. | Uyumlu |
| KS-10-06 | 3 | Görevli/Admin Reddet yolunu seçer. | Reddedildi; puan ve yorum diğer öğrencilere yayımlanmaz. | Y03 ret kolunda yayın adımı yok. | Uyumlu |
| KS-10-07 | 3 | Öğrenci onay kararı göndermeyi dener. | Onay işlemi reddedilir. | Y03'te onay yetkisi yalnızca Görevli/Admin için tanımlı. | Uyumlu |

Kanıt: [Y01–Y03 ekranları ve durum akışı](../tasarim/us-10-puan-yorum.md). Yeni geri bildirimler PR'da kaydedilecek.
