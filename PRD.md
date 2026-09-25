# Panduan & Rencana Proyek: Web Portofolio (Pemula Friendly)

Dokumen ini dibuat khusus agar **Lutfi** dan **Dimas** bisa mengerjakan tugas Week 1 dengan mudah, tidak pusing, dan tidak berlebihan (*anti-overengineering*). 

Kalian juga disediakan **Template Prompt AI Siap Pakai** yang bisa langsung kalian *copy-paste* ke AI jika butuh bantuan ngoding!

---

## 1. Target Website Kita
Kita akan membuat **1 halaman (Single Page)** website Portofolio Developer. Pengunjung bisa klik menu di atas, lalu halaman otomatis geser (*smooth scroll*) ke bagian yang dituju.

Susunan halamannya berurutan dari atas ke bawah:
1. **Navbar** (Menu navigasi di paling atas)
2. **Hero Section** (Bagian pembuka: foto profil, sapaan, dan tombol aksi)
3. **Section 1: Tentang & Keahlian** (Cerita singkat dan daftar keahlian/tools)
4. **Section 2: Proyek / Karya** (3 kartu showcase hasil karya/proyek)
5. **Footer** (Bagian paling bawah: kontak dan media sosial)

---

## 2. Aturan Wajib Penugasan
1. **Dilarang pakai "Lorem Ipsum":** Tulis kalimat asli dalam bahasa Indonesia yang masuk akal.
2. **Semua gambar wajib punya `alt`:** Contoh: `<img src="..." alt="Foto profil developer">`.
3. **Cantumkan sumber gambar:** Ambil foto gratis di [Unsplash](https://unsplash.com) atau [Pexels](https://pexels.com), lalu tulis sumbernya di komentar kode HTML.
4. **Wajib HTML Semantik:** Gunakan `<nav>`, `<header>`, `<section>`, `<footer>`. Jangan semua dibungkus `<div>`.
5. **Catat AI yang dipakai:** Nanti sebutkan nama AI (misal ChatGPT, Claude, atau Gemini) di file `ReadME.md`.

---

## 3. Cara Menjalankan Tailwind CLI

Tidak perlu pusing dengan setup rumit. Cukup jalankan langkah ini di terminal (VS Code):

1. **Jalankan pemantau Tailwind (Watch mode):**
   ```bash
   npx tailwindcss -i ./src/input.css -o ./style.css --watch
   ```
   *Artinya: Setiap kalian mengetik class Tailwind di HTML dan menyimpan file, Tailwind otomatis mengupdate file `style.css`.*

2. Di file `index.html`, pastikan file CSS sudah terhubung di dalam `<head>`:
   ```html
   <link rel="stylesheet" href="style.css">
   ```

---

## 4. Pembagian Tugas yang Adil (50:50)

| Penanggung Jawab | Bagian yang Dikerjakan | Yang Perlu Dibuat |
| :--- | :--- | :--- |
| **Lutfi** | **Pondasi & Bagian Atas Website** | • Setup Tailwind CLI & struktur awal `index.html`<br>• **Navbar** (Logo/Nama, 2 link menu, 1 tombol kontak)<br>• **Hero Section** (Sapaan, deskripsi diri 1-2 kalimat, foto profil, tombol CTA) |
| **Dimas** | **Bagian Tengah & Bawah Website** | • **Section 1: Tentang & Keahlian** (Bio singkat & tampilan kartu/badge skill)<br>• **Section 2: Karya / Proyek** (3 kartu proyek rapi dalam bentuk grid)<br>• **Footer** (Nama, pesan penutup, dan 3 link medsos) |

---

## 5. Kumpulan Prompt AI Siap Pakai untuk Lutfi & Dimas

Kalian boleh minta bantuan AI untuk membuatkan kode Tailwind-nya. Agar hasil codingan dari AI langsung sesuai aturan tugas dan tidak *overengineering*, gunakan template prompt di bawah ini:

---

### Bagian Lutfi

#### Prompt AI 1: Membuat Navbar
```text
Tolong buatkan kode HTML semantik untuk bagian Navbar (<nav>) menggunakan Tailwind CSS.
Ketentuannya:
1. Posisi sticky di atas dengan background gelap/bersih dan efek blur.
2. Di sebelah kiri: Nama/logo personal (misal: "AlexDev").
3. Tepat 2 link navigasi menuju section halaman: "Tentang" (href="#about") dan "Proyek" (href="#projects").
4. Di sebelah kanan: 1 tombol Call-to-Action (CTA) yang menonjol bertuliskan "Hubungi Saya" (href="#contact").
5. Jangan gunakan JavaScript yang rumit, cukup gunakan utility class Tailwind CSS yang rapi.
6. Berikan komentar penjelasan di bawah kodenya.
```

#### Prompt AI 2: Membuat Hero Section
```text
Tolong buatkan kode HTML semantik untuk bagian Hero Section (<header id="hero">) menggunakan Tailwind CSS.
Ketentuannya:
1. Tata letak responsif (2 kolom di layar laptop/desktop, 1 kolom di HP).
2. Sisi teks: Headline judul menarik tentang Frontend Developer, sub-judul 1-2 kalimat deskripsi singkat yang ramah (TIDAK BOLEH pakai Lorem Ipsum), dan 1 tombol CTA "Lihat Portofolio" (href="#projects").
3. Sisi visual: 1 foto profil developer (gunakan link placeholder Unsplash bertema developer) lengkap dengan atribut alt="Foto Profil Pengembang Web".
4. Tambahkan komentar HTML di atas tag <img> yang mencantumkan sumber gambar Unsplash.
5. Desain modern, bersih, dan rapi.
```

---

### Bagian Dimas

#### Prompt AI 3: Membuat Section 1 (Tentang & Keahlian)
```text
Tolong buatkan kode HTML semantik untuk bagian About & Skills (<section id="about">) menggunakan Tailwind CSS.
Ketentuannya:
1. Judul section yang jelas: "Tentang Saya" dan deskripsi singkat 2-3 kalimat tentang perjalanan belajar web development (TIDAK BOLEH pakai Lorem Ipsum).
2. Bagian Keahlian (Skills): Tampilkan minimal 4 keahlian (contoh: HTML5, CSS3, Tailwind CSS, Git & GitHub) dalam bentuk kartu kecil atau badges/pills yang rapi menggunakan Tailwind grid/flex.
3. Gunakan palet warna yang serasi dan konsisten.
4. Berikan komentar penjelasan di bawah kodenya.
```

#### Prompt AI 4: Membuat Section 2 (Showcase 3 Proyek)
```text
Tolong buatkan kode HTML semantik untuk bagian Portofolio Proyek (<section id="projects">) menggunakan Tailwind CSS.
Ketentuannya:
1. Judul section: "Proyek Pilihan" dengan pengantar 1 kalimat singkat.
2. Tampilkan minimal 3 kartu proyek dalam bentuk grid responsif (grid-cols-1 md:grid-cols-3).
3. Setiap kartu proyek wajib berisi:
   - Gambar screenshot proyek (gunakan gambar Unsplash dengan atribut alt yang jelas dan sertakan komentar sumber gambarnya).
   - Judul proyek (contoh: "Web Landing Page Donasi", "Katalog Kopi Lokal", "Dashboard Cuaca").
   - Deskripsi singkat 1-2 kalimat tentang proyek tersebut.
   - Tag teknologi kecil (misal: "HTML", "Tailwind").
   - Link kecil bertuliskan "Lihat Demo" atau "Kode GitHub".
4. Jangan gunakan animasi JS yang berlebihan, utamakan hover effect Tailwind yang halus.
```

#### Prompt AI 5: Membuat Footer
```text
Tolong buatkan kode HTML semantik untuk bagian Footer (<footer> id="contact">) menggunakan Tailwind CSS.
Ketentuannya:
1. Tampilkan nama website/developer dan tahun copyright 2026.
2. Tuliskan 1 kalimat motto atau ajakan kolaborasi yang ramah.
3. Tampilkan tepat 3 link media sosial (Instagram, LinkedIn, dan GitHub) yang rapi dengan hover effect.
4. Berikan komentar penjelasan di bawah kodenya.
```

---

## 6. Checklist Pengumpulan Sebelum Deadline (26 September 2026)
- [ ] Buka `index.html` di browser, pastikan tampilannya rapi dan warnanya serasi.
- [ ] Coba klik link di navbar, pastikan halaman bergeser mulus ke section yang benar.
- [ ] Cek semua gambar: sudah ada teks `alt` dan komentar sumbernya di kode HTML.
- [ ] Pastikan tidak ada tulisan *Lorem Ipsum* sama sekali.
- [ ] Buka file `ReadME.md`, jelaskan website kalian dan tulis AI apa saja yang kalian gunakan.
- [ ] Buka file `PengerjaanKelompok.md`, pastikan nama lengkap kalian berdua sudah tertulis.
- [ ] Satukan seluruh file ke dalam format `.zip` dengan nama: `Kelompok [Nomor]_Penugasan Week 1.zip`.
