# DragonsLair — Claude koordinasyon ve uygulama kuralları

**ÖNCE OKU:** [GDD v0.2](docs/game-design/GDD.md), [25 soruluk görüş kaydı](docs/requirements/design-intake-2026-10-27.md), [önerilen yol haritası](docs/roadmap.md), [Faz 0 DRAFT görev planı](docs/phases/phase-0-plan.md), [yerel testler](docs/operations/testing.md) ve GitHub'daki **gerçek** Issue/PR durumları.

**Mevcut durum:** Ürün gereksinimleri için 25 yanıt geldi, GDD 0.2 DRAFT'tır. Hazırlık PR #1 henüz merge edilmedi. Faz 0 Issue'ları DRAFT; hiçbir uygulama fazı başlamadı. GitHub kanonik; ChatGPT konuşması yalnız ara çalışma alanı.

## Ürün / yaratıcı sınırlar
- Referans: *Stickman Defense: Survival TD*. **Otomatik savaş, düşman dalgaları, seçime bağlı güçlendirme/kart havuzu, özelleştirilebilir güçlü build'ler ve sürekli gelişim hissi** korunmak istenir. Bu, referansın özgün kod/görsel/ses/metin/ayırt edici UI'sını kopyalamak değildir.
- Mağaradaki yavru ejderha küçük canlılara karşı gelişir, sonra goblin/kurt/rakip ejderha, insan akınları, paladin/rahip ve dış dünya tehditlerine doğru büyür. **Hikâye oyunu, diyalog, zorunlu ara sahne, senaryo görevi tasarlama.**
- Gelen ürün yönü: başlangıçta tek ana yavru, ileride yardımcı ejderhalar (hibrit); hareket ve normal saldırı otomatik; oyuncu kartları ve özel yetenekleri kontrol eder, özel yeteneklerde auto düğmesi; yatay 2.5D görünüm; ejderha HP kaybetme koşulu; bölüm boss'u; kalıcı ve geçici gelişim/evrim, ekipman, taş/rün, Rage; güç kombinasyonları.
- Normal karşılaşmalar için 4 dakika hedefi, özel etkinlikler ≤10 dakika; **ilk demo farklıdır: 2–3 dk dalga savaşı + boss + birkaç evrim örneği**.
- Bunlar `DIRECTION_RECEIVED` (iletilmiş tercih); **resmî APPROVED ve implementasyon izni değildir**. D-005 motor, D-008 4 dk tanımı, D-010 IP/repo hakları ve diğer alt kararlar açık.

## Roller ve yetkiler
Kullanıcı ve oyunu isteyen arkadaşı ürün/yaratıcılık, kapsam ve hak kararlarını onaylar. ChatGPT teknik planlama ve bağımsız review; Claude Projects koordinatör; Claude Code geliştirici. GitHub kod, Issue, karar ve kabul edilmiş GDD için tek kanonik kaynak.

## Görev/faz akışı
Her Issue: amaç, kapsam, kapsam dışı, bağımlılık, kabul kriterleri, yerel doğrulama planı, teslim kanıtı, risk/açık karar. Durum: DRAFT → READY → IN_PROGRESS → REVIEW → ACCEPTED veya REVISION_REQUIRED / BLOCKED.
- Kullanıcı ilgili READY işleri/fazı kabul etmeden Claude Code uygulamaya başlamaz.
- `Faz N'i başlat` onaylı işlerde normal kod, lokal test, düzeltme, commit/push ve PR hazırlığını kapsar; aynı adımlar için tekrar izin isteme.
- Her görev izole branch/thread ve tercihen PR. Exact HEAD + gerçek diff/test kanıtıyla ChatGPT bağımsız inceleme yapar. Koşulmayan test `NOT RUN`.
- **Merge için kullanıcı açık onayı**; Claude kendi işini bağımsız biçimde ACCEPTED ilan edemez. Otomatik yeni faz yok.
- Faz dışı mimari, ücretli işlem veya yeni büyük kapsam için ürün kararı gerekir.

## Hız, test, maliyet
- GitHub Actions / hosted CI **YOK**; workflow dosyası oluşturma veya tetikleme.
- Küçük değişiklikte en dar test/lint → Issue sonunda ilgili scene/entegrasyon smoke → faz sonunda ilgili regresyon → MVP cihaz testi. Kod/ortam aynıysa geçerli testleri sebep olmadan tekrar çalıştırma.
- Savaş hissi, okunabilir animasyon, mobil performans ve kısa geri bildirim önceliği. Gereksiz eklenti/mimari yükü ve tüm çeşitleri ilk MVP'de yapma.
- AI asset kaynağı, lisans ve ticari kullanım kontrolü; ücretli araç kullanıcı onayıyla. Fikri mülkiyet ve repo şu an **public** görünürlüğü D-010 kapsamında açık.
