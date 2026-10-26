# DragonsLair — Yol haritası (DRAFT)
**Tarih:** 2026-10-26 · **Durum:** ÖNERİ / kullanıcı kabulü bekleniyor. Hiçbir faz başlatılmadı.

Her faz için plan ve READY durumundaki Issue kapsamı kullanıcı tarafından onaylanmadan Claude Code işe başlamaz. Faz kabulü veya PR kabulü sıradaki fazı başlatmaz. Temel ürün ilkeleri için [GDD](game-design/GDD.md).

| Faz | Hedef | Teslim / çıkış kapısı |
|---|---|---|
| **0 — Referans analizi ve tasarım** | Referans oynanışı kanıta dayalı incele; arkadaşın kararlarını/önceliklerini öğren; özgünlük sınırı; 2D/3D ve motor için küçük fizibilite; prototip kapsamını yaz | GDD revizyonu, açık karar listesi, Faz 1 READY adayları; kullanıcı kabulü |
| **1 — Temel savaş prototipi** | Otomatik saldırı, düşman dalgaları, hasar, XP, roguelike yükseltme seçimi, zafer/yenilgi; placeholder varlıklar serbest | Kısa oynanabilir mağara savunma koşusu; hedefli testler, görsel smoke, temel oynanış geri bildirimi |
| **2 — Ejderha gelişimi ve evrim** | Onaylanmış tek/takım/hibrit modele göre gelişim, koşu içi/kalıcı ilerleme ayrımı ve evrimin oynanış etkisi | Test edilebilir gelişim döngüsü ve birkaç anlamlı kombinasyon |
| **3 — Görsel kimlik ve içerik** | Özgün ejderha/düşman/ortam, animasyon, savaş efektleri, HUD okunabilirliği, ses; küçükten insan akınına geçiş | Tutarlı sanat hattı ve genişletilmiş oynanış içeriği |
| **4 — Mobil MVP ve testler** | Android export, veri saklama, dokunmatik deneyim, performans, fiziksel cihaz testleri, playtest ve dengeleme | Gerçek telefonda incelenebilir MVP ve kanıt raporu |
| **5 — Yayın hazırlığı** | Mağaza, lisans, gizlilik, marka, kalite ve dağıtım kontrolleri; yayın stratejisi | Yayın kararı için sürüm adayı; yayınlama ayrıca onay gerektirir |

**Önemli bağımlılıklar:**
- Faz 0'daki oyun referansı incelemesi, Faz 1'in mekanik ve kamera kararlarını besler.
- Görsel üretim fizibilitesi Faz 0'da başlar; gerçek sanat içeriği Faz 3'e bırakılsa da Faz 1'de placeholder animasyon/efekt bulunur.
- Ejderha organizasyon modeli (**D-001**) Faz 2'de kesinleşmeden çoklu ejderha mimarisi taahhüt edilmez.
- Monetizasyon, multiplayer, live ops, backend ve iOS yayımlama otomatik MVP kapsamına girmez.
- Süre/sayısal içerik miktarları onaylanmış taahhüt değildir; ilk oynanabilir deneyimle ölçülür.

**Planlama durumu:** Faz 0 ayrıntılı Issue planı **henüz hazırlanmadı ve onaylanmadı**. Kullanıcıyla birlikte sonraki adımda yapılacak. Sonraki fazlar yalnız üst seviye öneri olarak kayıtlıdır.
