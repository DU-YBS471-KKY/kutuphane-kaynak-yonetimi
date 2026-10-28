# Sprint 1 - Kabul kriteri kontrolü

Hazırlayan: Kübra Şen  
Kontrol tarihi: 27 Ekim 2026  
Kapsam: US-01-05 / KKY-3, KKY-4, KKY-5, KKY-6, KKY-15  
Yöntem: Proje planı, Jira kabul kriterleri ve GitHub belgeleri arasında doküman tutarlılığı incelemesi.

Bu kayıt çalışan yazılım testi veya nihai Story kabulü değildir. Bulgular PO ve ilgili Story sahibinin değerlendirmesine sunulmuştur. Başka üyelerin Story durumları bu incelemeyle değiştirilmemiştir.

## Kaynaklar

- YBS 471 Kütüphane Sistemi Proje Planı: slayt 5 (Kübra'nın kriter kontrolü görevi), slayt 8 (Sprint 1 kabul kriterleri), slayt 10 (takvim).
- Kütüphane Projesi Ekip Rehberi: kabul kriterleri, bağımsız inceleme ve sprint raporları.
- [İncelenen Eray belgesi, sabit sürüm](https://github.com/DU-YBS471-KKY/kutuphane-kaynak-yonetimi/blob/91daea982dbd71d73a5db3c612dd151ce413975b/docs/gereksinimler/eray-us-01-04-hazirlik.md)
- [Güncel ekip planı ve bitirme tanımı](https://github.com/DU-YBS471-KKY/kutuphane-kaynak-yonetimi/tree/develop#readme-ov-file)

## Kontrol tablosu

| İş | Plandaki beklenti | 27 Ekim'de gözlenen | Sonuç / izlenecek adım |
| --- | --- | --- | --- |
| [US-01 / KKY-3](https://dagdelen41.atlassian.net/browse/KKY-3) | E-posta doğrulaması ve 8 haneli şifre | E-posta doğrulaması Jira ve belgede var. İK-01.1 şifrenin boş olmamasını istiyor; 8 hane koşulu yok. Belgenin US-01 başlığı kayıt ile kullanıcı girişini karıştırıyor. | KC-01: Şifre koşulu ve kayıt adlandırması Eray/PO tarafından netleştirilmeli. |
| [US-02 / KKY-4](https://dagdelen41.atlassian.net/browse/KKY-4) | 3 hatalı girişte geçici hesap kilidi | Jira kriterlerinde kilit koşulu yok. Belgedeki İK-02.3, 5 başarısız girişten sonra 15 dakika kilit diyor. | KC-02: 3/5 deneme çelişkisi için PO kararı ve varsa onaylı değişiklik referansı gerekli. |
| [US-03 / KKY-5](https://dagdelen41.atlassian.net/browse/KKY-5) | Telefon ve bildirim tercihi kaydı | Jira ve belge telefon/e-posta güncellemesini kapsıyor; bildirim tercihi kaydı yok. | KC-03: Bildirim tercihi kapsamı Eray/PO tarafından netleştirilmeli. |
| [US-04 / KKY-6](https://dagdelen41.atlassian.net/browse/KKY-6) | Rol atama ve yetki iptali | Jira ve belgede yetki atama, geri alma ve yetkisiz erişim kuralları var. | Bu başlıklarda plan-belge uyumsuzluğu görülmedi; nihai kabul PO/Review kapsamındadır. |
| [US-05 / KKY-15](https://dagdelen41.atlassian.net/browse/KKY-15) | Kategori filtresi ve hızlı sonuç listesi | Jira'da kategori filtresi, sonuç alanları ve sonuç bulunamadı mesajı var. Hız için sayısal sınır tanımlanmamış. | Kriter başlıkları mevcut. Hızın nasıl kontrol edileceği PO/Esat tarafından açıklanabilir; sayısal sınır bu incelemede uydurulmadı. |

## Karar ve yeniden kontrol

KC-01, KC-02 ve KC-03 bu kayıt hazırlanırken açıktır. Bir kuralı tek taraflı değiştirmek yerine PO'dan geçerli kuralın veya onaylı değişikliğin belirtilmesi istenmektedir. İlgili Jira kartlarına bulgu ve bu kayıt bağlantısı eklenecektir.

Düzeltme/karardan sonra Kübra'nın yeniden kontrolü:

1. Plan veya onaylı değişiklik, Jira kriteri, iş kuralı, ekran taslağı ve kontrol senaryosu aynı koşulu anlatıyor mu?
2. Şifre uzunluğu, başarısız giriş sayısı ve bildirim tercihi için açık beklenen sonuç var mı?
3. Güncel dosya ve PR bağlantıları Jira'da bulunuyor mu?
4. Düzeltme bağımsız incelemeden geçti mi? PO kabul kararı ve gerçek kontrol bulgusu kaydedildi mi?

Bu adımlar henüz uygulanmış kontrol sonucu olarak işaretlenmemiştir. 28 Ekim kapanışında verilen gerçek kararlar ve yeniden kontrol sonucu bu kayda eklenecektir.
