# 🚀 GitHub Pages Deployment Rehberi

Blog sitenizi **5 dakikada** ücretsiz olarak yayınlayın!

## 📋 Ön Koşullar

- ✅ GitHub hesabınız olmalı
- ✅ Git yüklü olmalı
- ✅ Blog dosyaları hazır

## 🎯 Adım Adım Kurulum

### 1. GitHub Repository Oluşturma

#### Option A: Kişisel Site (Önerilen)
Repository adı: `remzisahbaz.github.io`
- URL: `https://remzisahbaz.github.io`
- Otomatik aktif edilir

#### Option B: Project Site
Repository adı: `blog` (veya istediğiniz isim)
- URL: `https://remzisahbaz.github.io/blog`
- Manuel aktifleştirme gerekir

**İlk seçeneği öneriyorum!**

### 2. Repository Oluşturma (GitHub'da)

```bash
# GitHub'da:
1. github.com/new
2. Repository name: remzisahbaz.github.io
3. Public ✅
4. Create repository
```

### 3. Blog Dosyalarını Yükleme

```bash
# Terminal'de blog klasörüne gidin
cd /path/to/remzi-blog

# Git init
git init
git add .
git commit -m "Initial commit: Blog sitesi oluşturuldu"

# GitHub'a bağlan
git remote add origin https://github.com/remzisahbaz/remzisahbaz.github.io.git

# Push
git branch -M main
git push -u origin main
```

### 4. GitHub Pages Aktivasyonu

**Kişisel site için** (`remzisahbaz.github.io`):
- ✅ Otomatik aktif olur
- 2-3 dakika bekleyin
- `https://remzisahbaz.github.io` adresine gidin

**Project site için**:
1. Repository → Settings
2. Sol menüden "Pages"
3. Source: `main` branch
4. Folder: `/ (root)`
5. Save

### 5. Doğrulama

```bash
# 2-3 dakika sonra tarayıcıda açın:
https://remzisahbaz.github.io
```

## 🎨 Özel Domain Bağlama (Opsiyonel)

### blog.remzisahbaz.com.tr için:

#### 1. CNAME Dosyası Oluştur

```bash
# Blog klasöründe:
echo "blog.remzisahbaz.com.tr" > CNAME

# Git'e ekle
git add CNAME
git commit -m "Add custom domain"
git push
```

#### 2. DNS Ayarları

Domain sağlayıcınızda (örn: GoDaddy, Namecheap):

```
Type: CNAME
Name: blog
Value: remzisahbaz.github.io.
TTL: 1 Hour
```

#### 3. GitHub Settings

1. Settings → Pages
2. Custom domain: `blog.remzisahbaz.com.tr`
3. Save
4. Enforce HTTPS ✅ (24 saat sonra)

## 🔄 Güncelleme Workflow'u

### Yeni Blog Post Ekleme

```bash
# 1. Dosyaları düzenle
nano posts/yeni-makale.html
nano index.html  # Yeni post'u ekle

# 2. Git commit
git add .
git commit -m "Yeni blog post: Başlık"
git push

# 3. Site otomatik güncellenir (1-2 dakika)
```

### Hızlı Güncelleme Script'i

`.git-push.sh` oluşturun:
```bash
#!/bin/bash
git add .
git commit -m "$1"
git push
echo "✅ Site güncelleniyor... 1-2 dakika bekleyin"
```

Kullanım:
```bash
chmod +x .git-push.sh
./.git-push.sh "Yeni post eklendi"
```

## 🛠️ Troubleshooting

### Site açılmıyor (404 hatası):
```bash
# 1. Doğru repo adı mı?
remzisahbaz.github.io ✅
remzi-blog ❌ (bu project site olur)

# 2. index.html ana dizinde mi?
remzi-blog/
└── index.html ✅

remzi-blog/
└── src/
    └── index.html ❌
```

### CSS yüklenmiyor:
```html
<!-- ❌ Yanlış -->
<link rel="stylesheet" href="/styles.css">

<!-- ✅ Doğru (kişisel site için) -->
<link rel="stylesheet" href="styles.css">

<!-- ✅ Doğru (project site için) -->
<link rel="stylesheet" href="/blog/styles.css">
```

