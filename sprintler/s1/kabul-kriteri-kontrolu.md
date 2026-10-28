# Sprint 1 - Kabul kriteri kontrolü

Hazırlayan: Kübra Şen  
Kontrol tarihi: 27 Ekim 2026  
Kapsam: US-01-05 / KKY-3, KKY-4, KKY-5, KKY-6, KKY-15  
Yöntem: Proje planı, Jira kabul kriterleri ve GitHub belgeleri arasında doküman tutarlılığı incelemesi.

Bu kayıtta doküman tutarlılığını inceledim; çalışan yazılım testi veya nihai Story kabulü yapmadım. Bulgularımı PO ve ilgili Story sahibinin değerlendirmesine sundum. Başka üyelerin Story durumlarını değiştirmedim.

## Kaynaklarım

- YBS 471 Kütüphane Sistemi Proje Planı: slayt 5 (kriter kontrolü görevim), slayt 8 (Sprint 1 kabul kriterleri), slayt 10 (takvim).
- Kütüphane Projesi Ekip Rehberi: kabul kriterleri, bağımsız inceleme ve sprint raporları.
- [İncelediğim Eray belgesi, sabit sürüm](https://github.com/DU-YBS471-KKY/kutuphane-kaynak-yonetimi/blob/91daea982dbd71d73a5db3c612dd151ce413975b/docs/gereksinimler/eray-us-01-04-hazirlik.md)
- [Ekip planı ve bitirme tanımı](https://github.com/DU-YBS471-KKY/kutuphane-kaynak-yonetimi/tree/develop#readme-ov-file)

## 27 Ekim kontrol tablom

| İş | Plandaki beklenti | 27 Ekim'de gözlemlediğim | Sonuç / takip adımım |
| --- | --- | --- | --- |
| US-01 / KKY-3 | E-posta doğrulaması ve 8 haneli şifre | E-posta doğrulamasını Jira ve belgede gördüm. İK-01.1 şifrenin boş olmamasını istiyor; 8 hane koşulunu bulamadım. Belgenin US-01 başlığında kayıt ile kullanıcı girişinin karıştığını gördüm. | KC-01: Şifre koşulu ve kayıt adlandırması için Eray/PO'dan açıklama istedim. |
| US-02 / KKY-4 | 3 hatalı girişte geçici hesap kilidi | Jira kriterlerinde kilit koşulunu bulamadım. Belgedeki İK-02.3'te 5 başarısız girişten sonra 15 dakika kilit koşulunu gördüm. | KC-02: 3/5 deneme farkı için PO kararını ve varsa onaylı değişiklik referansını istedim. |
| US-03 / KKY-5 | Telefon ve bildirim tercihi kaydı | Jira ve belgede telefon/e-posta güncellemesini gördüm; bildirim tercihi kaydını bulamadım. | KC-03: Bildirim tercihi kapsamını netleştirmesini Eray/PO'dan istedim. |
| US-04 / KKY-6 | Rol atama ve yetki iptali | Jira ve belgede yetki atama, geri alma ve yetkisiz erişim kurallarını gördüm. | Bu başlıklarda plan-belge uyumsuzluğu görmedim; nihai kabulü PO/Review kapsamında değerlendirdim. |
| US-05 / KKY-15 | Kategori filtresi ve hızlı sonuç listesi | Jira'da kategori filtresini, sonuç alanlarını ve sonuç bulunamadı mesajını gördüm. Hız için sayısal sınır bulamadım. | Kriter başlıklarını doğruladım. Hız kontrolünün yöntemini PO/Esat'ın açıklamasına bıraktım; kendim sayısal sınır eklemedim. |

## Karar ve yeniden kontrol takibim

27 Ekim'deki incelememde KC-01, KC-02 ve KC-03'ü açık bulgu olarak kaydettim. Geçerli kuralı veya onaylı değişiklik kaynağını PO'dan istedim; ilgili Jira kartlarına bulgularımı ve bu kayıt bağlantısını ekledim. Kapanış durumunu ilgili karar ve düzeltme kanıtıyla ayrıca kontrol edeceğim.

Düzeltme/karardan sonra şu noktaları yeniden kontrol edeceğim:

1. Plan veya onaylı değişiklik, Jira kriteri, iş kuralı, ekran taslağı ve kontrol senaryosu aynı koşulu anlatıyor mu?
2. Şifre uzunluğu, başarısız giriş sayısı ve bildirim tercihi için açık beklenen sonuç var mı?
3. Güncel dosya ve PR bağlantıları Jira'da bulunuyor mu?
4. Düzeltme bağımsız incelemeden geçti mi? PO kabul kararı ve gerçek kontrol bulgusu kaydedildi mi?

Bu adımları henüz uygulanmış kontrol sonucu olarak işaretlemedim. Gerçek kararları ve yeniden kontrol sonuçlarımı kanıtlarıyla bu kayda ekleyeceğim.
