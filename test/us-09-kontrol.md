# US 09 belge kontrol senaryoları

Hazırlayan ve belge kontrolü: Mert Seçkin | 29 Ekim 2026  
Jira: [KKY-19](https://dagdelen41.atlassian.net/browse/KKY-19) | Sprint 2

Kopya durumunu, yetkiyi ve müsait sayısını tasarım üzerinde değerlendirdim. “Uyumlu” sonucu belge eşleşmesini belirtir; çalışan ödünç sistemi üzerinde test yapılmadı. Bağımsız incelemem 29 Ekim 2026'da Kübra Şen tarafından [PR #25'te onaylandı](https://github.com/DU-YBS471-KKY/kutuphane-kaynak-yonetimi/pull/25#pullrequestreview-5695366811); PR aynı gün develop dalına birleştirildi.

Başlangıç örneği: Aynı kitabın K-001 ve K-002 kopyaları Müsait, toplam müsait sayı 2. Örnek kullanıcılar Öğrenci, Görevli ve Admin rollerindedir.

| Kod | Kriter | Kontrol adımı | Beklenen sonuç | Belgede gözlediğim kanıt | Sonuç |
|---|---|---|---|---|---|
| KS-09-01 | 1 | Görevli ve Admin için K-001'i Bakımda yapma akışı ayrı ayrı incelenir. | Her iki yetkili rol işlem yapabilir. | B01 iki rolü tanımlıyor; B02 durum değişimini gösteriyor. | Uyumlu |
| KS-09-02 | 1 | Öğrencinin ekranı ve doğrudan durum değiştirme isteği incelenir. | Düğme gösterilmez; doğrudan istek de reddedilir. | B01 hem görünürlük hem işlem yetkisi engelini tanımlıyor. | Uyumlu |
| KS-09-03 | 2 | K-001 Bakımda yapılır ve bu kopya ödünç için seçilir. | Kopya ödünç verilemez; müsait sayı 1 olur. | B02'de K-001 Bakımda, ödünç düğmesi kapalı ve sayı 1. Doğrudan işlem de engelleniyor. | Uyumlu |
| KS-09-04 | 2 | K-001 bakımdayken K-002 incelenir. | Sağlam kopya Müsait kalır ve seçilebilir. | B02'de K-002'nin durumu ve ödünç düğmesi korunuyor. | Uyumlu |
| KS-09-05 | 3 | Görevli/Admin K-001'i yeniden Müsait yapar. | Kopya Müsait; sayı yeniden 2. | B03 durum değişimini ve yeniden hesaplamayı açıklıyor. | Uyumlu |

Kanıt: [B01–B03 ekran ve akışları](../tasarim/us-09-bakim-durumu.md). Bağımsız inceleme sonucu PR #25 geçmişinde kayıtlıdır; sonraki düzeltmeler aynı teslim bağlantısıyla izlenebilir.