### Custom domain çalışmıyor:
1. DNS propagation: 24-48 saat bekleyin
2. CNAME dosyası main branch'te mi?
3. DNS ayarları doğru mu? (`dig blog.remzisahbaz.com.tr`)

### HTTPS hatası:
- Custom domain ekledikten sonra 24 saat bekleyin
- GitHub otomatik SSL sertifikası oluşturur

## 📊 Google Analytics Ekleme

### 1. Google Analytics Hesabı Oluştur
- analytics.google.com
- "Özellik Oluştur"
- Tracking ID'nizi alın: `G-XXXXXXXXXX`

### 2. Tracking Code Ekle

`index.html` ve tüm post sayfalarına `</head>` etiketinden önce:

```html
<!-- Google Analytics -->
<script async src="https://www.googletagmanager.com/gtag/js?id=G-XXXXXXXXXX"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'G-XXXXXXXXXX');
</script>
```

### 3. Push ve Test

```bash
git add .
git commit -m "Add Google Analytics"
git push
```

24 saat sonra Google Analytics'te veriler görünmeye başlar.

## 🎯 Performance Optimizasyonu

### 1. Image Optimization
```bash
# ImageMagick ile resize
convert image.jpg -resize 1200x -quality 85 image-optimized.jpg
```

### 2. Minify CSS (Opsiyonel)
```bash
# Online tool: cssminifier.com
# veya
npm install -g clean-css-cli
cleancss -o styles.min.css styles.css
```

### 3. CDN için Font Preconnect
```html
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
```

## 📱 Mobil Test

### Chrome DevTools:
1. F12
2. Toggle device toolbar (Ctrl+Shift+M)
3. Test different devices

### Online Tools:
- Google PageSpeed Insights
- GTmetrix
- WebPageTest

## 🔒 Güvenlik

GitHub Pages otomatik olarak:
- ✅ HTTPS sağlar (custom domain için 24 saat sonra)
- ✅ DDoS koruması var
- ✅ CDN hızlandırma var

## 💡 İpuçları

### Deployment Speed:
- İlk deployment: 2-3 dakika
- Güncellemeler: 30-60 saniye

### Build Limits:
- ✅ 1GB repository boyutu
- ✅ Aylık 100GB bandwidth
- ✅ 10 build/saat

### Best Practices:
1. Her commit için anlamlı mesajlar
2. Büyük dosyalar (>50MB) eklemeyin
3. `.gitignore` kullanın
4. Branch'ler ile çalışın (staging vs)

## 🎓 İleri Seviye

### GitHub Actions ile Auto-deployment

`.github/workflows/deploy.yml`:
```yaml
name: Deploy Blog
on:
  push:
    branches: [ main ]
jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      - name: Deploy to GitHub Pages
        run: echo "Auto-deployed ✅"
```

### Branch Strategy:
```bash
# Development branch
git checkout -b dev
# ... değişiklikler

# Test
python -m http.server 8000

# Merge to main (production)
git checkout main
git merge dev
git push
```

## 📚 Kaynaklar

- [GitHub Pages Docs](https://docs.github.com/en/pages)
- [Custom Domain Setup](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site)
- [Jekyll Alternative](https://jekyllrb.com/) (Static site generator)

## ✅ Checklist

Deployment öncesi kontrol edin:

- [ ] Repository adı doğru (`username.github.io`)
- [ ] `index.html` ana dizinde
- [ ] Tüm linkler relative path
- [ ] Images optimize edilmiş
- [ ] Meta tags dolu
- [ ] Responsive test yapıldı
- [ ] CNAME dosyası var (custom domain için)
- [ ] .gitignore dosyası var

## 🎉 Tebrikler!

Blog siteniz artık canlı! 🚀

**URL**: https://remzisahbaz.github.io

---

**Sorular?**
- GitHub Issues: github.com/remzisahbaz/remzisahbaz.github.io/issues
- Email: sahbazremzii@gmail.com
