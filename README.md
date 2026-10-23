# Kütüphane Kaynak Yönetim Sistemi

DÜ YBS 471 Yazılım Yönetimi (Güz 2026) dönem projesi. Bir kütüphane yazılımını Agile / Scrum yöntemiyle dört sprint boyunca yönetiyoruz. Kodlama zorunlu değil; çıktılarımız gereksinim belgeleri, ekran taslakları ve kontrol senaryolarıdır.

## Bağlantılar

| Araç | Ne için | Bağlantı |
|---|---|---|
| Jira (KKY) | Backlog, sprintler, hatalar, raporlar | https://dagdelen41.atlassian.net/jira/software/c/projects/KKY/boards/2 |
| Trello | Kanban alıştırması (5 sütunlu pano) | https://trello.com/b/BYmjSKQd/kutuphane-kaynak-yonetim-sistemi |
| GitHub | Dosyalar, değişiklikler, incelemeler | Bu depo |

## Ekip

19 Ekim 2026 tarihli ekip rehberine göre:

| Üye | Kendi Story’leri | Ortak sorumlulukları |
|---|---|---|
| Eray | US-01–04 | Jira ve Epic düzeni; Sprint 1–3 Planning notları |
| Esat | US-05–07 | Sprint 1–3 yönetimi ve Daily Standup tablosu |
| Mert | US-08–10 | GitHub dal düzeni; Jira raporları; Kadir ile Review; Sprint 4 Standup |
| Abdülkadir (Kadir) | US-11–13 | GitHub kurulumu; Bug/Issue takibi; Mert ile Review |
| Kübra | US-14–17 | Kabul kriteri kontrolü; Enes ile retrospektif; Sprint 4 Planning; final sunumu |
| Enes | US-18–20 | Trello Kanban; risk tablosu; Kübra ile retrospektif |

**Scrum rolleri:** Sprint 1–3 Product Owner Eray, Scrum Master Esat. Sprint 4 Product Owner Kübra, Scrum Master Mert. Rol değişimi Sprint 3 sonunda bir kez yapılır.

## Sistemin kullanıcıları

- **Öğrenci:** kitap bulur, ödünçlerini izler.
- **Görevli:** kitap, ödünç ve iade kaydeder.
- **Yönetici:** yetki ve ödünç kurallarını belirler.

## Dal düzeni

| Dal | Anlamı |
|---|---|
| `main` | Onaylı sürüm. Her sprint sonunda `develop`'tan alınır ve etiketlenir. |
| `develop` | İncelenmiş çalışmaların birleştiği dal. Varsayılan dal budur. |
| `feature/us-XX-konu` | Üzerinde çalışılan iş. Örnek: `feature/us-05-kitap-arama` |
| `hotfix/konu` | Gerçek bir düzeltme. `main`'den açılır, düzeltme `main` ve `develop`'a alınır. |

`main` ve `develop` dallarına doğrudan push kapalıdır. Her değişiklik Pull Request ile ve başka bir üyenin onayıyla girer.

## Bir dosyayı teslim etme

1. `develop`'tan kendi `feature/...` dalını aç (tarayıcıda dal menüsünden de olur).
2. Dosyanı **kendi GitHub hesabınla** ekle veya düzenle. Commit mesajına iş kodunu yaz, örnek: `US-05: arama ekranı taslağı eklendi`
3. Pull Request aç, hedef dal `develop`. Kontrol eşinden inceleme iste.
4. İnceleme sonrası **Create a merge commit** ile birleştir. Squash ve rebase kapalıdır; böylece herkesin commit geçmişi korunur.
5. Dosya ve PR bağlantısını ilgili Jira işine ekle.

Hedef: her üye dönem boyunca en az 10 anlamlı commit, ekipte en az 5 incelenmiş PR ve en az 5 etiketli Issue.

## Klasör düzeni

| Klasör | İçerik |
|---|---|
| `docs/gereksinimler` | Kapsam, kullanıcılar, Story'ler |
| `docs/is-kurallari` | Kayıt, ödünç, iade, yetki kuralları |
| `docs/kullanim` | Kullanım açıklamaları |
| `docs/risk-degisiklik` | Risk ve değişiklik kayıtları |
| `tasarim` | Ekran ve akış taslakları |
| `test` | Kontrol senaryoları ve sonuçları |
| `sprintler/s1` … `s4` | Planning, daily log, review, retrospektif |
| `kanitlar/jira` | Jira ekran görüntüleri |
| `teslim` | Final raporu ve sunum |

Klasörler ilk dosya eklendiğinde oluşur.

## Bitirme tanımı (Definition of Done)

1. Kararlaştırılan çıktı kabul kriterlerini karşılıyor.
2. Başka bir üye inceledi, kritik eksikler giderildi.
3. Dosya GitHub'da; Jira'da çıktı ve inceleme bağlantıları var.

## Sprint ve sürüm hedefleri

Aşağıdaki tarihler 19 Ekim tarihli ekip rehberindeki plan hedefleridir. Jira’da fiilî başlangıç veya bitiş kaydı yerine geçmez; gerçekleşen tarihler ayrıca izlenir.

| Dönem | Planlanan aralık (2026) | İçerik | Hedef sürüm |
|---|---|---|---|
| Hazırlık (Sprint 0) | 23 Eylül – 21 Ekim | Ekip, araçlar, 4 Epic ve 20 Story | — |
| Sprint 1 | 21–28 Ekim | US-01–05; ilk rapor paketi | v0.1 — 28 Ekim |
| Sprint 2 | 28 Ekim – 4 Kasım | US-06–10; risk tablosu, Bug kayıtları ve rapor paketi | v0.2 — 4 Kasım |
| Sprint 3 | 4–11 Kasım | US-11–15; kriz simülasyonu ve rapor paketi | v0.3 — 11 Kasım |
| Sprint 4 | 11–24 Kasım | US-16–20; rol değişimi ve rapor paketi | v0.4 — 24 Kasım |
| Final hazırlığı | 25 Kasım’dan itibaren | 10–15 sayfa rapor, kanıtlar ve tüm üyelerin konuşacağı sunum | v1.0 — final teslimi |

Sprint 4, ekip planında vize nedeniyle iki hafta olarak ayrılmıştır. Her sprintte Planning, Daily Log, Review ve Retrospektif belgeleri tutulur. Hotfix dalı kriz simülasyonunda ihtiyaç oluştuğunda açılır.

Final raporu dersin 14. haftasında teslim edilir; kesin gün ve yükleme yöntemi hocadan teyit edilmelidir. Sprint hedef tarihleri final teslim tarihi değildir.
