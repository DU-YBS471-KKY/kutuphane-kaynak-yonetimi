# Sprint 1: Planlama (Planning) Raporu

Tarih: 23 Ekim 2026  
Sprint Süresi: 21 Ekim 2026 – 28 Ekim 2026  
Product Owner (PO): Eray Yakup Dağdelen  
Scrum Master (SM): Esat Kor   

---

## 1. Sprint 1 Hedefi
Kütüphane Kaynak Yönetimi (KKY) sisteminin temel kullanıcı ve üyelik altyapısını kurgulamak; öğrenci kayıt, güvenli giriş/şifre sıfırlama, profil güncelleme, admin personel yetkilendirme süreçleri ile katalogda yazar/başlık/ISBN bazlı kitap arama işlevinin iş kurallarını, ekran taslaklarını ve kabul senaryolarını tamamlamaktır.

---

## 2. Sprint 1 Kapsamı ve Seçilen Kullanıcı Hikayeleri (Sprint Backlog)

Product Owner önceliklendirmesi ve ekip kapasite değerlendirmesi sonucunda, Sprint 1 kapsamında toplam **15 Story Point (SP)** değerinde **5 User Story** alınmasına karar verilmiştir:

| Plan Kodu | Jira Kodu | User Story Başlığı | Sorumlu | Epic | Story Point (SP) |
| :--- | :--- | :--- | :--- | :--- | :---: |
| **US-01** | [KKY-3](https://dagdelen41.atlassian.net/browse/KKY-3) | Bir üye olarak kullanıcı girişi / öğrenci numarasıyla kayıt olabilme | Eray Yakup Dağdelen | Kullanıcı ve Üye Yönetimi | 3 |
| **US-02** | [KKY-4](https://dagdelen41.atlassian.net/browse/KKY-4) | Sisteme giriş yapma ve şifre sıfırlama | Eray Yakup Dağdelen | Kullanıcı ve Üye Yönetimi | 2 |
| **US-03** | [KKY-5](https://dagdelen41.atlassian.net/browse/KKY-5) | Öğrenci profil ve iletişim bilgisi güncelleme | Eray Yakup Dağdelen | Kullanıcı ve Üye Yönetimi | 2 |
| **US-04** | [KKY-6](https://dagdelen41.atlassian.net/browse/KKY-6) | Admin personel hesabı yetkilendirme | Eray Yakup Dağdelen | Kullanıcı ve Üye Yönetimi | 5 |
| **US-05** | [KKY-15](https://dagdelen41.atlassian.net/browse/KKY-15) | Yazar, başlık ve ISBN ile kitap arama | Esat Kor | Kaynak ve Kitap Envanteri | 3 |
| **TOPLAM** | | **5 Kullanıcı Hikayesi** | | | **15 SP** |

---

## 3. Teslimat ve Tamamlanma Kriterleri 
Bu sprint sonunda seçilen 5 hikayenin "Tamamlandı (Done)" sayılabilmesi için aşağıdaki koşulların sağlanması kararlaştırılmıştır:
1. Her hikayenin Jira kartında kullanıcı hikayesi cümlesi ve en az 3 kabul kriteri eksiksiz yer almalıdır.
2. İlgili hikayelerin iş kuralları (`docs/is-kurallari/`), ekran/akış taslakları (`tasarim/`) ve kontrol senaryoları (`test/`) GitHub deposuna yüklenmelidir.
3. Yüklenen tüm belgeler kişisel GitHub hesapları üzerinden ayrı dal (`feature/us-XX-...`) açılarak gönderilmeli ve en az bir ekip üyesinin Pull Request (PR) incelemesinden (Review) geçerek `Create a merge commit` yöntemiyle `develop` dalına birleştirilmelidir.
4. Birleştirilen dosyaların ve PR'ların bağlantıları Jira'daki ilgili kartlara işlenmelidir.

---

## 4. Görev Dağılımı ve Sprint Ritüelleri Planı
* **Sprint Yönetimi ve Daily Standup:** Scrum Master (Esat Kor) tarafından Jira'da Sprint 1 başlatılacak ve günlük ilerleme/engel kayıtları (Daily Log) takip edilecektir.
* **Sprint Review (Değerlendirme):** 28 Ekim'de tamamlanan US-01–US-05 çıktıları Mert ve Abdülkadir tarafından incelenerek raporlanacaktır.
* **Sprint Retrospektif:** Sprint sonunda süreç değerlendirmesi Kübra Şen ve Enes tarafından hazırlanacaktır.
* **Kanban Eşlemesi:** Jira Board üzerindeki durum geçişleri (To Do -> In Progress -> Done) Enes tarafından Trello panosu ile senkronize tutulacaktır.
