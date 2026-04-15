---
name: ux-review
description: >-
  Review the current UI/UX of any web or mobile application page with a product
  and business-focused lens. Automatically detects the page type (landing,
  dashboard, form, auth, settings, listing, detail, editor) and applies
  type-specific evaluation criteria. Supports single-page review and full-project
  audit modes. Evaluates usability, visual design, interaction patterns,
  accessibility, and provides actionable improvements with scores. Use when the
  user asks for a UX review, UI audit, usability check, design feedback, page
  review, accessibility review, project-wide UX audit, or wants to improve their
  application's user experience. Also triggers on Turkish phrases like UX incele,
  UX değerlendir, tasarım incele, kullanılabilirlik kontrolü, erişilebilirlik
  kontrolü, sayfa inceleme, UI kontrol, arayüz değerlendirmesi, sayfayı incele,
  landing incele, dashboard incele, projeyi değerlendir, tüm sayfaları incele.
---

# UX Review

Bir uygulamanın veya sayfanın UI/UX kalitesini **ürün ve iş odaklı** değerlendir.
Teknik audit değil, bir UX danışmanı gözüyle pratik ve uygulanabilir feedback ver.
**Sayfa türüne göre** uygun kriterleri uygula.

## Yaklaşım Prensipleri

- **Önce güçlü yönleri** belirt, sonra geliştirilebilecekleri
- **Somut ve spesifik** ol: "buton rengi değişmeli" yerine "CTA butonu arka planla kontrast oluşturmuyor, gradient turuncu/mor daha dikkat çekici olur" gibi
- **Neden önemli olduğunu** açıkla: her önerinin kullanıcı davranışına veya iş metriğine etkisini belirt
- **Örnek çözümler** sun: "şöyle yapılabilir" ile birlikte alternatif metin, layout veya yaklaşım öner
- **Sayfa türüne göre değerlendir**: Landing page'e "data freshness" sorma, dashboard'a "3 saniye testi" uygulama
- Her zaman **Türkçe** yanıt ver

---

## Çalışma Modları

Bu skill iki modda çalışır:

### Mod A: Tekil Sayfa İncelemesi

Kullanıcı belirli bir dosyayı `@` ile referans verdiğinde tetiklenir.

**Örnek tetikleyiciler:**
- `@app/page.tsx UX incele`
- `@app/dashboard/page.tsx sayfayı incele`
- `@components/auth/login-form.tsx tasarım incele`

### Mod B: Proje Geneli İncelemesi

Kullanıcı tüm projeyi değerlendirmek istediğinde tetiklenir.

**Örnek tetikleyiciler:**
- "Tüm sayfaları incele"
- "Projeyi UX açısından değerlendir"
- "Tüm uygulamanın UX review'ini yap"

---

## Sayfa Türü Tespiti

Her sayfayı incelemeden önce **türünü tespit et**. Türe göre uygun checklist uygulanır.

### Sayfa Türleri ve Tespit Kuralları

| Tür | Açıklama | Tespit İpuçları |
|-----|----------|-----------------|
| **landing** | Pazarlama/tanıtım sayfaları | Ana sayfa, pricing, about, features; hero section, CTA butonları, testimonial, sosyal kanıt bileşenleri |
| **dashboard** | Veri özeti ve yönetim paneli | Chart/grafik bileşenleri, stat kartları, data table, sidebar navigasyon, metric widget'ları |
| **form** | Veri giriş sayfaları | Form elemanları (input, select, textarea), validation logic, submit handler, multi-step yapı |
| **auth** | Giriş/kayıt/şifre sayfaları | Login/register/forgot-password route, email+password input, OAuth butonları |
| **settings** | Ayar ve profil sayfaları | Toggle/switch bileşenleri, save/update butonları, tab/section grouping, preference form'ları |
| **listing** | Liste ve tablo sayfaları | DataTable/list bileşenleri, filter/sort kontrolleri, pagination, search bar, bulk action |
| **detail** | Detay görüntüleme sayfaları | Dinamik route ([id], [slug]), tek kayıt veri gösterimi, edit/delete aksiyonları, related content |
| **editor** | İçerik/veri düzenleme sayfaları | Rich text editor, code editor, drag-drop builder, toolbar, undo/redo, autosave |
| **onboarding** | İlk kullanım ve boş durum | Step indicator, welcome mesajı, setup wizard, empty state ile yönlendirme |

