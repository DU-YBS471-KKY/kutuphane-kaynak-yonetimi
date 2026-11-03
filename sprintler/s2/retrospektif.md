# Sprint 2 retrospektif önerilerim

Hazırlayan: Kübra Şen  
Ara değerlendirmem: 31 Ekim 2026  
Planlanan sprint: 28 Ekim–4 Kasım 2026  
Son değerlendirme hedefim: 4 Kasım 2026

Bu kaydı sprint sürerken kendi gözlemlerimle hazırladım. Aşağıdaki maddeleri öneri olarak sunuyorum; gerçekleşmiş bir retrospektif toplantısı veya ekipçe alınmış karar olarak kaydetmiyorum. Son değerlendirmemi sprint sonucuyla tamamlayacağım.

## Devam etmek istediğim uygulamalar (Keep)

1. Kabul kriterlerini senaryo ve kanıt bağlantısıyla tek tek eşleştirmeye devam etmek istiyorum. US-06–10 için 17 kriterlik listem, uyumlu koşullarla açık senaryo ve kanıt ihtiyaçlarını ayrı izlememi sağladı.
2. Teslimi başka bir üyeye inceletip onaydan sonra birleştirme uygulamasını sürdürmek istiyorum. Mert'in PR #25 teslimini inceledim; kendi kontrol listem ve günlüğüm de PR #26'da Eray'ın bağımsız onayıyla birleşti.

## İyileştirmek istediğim noktalar (Improve)

1. Kendi günlük aktarımımı aynı gün tamamlamak istiyorum. 29 Ekim günlüğümü GitHub'da hazırladığım halde ortak Sprint 2 tablosuna aynı gün aktarmadım. Sonradan eklediğim kayıtlarda giriş tarihini belirterek gecikmeyi görünür tutacağım.
2. Senaryolarda ön koşul, işlem ve beklenen sonucu daha açık izlemek istiyorum. US-06 stok değişimi ve US-07 oturumsuz PDF erişimi için açtığım F-01/F-02 notlarına 31 Ekim kontrolümde yeni yanıt veya teslim kanıtı göremedim. Kanıt gelmeden bu koşulları tamamlandı saymayacağım.

## Sonraki sprint için önerim (Try)

| Alan | Önerim / kendi takip planım |
| --- | --- |
| Eylem | Sprint 3'te her teslim için Jira kriteri–senaryo–kanıt eşleştirmesini PR incelemesi öncesinde kontrol etmeyi öneriyorum. Eksik kanıt veya beklenen sonucu kontrol listeme gerekçesiyle yazacağım. |
| Sorumlu | Kendi kabul kriteri listemi ben takip edeceğim. Ekip çapındaki uygulama için PO ve teslim sahiplerinin görüşünü isteyeceğim. |
| Takvim | 4 Kasım'da Sprint 2 sonucuyla önerimi gözden geçireceğim; 4–11 Kasım Sprint 3 boyunca takip edip 11 Kasım'da değerlendireceğim. |
| Kontrol yöntemi | Jira koşullarını gereksinim, ekran/akış ve senaryo sonuçlarına bağlayacağım; açık notun sorumlusunu, bekleme gerekçesini ve yeniden kontrol tarihini kaydedeceğim. |
| Başarı ölçütü | US-11–15 kapsamındaki her Jira kriteri için kanıt bağlantısı veya açık bekleme gerekçesi bulunmasını hedefliyorum. Açık not sayısını ve karşılanmayan koşulları sprint sonunda ayrıca raporlayacağım. |

## Enes'in katkısını nasıl ekleyeceğim?

31 Ekim kontrolümde Enes'in Sprint 2 için yeni bir retrospektif katkısını görmedim. Keep / Improve / Try görüşünü paylaştığında kendi adıyla ilgili bölüme ekleyeceğim. Kendi önerimi onun görüşü veya ortak ekip onayı olarak yazmadım.

## Dayandığım kayıtlar

- [Kriter kontrol listem](kabul-kriteri-kontrolu.md)
- [29 Ekim günlüğüm](kubra-29-ekim.md)
- [PR #25 incelemem](https://github.com/DU-YBS471-KKY/kutuphane-kaynak-yonetimi/pull/25#pullrequestreview-5695366811)
- [PR #26 onay ve birleşme kaydı](https://github.com/DU-YBS471-KKY/kutuphane-kaynak-yonetimi/pull/26)
- [PR #33: 2 Kasım yeniden kontrolüm](https://github.com/DU-YBS471-KKY/kutuphane-kaynak-yonetimi/pull/33)
- [PR #36: Esat'ın F-01 ve klasör düzeltmesi](https://github.com/DU-YBS471-KKY/kutuphane-kaynak-yonetimi/pull/36)

## 2 Kasım akşamı: önerilerimin sprint sonucuyla durumu

Bu bölümü 2 Kasım akşamı, açık bulgularım kapandıktan sonra ekledim. Sprint henüz kapatılmadı; nihai değerlendirmemi kapanıştan sonra tamamlayacağım.

- **Keep 1 (kriter–senaryo–kanıt eşleştirmesi) işe yaradı.** 17 kriterlik listem iki kapsam açığını (F-01 stok, F-02 oturumsuz PDF erişimi) görünür kıldı. İkisi de teslim sahibi tarafından düzeltildi: F-02 PR #30'da, F-01 PR #36'daki KS-06-04 senaryosuyla. Son dağılımım 17 kriterde 17 Uyumlu.
- **Improve 2 (ön koşul / işlem / beklenen sonucu açık izlemek) karşılığını buldu.** Açtığım iki not, Mert'in [#34](https://github.com/DU-YBS471-KKY/kutuphane-kaynak-yonetimi/issues/34) ve [#35](https://github.com/DU-YBS471-KKY/kutuphane-kaynak-yonetimi/issues/35) numaralı Issue kayıtlarına dönüştü ve ikisi de kapandı. Bulgunun Issue olarak kaydedilmesi takibi kolaylaştırdı; bunu Sprint 3'te de sürdürmeyi öneriyorum.
- **Improve 1 (günlüğümü aynı gün yazmak) bu sprintte düzeldi.** 1 ve 2 Kasım kayıtlarımı aynı gün girdim; 1 Kasım satırında giriş tarihini belirttim.
- **Yeni gözlemim:** Kontrol senaryolarının sonuç sütunundaki "Geçti" ifadesi ekibin bazı dosyalarında belge/ekran taslağı üzerinden doğrulamayı anlatıyor, bazılarında ise dayanağı yazılmamış. Sprint 3'te her kontrol dosyasının başına sonucun neye dayandığını yazan bir satır eklenmesini öneriyorum. Bu bir öneridir; ekipçe alınmış karar değildir.

Enes'in katkısı: 2 Kasım akşamına kadar Enes'in Sprint 2 için bir retrospektif katkısını görmedim. Keep / Improve / Try görüşünü paylaştığında kendi adıyla ekleyeceğim; ortak bölümü onun katkısı geldiğinde kesinleştireceğim.
