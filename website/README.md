# Website TK ABA Kalikajar

Website resmi TK ABA Kalikajar - Taman Kanak-Kanak 'Aisyiyah Bustanul Athfal Kalikajar, Wonosobo.

## 🚀 Tentang Proyek

Website ini dibangun menggunakan [Astro](https://astro.build), framework web modern yang mengutamakan performa dan pengalaman developer yang baik. Website ini menampilkan informasi lengkap tentang TK ABA Kalikajar, termasuk profil sekolah, visi misi, data guru dan siswa, serta galeri foto kegiatan.

## 📋 Fitur

- **Beranda**: Informasi utama dan highlight sekolah
- **Tentang Kami**: Sejarah, visi, misi, dan tujuan
- **Profil**: Data lengkap lembaga dan akreditasi
- **Guru & Staff**: Informasi tenaga pendidik
- **Siswa**: Data siswa dan rombongan belajar
- **Galeri**: Koleksi foto kegiatan sekolah
- **Kontak**: Informasi kontak dan formulir hubungi kami

## 🛠️ Teknologi

- **Astro** - Static Site Generator
- **Tailwind CSS** - Styling
- **TypeScript** - Type Safety

## 📦 Instalasi

```bash
# Install dependencies
npm install

# Run development server
npm run dev

# Build for production
npm run build

# Preview production build
npm run preview
```

## 🌐 Development

Server development akan berjalan di `http://localhost:4321`

## 📁 Struktur Proyek

```
/
├── public/
│   └── images/          # Foto dan gambar
├── src/
│   ├── layouts/
│   │   └── BaseLayout.astro
│   ├── pages/
│   │   ├── index.astro       # Beranda
│   │   ├── tentang.astro     # Tentang Kami
│   │   ├── profil.astro      # Profil
│   │   ├── guru-staff.astro  # Guru & Staff
│   │   ├── siswa.astro       # Siswa
│   │   ├── galeri.astro      # Galeri
│   │   └── kontak.astro      # Kontak
│   └── styles/
└── package.json
```

## 🎨 Customization

### Warna Tema
Warna tema utama dapat diubah di `tailwind.config.mjs`:
- Primary: Green (#16a34a)
- Secondary: Yellow (#eab308)

### Konten
Semua konten dapat diedit langsung di file `.astro` yang relevan di folder `src/pages/`

## 📝 Catatan

- Website menggunakan Bahasa Indonesia sesuai target market lokal
- Responsive design untuk mobile, tablet, dan desktop
- SEO optimized dengan metadata yang sesuai
- Performa tinggi dengan Astro static generation

## 👥 Kontak

**TK ABA Kalikajar**
- Alamat: Kalikajar RT 04 RW 08, Kalikajar, Wonosobo, Jawa Tengah 56372
- Telepon: 082324445217
- Email: abakalikajar@gmail.com

## 📄 Lisensi

© 2025 TK ABA Kalikajar. All rights reserved.
