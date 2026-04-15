# UX Değerlendirme Kontrol Listesi

Bu checklist iki katmanlıdır:
1. **Evrensel Kriterler** — her sayfa türüne uygulanır
2. **Sayfa Türüne Özel Kriterler** — tespit edilen türe göre ilgili bölüm uygulanır

---

# Evrensel Kriterler

Aşağıdaki kriterler sayfa türünden bağımsız olarak **tüm sayfalara** uygulanır.

## Görsel Tasarım ve Tutarlılık

- [ ] Görsel hiyerarşi net mi? (en önemli eleman en çok dikkat çekiyor mu?)
- [ ] Renk paleti tutarlı ve marka ile uyumlu mu?
- [ ] Beyaz alan (white space) yeterli mi, sayfa sıkışık görünmüyor mu?
- [ ] Tipografi okunabilir mi? (font boyutu, satır yüksekliği, satır uzunluğu)
- [ ] İkonografi tutarlı mı? (aynı stil, aynı set)
- [ ] Renk kontrastı yeterli mi? (okunabilirlik açısından)
- [ ] Spacing sistemi tutarlı mı? (padding/margin değerleri arasında düzen var mı?)

## Etkileşim Tasarımı

- [ ] Tıklanabilir elemanlar açıkça ayırt edilebiliyor mu?
- [ ] Hover/focus/active durumları var mı?
- [ ] Loading durumları kullanıcıyı bilgilendiriyor mu? (skeleton, spinner, progress)
- [ ] Hata durumları yardımcı mı? (ne oldu + ne yapılmalı)
- [ ] Başarı durumları gösteriliyor mu?
- [ ] Animasyonlar/geçişler doğal ve amaca hizmet ediyor mu?
- [ ] Boş durumlar (empty state) bilgilendirici ve yönlendirici mi?

## Navigasyon

