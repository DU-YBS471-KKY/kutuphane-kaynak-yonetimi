# Sprint 4 Planning ve açılış kaydım

Mert Seçkin — 27 Kasım 2026

| Alan | Kayıt |
|---|---|
| Durum | Jira’da aktif |
| Başlangıç | 27 Kasım 2026 23.09 |
| Bitiş hedefi | 11 Aralık 2026 23.55, Türkiye saati |
| PO / SM | Kübra Şen / Mert Seçkin |
| Açılış kapsamı | 5 Story / 16 SP + 3 bug = 8 iş |

## Hedef

Ödünç sonrası bildirim, ceza ve tahsilat akışlarını hazırlamak; sınırlı kitap paylaşımını ve üç ders bug’ının çözüm akışlarını bağımsız kontrollerle doğrulamak.

Kübra hedefi ve 9 işlik aday kapsamı koşullu uygun bulmuş, US-20’yi ilk çıkarılacak iş olarak belirtmişti. Devir teyidi açık olduğu için US-20’yi açılışta backlog’da bıraktım; aktif kapsam 8 iş oldu. Enes’in aktif yükü 10 SP. Eray/Enes teyidi ve PO kapsam kararıyla US-20 ayrıca değerlendirilecek. İki haftalık planı kontrol, düzeltme ve kapanış çalışmaları için kaydettim.

| İş | Sorumlu | SP | Açılış durumu | Çıktı ve kontrol |
|---|---|---|---|---|
| KKY-23 / US-16 | Kübra | 3 | To Do; PR #62 hazır | İade hatırlatması; 6 senaryo, Eray/Kadir incelemesi. |
| KKY-24 / US-17 | Kübra | 3 | To Do; PR #62 hazır | Rezervasyon bildirimi; 6 senaryo, Eray/Kadir incelemesi. |
| KKY-16 / US-18 | Enes | 5 | To Do; PR #63 gereksinim | Ceza hesabı ekran/akışı ve sınır kontrolleri. |
| KKY-17 / US-19 | Enes | 3 | To Do; PR #63 gereksinim | Tahsilat ve makbuz; US-18 kuralına bağlı. |
| KKY-26 / US-21 | Enes | 2 | To Do; PR #63 gereksinim | Kullanıcı onaylı kitap adı/yazar paylaşımı; QA Kübra. |
| KKY-27 | Esat | - | To Do | Arama ders bug’ı; çözüm ve kontrol sonucu. |
| KKY-28 | Kadir | - | To Do | 3 kitap limiti ders bug’ı; sınır ve ret kontrolü. |
| KKY-29 | Mert | - | In Progress; PR #61 | İade sonrası liste akışı; 5 senaryo, Kübra incelemesi. |

Öncelik: KKY-29 → 23 → 24 → 16 → 27/28 → 17 → 26. Sekiz işin Jira başlangıcı 27 Kasım, bitişi 11 Aralık olarak eşitlendi. Üç bug puanlanmamış; 16 SP toplamına sıfır eforla eklenmiş sayılmaz.

## Açık kapasite ve kapsam kayıtları

| Üye | Önceki kayıttaki saat | Yeni dönem teyidi |
|---|---|---|
| Mert | | Güncellenecek |
| Kübra | 8 | Önceki 2 Aralık planı; 11 Aralık için güncellenecek |
| Eray | 6 | Önceki 2 Aralık planı; 11 Aralık için güncellenecek |
| Esat | | Güncellenecek |
| Kadir | | Güncellenecek |
| Enes | | Güncellenecek |

US-20 (KKY-18, 5 SP) ve kopya KKY-30 aktif sprint dışında. US-20’nin devir/kapsam kararı, KKY-30’un kapanışı için Enes teyidi takip edilecek.

## Tamamlanma kriterleri

1. Çıktı kabul kriterlerini ve kaydedilen PO kararlarını karşılar.
2. Başka bir üye inceler; bulgular düzeltilir ve kontrol sonucu yazılır.
3. PR onaylanıp birleşir; Jira’da çıktı, kontrol ve kabul bağlantısı yer alır.
