# Faz 0 — Referans Oyun Analizi ve Tasarım Doğrulaması

**Durum:** DRAFT / plan hazır, **çalışma BAŞLAMADI**  
**Tarih:** 2026-10-26  
**Bağlı PR:** #1 (başlangıç belgeleri; draft, merge değil)  
**Amaç:** Stickman Defense: Survival TD oynanışının gerçekten sevilen prensiplerini anlamak ve bunlara dayalı, özgün bir ejderha savunma prototipini küçük, test edilebilir görevlere çevirmek.

## Faz 0 iş paketi (tamamı DRAFT)

| Grup | GitHub Issue | Somut çıktı | Önkoşul |
|---|---|---|---|
| A — Referans | [#2](https://github.com/mertkaanakgunlu-debug/DragonsLair/issues/2) Kanıta dayalı oynanış analizi | Kaynak/gözlem işaretli mekanik envanteri | Yok |
| A — Ürün | [#3](https://github.com/mertkaanakgunlu-debug/DragonsLair/issues/3) Arkadaşın tercihleri ve kararlar | Onaylı, öneri ve OPEN ayrılmış brief | Yanıt gelmeyebilir; eksikler OPEN |
| B — Tasarım | [#4](https://github.com/mertkaanakgunlu-debug/DragonsLair/issues/4) Çekirdek döngü sözleşmesi | İlk koşu akışı ve ölçülebilir playtest | #2 ve erişen #3 yanıtları |
| A — Sanat | [#5](https://github.com/mertkaanakgunlu-debug/DragonsLair/issues/5) AI art/animasyon hattı | 2D/3D seçenek tablosu, lisans ve maliyet | Yok; #6 ile bilgi paylaşır |
| A/B — Teknik | [#6](https://github.com/mertkaanakgunlu-debug/DragonsLair/issues/6) Motor/Android fizibilitesi | Godot/Unity ve yerel test önerisi | GDD; #4/#5 çıktısıyla revizyon |
| C — Konsolidasyon | [#7](https://github.com/mertkaanakgunlu-debug/DragonsLair/issues/7) GDD ve karar senkronizasyonu | GDD revizyonu ve gerekli ADR taslakları | #2–#6 sonuçları |
| D — Devir | [#8](https://github.com/mertkaanakgunlu-debug/DragonsLair/issues/8) Faz 1 küçük görevleri | Sıralı DRAFT backlog ve Faz 1 başlatma kapısı | #4, #6, #7 |

**Önerilen sıra:** A grubu (#2, #3, #5 ve #6 ilk araştırma) paralel → B grubu (#4 ve #6 sonlandırma) → C (#7) → D (#8).

## Faz 0 sınırları

**Dahil:** Oynanış kaynakları, özgünlük değerlendirmesi, arkadaşın yanıtlarının toplanması, karar seçenekleri, teknik/sanat fizibilite araştırması, GDD ve Faz 1 görev planı.

**Dahil değil:** Oyun kodu, gerçek oyun varlıklarını topluca üretme, tüm oyun ekonomisini tasarlama, pazarlama, yeni GitHub Actions/hosted CI, ücretli servis kullanımı, PR merge, onaylanmamış mimari karar.

**Kaynak kalitesi:** Resmî mağaza açıklaması mekanik beyanı sağlar, tam oynanışın kanıtı değildir. Oyun içi davranış için mümkünse kısa ekran kaydı + zaman kodu gerekir. Yoksa BELİRSİZ bırakılır; izlenmemiş video oynanmış gibi raporlanmaz.

**Arkadaşın onayı gecikirse:** #2/#5/#6 gibi araştırmalar taslak olarak ilerleyebilir. D-001 tek/takım/hibrit, D-003 kamera, D-005 motor ve D-007 ne savunuluyor kararları gerekiyorsa Faz 1 READY önkoşulu olarak bloke edilir. GDD'de OPEN kalırlar, herhangi biri sessizce seçilmez.

## Kabul kapısı

Faz 0'ın **ACCEPTED** olması için:
1. #2 mekanik kanıt envanteri ve #3 ürün karar kaynakları raporlandı; mümkün olmayan gerçek oyun incelemeleri **NOT VERIFIED**.
2. #4 ilk koşu akışı ve önerilen ölçülebilir prototip kriterleri var.
3. #5 / #6 görsel-animasyon ve motor/Android maliyet-kalite seçenekleri gerekçeli.
4. #7 GDD, karar defteri ve varsa ADR aynı gerçeği anlatıyor; açık kararlar saklanıyor.
5. #8 Faz 1 için sıralı DRAFT Issue listesi ve başlatma engelleri var.
6. ChatGPT bağımsız inceleme raporu: **PASS / REVISION_REQUIRED / BLOCKED** ve dokümanlar için link/sürüm kontrolü.
7. **Kullanıcı açık kabulü** — otomatik Faz 1 başlatma veya merge yok.

## Yerel test politikası

Faz 0 doküman yoğunluklu: kaynak URL/yürütülebilirlik/bağlantı kontrolü ve çelişki taraması yeterli. Kod olmadığı sürece oyun testi **NOT RUN**. GitHub Actions **NOT RUN (budget)**. Eğer önceden onaylı ufak bir masaüstü görsel tekniği denemesi yapılırsa yalnız ilgili çıktı doğrulanır, tam suite yok.

## Karar yönetimi

Kritik OPEN kararları GDD §12'de tut. Kullanıcıdan/arkadaştan yeni bilgi geldikçe bağlı Issue ve GDD güncellenir; bu planın açılması hiçbir ürünü veya fazı APPROVED yapmaz.

## Yetki

DRAFT Issue oluşturmak planlamadır. **Faz 0'ı başlat** onayı gelmeden Claude Code üretim çalışmalarına başlamaz. Faz 0 onayı onaylı görevler kapsamındaki olağan doküman hazırlama / araştırma / hedefli kontrol / branch ve PR hazırlığını kapsar. **Merge için ayrıca açık kullanıcı onayı gerekir.**