- [ ] Kullanıcı her zaman nerede olduğunu biliyor mu?
- [ ] Geri dönüş yolu açık mı?
- [ ] Öğrenme maliyeti düşük mü? (standart UX pattern'ları kullanılmış mı?)

## İçerik ve Metin Kalitesi (Microcopy)

- [ ] Buton metinleri eylem belirtiyor mu? ("Hesap Oluştur" vs "Tamam")
- [ ] Ton tutarlı mı? (samimi/resmi karışmamış)
- [ ] Gereksiz metin var mı? (kullanıcı okumayacağı paragraflar)
- [ ] Sayılar formatlanmış mı? (binlik ayracı, para birimi, tarih)

## Responsive ve Mobil Deneyim

- [ ] Mobilde (375px) layout düzgün mü, kırılma var mı?
- [ ] Dokunma hedefleri yeterli büyüklükte mü? (min 44x44px)
- [ ] Metin mobilde okunabilir mi? (min 16px)
- [ ] Yatay kaydırma oluşuyor mu?
- [ ] Navigasyon mobilde kullanılabilir mi?
- [ ] Hover-only etkileşimlerin mobil alternatifi var mı?
- [ ] Input alanlarında iOS zoom sorunu var mı? (font-size < 16px)

## Erişilebilirlik (Temel Kontroller)

- [ ] Renk kontrastı WCAG AA standardını karşılıyor mu? (4.5:1 normal metin)
- [ ] Bilgi sadece renk ile iletilmiyor, ikon/metin eşlik ediyor mu?
- [ ] Görsellerde anlamlı alt text var mı?
- [ ] Klavye ile navigasyon çalışıyor mu?
- [ ] Focus durumları görünür mü?
- [ ] Semantik HTML kullanılmış mı? (button, nav, main, h1-h6 sırası)
- [ ] Form alanlarında label ilişkilendirilmiş mi?

## Performans ve Algılanan Hız

- [ ] Sayfa hızlı yükleniyor mu? (algılanan hız)
- [ ] Skeleton/shimmer loader kullanılmış mı?
- [ ] Görseller optimize mi? (lazy load, uygun format)
- [ ] Layout shift var mı? (içerik kayması, CLS)

---
---

# Sayfa Türüne Özel Kriterler

Aşağıdaki bölümlerden **sadece tespit edilen sayfa türüne** ait olan uygulanır.

---

## Landing / Pazarlama Sayfası

> Amacı: Ziyaretçiyi bilgilendirmek, ikna etmek ve aksiyona yönlendirmek (dönüşüm).

### İlk İzlenim ve 3 Saniye Testi
- [ ] Sayfa ne yaptığını 3 saniyede anlatıyor mu?
- [ ] Hedef kitleye uygun ton ve görsellik var mı?
- [ ] Sayfanın genel "hissi" ne? (Premium, kurumsal, samimi, teknik)
- [ ] Rakiplerden farklılaşan bir görsel kimlik var mı?

### Değer Önerisi ve Mesaj Netliği
- [ ] Ana başlık (headline) net bir fayda vaat ediyor mu?
- [ ] Başlık somut mu yoksa soyut mu? ("10x başarı" vs "3 kat fazla mülakat daveti")
- [ ] Alt metin (subheadline) başlığı destekleyip detaylandırıyor mu?
- [ ] Kullanıcı "bu benim için ne yapıyor?" sorusuna hemen cevap bulabiliyor mu?
- [ ] Jargon veya teknik terimler açıklanmadan kullanılmış mı?
- [ ] Hedef kitle segmentasyonu var mı?

### CTA ve Dönüşüm Tasarımı
- [ ] Primary CTA açıkça görünür ve dikkat çekici mi?
- [ ] CTA metni net bir aksiyon ifade ediyor mu? ("Başla", "Ücretsiz Dene" vs "Gönder")
- [ ] Primary vs secondary CTA ayrımı net mi?
- [ ] CTA fold üstünde mi (scroll etmeden görünüyor mu)?
- [ ] CTA altında risk azaltıcı microcopy var mı? ("Kredi kartı gerekmez")
- [ ] CTA sayfa boyunca tekrarlanıyor mu? (uzun sayfalarda)

### Güven Sinyalleri ve Sosyal Kanıt
- [ ] Rakamlar/istatistikler var mı? ("1M+ CV analiz edildi")
- [ ] Rakamlar inandırıcı ve doğrulanabilir mi?
- [ ] Müşteri/kullanıcı yorumları (testimonial) var mı?
- [ ] Bilinen marka logoları var mı?
- [ ] Güven rozetleri var mı? (SSL, güvenlik, ödeme)
- [ ] Gerçek kişi/fotoğraf kullanılmış mı yoksa stok mu?

### Bilgi Mimarisi
- [ ] Menü sade ve anlaşılır mı? (5-7 öğe ideal)
- [ ] Sayfa bölümleri mantıksal sırada mı? (problem → çözüm → kanıt → aksiyon)
- [ ] Görseller/illüstrasyonlar amaca hizmet ediyor mu yoksa dekoratif mi?
- [ ] Ürünün kendisi gösteriliyor mu? (stok fotoğraf yerine ekran görüntüsü)

### Puanlanacak Ek Kategoriler
- Mesaj Netliği (X/10)
- Dönüşüm Potansiyeli (X/10)

---

## Dashboard / Yönetim Paneli

> Amacı: Kullanıcının verileri hızlıca kavramasını, durumu anlamasını ve aksiyona geçmesini sağlamak.

### Bilgi Mimarisi ve Hiyerarşi
- [ ] En önemli metrikler/veriler ilk bakışta görünür mü?
- [ ] Bilgi yoğunluğu dengeli mi? (ne çok seyrek ne çok yoğun)
- [ ] Kartlar/widget'lar mantıksal gruplar halinde mi?
- [ ] Veri hiyerarşisi kullanıcı önceliklerine uygun mu?
- [ ] Dashboard kişiselleştirilebilir mi? (widget sıralama, gizleme)

### Veri Sunumu
- [ ] Grafik/chart türleri veriye uygun mu? (pie chart yerine bar chart vb.)
- [ ] Sayılar bağlam içinde mi? (trend, karşılaştırma, değişim yüzdesi)
- [ ] Renk kodlaması anlamlı mı? (kırmızı=kötü, yeşil=iyi tutarlılığı)
- [ ] Veri güncelleme zamanı gösteriliyor mu? ("Son güncelleme: 5dk önce")
- [ ] Büyük sayılar okunabilir formatta mı? (1.234.567 veya 1.2M)

### Hızlı Aksiyonlar
- [ ] Sık kullanılan aksiyonlara kolay erişim var mı?
- [ ] Filtreleme/tarih aralığı kontrolleri erişilebilir mi?
- [ ] Dışa aktarma (export) seçenekleri var mı?
- [ ] Detaya gitme (drill-down) yolları açık mı?

### Durum ve Bildirimler
- [ ] Kritik durumlar vurgulanıyor mu? (uyarı, hata, dikkat gerektiren öğeler)
- [ ] Bildirim/alert sistemi yormayacak düzeyde mi?
- [ ] Boş durumlar yönlendirici mi? ("Henüz veri yok, ilk kaydını oluştur")

### Navigasyon
- [ ] Sidebar/navigasyon yapısı derinlik seviyesine uygun mu?
- [ ] Aktif menü öğesi belirgin mi?
- [ ] Sık kullanılan sayfalara kısayol var mı?

### Puanlanacak Ek Kategoriler
- Bilgi Mimarisi (X/10)
- Görev Verimliliği (X/10)

---

## Form Sayfası

> Amacı: Kullanıcıdan veriyi minimum sürtünme ile toplamak.

### Form Yapısı ve Akış
- [ ] Alanlar mantıksal sırada mı? (kişisel bilgiler → iletişim → detaylar)
- [ ] İlgili alanlar gruplanmış mı? (section/fieldset)
- [ ] Form uzunluğu makul mü? (gereksiz alan var mı?)
- [ ] Multi-step formlarda ilerleme göstergesi var mı?
- [ ] Multi-step formlarda geri dönüş mümkün mü?

### Alan Tasarımı
- [ ] Her alanda label var mı? (placeholder tek başına yeterli değil)
- [ ] Placeholder'lar örnek format içeriyor mu? ("ornek@email.com")
- [ ] Zorunlu alanlar belirtilmiş mi? (veya opsiyoneller işaretli)
- [ ] Input tipleri doğru mu? (email, tel, number, date)
- [ ] Varsayılan değerler akıllıca seçilmiş mi?
- [ ] Karakter/boyut limitleri gösteriliyor mu?

### Doğrulama ve Hata Yönetimi
- [ ] Inline validation var mı? (submit'e basmadan hata gösterme)
- [ ] Hata mesajları 3 parçalı mı? (ne oldu + neden + ne yapılmalı)
- [ ] Hata mesajları ilgili alanın yanında mı? (sayfa üstü genel hata değil)
- [ ] Başarılı validasyon görsel feedback veriyor mu? (yeşil tick)
- [ ] Form submit edildiğinde hatalar scroll ile görünür yapılıyor mu?

### Submit ve Sonrası
- [ ] Submit butonu duruma göre değişiyor mu? (disabled, loading, success)
- [ ] Çift tıklama/çoklu submit koruması var mı?
- [ ] Başarı durumu net mi? (ne oldu, sırada ne var)
- [ ] Form verileri beklenmedik çıkışta korunuyor mu? (draft/autosave)

### Puanlanacak Ek Kategoriler
- Form UX (X/10)
- Hata Yönetimi (X/10)

---

## Auth (Giriş/Kayıt) Sayfası

> Amacı: Kullanıcının minimum sürtünme ile hesap oluşturmasını veya giriş yapmasını sağlamak.

### Basitlik ve Hız
- [ ] Form minimum alan içeriyor mu? (kayıtta gereksiz bilgi istenmiyor mu?)
- [ ] Sosyal giriş seçenekleri var mı? (Google, GitHub, vb.)
- [ ] Login ve register arasında geçiş kolay mı?
- [ ] Akış kaç adımda tamamlanıyor? (ne kadar az o kadar iyi)

### Şifre UX
- [ ] Şifre gereksinimleri önceden gösteriliyor mu? (8 karakter, büyük harf, vb.)
- [ ] Şifre göster/gizle toggle'ı var mı?
- [ ] Şifre gücü göstergesi var mı?
- [ ] "Şifremi unuttum" linki erişilebilir mi?

### Hata ve Güvenlik
- [ ] Hata mesajları güvenlik açısından uygun mu? ("E-posta veya şifre yanlış" vs "Bu e-posta kayıtlı değil")
- [ ] Rate limiting/brute force koruması var mı?
- [ ] "Beni hatırla" seçeneği var mı?
- [ ] Başarılı girişten sonra yönlendirme doğru mu?

### Güven
- [ ] Sayfa güvenilir görünüyor mu? (marka, SSL, profesyonel tasarım)
- [ ] Gizlilik politikası ve kullanım koşulları linkleri var mı?
- [ ] Kayıt formunda "ne alacağım" bilgisi var mı?

### Puanlanacak Ek Kategoriler
- Basitlik (X/10)
- Güvenlik Algısı (X/10)

---

## Settings / Ayarlar Sayfası

> Amacı: Kullanıcının tercihlerini kolayca bulup değiştirmesini sağlamak.

### Organizasyon ve Keşfedilebilirlik
- [ ] Ayarlar mantıksal kategorilere ayrılmış mı?
- [ ] Kategori isimleri açık ve anlaşılır mı?
- [ ] Arama/filtreleme var mı? (çok sayıda ayar varsa)
- [ ] En sık kullanılan ayarlar kolay erişilebilir mi?
- [ ] Ayar açıklamaları yeterli mi? (her ayarın ne yaptığı anlaşılıyor mu?)

### Kaydetme ve Geri Alma
- [ ] Kaydetme mekanizması açık mı? (otomatik vs manuel)
- [ ] Değişiklik yapıldığında "kaydedilmemiş değişiklik" uyarısı var mı?
- [ ] "Varsayılana sıfırla" seçeneği var mı?
- [ ] Kaydetme sonrası onay/feedback gösteriliyor mu?

### Tehlikeli Aksiyonlar
- [ ] Hesap silme, veri temizleme gibi aksiyonlar belirgin uyarı ile mi?
- [ ] Geri dönüşü olmayan aksiyonlarda onay adımı var mı?
- [ ] Tehlikeli aksiyonlar görsel olarak ayrışıyor mu? (kırmızı zona, ayrı section)

### Değişiklik Etkisi
- [ ] Bir ayarı değiştirmenin etkisi anlaşılıyor mu?
- [ ] Bağımlı ayarlar gruplanmış mı?
- [ ] Plan/abonelik ile kısıtlı ayarlar belirtilmiş mi?

### Puanlanacak Ek Kategoriler
- Keşfedilebilirlik (X/10)
- Organizasyon (X/10)

---

## Listing / Liste ve Tablo Sayfası

> Amacı: Kullanıcının veri setinde hızlıca aradığını bulması, filtrelemesi ve aksiyon alması.

### Arama ve Filtreleme
- [ ] Arama çubuğu belirgin ve erişilebilir mi?
- [ ] Filtreler kullanışlı ve arayüzü boğmuyor mu?
- [ ] Aktif filtreler görünür mü? (chip, tag olarak)
- [ ] Filtreleri temizleme kolay mı? ("Tümünü temizle")
- [ ] Sıralama seçenekleri var mı ve mevcut sıralama belli mi?

### Veri Sunumu
- [ ] Tablo/liste yoğunluğu okunabilir mi?
- [ ] Önemli sütunlar/bilgiler öncelikli mi?
- [ ] Satır/kart üzerindeki aksiyonlar erişilebilir mi?
- [ ] Sayfalama veya infinite scroll var mı?
- [ ] Toplam sonuç sayısı gösteriliyor mu?
- [ ] Sütun genişlikleri içeriğe uygun mu?

### Toplu İşlemler
- [ ] Çoklu seçim var mı? (multi-select, select all)
- [ ] Toplu aksiyon seçenekleri var mı? (sil, taşı, dışa aktar)
- [ ] Seçili öğe sayısı gösteriliyor mu?

### Boş ve Yükleme Durumları
- [ ] Sonuç bulunamadığında yönlendirici mesaj var mı?
- [ ] İlk kez boş listede onboarding/yönlendirme var mı?
- [ ] Yükleme sırasında skeleton/placeholder gösteriliyor mu?

### Puanlanacak Ek Kategoriler
- Arama/Filtreleme (X/10)
- Veri Sunumu (X/10)

---

## Detail / Detay Sayfası

> Amacı: Tek bir kaydın/içeriğin tüm bilgisini anlaşılır şekilde sunmak ve ilgili aksiyonlara erişim sağlamak.

### İçerik Hiyerarşisi
- [ ] En önemli bilgi en üstte/belirgin mi?
- [ ] Bilgi bölümleri mantıksal gruplar halinde mi?
- [ ] Uzun içerikte tab/accordion gibi organizasyon var mı?
- [ ] Meta bilgiler (tarih, yazar, durum) uygun yerde mi?

### Aksiyon Erişilebilirliği
- [ ] Primary aksiyonlar (düzenle, sil, paylaş) kolay erişilebilir mi?
- [ ] Aksiyonlar bağlama uygun mu? (draft → yayınla, aktif → durdur)
- [ ] Silme gibi tehlikeli aksiyonlarda onay var mı?
- [ ] Geri dönüş (back) navigasyonu açık mı?

### İlişkili İçerik
- [ ] İlgili/benzer öğeler gösteriliyor mu?
- [ ] Bağlantılı veriler arasında geçiş kolay mı?
- [ ] Breadcrumb var mı? (derin yapılarda)

### Medya ve Görseller
- [ ] Görseller büyütülebilir/galeri görünümü var mı?
- [ ] Video/medya player kontrolleri kullanılabilir mi?
- [ ] Dosya ekleri indirilebilir mi?

### Puanlanacak Ek Kategoriler
- İçerik Hiyerarşisi (X/10)
- Aksiyon Erişilebilirliği (X/10)

---

## Editor / Düzenleme Sayfası

> Amacı: Kullanıcının içerik veya veri üretme/düzenleme sürecini verimli kılmak.

### Düzenleme Deneyimi
- [ ] Araç çubuğu (toolbar) amaca uygun ve sade mi?
- [ ] Undo/redo çalışıyor mu?
- [ ] Klavye kısayolları var mı ve keşfedilebilir mi?
- [ ] Otomatik kaydetme (autosave) var mı?
- [ ] Son kaydedilme zamanı gösteriliyor mu?

### Önizleme ve Çıktı
- [ ] Düzenleme ile sonuç arasında preview var mı?
- [ ] WYSIWYG ise render doğru mu?
- [ ] Çıktı formatı/boyutu hakkında bilgi var mı?

### Veri Güvenliği
- [ ] Kaydedilmemiş değişikliklerde sayfa terk uyarısı var mı?
- [ ] Taslak (draft) mekanizması var mı?
- [ ] Versiyon geçmişi/geri alma var mı?

### Puanlanacak Ek Kategoriler
- Düzenleme Verimliliği (X/10)
- Veri Güvenliği (X/10)

---

## Onboarding / İlk Kullanım Sayfası

> Amacı: Yeni kullanıcıyı ürüne alıştırmak, ilk değeri hızlıca deneyimletmek (time-to-value).

### İlk Değer Deneyimi
- [ ] Kullanıcı kaç adımda ilk değeri deneyimliyor? (ne kadar az o kadar iyi)
- [ ] "Aha moment" ne ve oraya yönlendirme var mı?
- [ ] Adımlar atlanabilir mi? (skip seçeneği)
- [ ] İlerleme göstergesi var mı?

### Yönlendirme Kalitesi
- [ ] Her adımda ne yapılacağı açık mı?
- [ ] Kullanıcı bilgi seviyesine göre yol ayrılıyor mu? (beginner/advanced)
- [ ] Örnek veri/şablon sunuluyor mu? (boş başlangıç yerine)
- [ ] Tamamlanma kutlaması/motivasyonu var mı?

### Esneklik
- [ ] Onboarding sonra tekrar erişilebilir mi?
- [ ] Yardım/destek erişimi kolay mı?
- [ ] Kullanıcı profili/tercihi doğru şekillendiriliyor mu?

### Puanlanacak Ek Kategoriler
- İlk Değer Hızı (X/10)
- Yönlendirme Kalitesi (X/10)
