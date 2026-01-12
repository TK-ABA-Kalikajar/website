# Panduan Deployment Website TK ABA Kalikajar

## 🚀 Opsi Deployment

Website Astro dapat di-deploy ke berbagai platform hosting. Berikut adalah beberapa opsi yang direkomendasikan:

### 1. Vercel (Recommended)

**Kelebihan:**
- Gratis untuk personal/small projects
- Setup otomatis untuk Astro
- CDN global
- HTTPS otomatis

**Cara Deploy:**

1. Push code ke GitHub repository
2. Kunjungi [vercel.com](https://vercel.com)
3. Sign in dengan GitHub
4. Click "New Project"
5. Import repository website
6. Vercel akan auto-detect Astro
7. Click "Deploy"

**Build Settings (Auto-detected):**
```
Build Command: npm run build
Output Directory: dist
Install Command: npm install
```

### 2. Netlify

**Cara Deploy:**

1. Push code ke GitHub
2. Kunjungi [netlify.com](https://netlify.com)
3. Click "Add new site" → "Import an existing project"
4. Connect GitHub repository
5. Configure build settings:
   - Build command: `npm run build`
   - Publish directory: `dist`
6. Click "Deploy site"

### 3. GitHub Pages

**Cara Deploy:**

1. Install GitHub Pages adapter:
```bash
npm install @astrojs/github-pages
```

2. Update `astro.config.mjs`:
```javascript
import { defineConfig } from 'astro/config';
import tailwind from '@astrojs/tailwind';

export default defineConfig({
  integrations: [tailwind()],
  site: 'https://username.github.io',
  base: '/repository-name',
});
```

3. Create `.github/workflows/deploy.yml`:
```yaml
name: Deploy to GitHub Pages

on:
  push:
    branches: [ main ]

permissions:
  contents: read
  pages: write
  id-token: write

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout
        uses: actions/checkout@v3
      - name: Setup Node
        uses: actions/setup-node@v3
        with:
          node-version: '18'
      - name: Install dependencies
        run: npm install
      - name: Build
        run: npm run build
      - name: Upload artifact
        uses: actions/upload-pages-artifact@v1
        with:
          path: ./dist

  deploy:
    environment:
      name: github-pages
      url: ${{ steps.deployment.outputs.page_url }}
    runs-on: ubuntu-latest
    needs: build
    steps:
      - name: Deploy to GitHub Pages
        id: deployment
        uses: actions/deploy-pages@v1
```

4. Push ke GitHub
5. Enable GitHub Pages di repository settings

### 4. Cloudflare Pages

**Cara Deploy:**

1. Push code ke GitHub
2. Kunjungi [pages.cloudflare.com](https://pages.cloudflare.com)
3. Click "Create a project"
4. Connect GitHub repository
5. Configure:
   - Build command: `npm run build`
   - Build output directory: `dist`
6. Click "Save and Deploy"

## 📋 Checklist Sebelum Deploy

- [ ] Test website secara lokal (`npm run build && npm run preview`)
- [ ] Pastikan semua images ada dan ter-load
- [ ] Test responsive design di berbagai device
- [ ] Validasi semua form berfungsi
- [ ] Cek SEO metadata di setiap halaman
- [ ] Update site URL di `astro.config.mjs` sesuai domain production
- [ ] Test semua link navigasi
- [ ] Optimize images jika diperlukan

## 🔧 Custom Domain

Setelah deploy, untuk menggunakan custom domain (misal: tkabakalikajar.com):

### Vercel:
1. Buka project settings di Vercel
2. Go to "Domains"
3. Add custom domain
4. Update DNS records sesuai instruksi Vercel

### Netlify:
1. Buka site settings
2. Go to "Domain management"
3. Add custom domain
4. Update DNS records

**DNS Records yang diperlukan:**
```
Type: A
Name: @
Value: [IP dari hosting provider]

Type: CNAME
Name: www
Value: [domain dari hosting provider]
```

## 🔄 Update Website

Untuk update konten atau fitur:

1. Edit file yang diperlukan di `src/pages/`
2. Test lokal dengan `npm run dev`
3. Commit dan push ke GitHub
4. Platform hosting akan auto-deploy

## 📊 Analytics (Optional)

Untuk menambahkan Google Analytics:

1. Buat Google Analytics account
2. Dapatkan tracking ID
3. Tambahkan ke `BaseLayout.astro` di `<head>`:

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

## 🐛 Troubleshooting

### Build Failed
- Check Node.js version (requires 18+)
- Clear cache: `rm -rf node_modules && npm install`
- Check for syntax errors in `.astro` files

### Images Not Loading
- Verify images are in `public/images/` folder
- Check image paths start with `/images/`
- Ensure filenames match exactly (case-sensitive)

### Styling Issues
- Clear build cache: `rm -rf dist .astro`
- Rebuild: `npm run build`
- Check Tailwind config

## 📞 Support

Jika mengalami masalah deployment, silakan hubungi:
- Email: abakalikajar@gmail.com
- Dokumentasi Astro: https://docs.astro.build

---

Good luck with your deployment! 🚀