### Tespit Akışı

1. Dosya yoluna bak (route yapısı: `/dashboard`, `/settings`, `/login`, `/[id]` vb.)
2. Component yapısını ve import'ları incele
3. Kullanılan UI pattern'larını analiz et (form, table, chart, hero, vb.)
4. Birden fazla türe uyuyorsa **baskın olanı** seç, diğerlerini not düş

---

## Workflow

### Adım 1: Kapsamı Belirle

**Mod A (Tekil Sayfa):**
1. Referans verilen dosyayı oku
2. Import edilen alt bileşenleri tespit et ve onları da oku
3. İlgili layout dosyasını kontrol et (varsa)

**Mod B (Proje Geneli):**
1. Proje yapısını tara — `app/` veya `pages/` dizinindeki tüm sayfa dosyalarını bul
2. Her sayfayı listele ve türünü tespit et
3. Kullanıcıya bulunan sayfaları ve tespit edilen türleri tablo olarak sun, onay al
4. Onaydan sonra her sayfayı sırayla incele

### Adım 2: Sayfa Türünü Tespit Et

Her sayfa için [Sayfa Türü Tespiti](#sayfa-türü-tespiti) bölümündeki kuralları uygula.
Tespit edilen türü raporda belirt.

### Adım 3: Analiz Et

Detaylı kontrol listesi için [ux-checklist.md](ux-checklist.md) dosyasını oku.

**Her sayfa için uygulanan checklist:**
1. **Evrensel Kriterler** (tüm sayfa türlerine uygulanır) — ux-checklist.md "Evrensel Kriterler" bölümü
2. **Sayfa Türüne Özel Kriterler** — ux-checklist.md'de ilgili tür bölümü

### Adım 4: Raporu Oluştur

Aşağıdaki format ve sırayı kullan.

**Mod A için** rapor doğrudan aşağıdaki formatta üretilir.
**Mod B için** her sayfanın kendi raporu üretilir, sonunda proje geneli özet eklenir.

```markdown
## 📋 Sayfa Bilgisi

| | |
|---|---|
| **Dosya** | `[dosya yolu]` |
| **Tespit Edilen Tür** | [landing / dashboard / form / auth / settings / listing / detail / editor / onboarding] |
| **Uygulanan Checklist** | Evrensel + [Tür Adı] |

---

## Genel İzlenim

* [Sayfanın verdiği genel his, profesyonellik düzeyi]
* [Hedef kitleye ve sayfa amacına uygunluk]
* [Sayfa türüne özel ilk izlenim notu]

---

## Güçlü Yönler

### 1. [Kategori Adı]
* [Ne iyi yapılmış]
* [Neden etkili]

### 2. [Kategori Adı]
...

---

## Geliştirilebilecek Noktalar

### 1. [Sorun Başlığı]
* **Mevcut durum:** [Şu an ne var]
* **Sorun:** [Neden sorunlu, kullanıcıyı nasıl etkiliyor]
* **Öneri:** [Somut çözüm, örnek metin veya yaklaşım]

### 2. [Sorun Başlığı]
...

---

## Mobil UX Değerlendirmesi

* [Mobilde görünüm ve kullanılabilirlik]
* [Sayfa türüne özel mobil sorunlar]
* [Muhtemel riskler]

---

## Puan Tablosu

| Kategori | Puan |
|----------|------|
| Görsel Tasarım | X/10 |
| Kullanılabilirlik | X/10 |
| [Sayfa Türüne Özel Kategori 1] | X/10 |
| [Sayfa Türüne Özel Kategori 2] | X/10 |
| Mobil Uyumluluk | X/10 |
| Erişilebilirlik | X/10 |
| **Genel** | **X/10** |

> **Not:** Puan tablosundaki kategoriler sayfa türüne göre değişir.
> Landing → Mesaj Netliği, Dönüşüm Potansiyeli
> Dashboard → Bilgi Mimarisi, Görev Verimliliği
> Form → Form UX, Hata Yönetimi
> Auth → Basitlik, Güvenlik Algısı
> Settings → Keşfedilebilirlik, Organizasyon
> Listing → Arama/Filtreleme, Veri Sunumu
> Detail → İçerik Hiyerarşisi, Aksiyon Erişilebilirliği

---

## En Kritik 3 İyileştirme

1. [En önemli iyileştirme + kısa açıklama]
2. [İkinci önemli + kısa açıklama]
3. [Üçüncü önemli + kısa açıklama]

---

## Aksiyon Listesi

| # | İyileştirme | Etki | Efor |
|---|------------|------|------|
| 1 | [kısa başlık] | [Yüksek/Orta/Düşük] | [Kolay/Orta/Zor] |
| 2 | [kısa başlık] | [Yüksek/Orta/Düşük] | [Kolay/Orta/Zor] |
| ... | ... | ... | ... |
```

### Adım 4b: Proje Geneli Özet (sadece Mod B)

Tüm sayfaların bireysel raporlarından sonra aşağıdaki özeti ekle:

```markdown
---

# Proje Geneli UX Özeti

## İncelenen Sayfalar

| Sayfa | Tür | Genel Puan |
|-------|-----|------------|
| `app/page.tsx` | Landing | X/10 |
| `app/dashboard/page.tsx` | Dashboard | X/10 |
| ... | ... | ... |
| **Proje Ortalaması** | | **X/10** |

## Projede Tekrar Eden UX Sorunları

1. [Birden fazla sayfada görülen sorun + etki]
2. [Tutarsızlık örnekleri]
3. ...

## Proje Geneli Öncelikli Aksiyonlar

| # | İyileştirme | Etkilenen Sayfalar | Etki | Efor |
|---|------------|-------------------|------|------|
| 1 | [kısa başlık] | [sayfa listesi] | Yüksek | Orta |
| ... | ... | ... | ... | ... |
```

### Adım 5: Onay ve Uygulama

Raporu sunduktan sonra **AskQuestion** aracını kullanarak kullanıcıya çoklu seçim sun.
Her iyileştirme maddesi bir seçenek olarak listelenecek (allow_multiple: true).

**Mod A örneği:**
```
questions: [{
  id: "apply_fixes",
  prompt: "Hangi iyileştirmeleri uygulamamı istersiniz?",
  options: [
    { id: "1", label: "#1 - [İyileştirme başlığı] (Yüksek etki, Kolay)" },
    { id: "2", label: "#2 - [İyileştirme başlığı] (Yüksek etki, Zor)" },
    ...
  ],
  allow_multiple: true
}]
```

**Mod B örneği:**
Proje geneli aksiyonlar ile sayfa bazlı aksiyonları birleştir. Önce proje geneli (cross-cutting) aksiyonları, sonra sayfa bazlı olanları listele.

```
questions: [{
  id: "apply_fixes",
  prompt: "Hangi iyileştirmeleri uygulamamı istersiniz?",
  options: [
    { id: "global_1", label: "[Proje Geneli] #1 - Renk kontrastını düzelt (5 sayfa, Yüksek etki)" },
    { id: "landing_1", label: "[Landing] #1 - Hero başlığını somutlaştır (Yüksek etki, Kolay)" },
    { id: "dashboard_1", label: "[Dashboard] #1 - Loading state ekle (Orta etki, Kolay)" },
    ...
  ],
  allow_multiple: true
}]
```

Kullanıcı seçimlerini yaptıktan sonra:

1. Seçilen iyileştirmeleri **öncelik sırasına** göre kodda uygula
2. Her değişiklikten sonra lint kontrolü yap
3. Tüm değişiklikler bittikten sonra öncesi/sonrası karşılaştırması sun
