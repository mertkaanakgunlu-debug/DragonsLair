# Karar kayıtları

**Tek kanonik karar listesi:** [GDD §11 — kararlar](../game-design/GDD.md). Tam soruların 25 yanıtı ayrıca [2026-10-27 ürün görüşü girdisi](../requirements/design-intake-2026-10-27.md) olarak arşivlenir; bu ikinci karar envanteri değildir.

**Durum sözlüğü:** `OPEN` (yanıt eksik), `DIRECTION_RECEIVED` (kullanıcı yön bildirdi, resmi onay değildir), `PROPOSED` (teknik/tasarım önerisi), `APPROVED` (ürün sahiplerinin açık kabulü), `DEFERRED` (bilinçli erteleme), `REJECTED`.

Gerektiğinde ADR (Architecture/Design Decision Record) açılır:
- ID, başlık, tarih, durum, onaylayan
- Problem ve kısıtlar; ürün görüşüne kaynak
- Seçenekler, artıları/eksileri, geri dönüş maliyeti
- Önerilen karar, gerçek onay veya bekleyen soru
- GDD D-ID, etkilenen Issue'lar

**Dikkat:** 25 yanıt birçok tasarım yönünü netleştirdi (hibrit ana + yardımcı ejderhalar, oto hareket/saldırı, yatay 2.5D, evrim ve build). Teknik alt kararlar ve özellikle oyun motoru (D-005), Rage sayısal kuralları (D-013), 4 dakika yorumu (D-008), karakter/yayın sahipliği ve şu an public repo (D-010) hâlâ açık. Onay gelmedikçe teknik tercihler sessizce sabitlenmez.
