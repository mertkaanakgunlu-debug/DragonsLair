# DragonsLair — Game Design Document (GDD)
**Sürüm:** 0.3 / 25 ürün yanıtı + 4 tasarım netleştirmesi; henüz DRAFT  
**Tarih:** 2026-10-27  
**Durum:** DRAFT — kullanıcı tarafından iletilen 25 ürün yanıtı kaydedildi; nihai ürün sahipliği/teknik onay ve referans oynanış doğrulaması bekliyor.  
**Çalışma adı:** DragonsLair. Yayın/marka kararı değildir.

> **Karar statüsü sözlüğü:** `DIRECTION_RECEIVED` = konuşmada yön/tercih bildirildi, GDD'ye işlendi; resmi ürün onayı/READY demek değildir. `OPEN` = yanıt yok veya önemli alt tercih eksik. `DEFERRED` = bilinçli ertelendi. `APPROVED` = ürün sahiplerinin açık kararıyla kesinleştirildi. Şu belge hiçbir geliştirme fazını başlatmaz.

## 1. Ürün vizyonu ve referans sınırı
Stickman Defense: Survival TD'nin **savaş içi yükseltme seçimi, seçilen yükseltmelerin sonraki seçenekleri etkilemesi, farklı build oluşturma, otomatik savaş, dalga/boss mücadeleleri ve kalıcı gelişim** deneyimini koruyan; ancak **özgün** ejderha karakterleri, yardımcı ejderhalar, özel yetenekler ve evrim seçenekleri olan mobil savunma/roguelike oyunudur.

**Gameplay-first, implicit narrative:** Oyuncu yavru ejderhayla mağarada küçük yaratıklara karşı başlar; farklı mağara bölgelerinde büyüyerek goblinler, kurtlar ve diğer ejderhalara, sonunda hazine avcıları, şövalyeler, okçular, büyücüler, paladinler ve rahiplerin baskınlarına karşı koyar; ilerleyen oyun dış dünyaya taşar. Bu, zorunlu ara sahne/diyalog/öykü görevi anlamına **gelmez**. Düşman ve ortam çeşitliliği yalnızca ilerleme hissine hizmet eder.

**Özgünlük:** Rakibin kaynak kodu, telifli görsel/ses, karakter tasarımı, ayırt edici arayüz kompozisyonu veya metinleri alınmaz. “Referansın savaş düzenine yakın” isteği işlevsel mekanik yaklaşıma ilişkindir, piksel kopyasına değil.

