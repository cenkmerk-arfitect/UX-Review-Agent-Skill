# UX Review Agent Skill

## Proje Özeti

Tasarım süreçlerinde **otomatik UX geri bildirimi** sağlayan bir AI agent skill'i. Cursor IDE içinde çalışır; sayfanın türünü otomatik tespit eder, türe uygun kriterleri uygular ve kullanıcının onayladığı iyileştirmeleri doğrudan koda uygular.

### Motivasyon

Tasarım ve geliştirme aşamasında UX kalitesini erken yakalamak, ürünün dönüşüm oranını ve kullanıcı memnuniyetini doğrudan etkiler. Manuel UX review süreci zaman alıcı ve uzman bağımlıdır. Bu skill, bir UX danışmanının bakış açısını AI agent'a kazandırarak:

- Geliştirici iş akışını bozmadan anlık UX feedback sağlar
- Tekrarlanabilir ve tutarlı bir değerlendirme standardı oluşturur
- Onaylanan değişiklikleri otomatik uygulayarak cycle time'ı düşürür

## Nasıl Çalışır

### İki Çalışma Modu

| Mod              | Tetikleyici                       | Ne Yapar                                            |
| ---------------- | --------------------------------- | --------------------------------------------------- |
| **Tekil Sayfa**  | Dosyayı `@` ile referans ver      | Tek sayfayı türüne göre inceler                     |
| **Proje Geneli** | "Tüm sayfaları incele" gibi ifade | Tüm sayfaları bulur, sınıflandırır, sırayla inceler |

### Sayfa Türü Tespiti

Skill, her sayfayı incelemeden önce türünü otomatik tespit eder ve türe uygun checklist uygular:

| Tür            | Örnek                          | Özel Değerlendirme Odağı                              |
| -------------- | ------------------------------ | ----------------------------------------------------- |
| **Landing**    | Ana sayfa, pricing, features   | Değer önerisi, CTA, 3 saniye testi, güven sinyalleri  |
| **Dashboard**  | Admin panel, analytics         | Bilgi hiyerarşisi, veri sunumu, hızlı aksiyonlar      |
| **Form**       | Kayıt, veri giriş              | Form yapısı, doğrulama, hata yönetimi                 |
| **Auth**       | Login, register, şifre sıfırla | Basitlik, şifre UX, güvenlik algısı                   |
| **Settings**   | Kullanıcı ayarları, profil     | Organizasyon, keşfedilebilirlik, tehlikeli aksiyonlar |
| **Listing**    | Veri tablosu, arama sonuçları  | Arama/filtreleme, toplu işlem, boş durumlar           |
| **Detail**     | Ürün detay, kayıt görüntüleme  | İçerik hiyerarşisi, aksiyonlar, ilişkili içerik       |
| **Editor**     | İçerik düzenleyici, builder    | Toolbar, autosave, undo/redo, preview                 |
| **Onboarding** | İlk kullanım, setup wizard     | İlk değer hızı, yönlendirme kalitesi                  |

### Checklist Sistemi (2 Katmanlı)

Her değerlendirmede iki katman uygulanır:

1. **Evrensel Kriterler** — Tüm sayfa türlerine uygulanır (görsel tasarım, etkileşim, navigasyon, responsive, erişilebilirlik, performans)
2. **Türe Özel Kriterler** — Tespit edilen sayfa türüne göre ilgili bölüm uygulanır

### Tetikleme Örnekleri

**Tekil Sayfa (Mod A):**

- `@app/page.tsx UX incele`
- `@app/dashboard/page.tsx sayfayı incele`
- `@components/auth/login-form.tsx tasarım incele`
- `@app/settings/page.tsx UI kontrol`

**Proje Geneli (Mod B):**

- "Tüm sayfaları incele"
- "Projeyi UX açısından değerlendir"
- "Tüm uygulamanın UX review'ini yap"

### İş Akışı

```
Kapsamı Belirle → Sayfa Türü Tespit Et → Analiz Et → Rapor → Onay & Uygulama
```

1. **Kapsamı Belirle:** Tekil sayfa mı proje geneli mi belirle
2. **Sayfa Türü Tespit Et:** Route yapısı, component yapısı ve UI pattern'larından türü belirle
3. **Analiz Et:** Evrensel + türe özel checklist uygula
4. **Rapor Oluştur:** Güçlü yönler, geliştirilebilecekler, türe göre puan tablosu, aksiyon listesi
5. **Onay & Uygulama:** Kullanıcı iyileştirmeleri seçer, agent kodda uygular

### Farklılaştırıcı Özellikler

| Özellik                  | Açıklama                                                                         |
| ------------------------ | -------------------------------------------------------------------------------- |
| **Sayfa türü tespiti**   | Landing, dashboard, form, auth — her tür kendi kriterlerine göre değerlendirilir |
| **2 katmanlı checklist** | Evrensel + türe özel kriterler birlikte uygulanır                                |
| **Proje geneli audit**   | Tek komutla tüm sayfalar sınıflandırılıp incelenir                               |
| **Ürün/iş odaklı bakış** | Teknik audit değil, dönüşüm ve kullanıcı davranışı odaklı                        |
| **Somut öneriler**       | "Buton kötü" yerine "CTA kontrast oluşturmuyor, şu yaklaşım daha iyi"            |
| **Onay mekanizması**     | Hiçbir değişiklik kullanıcı onayı olmadan uygulanmaz                             |
| **Otomatik uygulama**    | Onaylanan iyileştirmeler doğrudan koda uygulanır                                 |

## Dosya Yapısı

```
.cursor/skills/ux-review/
├── SKILL.md            # Agent skill tanımı (modlar, türler, workflow, rapor formatı)
├── ux-checklist.md     # 2 katmanlı checklist (evrensel + 9 sayfa türü)
└── README.md           # Bu döküman
```

## Kullanım Ortamları

Bu skill Cursor IDE'nin Agent Skill altyapısı üzerinde çalışır. Aynı zamanda içerik, sistem promptu olarak diğer AI agent host yapılarına da (ChatGPT custom instructions, Claude projects, vb.) uyarlanabilir. Temel bileşenler:

- **SKILL.md:** Agent'ın davranışını, iş akışını ve çıktı formatını tanımlar. Başka bir platforma taşınırken sistem promptu olarak kullanılabilir.
- **ux-checklist.md:** Platform bağımsız kontrol listesi. Herhangi bir LLM'e referans doküman olarak verilebilir.

## Örnek Çıktı Yapısı

Agent çalıştırıldığında aşağıdaki bölümleri içeren bir rapor üretir:

1. **Sayfa Bilgisi** — Dosya yolu, tespit edilen tür, uygulanan checklist
2. **Genel İzlenim** — Sayfa türüne uygun ilk izlenim
3. **Güçlü Yönler** — Kategorize edilmiş olumlu tespitler
4. **Geliştirilebilecek Noktalar** — Mevcut durum, sorun ve somut öneri üçlüsü
5. **Mobil UX Değerlendirmesi** — Mobil spesifik sorunlar ve riskler
6. **Puan Tablosu** — Türe göre değişen kategorilerde 10 üzerinden puanlama
7. **En Kritik 3 İyileştirme** — Önceliklendirilmiş aksiyonlar
8. **Aksiyon Listesi** — Etki/efor matrisi ile seçilebilir iyileştirmeler
9. **Proje Geneli Özet** (sadece Mod B) — Cross-cutting sorunlar ve proje ortalaması
