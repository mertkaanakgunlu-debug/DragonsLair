# Game Design Document (GDD) — DragonsLair
**Sürüm:** 0.1 / keşif taslağı  
**Tarih:** 2026-10-26  
**Durum:** DRAFT — ürün sahibi arkadaşın geri bildirimi ve uygulamalı referans analizi bekleniyor  
**Ad:** DragonsLair (repo/çalışma adı; marka kararı değildir)

## 1. Tek cümlelik ürün vaadi
Oyuncu, mağarasında yeni doğmuş bir ejderhanın güçlenmesini deneyimler; otomatik savaş, düşman dalgaları ve roguelike yükseltme seçimleriyle önce küçük mağara canlılarına, zamanla yuvasını yağmalamaya gelen maceracılara karşı hayatta kalır.

## 2. Ürün kimliği — kullanıcı tarafından belirlenen ilkeler (arkadaş onayı bekleniyor)
1. **Gameplay first.** Amaç referans oyunun sevilen döngüsüne yakın hisseden, tekrar oynanabilir bir savunma oyunu yapmaktır; tamamen başka tür bir oyuna dönüşmemek esastır.
2. **Implicit narrative.** Hikâye anlatımı, ara sahne, zorunlu diyalog ve senaryo görevleri yoktur. Oyuncu ejderhanın büyümesini ve mağaranın zamanla insan baskınlarına hedef olmasını rakiplerden, çevreden ve güçlenmeden kendisi anlar.
3. **Özgün içerik.** Ejderhalar, insan ve canavar düşmanları, sanat, ses, arayüz, ilerleme dengesi ve marka özgün tasarlanacak; referans oyundan korunabilir yaratıcı ifade kopyalanmayacak.
4. **Hızlı prototip.** Önce savaş hissi doğrulanacak; büyük içerik, ekonomi ve yayın sistemi sonradan değerlendirilecek.

## 3. Referans oyun ve doğrulama düzeyi
**Stickman Defense: Survival TD — Pusilung**  
Resmî Google Play sayfası: https://play.google.com/store/apps/details?id=com.thp020.stickman.casual.war.game

Mağaza açıklamasında aktarılan üst düzey unsurlar: roguelike / tower-defense / idle aksiyon RPG karışımı, otomatik savaş, beceri kartı seçme/birleştirme, dalga savunması, karakterin saldırı hızı/kritik/savunma gibi gelişim parametreleri, ekipman, destekçi/pet, boss dövüşleri ve çevrimdışı oynama. Bu **mağaza açıklaması düzeyinde teyittir**, bütün ayrıntıların uygulamada bizzat test edildiği anlamına gelmez.

**Faz 0'da uygulamalı inceleme bekleyenler:** kamera ve hareket kısıtları; ana saldırının tam hedefleme kuralı; dalga süreleri ve düşman giriş yolları; beceri seçiminde kaç kart sunulduğu; seçim anında savaşın durup durmadığı; gerçek ilerleme/ekonomi; yenilgi ve tekrar başlatma akışı; oynanış oturumu uzunluğu; ekran yönü; HUD; arkadaşın en beğendiği mikro detaylar. Görüntü/video ve arkadaşın deneyimiyle kanıt toplanacak.

**Özgünlük sınırı:** Genel tür mekanikleri incelenebilir, referans arayüz veya varlıkları birebir kopyalanamaz.

## 4. Hedef deneyim ve temel döngü — TASLAK
1. Bölüme/koşuya gir; ejderha ya da onaylanmış savunma kadrosuyla mağarada konumlan.
2. Düşman dalgaları oluşur; ejderha(lar) onaylanacak kurallarla **otomatik saldırır**.
3. Düşmanlardan XP, puan veya savaş içi gelişim kaynağı kazanılır.
4. Oyuncu düzenli aralıklarla sınırlı **roguelike yükseltme seçeneklerinden** birini seçer: saldırı biçimi, alan etkisi, element, hız, dayanıklılık, sinerji vb.
5. Dalga/boss sonunu atlat; ödüller ve gerekiyorsa kalıcı ilerleme edin.
6. Gelişen ejderhayla daha zor bölüm/koşuyu dene; farklı yükseltme kombinasyonları yarat.

Bu çevrim asıl ürünün kendisidir. Henüz onaylanmamış ayrıntılar (ör. tam üç kart, sabit beş dakika, zorunlu boss sıklığı) **karar değildir**.

## 5. Mekanik bileşenler — ÖN TASARIM
### 5.1 Savaş ve savunma
- Otomatik saldırı; hedef seçimi, saldırı aralığı, hasar tipi ve alan hasarı parametreleştirilebilir olmalı.
- Düşman dalgaları ve zorluk artışı içerik verisinden yönetilmeli; her düşman farklı hız/HP/davranışla ayırt edilebilir.
- Savunulan nesnenin yalnız ejderhanın HP'si mi, yuva HP'si mi olduğu **OPEN**.
- Oyuncunun konum/nişan kontrolü, kamera perspektifi ve ekranda birden fazla ejderha olup olmaması **OPEN**.