## 2. Gereksinimlerin kanıt düzeyi
- **ÜRÜN TERCİHİ / DIRECTION_RECEIVED:** 2026-10-27 tarihinde kullanıcı tarafından yanıtlanan 25 tasarım sorusu. Cevaplar bu belgeye girdi oldu; arkadaşın ayrı/nihai onayı varsayılmıyor. Tam numaralı iz kaydı: [Intake-2026-10-27](../requirements/design-intake-2026-10-27.md).
- **REFERANS OYUN KANITI:** Resmî [Google Play sayfası](https://play.google.com/store/apps/details?id=com.thp020.stickman.casual.war.game) çeşitli üst düzey özellikleri beyan eder; birebir mekanik davranış, kamera, UI ve tüm seçim kuralları oynanmış/incelemiş kabul edilmez. Bu alanlar [Issue #2](https://github.com/mertkaanakgunlu-debug/DragonsLair/issues/2) ile doğrulanacak.
- **ÖNERİ:** Minimum prototipte bir test ejderhası ve sınırlı sayıda yetenek/evolution örneği; içerik sayıları ve işletim sistemi/engine seçimi sonradan onaylanır.

## 3. Çekirdek oynanış ve kontrol
1. Oyuncu başlangıçta **tek yavru ana ejderhaya** sahip olur; zamanla başka oynanabilir türler açılabilir. Savaşta **ana ejderha + yardımcı ejderhalar** yaklaşımı tercih edildi (`D-001`); yardımcıların açılma zamanı, sayısı ve rolü henüz açık.
2. Normal saldırılar **ve hareket otomatik**; oyuncu savaş içi yükseltme/kart seçimlerini yapar.
3. **Özel yetenekler** oyuncu tarafından elle tetiklenebilir; ayrıca tek tuşla **otomatik özel yetenek kullanımı** seçeneği vardır. Otomatik özel yeteneklerin zamanlama/öncelik kuralları ayrıca tasarlanır.
4. Korunan varlık olarak **ana ejderhanın HP'si** tercih edildi; ayrı bir yuva/hazine HP'si ilk tasarımın zorunlu öğesi değil.
5. Normal bölümler **düşman dalgalarından oluşur ve bölüm sonunda boss vardır.** Başarı/yenilgi, tekrar oynama ve koşu sonunda kalıcı ödül döngüsü vardır.
6. Savaş içi yükseltmeler karaktere özgü ve **önceki kart/ekipman seçimine duyarlı** olmalıdır. Aynı yeteneği tekrar güçlendirme, sinerji ve sıra dışı derecede güçlü (“broken”) ancak ulaşılması keyifli kombinasyonların ortaya çıkması hedeflenen güç fantezisidir. Bunun için rastgelelik, seçim ağırlıkları ve denge tasarlanacak; her koşuda garanti güç fantezisi veya oyunu çökerten exploit anlamına gelmez.
7. **Rage modu:** Belirli sayıda düşman öldürünce açılan/güçlenen savaş mekaniği tercih edildi; eşik, süre, reset kuralı ve manuel/otomatik kullanım davranışı `OPEN`.

**Kamera:** Referans oyundaki savaş sunumuna benzer ritim/düzen tercih edildi; ekran **yatay**. **2.5D** sanat tercihi alındı, fakat kamera açısı/yerleşimi ve 2D sprite-derinlik vs 3D sahne uygulaması teknik araştırma sonrasında belirlenir.

## 4. Bölüm, etkinlik, zindan ve ödüller
- **Normal bölümdeki düşman dalgaları toplam 4 dakika sürer; ardından ayrı bir boss savaşı başlar.** Boss süresi 4 dakikanın dışında kalır. Boss için üst süre ve zaman aşımı kuralı henüz OPEN.
- **Özel etkinlik hedef üst sınırı:** 10 dakika.
- **İlk oynanabilir demo:** 2–3 dakikalık düşman dalgaları, ardından boss. Bu tam bölüm değil, daha kısa bir **test** deneyimidir. İlk prototipin çekirdeği otomatik savaş, kart seçimleri ve örnek evrimlerdir; özel yeteneklerin manuel/oto kullanımı, Rage ve yardımcı ejderhalar sonraki geliştirme aşamalarına ertelendi.
- Referansın dalga/savunma içeriğine ek olarak **zindan (Dungeon Dive) ve farklı etkinliklerle sürekli ilerleme yolları** bulunmalı; miktar ve mod kuralları sonradan belirlenir.
- **Enerji kazanımı daha kolay** ve **günlük Dungeon Dive giriş sayısı daha yüksek** olsun; referansa göre hangi oranda olduğu bilinmiyor. Erken prototipte eğlence döngüsünü enerji kapısıyla sınırlamak gerekmiyor.
- **Kaybedilen koşu** baştan başlar; öldürülen canavar ve ilerleme üzerinden kısmi ödül alınır, miktar **tam maksimum ödülün %50'sini geçemez**. Formül, kötüye kullanım/farm riskleri ve ödül türleri TBD.
- Her normal bölüm sonunda **davranışı veya stat odağı farklı bir boss** olsun; örn. yüksek HP, büyü hasarı, fiziksel güç. Aynı boss'un sadece HP artışı olması uzun vadeli hedefi karşılamaz.

## 5. Ejderha gelişimi ve build çeşitliliği
### 5.1 Kalıcı meta gelişim
- Ana ejderhanın seviyesi koşular arasında **kalıcı**.
- Bazı pasif yetenekler, **ekipman**, **rünler/taşlar** ve uygun kaynaklar kalıcı.
- **Ekipman kişiselleştirmesi** farklı savaş tarzları yaratmalı; seçilen silah/ekipman profili savaş içinde sunulabilecek eklenti türlerini etkileyebilmeli.
- Tam teçhizat slotu, silahın ejderha anatomisine nasıl uyarlanacağı, nadirlik/upgrade ve ekonomi kuralları `OPEN`; “silah” mutlaka insan tipi elde tutulan bir silah olmak zorunda değil (pençe/nefes odağı gibi adaylar).

### 5.2 Geçici koşu gelişimi
- Her koşuda yeni kartlar/güçler seçilir, aynı kart tekrarlanıp kademeli güçlendirme yapılabilir.
- Kart havuzu mevcut ejderha türüne, seçili ekipman/silah kategorisine ve önceki kartlara tepki verir.
- Geçici evrim/güçlenme de mümkün; **kalıcı evrim + koşuya özel dönüşüm** birlikte arzu ediliyor.
- Evrim yeni **görünüş, vücut parçaları, animasyon ve saldırı biçimi** getirmeli; yalnız ölçek büyütmek yeterli değil.
- Birçok ejderha türüne genişleyebilen **veri temelli ve yeniden kullanılabilir içerik üretimi** hedeflenir; *ilk MVP'de her tür ejderhayı üretme yükümlülüğü yoktur*.

### 5.3 Ana/yardımcı ejderhalar
- Petler yerine **oyun dünyasına uygun yardımcı ejderhalar** olacak; nasıl edinildikleri, kaç tane oldukları, destek mi saldırı mı yaptıkları ve kalıcı olup olmadıkları TBD.
- Başlangıçta tek yavru ana ejderha; sonraki türler ilerledikçe açılabilir. Bu, takım/hibrid yanıtlarıyla çelişmez: **başlangıç kadrosu tek, ileriki savaşa yardımcı katılabilir.**

## 6. Düşman, boss ve mekân ilerlemesi (örtük anlatı)
| Basamak | Aday düşmanlar | Oyun hissi |
|---|---|---|
| 1 — Yavru / mağara | örümcek, sıçan, küçük böcek | ilk savunma, büyümenin başlangıcı |
| 2 — Derin mağara | akrep, iri yaratıklar, goblin, kurt | güç ve çeşitlenen tehdit |
| 3 — Rakipler | rakip ejderhalar, güçlü canavarlar | artık başka tehditlere meydan okuma |
| 4 — İnsan keşifleri | keşifçi, hazine avcısı, savaşçı | mağaranın fark edilmesi |
| 5 — Akınlar | şövalye, okçu, büyücü, paladin, rahip, ejderha avcısı | sistematik insan baskınları |
| 6 — Dış dünya | seçkin timler, diğer ejderhalar, ileri boss'lar | mağara dışına açılma, yeni yaşam alanları |

İçerik sırası mekanik tempo ve dengeye göre ayarlanabilir; zorunlu lineer hikâye, cutscene, diyalog veya görev zinciri tasarlanmaz.

## 7. Sanat, animasyon ve AI üretimi
- **Sanat tonu:** Stilize, fantastik, güçlendikçe daha görkemli.
- **Sunum tercihi:** 2.5D; teknik yöntem henüz OPEN. **2D sprite + katmanlı derinlik** ve **3D karakter/ortam + sabit/yarı sabit kamera** yaklaşımları birer küçük, karşılaştırılabilir örnekle değerlendirilecek. Nihai görsel hat ve motor seçimi, oynanış/animasyon/Android performansı ve üretim maliyeti birlikte incelenmeden yapılmayacak.
- Yapay zekâdan olabildiğince yararlanılsın; ancak **üretilmiş konsept resmi = oyun-hazır animasyon/rig/efekt** değildir. Tutarlılık, farklı form/evrim animasyonları, performans ve lisans için kalite kapısı zorunlu.
- Claude Code asset düzenleme, import, rig/animasyon yardımcı betikleri, shader/partikül ve oyun entegrasyonunu otomatikleştirebilir; çıktılar gerçek sahnede gözle incelenir.
- Kaynak/lisans, üretim araçları ve ticari kullanım hakkı her varlık için kayıt edilir. Ücretli araç kullanımı kullanıcı onayı gerektirir.

## 8. Hedef platform, gelir ve güvenlik
- **Önce Android, sonra iOS**; Android üzerinde oynanabilir mobil MVP. Windows'ta yerel geliştirme ve test yaklaşımı.
- **Önce eğlenceli oyun, gelir modeli sonra.** Reklam, IAP, enerji monetizasyonu ve live ops ilk prototipe zorla eklenmez.
- **İki geliştiricinin kontrolünde** yürütülecek. Bu yönetsel tercih hisse/IP paylaşımı, dış yayın hesapları, fikrin sahibi arkadaşın hakları ve GitHub sahiplik haklarının ayrıntısını hukuken belirlemez. Depo şu anda `public`; görünürlük ve IP sahipliği **OPEN**.
- **GitHub Actions / hosted CI yok.** Yerel hedefli testler, Issue sonu smoke, faz sonu ilgili regresyon, MVP eşiğinde gerçek cihaz testi. Çalışmayan testler `NOT RUN`.

## 9. İlk prototip, MVP ve kapsam sınırı
### Faz 1 için kullanıcı tarafından istenen ilk demo
- Küçük yavru ana ejderha, otomatik hareket ve saldırı.
- Tek kısa mağara sahnesinde düşman dalgası, **2–3 dakika**, sonunda bir boss.
- **Savaş içi beceri kartları**, en az birkaç anlamlı yükseltme/sinerji denemesi.
- **Birkaç evrim örneğinin** etkisini gösteren, nicelik hedefi sonradan belirlenecek görsel ve saldırı davranışı.
- Saldırı/hasar, HP, dalga/başarı/yenilgi, yükseltme farkı gözlenebilir.
- **İlk demo dışında:** Manuel/otomatik özel yetenek kullanımı, Rage ve yardımcı ejderhaların tam savaş mekaniği sonraki iterasyonlara bırakılacak. Faz 0'da gelecekte eklenebilirlik analiz edilir; Faz 1'de tamamlanmaları kabul ölçütü değildir.

### İlk demo dışındaki ürün vizyonu (otomatik kapsam taahhüdü değil)
Yardımcı ejderhalar, tür çeşitliliği, tam ekipman ve rün ekonomisi, Dungeon Dive/günlük etkinlikler, ilerleme ve kısmi ödül sistemi, detaylı Rage dengesi, dış dünya biyomları, tüm boss çeşitliliği, tüm evrim ağacı ve mobil yayın kalitesi sonraki fazların adaylarıdır.

### Çıkış ölçütü
Bir test oyuncusu hikâye metni olmadan kısa koşuyu başlatabilir, ejderhanın otomatik saldırdığını görebilir, kartın saldırı hissini değiştirdiğini fark eder, evrim farkını deneyimler ve boss sonucunu görür. Oyun hissi manuel test edilir; salt birim testiyle PASS sayılamaz.

## 10. Fazlar (üst düzey öneri, henüz kesinleştirilmedi)
- **Faz 0 — Referans analizi / GDD / teknik & sanat fizibilitesi.** Mevcut DRAFT Issue #2–#8. Yeni yanıtlar #3 için gereksinim girdi ve diğer Issue'lar için kısıt oldu.
- **Faz 1 — Çekirdek savaş prototipi.** 2–3 dk dalga + boss, otomatik hareket/saldırı, kartlar ve sınırlı evrim örnekleri. Özel yetenek, Rage ve yardımcı ejderhalar bu prototipin kapsamı dışında; görevlerin kesin içeriği Faz 0 sonunda onaylanır.
- **Faz 2 — Ejderha gelişimi, build ve savaş katmanı.** Kalıcı stat/ekipman/rün, koşu yükseltmeleri, Rage, özel yetenek auto-tetikleme, yardımcı ejderha ve sistem sinerjileri için kademeli plan.
- **Faz 3 — Görsel üretim hattı ve içerik.** 2.5D stilin uygulanması, evrim animasyonları, düşman/boss farklılıkları, zindan/etkinlik adayları ve mekân çeşitliliği.
- **Faz 4 — Android MVP + playtest.** 4 dakikalık normal bölüm hedefi, özel etkinlikler için maksimum 10 dakika, kayıt/ödül sistemi, gerçek cihaz performansı ve denge; hangi sistemlerin MVP kapsamında olacağı oyun testlerinden sonra kesinleştirilir.
- **Faz 5 — Yayın hazırlığı.** Uygulama mağazaları, IP/lisans/marka, varsa ticari model ve dağıtım kararı.

**Proje/faz numaraları değişmedi; içerik yoğunluğu ve gerekirse alt dilimler Phase 0 onayı sonrası değerlendirilecek.** Faz 0 DRAFT planı: [phase-0-plan.md](../phases/phase-0-plan.md).

## 11. Açık karar defteri — tek kanonik karar listesi
Aşağıdaki `DIRECTION_RECEIVED` satırları cevaplanan tercihlerdir; **APPROVED sayılmaz**. Bunların ürün sahiplerince son kabulü, kapsamların READY yapılması ve teknik plan kararı ayrı işlemdir.

| ID | Başlık | Durum / alınan yön | Çözülmesi gereken alt karar |
|---|---|---|---|
| D-001 | Kadro modeli | DIRECTION_RECEIVED — ana + yardımcı ejderha (hibrit), başlangıç tek yavru | yardımcı açılış, sayı, roller |
| D-002 | Referansta sevilenler | DIRECTION_RECEIVED — eklenti/kart koşullu güçlenmesi, build özelleştirme, alternatif sürekli ilerleme | gerçek oynanış kurallarını kanıtla |
| D-003 | Kontrol/kamera | DIRECTION_RECEIVED — otomatik hareket/saldırı, manuel/auto özel yetenek, yatay referans benzeri | tam kamera açısı, HUD özgün kompozisyonu |
| D-004 | Sanat tekniği | DIRECTION_RECEIVED — 2.5D; 2D katmanlı ve 3D sabit kamera küçük karşılaştırmalarla değerlendirilecek | Sonuç ve teknik pipeline seçimi OPEN |
| D-005 | Oyun motoru | OPEN — Godot/Unity değerlendirilecek | lokal test, Android export, ekip yetkinliği |
| D-006 | Evrim | DIRECTION_RECEIVED — kalıcı + geçici; görsel ve saldırı değişir | eşikler, ağaç/çeşit, prototip örnekleri |
| D-007 | Kaybetme nesnesi | DIRECTION_RECEIVED — ana ejderha HP | yardımcı hasar/ölüm kuralları |
| D-008 | Koşu süresi/sonuç | DIRECTION_RECEIVED — normal bölümde 4 dk toplam dalga, **ardından ayrı boss**; etkinlik ≤10 dk, yenilgide kısmi ödül ≤%50 | Boss üst süresi/zaman aşımı ve kısmi ödül formülü OPEN |
| D-009 | Sanat tonu | DIRECTION_RECEIVED — stilize fantazi, 2.5D | referans görseli ve üretim stil kılavuzu |
| D-010 | Sahiplik/IP | **OPEN — henüz karar verilmedi**; iki geliştirici kontrolü önceki bir tercih, hukuki onay değildir | Repo public/private, ortak haklar, üçüncü taraf varlık lisansları, yayın hesapları ve yetkiler OPEN |
| D-011 | Monetizasyon | DEFERRED — önce eğlence; model sonra | reklam/IAP ve enerji kısıtları |
| D-012 | Hedef cihaz/platform | DIRECTION_RECEIVED — Android → iOS | cihaz, minimum Android / FPS ve performans |
| D-013 | Rage modu | DIRECTION_RECEIVED — kill eşiğinde açılır | sayaç/reset/eşik/süre/etki |
| D-014 | Yardımcı ejderha | DIRECTION_RECEIVED — pet yerine helper dragon | edinim, roller, savaş içi kontrol |
| D-015 | Enerji ve Dungeon Dive | DIRECTION_RECEIVED — enerji daha kolay, giriş hakkı daha yüksek | sayısal oran ve gerekli olup olmadığı |
| D-016 | Build / ekipman / rün | DIRECTION_RECEIVED — kalıcı ekipman/taş + koşula duyarlı beceri havuzu | slotlar, sinerji, kaydetme ve meta ekonomisi |
| D-017 | Boss ve dünya | DIRECTION_RECEIVED — bölüm sonu farklı boss, mağaradan dış dünyaya | demo boss tasarımı, harita temposu |

## 12. Faz 0'da mutlaka netleştirilmesi gerekenler (kısa liste)
1. **Referans ekran kaydı**: kamera, kart/upgrade geliş mekanikleri, koşu ve boss geçişleri; [#2](https://github.com/mertkaanakgunlu-debug/DragonsLair/issues/2).
2. **2.5D teknik çözüm** ve oyun motoru; #5/#6.
3. **Normal bölüm süre yapısı netleşti:** toplam 4 dk dalga, sonra boss; yalnız boss maksimum süresi/zaman aşımı OPEN.
4. **İlk 2–3 dakikalık demo:** otomatik saldırı + kartlar + sınırlı evrim + boss; Rage, manuel/oto özel yetenek ve yardımcılar sonraya ertelendi. Kart/evrim adetleri testle netleşecek.
5. **Public repo ve fikrî mülkiyet tamamen OPEN**: iki geliştiricinin kontrol düzeyi, içerik hakları ve mağaza hesapları; #3. Bu karar henüz verilmedi.
6. Referansın keyif veren build-zinciri mekaniklerinin hangi davranışları birebir hissettirilecek, hangileri özgün ejderha varyantları olacak?

Bunlar netleşene dek belirsizlikler mimariye gizlice gömülmeyecek; ancak belgeler üzerinde planlamayı durdurmaz.

## 13. Test, kanıt ve onay
Kod yokken yalnız doküman/bağlantı/kapsam tutarlılık kontrolü; uygulama testi `NOT RUN`; GitHub Actions `NOT RUN (budget)`. Devam eden implementasyonda değişiklik odaklı küçük testler → Issue smoke → faz sonu seçilmiş regresyon → MVP gerçek Android.

Akış: DRAFT → READY (açık kullanıcı onayı) → IN_PROGRESS (faz başlat) → REVIEW (diff, test, exact HEAD) → ACCEPTED / REVISION_REQUIRED / BLOCKED. GitHub PR merge **ayrı kullanıcı izni** gerektirir. Başka faz kendiliğinden başlamaz.

## 14. Değişiklik geçmişi
- **v0.1 — 2026-10-26:** İlk ilke, referans sınırı, örtük anlatı, belirsiz kararlar.
- **v0.2 — 2026-10-27:** 25 yanıt işlendi: hibrit ejderha, otomatik hareket/saldırı + özel yetenek, yatay 2.5D, koşu süresi ve kayıp ödülü, build/ekipman/rün, Rage, geçici/kalıcı evrim, boss, zindan/etkinlik, AI asset, Android → iOS ve demo.
- **v0.3 — 2026-10-27:** 4 takip kararı: 4 dk dalga ardından boss; ilk demoda yalnız çekirdek kart+evrim (Rage/özel yetenek/helper ertelendi); iki 2.5D yöntemi örnekle karşılaştırılacak; repo görünürlüğü/IP OPEN. DRAFT statüsü ve faz onayı değişmedi.
