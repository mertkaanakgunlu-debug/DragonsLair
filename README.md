# DragonsLair

**Durum:** Tasarım / keşif hazırlığı — **DRAFT**. Geliştirme fazı henüz başlatılmadı. Bu repo bir oyunun mevcut kaynak kodunu klonlamak için değil, özgün bir oyun geliştirmek içindir.

## Ürün vizyonu

[Stickman Defense: Survival TD](https://play.google.com/store/apps/details?id=com.thp020.stickman.casual.war.game) oyunundaki otomatik savaş, düşman dalgaları, roguelike yükseltme ve ilerleme hissinden ilham alan **özgün ejderha savunma oyunu**. Yavru ejderha mağara yaratıklarıyla başlar, zamanla insan maceracıların baskınlarına karşı yuvasını savunur. Bu bir anlatı/hikâye oyunu değildir; gelişim ve düşman sırası örtük bağlam sağlar.

Korunabilir yaratıcı ifade, kod, arayüz kompozisyonları, sesler veya sanat varlıkları referanstan alınmaz.

## Kanonik belgeler

- [GDD v0.1 — oyun tasarım taslağı](docs/game-design/GDD.md)
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

En önemlisi **tek ana ejderha / ejderha takımı / hibrit** modeli; ayrıca kamera, 2D/3D, oyun motoru, evrim yapısı, oynanış oturumu ve fikrî mülkiyet sahipliği kesinleşmedi. Bunlar [GDD açık karar listesinde](docs/game-design/GDD.md#12-açık-karar-defteri--arkadaşın-yanıtı-beklenecek) korunur.

**Sıradaki adım:** Faz 0'ı kullanıcıyla birlikte ayrıntılandırmak, küçük ve test edilebilir Issue taslakları hazırlamak; onay gelmeden uygulamaya geçmemek.