### 5.2 Yetenek ve roguelike seçimleri
- Savaş içi seçimler karar vermeye değer olmalı: artan saldırı hızı, ateş püskürtme paterni, zincirleme etki, yavaşlatma, savunma vb. **örneklerdir**.
- Başlangıçta çok sayıda kart değil, birkaç anlamlı ve test edilebilir kombinasyonla ilerle.
- Kartların sayısı, nadirlik, tekrar çekme, birleştirme ve sinerji kuralları referans analizinden sonra belirlenir.

### 5.3 Kalıcı gelişim ve evrim
- Ejderhanın küçükten büyüğe dönüşmesi ana görsel/oynanış ilerleme motifidir.
- Kalıcı güçlenme ile tek koşudaki geçici yükseltmeleri açıkça ayır.
- Evrim yalnız kozmetik olmak zorunda değildir; yeni saldırı biçimleri ve taktik seçenekler açabilir. Ancak evrim ağacı sayısı, dallar ve ekonomi **OPEN**.
- Ateş/Buz/Fırtına gibi elementler yalnız **değerlendirilecek fikir**; onaylanmış başlangıç kadrosu değil.

## 6. Düşman ve ortam ilerlemesi — TEMATİK TASLAK
| İlerleme bandı | Düşman örnekleri | Ortam/oynanış anlamı |
|---|---|---|
| Erken | Örümcek, sıçan, küçük böcek | Yeni doğmuş ejderhanın ilk savunmaları |
| Büyüme | Akrep, iri örümcek, yarasa | Daha tehlikeli mağara bölgeleri |
| Güçlenme | Goblin, kurt, mağara canavarı | Ejderhanın yerel tehditleri aşması |
| İnsan teması | Keşifçi, hazine avcısı | Yuva artık fark ediliyor |
| Baskınlar | Şövalye, okçu, büyücü, ejderha avcısı | İnsanların ejderhaya düzenli saldırısı |
| İleri oyun | Elit baskın timleri, özel boss'lar | Büyük savunma mücadeleleri |

Bu **senaryo bölümleri zorunluluğu** veya lineer görev zinciri değildir. Dalga/içerik sıralamasına yön veren örtük anlatı çerçevesidir. Düşman sıralaması oyun dengesiyle değişebilir.

## 7. Görsel / animasyon / asset yaklaşımı — AÇIK
- Hedef: mekanikleri net okutan, mobil performansa uygun özgün karakter ve efektler.
- Aday üretim hatları: (A) 2D sprite/skeletal cutout + motor animasyon sistemi, (B) 3D model + rig/animasyon + uygun motor. Seçim bir küçük ejderha, bir düşman ve bir saldırı efektiyle yapılan **görsel fizibilite değerlendirmesi** sonrası verilecek.
- AI konsept üretimi mümkündür; oyun-hazır tutarlı sprite/rig/mesh/animasyon **otomatik garanti değildir**. Claude Code; asset dönüştürme, import, araç betikleri, efekt/shader ve oyun içi bağlama işleri yapabilir. Nihai sanat kalitesi gözle kontrol edilir.
- Her asset için kaynak, lisans, ticari kullanım, üretim aracı/sürümü, değiştirilmiş dosya ve gerekiyorsa insan onayı kaydı tutulur. Telifli oyundan asset çıkarılmaz.

## 8. UX ve ekonomi — KARARA BAĞLANMAMIŞ
- Ekran yönü ve kontrol şeması, gerçek oynanış analizi sonrası netleşir.
- HUD savaş durumunu, seçilebilir yükseltmeyi ve düşman tehdidini okunur göstermeli; referansın özgün yerleşimi kopyalanmamalı.
- Kalıcı para birimleri, ekipman, idle ödül, reklam, satın alma, enerji ve sezon sistemleri MVP'ye **otomatik dahil değildir**. İlkin eğlence ve denge kanıtlanacak.
- Offline oynama MVP hedefi olarak değerlendirilebilir; sunucu bağımlılığı sadece onaylı somut ihtiyaç varsa eklenir.

## 9. İlk prototip / MVP kapsam ayrımı
**Vertical slice önerisi (ürün mimarisini kilitlemez):** bir yavru ejderha test karakteri, mağara sahnesi, örümcek ve sıçan düşmanları, otomatik saldırı, dalga üretimi, savaş içi birden fazla upgrade seçeneği, basit kaybet/kazan akışı. Amaç eğlence, okunabilirlik, performans ve AI destekli asset/animasyon hattını doğrulamak.

**MVP kapsamı:** Vertical slice playtest sonucunda belirlenecek. İçerik sayıları, motor, oturum süresi, para sistemi, evrim sayısı şu anda taahhüt değildir.

**MVP dışı varsayılanlar:** online PvP, multiplayer, sunucu ekonomi sistemi, canlı etkinlikler, abonelik, ücretli sandıklar, sezonluk içerik ve agresif reklam sistemleri.

