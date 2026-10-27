# DragonsLair — 25 Soruluk Oyun Tasarımı Görüşü, 2026-10-27
**Kaynak:** Kullanıcının konuşmada verdiği numaralı 1–25 cevapları. **Statü:** Ürün görüşü girdisi (`DIRECTION_RECEIVED`), ayrıca resmi kabul/uygulama onayı değil. Konuşmanın birebir transkripti değildir; cevapların anlamı sadeleştirilerek korunmuştur.

> Karar statüsünün **tek kanonik yeri** [GDD §11](../game-design/GDD.md). Bu belge yalnızca cevap izini taşır, ikinci bir karar defteri değildir.

| Soru | Alınan cevap (sadık özet) | GDD / Karar |
|---|---|---|
| 1 | Eklenti seçimlerinin sonraki güçlendirmeleri etkilemesi; etkinlik, dalga ve zindanla sürekli ilerleme; ekipman ve build özelleştirmesi | §1, §4–5; D-002, D-015, D-016 |
| 2 | Enerji kazanımı kolaylaşsın; günlük Dungeon Dive hakları artsın; silaha bağlı daha çok eklenti; oyuncu seçimleriyle çok güçlü/broken build mümkün olsun | §3–5; D-002, D-015, D-016 |
| 3 | Referans döngü korunsun; ejderhaya özgü eklenti/mekanik; pet yerine tematik yardımcı sistem | §1, §5; D-014 |
| 4 | Hibrit: ana ejderha + yardımcı ejderhalar | §3, §5; D-001 |
| 5 | Hareket ve saldırı otomatik, yükseltme oyuncuda; manuel özel yetenek ve otomatik kullanma düğmesi olsun | §3; D-003 |
| 6 | Referansa yakın savaş sunumu, **yatay** ekran | §3; D-003 |
| 7 | Ayrı yuva değil ana ejderhanın HP'si kayıp koşulu | §3; D-007 |
| 8 | Her bölüm dalgalar + sonunda boss | §3–4; D-017 |
| 9 | Rastgele kartlar + sinerji/birleştirmeler, aynı yeteneği tekrar geliştirme | §3, §5; D-016 |
| 10 | Normal dalgalar 4'er dakika; özel etkinlikler en fazla 10 dakika | §4; D-008 (4 dk tanımı ayrıca netleşecek) |
| 11 | Kalıcı + geçici evrim; hem görsel hem mekanik değişim; çok farklı ejderha türlerine genişleyebilir yapı | §5; D-006 |
| 12 | Başlangıç tek yavru ejderha, sonradan yeni türler açılır | §3, §5; D-001 |
| 13 | Ejderha seviyesi kalıcı; savaş içi geçici gelişim; bazı pasifler, ekipman, rün/taş kalıcı; kill eşiğiyle Rage | §5; D-013, D-016 |
| 14 | Kaybedilen bölüme baştan girilir; ilerleme/öldürülen düşmana göre ödül, tam ödülün en fazla yarısı | §4; D-008 |
| 15 | Yardımcı ejderhalar olsun | §5; D-014 |
| 16 | Küçük yaratık → daha büyük → insanlar; rakip ejderhalar, paladin ve rahipler; yuva dışında dünya keşfi hissi | §6; D-017 |
| 17 | Her bölümün sonunda farklı davranış veya baskın özellikte boss: HP, büyü, fiziksel vb. | §4, §6; D-017 |
| 18 | Mağaranın bölgeleri; ileride dış dünya ve kendine ait yaşam alanları hissi | §6; D-017 |
| 19 | Stilize ve fantastik sanat tonu | §7; D-009 |
| 20 | 2.5D sunum | §7; D-004 |
| 21 | Evrim sadece büyüme değil; fiziksel özellik, animasyon ve saldırı değişmeli; yeni deneyim hissettirmeli | §5, §7; D-006 |
| 22 | AI üretimi ağırlıklı sanat/asset yaklaşımı | §7; D-004, D-009 |
| 23 | Önce Android, sonra iOS | §8; D-012 |
| 24 | Önce eğlenceli oyun, para kazanma sonra | §8; D-011 |
| 25 | İki geliştiricinin kontrolünde; ilk prototip yavru ejderha + birkaç evrim örneği + otomatik saldırı + kartlar + 2–3 dk dalga + bölüm sonu boss | §8–9; D-010 ve Faz 1 adayları |

## Yorumlamada teyit gerektirenler
- **4 dakika:** 'normal dalgalar' ifadesinin tek dalga, toplam bölüm veya boss dahil döngüye tam karşılığı.
- **İki geliştiricinin kontrolü:** operasyonel erişim mi, oyunun IP/yayın ortaklığı mı? Fikri öneren arkadaşın hakları nasıl?
- **Referansa yakın savaş ekranı:** kamera ve mekanik davranış mı, yoksa sanat kompozisyonu beklentisi mi? Kopya UI kabul edilemez.
- **Özel yetenek, Rage, helper dragon:** İlk 2–3 dakikalık prototipte mi, daha sonraki sprintlerde mi?
- **'Her şeyin ejderhası':** çok farklı ejderha türlerine esneyebilen sistem hedefi; ilk sürümde sınırsız tür taahhüdü değildir.

## Değişiklik / onay işleyişi
Yanlış yorum varsa bu intake kaydı ve GDD revize edilir. Onaylı ürün kararı, ayrı kullanıcı/ürün sahibi onayı ile GDD'deki ilgili D-ID'de `APPROVED` yapılır; yeni özellik tek başına Faz 1 READY veya geliştirme izni vermez.

## Takip netleştirmeleri — 2026-10-27

Bu dört yanıt, önceki 25 soruya **ek** ürün görüşü girdisidir; `APPROVED`/faz başlatma onayı değildir.

| ID | Gelen yanıt | Etkilenen karar ve kalan OPEN |
|---|---|---|
| T-01 | Normal bölümde **4 dakika düşman dalgaları**, ardından **boss savaşı** | D-008; boss üst süresi ve zaman aşımı OPEN |
| T-02 | İlk 2–3 dk prototipte **kartlar ve evrim örnekleri**; Rage, manuel/otomatik özel yetenek ve yardımcılar sonra | D-003/D-006/D-013/D-014 ve Faz 1 kapsamı; adet/ayrıntılar OPEN |
| T-03 | 2.5D için **2D sprite + derinlik** ile **3D model + sabit kamera** küçük karşılaştırılabilir denemeler | D-004/D-005; sonuç, motor ve nihai teknik seçim OPEN |
| T-04 | Repo görünürlüğü ve ürün/IP hakları için **henüz karar verilmedi** | D-010 OPEN; repodaki public durum otomatik onay sayılmaz |

Yorumlama kuralı: Burada yalnızca kullanıcının verdiği tercih aktarılmıştır; fikrin sahibi arkadaşın ayrı onayı varsayılmaz. Kanonik güncel statüler [GDD §11](../game-design/GDD.md) içindedir.
