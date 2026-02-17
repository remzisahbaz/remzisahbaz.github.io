# Remzi Şahbaz - Software Engineer Blog

Modern, minimalist blog sitesi. Spring Boot, mikroservisler, Java ve DevOps konularında deneyimlerimi paylaşıyorum.

## 🚀 Canlı Site

**GitHub Pages**: [https://remzisahbaz.github.io](https://remzisahbaz.github.io)

## ✨ Özellikler

- ✅ Modern, brutalist-minimal tasarım
- ✅ Tam responsive (mobil uyumlu)
- ✅ SEO optimize
- ✅ Hızlı yükleme
- ✅ Accessibility standartlarına uygun
- ✅ GitHub Pages ile ücretsiz hosting

## 🛠️ Teknolojiler

- **HTML5** - Semantic markup
- **CSS3** - Custom properties, Grid, Flexbox
- **Vanilla JavaScript** - Scroll animations, smooth navigation
- **Google Fonts** - JetBrains Mono, Crimson Pro
- **GitHub Pages** - Ücretsiz static site hosting

## 📁 Proje Yapısı

```
remzi-blog/
├── index.html              # Ana sayfa
├── styles.css              # Ana CSS dosyası
├── script.js               # JavaScript dosyası
├── posts/                  # Blog yazıları
│   ├── java-8-to-17-migration.html
│   ├── hexagonal-architecture-ddd.html
│   ├── jenkins-cicd-optimization.html
│   └── post-styles.css    # Post sayfaları CSS
├── README.md              # Bu dosya
└── .gitignore             # Git ignore dosyası
```

## 🎨 Tasarım Prensipleri

### Renk Paleti
- **Background**: `#0a0a0a` (Koyu siyah)
- **Surface**: `#151515` (Hafif açık siyah)
- **Text**: `#e8e8e8` (Açık gri)
- **Accent**: `#00ff88` (Neon yeşil)

### Tipografi
- **Monospace**: JetBrains Mono (kod ve body text)
- **Serif**: Crimson Pro (başlıklar ve vurgu)

### Aesthetic
Brutalist-minimal yaklaşım:
- Temiz, grid-based layout
- Bold typography
- Neon accent renkler
- Code-focused tasarım
- Minimal animasyonlar

## 🚀 Kurulum ve Kullanım

### Yerel Geliştirme

1. **Repo'yu klonlayın**:
```bash
git clone https://github.com/remzisahbaz/remzisahbaz.github.io.git
cd remzisahbaz.github.io
```

2. **Yerel sunucu başlatın** (Python 3):
```bash
python -m http.server 8000
```

3. **Tarayıcıda açın**:
```
http://localhost:8000
```

### GitHub Pages Deployment

1. **Repository ayarları**:
   - Repository adı: `remzisahbaz.github.io`
   - Settings → Pages
   - Source: `main` branch
   - Folder: `/ (root)`

2. **Push işlemi**:
```bash
git add .
git commit -m "Initial blog setup"
git push origin main
```

3. **Site 2-3 dakika içinde yayına girer**:
   - URL: `https://remzisahbaz.github.io`

## 📝 Yeni Blog Post Ekleme

1. **Post dosyası oluşturun**:
```bash
cp posts/java-8-to-17-migration.html posts/yeni-makale.html
```

2. **İçeriği düzenleyin**:
   - Başlık, meta tags
   - Post içeriği
   - Tarih ve kategori

3. **Ana sayfaya ekleyin** (`index.html`):
```html
<article class="article-card">
    <div class="article-tag">Kategori</div>
    <h3 class="card-title">
        <a href="posts/yeni-makale.html">
            Yeni Makale Başlığı
        </a>
    </h3>
    <p class="card-excerpt">
        Kısa açıklama...
    </p>
    <div class="article-meta">
        <span class="meta-item">10 dk</span>
        <span class="meta-separator">•</span>
        <span class="meta-item">17 Şubat 2026</span>
    </div>
</article>
```

## 🎯 SEO Optimizasyonu

- ✅ Semantic HTML5 tags
- ✅ Meta descriptions
- ✅ Open Graph tags
- ✅ Responsive images
- ✅ Fast loading (< 1s)
- ✅ Mobile-friendly
- ✅ Structured data (gelecekte)

## 📊 Analytics (Opsiyonel)

Google Analytics eklemek için `index.html` ve post sayfalarına ekleyin:

```html
<!-- Global site tag (gtag.js) - Google Analytics -->
<script async src="https://www.googletagmanager.com/gtag/js?id=GA_TRACKING_ID"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'GA_TRACKING_ID');
</script>
```

## 🔗 Özel Domain Bağlama

`blog.remzisahbaz.com.tr` gibi özel domain kullanmak için:

1. **CNAME dosyası oluşturun**:
```bash
echo "blog.remzisahbaz.com.tr" > CNAME
```

2. **DNS ayarları** (domain sağlayıcınızda):
```
Type: CNAME
Name: blog
Value: remzisahbaz.github.io
```

3. **GitHub Settings → Pages**:
   - Custom domain: `blog.remzisahbaz.com.tr`
   - Enforce HTTPS: ✅

## 📱 Responsive Breakpoints

```css
/* Mobile */
@media (max-width: 480px) { }

/* Tablet */
@media (max-width: 768px) { }

/* Desktop */
@media (min-width: 1024px) { }
```

## 🤝 Katkıda Bulunma

Pull request'ler kabul edilir! Büyük değişiklikler için önce issue açın.

## 📄 Lisans

MIT License - Detaylar için [LICENSE](LICENSE) dosyasına bakın.

## 📧 İletişim

- **Email**: sahbazremzii@gmail.com
- **LinkedIn**: [linkedin.com/in/remzisahbaz090](https://linkedin.com/in/remzisahbaz090)
- **GitHub**: [github.com/remzisahbaz](https://github.com/remzisahbaz)
- **Website**: [www.remzisahbaz.com.tr](https://www.remzisahbaz.com.tr)

---

**Made with ❤️ by Remzi Şahbaz** | Powered by GitHub Pages