## 10. Faz yaklaşımı (öneri, henüz başlatılmadı)
- **Faz 0 — Referans analizi ve tasarım:** oynanış envanteri, arkadaşın öncelikleri, kritik kararlar, hafif görsel/teknik fizibilite; GDD revizyonu ve prototip görevleri.
- **Faz 1 — Temel savaş prototipi:** tek sahne, düşman dalgaları, otomatik savaş, XP ve yükseltme seçimleri; geçici görseller kullanılabilir.
- **Faz 2 — Ejderha gelişimi ve evrim:** prototip sonucuna göre kalıcı ilerleme, evrim ve ejderha organizasyon modelinin ilk sürümü.
- **Faz 3 — Görsel kimlik ve içerik:** düşman katmanları, özgün ejderha/görsel/animasyonlar, okunur UI ve sesler.
- **Faz 4 — Mobil MVP ve oyun testleri:** Android paketleme, performans, kayıt güvenilirliği, cihaz smoke testleri, playtest ve dengeleme.
- **Faz 5 — Yayın hazırlığı:** yalnız MVP eğlence ve kalite kabulünden sonra mağaza, lisans, gizlilik ve yayın stratejisi.

Her faz **Issue listesi, kabul kriterleri, yerel hedefli test kanıtı, bağımsız inceleme ve kullanıcı onayı** ile ilerler. Faz isimleri yol haritası önerisidir; ürün sahibi onayı bekleniyor.

## 11. Performans, kalite ve test ilkeleri
- **Hosted CI / GitHub Actions yok.** Her commit'te tüm testleri çalıştırmak da yok.
- Günlük geliştirmede etkilenen mekanik için hızlı birim/lint; Issue çıkışında ilgili sahne smoke; fazda ilgili regresyon; MVP'de gerçek Android cihaz + kapsamlı test.
- Oyun hissi, düşman görünürlüğü ve beceri seçimleri gerçek oynanış izlenerek değerlendirilir; yalnız otomatik test eğlenceyi kanıtlamaz.
- Test kanıtları exact HEAD ve ortamla ilişkilendirilir. Koşulmayan testler `NOT RUN` yazılır.

## 12. Açık karar defteri — arkadaşın yanıtı beklenecek
| ID | Karar | Mevcut durum | Öncelik |
|---|---|---|---|
| D-001 | Tek ana ejderha mı, takım mı, hibrit mi? | OPEN | Yüksek |
| D-002 | Referans oyunda en sevilen 3–5 mikro mekanik hangileri? | OPEN | Çok yüksek |
| D-003 | Oyuncu ejderhayı hareket ettirecek mi? Savaş alanı/kamera nasıl? | OPEN | Yüksek |
| D-004 | 2D, 2.5D veya 3D sanat yaklaşımı | OPEN | Orta |
| D-005 | İlk oyun motoru ve export hedefleri | OPEN (Godot aday) | Orta |
| D-006 | Evrim şekil mi, mekanik dal mı, ikisi birden mi? | OPEN | Yüksek |
| D-007 | Korunan şey ejderhanın HP'si, yuva mı, hazine mi? | OPEN | Yüksek |
| D-008 | Run başına hedef süre, kaybetme ve kalıcı ilerleme akışı | OPEN | Orta |
| D-009 | Sanat tonu (sevimli, karanlık, stilize vb.) | OPEN | Orta |
| D-010 | Arkadaşın fikrî mülkiyet, repo ve yayın sahipliği | OPEN | Yüksek |
| D-011 | Para kazanma ve reklam yaklaşımı | DEFERRED | Düşük |
| D-012 | İlk Android cihazlar ve min. performans hedefi | OPEN | Orta |

Bir karar cevaplandığında yalnız ilgili satır **APPROVED** olarak güncellenir; bağlı kabul kriterleri ve ilgili Issue'lar revize edilir. Cevap yoksa keyfi kesinleştirme yapılmaz.

## 13. İlk kabul ölçütü: doğru sorunu çözen deney
Faz 1 sonunda bir oyuncu, hikâye metni okumadan bir mağara savunma koşusunu başlatabilmeli; düşmanların geldiğini, ejderhanın otomatik savaştığını, seçtiği yükseltmenin etkisini ve başarısızlık/başarı sonucunu **oyun içinde** görebilmelidir. Prototip gerçek oyun estetiğine ulaşmak zorunda değil, ancak oynanışı hissettirmelidir.

## 14. Revizyon protokolü
Her arkadaş geri bildirimi şu biçimde işlensin: `Girdi / Etkilenen bölüm / Önerilen değişiklik / Ürün kararı gerekli mi? / Onaylayan / GDD sürümü / Bağlı Issue`. Ayrıntılı yeni görüşler geldiğinde bu belge güncellenir; önceki fikirlerin sessizce silinmesi yerine değişiklik notu tutulur.

### Değişiklik kaydı
- **v0.1 — 2026-10-26:** İlk ürün vizyonu, referans mekanikleri, gameplay-first + implicit narrative ilkesi, düşman ilerlemesi, geliştirme modeli ve açık karar listesi. Henüz ürün sahibinin son onayı yok.
