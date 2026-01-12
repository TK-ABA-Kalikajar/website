# Panduan Mengelola Konten Website

Panduan ini untuk membantu Anda mengupdate konten website TK ABA Kalikajar tanpa perlu pengetahuan programming yang mendalam.

## 📝 Mengubah Teks

### 1. Halaman Beranda (`src/pages/index.astro`)

**Mengubah Judul Hero:**
Cari baris:
```html
<h1 class="text-4xl md:text-5xl lg:text-6xl font-bold mb-6">
  Selamat Datang di TK ABA Kalikajar
</h1>
```
Ubah teks di antara `<h1>` dan `</h1>`

**Mengubah Statistik:**
Cari bagian Stats Section dan ubah angka-angka:
```html
<div class="text-4xl font-bold text-green-600 mb-2">117</div>
<div class="text-gray-600">Siswa Aktif</div>
```

### 2. Halaman Tentang Kami (`src/pages/tentang.astro`)

**Mengubah Sejarah:**
Cari bagian dengan tag `<p>` di History Section dan edit teksnya.

**Mengubah Visi:**
```html
<p class="text-2xl font-bold text-green-700 italic leading-relaxed">
  "Terwujudnya Generasi Qur'ani..."
</p>
```

### 3. Halaman Profil (`src/pages/profil.astro`)

**Update Data Lembaga:**
Cari bagian dengan informasi seperti:
```html
<p class="text-lg font-semibold text-gray-800">082324445217</p>
```
Ganti dengan data terbaru.

### 4. Halaman Guru & Staff (`src/pages/guru-staff.astro`)

**Menambah Guru Baru:**
Tambahkan row baru di tabel:
```html
<tr class="hover:bg-gray-50">
  <td class="px-4 py-4 text-sm text-gray-800">10</td>
  <td class="px-4 py-4 text-sm text-gray-800">Nama Guru Baru</td>
  <td class="px-4 py-4 text-sm text-gray-800">Tempat Lahir</td>
  <!-- ... dst -->
</tr>
```

### 5. Halaman Kontak (`src/pages/kontak.astro`)

**Update Nomor Telepon:**
```html
<a href="tel:082324445217">082324445217</a>
```
Ubah kedua angka yang sama.

**Update Email:**
```html
<a href="mailto:abakalikajar@gmail.com">abakalikajar@gmail.com</a>
```

## 🖼️ Mengelola Gambar

### Menambah Foto Baru

1. Simpan foto di folder `public/images/`
2. Gunakan nama file yang deskriptif, contoh: `kegiatan-pramuka-2025.jpg`
3. Tambahkan di halaman Galeri:

```html
<img
  src="/images/kegiatan-pramuka-2025.jpg"
  alt="Kegiatan Pramuka 2025"
  class="w-full h-64 object-cover"
/>
```

### Mengganti Logo

1. Simpan logo baru di `public/images/logo.png`
2. Logo akan otomatis muncul di navigasi

### Optimasi Gambar

Untuk performa terbaik:
- Gunakan format JPEG untuk foto
- Gunakan format PNG untuk logo/grafis dengan transparansi
- Resize gambar sebelum upload (maksimal 1920px width)
- Compress gambar menggunakan tools seperti TinyPNG

## 🎨 Mengubah Warna

Warna tema dapat diubah di `tailwind.config.mjs`:

```javascript
colors: {
  primary: {
    500: '#22c55e',  // Hijau utama
    600: '#16a34a',  // Hijau gelap
    700: '#15803d',  // Hijau sangat gelap
  }
}
```

**Kode Warna yang Umum Digunakan:**
- Hijau: `green-600` → `#16a34a`
- Biru: `blue-600` → `#2563eb`
- Merah: `red-600` → `#dc2626`
- Kuning: `yellow-600` → `#ca8a04`

## 📋 Checklist Update Rutin

### Setiap Tahun Ajaran Baru:
- [ ] Update jumlah siswa di halaman Beranda
- [ ] Update data siswa per kelas di halaman Siswa
- [ ] Update tabel 5 tahun terakhir di halaman Profil
- [ ] Upload foto-foto kegiatan baru ke Galeri
- [ ] Update data guru jika ada perubahan

### Setiap Ada Event:
- [ ] Upload foto kegiatan ke folder `public/images/`
- [ ] Tambahkan ke halaman Galeri
- [ ] Update tanggal di halaman Kontak jika perlu

### Update Kontak:
- [ ] Periksa nomor telepon masih aktif
- [ ] Pastikan email berfungsi
- [ ] Update jam operasional jika berubah

## 🔧 Tips & Tricks

### Menyalin Format
Jika ingin menambah konten serupa (misal: guru baru), copy-paste section yang sudah ada dan ubah isinya.

### Preview Sebelum Publish
Selalu jalankan `npm run dev` dan buka `http://localhost:4321` untuk melihat hasil perubahan sebelum deploy.

### Backup
Sebelum melakukan perubahan besar:
```bash
git add .
git commit -m "Backup sebelum update"
git push
```

### Undo Perubahan
Jika salah ubah:
```bash
git checkout -- nama-file.astro
```

## ❓ Bantuan

Jika mengalami kesulitan:
1. Baca dokumentasi Astro: https://docs.astro.build
2. Tanya di komunitas Astro Discord
3. Hubungi developer yang membuat website ini

## 📞 Kontak Developer

Untuk bantuan teknis atau customization lebih lanjut, silakan hubungi developer website ini.

---

**Catatan Penting:**
- Selalu test perubahan di lokal sebelum deploy
- Jangan ubah struktur HTML/CSS jika tidak yakin
- Backup data penting sebelum update
- Commit changes secara regular

Happy editing! ✨
