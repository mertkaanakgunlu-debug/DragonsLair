# DragonsLair — Yol haritası (DRAFT, v0.2 ürün girdisiyle uyumlu)
**Tarih:** 2026-10-27 · **Durum:** ÖNERİ / resmi kapsam ve geliştirme onayı bekleniyor. Hiçbir faz başlatılmadı.

[Game Design Document v0.2](game-design/GDD.md) kullanıcı tarafından iletilen 25 cevabı ve açık kararları içerir. [Görüş girdisi](requirements/design-intake-2026-10-27.md) yanıtlara izlenebilirlik sağlar. Oyunun kimliği: **referansa yakın otomatik savaş / build seçimi / sürekli gelişim; özgün hibrit ejderha sistemi; hikâye odaklı değil.**

| Faz | Hedef | Teslim ve onay kapısı |
|---|---|---|
| **0 — Referans ve tasarım** | Kanıta dayalı referans incelemesi; gelen ürün yanıtları ve kalan kararların düzenlenmesi; 2.5D sanat + motor fizibilitesi; ilk prototip görevleri | Güncel GDD, kısa oynanış sözleşmesi, kararlar, Faz 1 DRAFT Issue seti |
| **1 — Savaş prototipi** | Yavru ejderha; oto hareket/saldırı; kart ve güçlendirme seçimi; kısa (2–3 dk) mağara koşusu, boss ve birkaç *örnek* evrim formu/saldırısı | Bir oyuncu kart etkisini, evrimi ve boss mücadele sonucunu hissedebiliyor mu? |
| **2 — Gelişim ve build sistemi** | Kalıcı ejderha seviyesi, ekipman/rün/pasifler; koşu içi yükseltmeler ve güçlü sinerjiler; Rage, özel yetenekler/auto-toggle, yardımcı ejderhalar **risk bazlı alt görevlere ayrılarak** | Çeşitli oynanış tarzı ve kayıt tutarlılığı için küçük testler |
| **3 — Özgün görsel ve içerik hattı** | 2.5D yaratım ve animasyon hattı; fiziksel evrim, farklı düşman ve boss'lar; mağara → dış dünya; etkinlik/zindan **yalnız öncelik onayı alırsa** | Özgün ve okunur sanat, yeniden üretilebilir asset hattı |
| **4 — Android MVP ve testler** | Gerçek Android testleri, dokunmatik, performans, kaydet/yükle, bölüm/ödül akışı; 4 dk normal bölüm ve ≤10 dk etkinlik tasarım hedefleri | Telefonda kabul edilebilir MVP, insan playtest, risk temelli regresyon |
| **5 — Yayın hazırlığı** | Marka/IP, mağaza ve dağıtım, lisans, gizlilik; gerekirse gelecek gelir modeli | Kullanıcı onaylı yayın adayı; yayın ayrıca açık onay gerektirir |

**Açık gereksinim / kapsam kapıları:**
- **D-001:** Hibrit ana + yardımcı model tercih edildi, ama Faz 1 kısa testinde yardımcıların tam mekanizması şart değildir. Faz 2'de kapsam onayı gerekir.
- **D-003/D-004/D-005:** Otomatik savaş ve 2.5D tercihleri var; kamera yerleşimi/2.5D pipeline/motor henüz mimari karar değildir.
- **D-008:** 4 dk tanımı ve boss süresi netleştirilecek; **Faz 1 demosu bilinçli olarak 2–3 dk**.
- **D-006:** İlk prototipte birkaç evrim örneğinin hareket/saldırı farkı gösterilecek; tam evrim ekonomisi sonraya.
- **D-010:** İki geliştirici kontrolü yönü var; IP ve repo görünürlüğü henüz açık.
- Dungeon Dive / etkinlik / enerji ve kapsamlı build ekonomisi **ürün vizyonudur**, kendiliğinden prototip kabul kriteri değildir.

**Uygulama yöntemi:** Faz 0 [DRAFT planı](phases/phase-0-plan.md) ve [DRAFT Issue #2–#8](https://github.com/mertkaanakgunlu-debug/DragonsLair/issues) mevcut. Her fazın READY görevlerine kullanıcı onay verir, sonra `Faz N'i başlat` ile yürütülür. Olağan uygulama/test/PR işleri kapsam içinde yürütülür; merge için ayrıca onay. Faz bitmesi sonrakini başlatmaz.

**CI politikası:** GitHub Actions / hosted CI yok; kod değişimine uygun dar test, Issue sonunda scene smoke, faz sonunda seçilmiş regresyon, kilometre taşında Android cihaz testi.
