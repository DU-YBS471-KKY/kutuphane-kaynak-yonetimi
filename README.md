# Kütüphane Kaynak Yönetim Sistemi

DÜ YBS 471 Yazılım Yönetimi (Güz 2026) dönem projesi. Bir kütüphane yazılımını Agile / Scrum yöntemiyle dört sprint boyunca yönetiyoruz. Kodlama zorunlu değil; çıktılarımız gereksinim belgeleri, ekran taslakları ve kontrol senaryolarıdır.

## Bağlantılar

| Araç | Ne için | Bağlantı |
|---|---|---|
| Jira (KKY) | Backlog, sprintler, hatalar, raporlar | https://dagdelen41.atlassian.net/jira/software/c/projects/KKY/boards/2 |
| Trello | Kanban alıştırması (5 sütunlu pano) | https://trello.com/b/BYmjSKQd/kutuphane-kaynak-yonetim-sistemi |
| GitHub | Dosyalar, değişiklikler, incelemeler | Bu depo |

## Ekip

| Üye | Takip ettiği alan |
|---|---|
| Mert | Jira ve zaman planı |
| Kadir | GitHub ve sürümler |
| Esat | İhtiyaçlar ve kapsam |
| Kübra | Belgeler ve sunum |
| Eray | Test ve hata takibi |
| Enes | Tasarım ve riskler |

**Scrum rolleri:** Sprint 1–3 Product Owner Esat, Scrum Master Mert. Sprint 4 Product Owner Enes, Scrum Master Kadir.

## Sistemin kullanıcıları

- **Öğrenci:** kitap bulur, ödünçlerini izler.
- **Görevli:** kitap, ödünç ve iade kaydeder.
- **Yönetici:** yetki ve ödünç kurallarını belirler.

## Dal düzeni

| Dal | Anlamı |
|---|---|
| `main` | Onaylı sürüm. Her sprint sonunda `develop`'tan alınır ve etiketlenir. |
| `develop` | İncelenmiş çalışmaların birleştiği dal. Varsayılan dal budur. |
| `feature/kut-XX-konu` | Üzerinde çalışılan iş. Örnek: `feature/kut-01-kitap-arama` |
| `hotfix/konu` | Gerçek bir düzeltme. `main`'den açılır, düzeltme `main` ve `develop`'a alınır. |

`main` ve `develop` dallarına doğrudan push kapalıdır. Her değişiklik Pull Request ile ve başka bir üyenin onayıyla girer.

## Bir dosyayı teslim etme

1. `develop`'tan kendi `feature/...` dalını aç (tarayıcıda dal menüsünden de olur).
2. Dosyanı **kendi GitHub hesabınla** ekle veya düzenle. Commit mesajına iş kodunu yaz, örnek: `KUT-01: arama ekranı taslağı eklendi`
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

## Sürümler

| Sürüm | Tarih | İçerik |
|---|---|---|
| v0.1 | 25 Ekim | Sprint 1: katalog |
| v0.2 | 1 Kasım | Sprint 2: ödünç süreci, risk ve kalite |
| v0.3 | 8 Kasım | Sprint 3: iade, giriş, konfigürasyon, rol devri |
| v0.4 | 22 Kasım | Sprint 4: yönetim kuralları, kapanış |
| v1.0 | Final | Teslim paketi |
