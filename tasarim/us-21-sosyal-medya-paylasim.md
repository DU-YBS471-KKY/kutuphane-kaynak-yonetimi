# US 21 sınırlı kitap bilgisi paylaşım ekranı ve işlem akışı

**Sorumlu:** Enes Ulutaş | **Tarih:** 28 Kasım 2026 | **Güncelleme:** 28 Kasım 2026
**Jira:** KKY-26 | **Sprint 4** | **2 SP**
**Durum:** Sprint 4 kapsamında hazırlandı; Eray'ın sınırlı paylaşım kararı esas alınmıştır, QA/inceleme ve Kübra'nın ürün kabulü bekleniyor.

Kullanıcının kitap detayından yalnızca **kitap adı** ve **yazar** bilgisini, açık kullanıcı onayıyla paylaşım metni/taslağı olarak hazırlama akışı gösterilir. Gerçek sosyal medya API çağrısı veya canlı paylaşım yapılmaz; `KKY-30` kopya kaydı kapsam dışı/kopyadır.

## U 01 Paylaşım önizleme ve sınırlı veri alanı

KİTAP PAYLAŞIM TASLAĞI          Durum: Kullanıcı Onayı Bekleniyor
Paylaşılacak Alanlar (Sınırlı):
- Kitap Adı: Ateşten Gömlek
- Yazar: Halide Edip Adıvar
Hariç Tutulan Bilgiler: Kullanıcı e-posta/telefon, ödünç geçmişi, ceza/bakiye bilgisi

Paylaşım önizlemesinde yalnızca kitap adı ve yazar yer alır; kişisel veya hesap verileri eklenmez.

## U 02 Kullanıcı onayı ve paylaşım taslağı oluşturma

PAYLAŞIM ONAY ADIMI             Durum: Kullanıcı
[ ] Kitap adı ve yazar bilgisinin paylaşılmasını onaylıyorum.
İşlem: [Paylaşım Metni Oluştur]

Kullanıcı onayı verilmeden paylaşım akışı tamamlanmaz; onay verildiğinde paylaşım taslağı hazırlanır.

## İşlem sırası

Kitap detayında "Paylaş" seçildiğinde -> Yalnızca kitap adı ve yazar bilgisini önizlemeye getir
  -> Kullanıcı onayı işaretli mi?
     -> Hayır: Paylaşımı başlatma, onay gerektiğini belirt
     -> Evet: Paylaşım metni/taslağını oluştur ve sonucu göster

| Kabul kriteri veya kapsam kuralı | Tasarım kanıtı | Kontrol kaydı |
| :--- | :--- | :--- |
| 1. Yalnızca kitap adı ve yazar paylaşılır | U 01 ve İşlem sırası | KS-21.1 |
| 2. Kullanıcı onayı olmadan paylaşım akışı ilerlemez | U 02 ve İşlem sırası | KS-21.2 |

## PO kararları

Sprint 4 kapsam ve gereksinim dokümanlarına göre aşağıdaki kurallar esas alınır:

- Eray'ın Sprint 3'te verdiği sınırlı paylaşım kararı geçerlidir: yalnızca kitap adı ve yazar paylaşılır.
- İşlem kullanıcı onayıyla ilerler; bağımsız kontrol ve ürün kabulü Kübra tarafından takip edilir.

[Kontrol senaryoları](../test/us-21-kontrol.md) · [Gereksinimler](../docs/gereksinimler)
