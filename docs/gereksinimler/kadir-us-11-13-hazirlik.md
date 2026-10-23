# US-11–US-13 Gereksinim ve Kabul Kriterleri

Sorumlu: Abdülkadir Güneş (@kadirgns)
Hazırlanma tarihi: 23 Ekim 2026

Sorumlu olduğum US-11, US-12 ve US-13 için kabul kriterlerini ve kontrol senaryolarını burada topladım. Ekran taslaklarını, işlem akışlarını ve kontrol sonuçlarını ekip planına göre Sprint 3'te (4–11 Kasım) hazırlayacağım. Şu anda üç iş de Backlog'da.

| İş | Jira | Puan | Hedef | Trello |
|---|---|---:|---|---|
| US-11 Barkodla ödünç verme | [KKY-10](https://dagdelen41.atlassian.net/browse/KKY-10) | 5 | Sprint 3 | [Kart](https://trello.com/c/YfgVXEIf) |
| US-12 İade ve stok onayı | [KKY-11](https://dagdelen41.atlassian.net/browse/KKY-11) | 3 | Sprint 3 | [Kart](https://trello.com/c/vspRpCLH) |
| US-13 Ödünç süresini uzatma | [KKY-12](https://dagdelen41.atlassian.net/browse/KKY-12) | 3 | Sprint 3 | [Kart](https://trello.com/c/o8Vvxw12) |

Bu üç işi Jira'da Ödünç Süreçleri Epic'i (KKY-13) altında takip ediyorum.

## US-11 — Barkodla kitap ödünç verme

**User Story:** Kütüphane görevlisi olarak öğrencinin ve kitabın barkodunu okutarak ödünç vermek istiyorum, böylece işlem hızlı ve hatasız kaydedilsin.

### Kabul kriterleri

1. Kitap barkodu okutulduğunda kitap bilgisi ve müsaitlik durumu görünür.
2. Yalnızca müsait kitap ödünç verilebilir; kitap başka durumdaysa uyarı gösterilir.
3. Ödünç süresi 15 gündür; iade tarihi otomatik hesaplanıp kayıtta gösterilir.

### Sprint 3'te hazırlayacaklarım

- Öğrenci ve kitap barkodunun okutulduğu ödünç verme ekranı taslağı.
- Müsaitlik kontrolü ve iade tarihi hesaplama akışı.
- Aşağıdaki senaryoların değerlendirilmesi ve sonuç kaydı.

| Senaryo | Beklenen sonuç |
|---|---|
| Müsait kitabın barkodu okutulur | Kitap bilgisi ve "Müsait" durumu görünür. |
| Müsait kitap ödünç verilir | Kayıt oluşur; iade tarihi ödünç tarihinden 15 gün sonrası olarak gösterilir. |
| Ödünçte ya da Bakımda olan kitap okutulur | Uyarı gösterilir; ödünç kaydı oluşmaz. |

## US-12 — İade edilen kitabın stok onayı

**User Story:** Kütüphane görevlisi olarak iade edilen kitabı kontrol edip stoğa geri almak istiyorum, böylece kitap tekrar ödünç verilebilsin.

### Kabul kriterleri

1. İade alınan kitabın durumu "Müsait" olur ve stok sayısı 1 artar.
2. Kitap hasarlıysa görevli "Bakımda" işaretleyebilir; bu durumda stoğa eklenmez.
3. İade tarihi ve işlemi yapan görevli kayda geçer.

### Sprint 3'te hazırlayacaklarım

- İade alma ve kitap kontrolü ekranı taslağı.
- Sağlam ve hasarlı iade için iki ayrı akış.
- Aşağıdaki senaryoların değerlendirilmesi ve sonuç kaydı.

| Senaryo | Beklenen sonuç |
|---|---|
| Sağlam kitap iade edilir | Durum "Müsait" olur; stok 1 artar. |
| Hasarlı kitap iade edilir, "Bakımda" seçilir | Durum "Bakımda" olur; stok değişmez. |
| Herhangi bir iade tamamlanır | İade tarihi ve işlemi yapan görevli kayıtta görünür. |

## US-13 — Ödünç süresini 7 gün uzatma

**User Story:** Öğrenci olarak ödünç aldığım kitabın süresini 7 gün uzatmak istiyorum, böylece okumayı bitirmeden iade etmek zorunda kalmayayım.

### Kabul kriterleri

1. Uzatma yalnızca iade tarihi geçmeden ve bir kez yapılabilir.
2. Kitap başka bir öğrenci tarafından rezerve edildiyse uzatma reddedilir ve sebebi gösterilir.
3. Uzatma onaylanınca yeni iade tarihi öğrencinin ödünç listesinde görünür.

### Sprint 3'te hazırlayacaklarım

- Öğrencinin ödünç listesinde "Süreyi uzat" işlemi taslağı.
- Uzatma kuralları ve ret mesajları.
- Aşağıdaki senaryoların değerlendirilmesi ve sonuç kaydı.

| Senaryo | Beklenen sonuç |
|---|---|
| Süresi dolmamış kitap ilk kez uzatılır | İade tarihi 7 gün ileri alınır; listede yeni tarih görünür. |
| Aynı kitap ikinci kez uzatılmak istenir | İşlem reddedilir; "Uzatma hakkı kullanıldı" bilgisi gösterilir. |
| Rezerve edilmiş kitap uzatılmak istenir | İşlem reddedilir; rezervasyon sebebi gösterilir. |
| İade tarihi geçmiş kitap uzatılmak istenir | İşlem reddedilir. |

## Diğer işlerle bağlantılar

- **US-12 ↔ US-09 (Mert):** Hasarlı iade edilen kitabın "Bakımda" durumu, US-09'daki bakım durumu tanımıyla aynı olmalı.
- **US-13 ↔ US-14 (Kübra):** Uzatma kontrolü, US-14'teki rezervasyon kaydını kullanır.

## İnceleme ve sonraki adım

Mert'in kabul kriterlerini ve kontrol senaryolarını incelemesini bekliyorum. Gelen düzeltmeleri aynı çalışma dalında yapacağım. Sprint 3'te ekran taslaklarını ve işlem akışlarını ekleyip senaryoları bunlar üzerinden kontrol edeceğim; sonuçları test belgesine yazacağım.
