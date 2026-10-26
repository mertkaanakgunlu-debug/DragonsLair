# DragonsLair — Claude koordinasyon başlangıcı

**Bu dosyayı, GDD'yi ve açık Issue/PR durumunu önce oku.** GitHub kanonik kaynaktır. Bu depo şu anda keşif/tasarım aşamasındadır; uygulama için açık faz onayı verilmemiştir.

- Ürün kimliği ve açık kararlar: [GDD](docs/game-design/GDD.md)
- Önerilen 6 faz (Faz 0–5): [Yol haritası](docs/roadmap.md)
- Onay/karar protokolü: [Karar kayıtları](docs/decisions/README.md)
- Test ve CI maliyet politikası: [Yerel test](docs/operations/testing.md)

## Roller ve yetki
ChatGPT oyun tasarımı/planlama ve bağımsız review, Claude Projects koordinasyon, Claude Code uygulama. Kullanıcı ve fikrin sahibi arkadaşı ürün karar sahipleridir. Tasarımcının onay vermediği ürün tercihlerini kesinleştirme.

## Proje dışına çıkma
- Referans oyun: Stickman Defense: Survival TD; genel savaş/roguelike/ilerleme mekaniklerine yakın oynanış, fakat özgün IP. Kaynak kodu/sanat/ses/ekran yerleşimini kopyalama.
- Önce küçük mağara yaratıkları, sonra insan baskınları: **örtük anlatı**. Diyalog, zorunlu ara sahne veya senaryo oyunu tasarlama.
- OPEN kararlar: tek ejderha / takım / hibrit; kamera / 2D/3D / motor / evrim/ekonomi / oturum / para kazanma. Bunları sessizce sabitleme.
- **GitHub Actions yok.** Yerel ve risk temelli test; her küçük değişiklikte tam test yok.
- `main`'e doğrudan uygulama commit'i, otomatik merge, yeni fazı kendiliğinden başlatma yok.

## İş akışı
Küçük, bağımlı ve test edilebilir Issue'lar: amaç, kapsam, kapsam dışı, bağımlılıklar, kabul kriterleri, doğrulama, teslim kanıtı, risk/kararlar.
Durum: DRAFT → READY → IN_PROGRESS → REVIEW → ACCEPTED / REVISION_REQUIRED / BLOCKED.
Yalnız kullanıcı tarafından onaylanmış READY işlerin fazı `Faz N'i başlat` komutuyla başlar; rutin kod/test/düzeltme/commit/PR için yeniden onay isteme. Her görevde mümkünse izole branch/thread/PR; exact HEAD ve test kanıtı ile ChatGPT bağımsız incelemesi; **merge için ayrı kullanıcı onayı**. Başlatılmış bir faz sonraki faza otomatik geçmez.

Hız ilkesi: eğlenceli savaş hissi, net yükseltme, okunabilir görseller, performans ve kısa geri bildirim döngüsüne öncelik. Gereksiz mimari/özellik kapsamı ekleme.
