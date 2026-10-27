# Yerel test ve maliyet politikası

**GitHub Actions / hosted CI kullanılmaz.** Otomatik iş akışı oluşturma, çalıştırma veya ücretli doğrulama servislerine erişme. CI gerekmiyorsa durumu açıkça `NOT RUN (budget policy)` kaydet.

## Dört katmanlı test

1. **Değişiklik sırasında:** En dar anlamlı statik kontrol / lint / ilgili birim testi. Her commit'te tam süit yok.
2. **Issue tamamlanırken:** Değişen mekaniğe ait hedefli entegrasyon ve sahne smoke, ilgili komşu davranış kontrolleri.
3. **Faz sonunda:** İlgili alt sistem regresyonu, açılış ve temel oyun döngüsü manuel/otomatik smoke, mümkün olduğunda kısa oynanış videosu veya kanıtı.
4. **MVP/yayın eşiğinde:** Daha geniş regresyon + fiziksel Android cihaz üzerinde performans, etkileşim, kayıt ve çökme testleri.

Kod değişmemiş, aynı HEAD/ortam/etki alanı değişmemişse geçerli test kanıtını sebep olmadan tekrar üretme. Risk yükselince kapsamı artır: kaydet/yükle, scene başlangıcı, build/export, veri formatı veya kontrol akışı değişiklikleri.

Her teslim raporu:
- Issue / PR / **exact HEAD**
- Test komutu ve ortamı
- PASS / FAIL / NOT RUN / BLOCKED ayrımı
- Neden bu testler yeterli; kalan doğrulama açıkları
- Gerçek cihaz testi çalışmadıysa **NOT RUN**

Oyun hissi, hedef görünürlüğü, animasyon kalitesi ve yükseltme seçimlerinin tatmin ediciliği salt otomatik testle doğrulanamaz; kısa insan oynanışı gerekir.
