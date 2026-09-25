# Web Portofolio & Landing Page - Kelompok 1

Landing page portofolio tim pengembang web (Single Page) yang dibuat menggunakan HTML5 Semantik dan Tailwind CSS CLI.

## Anggota Pengembang
- **Lutfi** (NIM: 2604140069) - Frontend Lead
- **Dimas** (NIM: 2605090004) - Content & UI Specialist

---

## Palet Warna & Desain (50 - 30 - 20)
- **50% Background Utama:** `#FCF9EA` (Cream hangat)
- **30% Struktur & Teks:** `#1C1E1F` (Charcoal black)
- **20% Aksen & Tombol:** `#134E4A` (Deep Forest Teal)

---

## Struktur Halaman
1. **Navbar:** Navigasi sticky dengan tautan ke Tentang Anggota, Layanan Kami, dan tombol Kontak.
2. **Hero Section:** Sapaan pembuka, proposisi nilai, CTA, dan foto visual meja kerja developer.
3. **Section 1 (Tentang Anggota):** Profil Lutfi dan Dimas lengkap dengan peran, foto profil, dan keahlian utama.
4. **Section 2 (Layanan Kami):** 3 kartu penawaran layanan (Landing Page Bisnis, Desain Tailwind, Perapihan Web).
5. **Footer:** Kontak langsung, hak cipta 2026, dan 3 tautan media sosial.

---

## Cara Menjalankan Tailwind CLI

### 1. Prasyarat
Pastikan Node.js dan npm sudah terpasang di komputer.

### 2. Jalankan Mode Watch (Pengembangan)
Jalankan perintah ini di terminal agar setiap perubahan class Tailwind langsung di-compile otomatis:
```bash
npm run watch
```
atau:
```bash
npx tailwindcss -i ./src/input.css -o ./style.css --watch
```

### 3. Build CSS untuk Produksi
Untuk meng-generate file `style.css` yang sudah terkompresi/minified:
```bash
npm run build
```

---

## Catatan Pengerjaan & AI yang Digunakan
- **AI Tool:** Claude Code (Anthropic) / Gemini via CLI
- **Bebas AI Slop & Bebas Lorem Ipsum:** Seluruh teks ditulis dalam bahasa Indonesia yang konkret, padat, dan langsung pada intinya. Semua tag `img` dilengkapi atribut `alt` dan komentar sumber Unsplash.
