# DragonsLair

**Durum:** Tasarım / keşif hazırlığı — **DRAFT**. 25 ürün yanıtı işlenmiş, nihai onay bekleniyor. Geliştirme fazı henüz başlatılmadı. Bu repo bir oyunun mevcut kaynak kodunu klonlamak için değil, özgün bir oyun geliştirmek içindir.

## Ürün vizyonu

[Stickman Defense: Survival TD](https://play.google.com/store/apps/details?id=com.thp020.stickman.casual.war.game) oyunundaki otomatik savaş, düşman dalgaları, roguelike yükseltme ve ilerleme hissinden ilham alan **özgün ejderha savunma oyunu**. Yavru ejderha mağara yaratıklarıyla başlar, zamanla insan maceracıların baskınlarına karşı yuvasını savunur. Bu bir anlatı/hikâye oyunu değildir; gelişim ve düşman sırası örtük bağlam sağlar.

Korunabilir yaratıcı ifade, kod, arayüz kompozisyonları, sesler veya sanat varlıkları referanstan alınmaz.

## Kanonik belgeler

- [GDD v0.2 — ürün yönünü içeren oyun tasarım taslağı](docs/game-design/GDD.md)
- [25 soruluk ürün görüşü izi](docs/requirements/design-intake-2026-10-27.md)
- [Faz 0 DRAFT görev planı](docs/phases/phase-0-plan.md)
- [Önerilen yol haritası — Faz 0–5](docs/roadmap.md)
- [Açık kararlar ve ADR işleyişi](docs/decisions/README.md)
- [Yerel test / CI maliyet politikası](docs/operations/testing.md)
- [Claude koordinatör ve Code çalışma kuralları](CLAUDE.md)
- [GitHub Issue görev şablonu](.github/ISSUE_TEMPLATE/task.md)

## Çalışma modeli

**ChatGPT:** planlama, oyun tasarımı, Issue kabul kriterleri, bağımsız PR review.  
**Claude Projects:** koordinasyon. **Claude Code:** uygulama.  
**Kullanıcı ve oyunu isteyen arkadaşı:** ürün kararları, kapsam, kabul ve merge yetkisi.

Her faz, ayrı onaylanmış READY Issue setiyle başlatılır. Çalışmalar izole branch/PR üzerinden ve yerel, değişiklik odaklı testlerle yapılır. **GitHub Actions / hosted CI kullanılmaz.** `main` üzerinde onaysız uygulama ya da merge yok.

## Açık kararlar

Yeni görüşte **hibrit ana ejderha + yardımcı ejderhalar**, otomatik hareket/saldırı, **yatay 2.5D** ve kalıcı/geçici evrim istendi; bunlar `DIRECTION_RECEIVED`, henüz ürün sahiplerince nihai `APPROVED` değildir. Motor, kesin kamera/2.5D uygulama yöntemi, bazı süre kuralları ve fikrî mülkiyet hâlâ açık. Tek karar listesi [GDD §11](docs/game-design/GDD.md) içindedir.

**Sıradaki adım:** [Faz 0 DRAFT Issue #2–#8](https://github.com/mertkaanakgunlu-debug/DragonsLair/issues) kapsamını ve kalan açık kararları doğrulayarak READY onayı almak. PR #1 Draft/merge edilmedi, Faz 0 başlamadı.
