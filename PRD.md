# Panduan & Rencana Proyek: Refactoring ReactJS dan Deploy Vercel - Week 2

Dokumen ini dibuat khusus agar **Lutfi** dan **Dimas** dapat memahami dan mengerjakan tugas Week 2 secara bertahap, mudah dipahami untuk pemula, tidak berlebihan (*anti-overengineering*), serta terhubung langsung dengan apa yang sudah mereka kerjakan di Week 1.

---

## 1. Peta Refactoring: Dari HTML Week 1 Menjadi ReactJS Week 2

Tujuan utama Week 2 adalah **refactoring** (memindahkan dan merombak codingan HTML & Tailwind yang sudah dibuat di Week 1) ke dalam bentuk komponen React modular dan multi-halaman:

| Codingan HTML Tailwind di Week 1 | Pembuat di Week 1 | Berubah Menjadi di Week 2 (ReactJS) | Keterangan Perubahan |
| :--- | :--- | :--- | :--- |
| Tag `<nav>` Navbar | **Lutfi** | `src/components/Navbar.jsx` | Ditambahkan state `useState` untuk tombol hamburger menu mobile. |
| Tag `<header>` Hero Section | **Lutfi** | `src/components/Hero.jsx` & `src/pages/Home.jsx` | Dibuat modular menerima data via props, dipasang di halaman Beranda. |
| Tag `<section>` Tentang & Keahlian | **Dimas** | `src/pages/Tentang.jsx` | Dipindahkan menjadi halaman mandiri yang memiliki rute sendiri (`/tentang`). |
| Tag `<section>` 3 Kartu Proyek | **Dimas** | `src/data/programs.js`, `src/components/Card.jsx`, & `src/pages/Program.jsx` | Datanya dipisah ke file array Javascript, komponen kartunya dibuat reusable, dan dirender via `.map()`. |
| Tag `<footer>` Footer | **Dimas** | `src/components/Footer.jsx` | Dijadikan komponen modular yang otomatis muncul di semua halaman via `MainLayout.jsx`. |

---

## 2. Fitur Baru yang Ditambahkan di Week 2
Selain merombak codingan lama, terdapat fitur baru wajib sesuai ketentuan penugasan:
1. **Multi-page Routing (React Router DOM):** Pengunjung berpindah halaman tanpa reload browser (`/`, `/program`, `/tentang`, `/kontak`, dan `*`).
2. **Layout Bersama (`MainLayout.jsx`):** Navbar dan Footer tidak perlu ditulis ulang di tiap halaman, cukup dipasang sekali bersama `<Outlet />`.
3. **Pop-up Modal Interaktif (`Modal.jsx`):** Komponen modal dengan state `useState` buka/tutup saat tombol CTA diklik.
4. **Halaman Formulir Kontak Terintegrasi API (`Kontak.jsx` & `ContactForm.jsx`):**
   - 3 input data: `author` (nama min 2 karakter), `title` (subjek min 3 karakter), `content` (pesan min 10 karakter).
   - Validasi error jika input belum memenuhi syarat.
   - Mengirim data via `POST` ke API: `https://devx2026-post.vercel.app/api/posts` dengan Header `Authorization: Bearer DEVX2026`.
   - Handling status respon: 201 (sukses), 400 (error validasi), dan 401 (unauthorized).
5. **Konfigurasi `vercel.json` & Deployment:** Deployment ke Vercel agar website bisa diakses secara online tanpa error 404 saat refresh.

---

## 3. Struktur Folder Project
```text
devX26/
├── public/
├── src/
│   ├── components/
│   │   ├── Navbar.jsx         # Dari Navbar Week 1 Lutfi + state hamburger
│   │   ├── Hero.jsx           # Dari Hero Week 1 Lutfi + props
│   │   ├── Section.jsx        # Pembungkus reusable
│   │   ├── Card.jsx           # Dari Card Proyek Week 1 Dimas
│   │   ├── Footer.jsx         # Dari Footer Week 1 Dimas
│   │   ├── Modal.jsx          # Komponen pop-up baru
│   │   └── ContactForm.jsx    # Form kontak baru + validasi + fetch API
│   ├── layouts/
│   │   └── MainLayout.jsx     # Navbar + <Outlet /> + Footer
│   ├── pages/
│   │   ├── Home.jsx           # Halaman Beranda (Hero + Ringkasan)
│   │   ├── Program.jsx        # Halaman Proyek (Data mapping Card)
│   │   ├── Tentang.jsx        # Dari Section About Week 1 Dimas
│   │   ├── Kontak.jsx         # Halaman Kontak Kami
│   │   └── NotFound.jsx       # Halaman 404 Not Found
│   ├── data/
│   │   └── programs.js        # Data array proyek
│   ├── App.jsx                # Konfigurasi routing
│   ├── main.jsx               # Titik awal React
│   └── index.css              # Directives Tailwind
├── vercel.json                # Pengaturan rewrite Vercel
├── package.json
├── README.md
├── PengerjaanKelompok.md
└── PRD.md
```

---

## 4. Pembagian Tugas yang Adil (Bagi Rata 50:50)

Setiap anggota bertanggung jawab mengonversi codingan Week 1 miliknya masing-masing, ditambah tugas baru yang seimbang:

| Anggota Tim | Yang Dikonversi dari Week 1 | Tugas Baru Week 2 |
| :--- | :--- | :--- |
| **Lutfi** | • Mengubah Navbar HTML lama menjadi `Navbar.jsx`<br>• Mengubah Hero HTML lama menjadi `Hero.jsx` & `Home.jsx` | 1. Setup project Vite React + Tailwind + React Router DOM.<br>2. Membuat `MainLayout.jsx` dan routing di `App.jsx`.<br>3. Menambahkan state mobile hamburger di `Navbar.jsx`.<br>4. Membuat halaman `NotFound.jsx` (404).<br>5. Menyiapkan file `vercel.json` dan dokumentasi di `README.md`. |
| **Dimas** | • Mengubah Section About lama menjadi `Tentang.jsx`<br>• Mengubah Section Proyek lama menjadi `programs.js`, `Card.jsx`, & `Program.jsx`<br>• Mengubah Footer HTML lama menjadi `Footer.jsx` | 1. Memisahkan data kartu proyek ke array `src/data/programs.js` dan mapping menggunakan `.map()`.<br>2. Membuat komponen reusable `Section.jsx`.<br>3. Membuat komponen interaktif `Modal.jsx` (dengan state buka/tutup).<br>4. Membuat komponen `ContactForm.jsx` dan halaman `Kontak.jsx` (state input, validasi error, POST ke API DevX, handling 201/400/401).<br>5. Melengkapi dokumentasi API dan AI di `README.md`. |

---

## 5. Kumpulan Prompt AI Siap Pakai untuk Lutfi & Dimas

---

### Bagian Lutfi

#### Prompt Lutfi 1: Setup React Router & MainLayout
```text
Saya sedang belajar ReactJS dengan Vite dan Tailwind CSS.
Tolong buatkan struktur konfigurasi routing menggunakan react-router-dom versi 6+.
Kebutuhannya:
1. File src/layouts/MainLayout.jsx yang berisi Navbar, komponen <Outlet />, dan Footer.
2. File src/App.jsx yang membungkus aplikasi dengan BrowserRouter dan Routes:
   - Path "/" mengarah ke Home.jsx
   - Path "/program" mengarah ke Program.jsx
   - Path "/tentang" mengarah ke Tentang.jsx
   - Path "/kontak" mengarah ke Kontak.jsx
   - Path "*" mengarah ke NotFound.jsx
3. Gunakan sintaks React modern dan berikan komentar penjelasan singkat untuk pemula.
```

#### Prompt Lutfi 2: Refactoring Navbar Lama ke Navbar.jsx dengan State Mobile Menu
```text
Saya punya kode HTML Navbar dengan Tailwind CSS dari tugas minggu lalu.
Tolong ubah menjadi komponen React src/components/Navbar.jsx.
Kriterianya:
1. Gunakan NavLink dari react-router-dom untuk menu: Beranda ("/"), Program ("/program"), Tentang ("/tentang"), Kontak ("/kontak").
2. Berikan styling aktif jika halaman sedang dibuka (menggunakan isActive).
3. Tambahkan tombol hamburger untuk layar mobile menggunakan useState (misal: const [isOpen, setIsOpen] = useState(false)).
4. Terapkan conditional rendering agar menu mobile muncul saat tombol hamburger diklik.
5. Berikan komentar jelas pada bagian state dan kodenya.
```

#### Prompt Lutfi 3: Refactoring Hero Lama ke Hero.jsx & Halaman Home, NotFound
```text
Tolong bantu saya membuat komponen Hero modular dan 2 halaman React dengan Tailwind CSS:
1. src/components/Hero.jsx: Mengubah tampilan Hero section lama menjadi komponen React yang menerima props (title, subtitle, ctaText, onCtaClick, image).
2. src/pages/Home.jsx: Menampilkan komponen Hero di atas, lalu ringkasan singkat dengan tombol yang mengarahkan ke halaman Program dan Kontak.
3. src/pages/NotFound.jsx: Halaman 404 estetik yang menampilkan pesan bahwa rute tidak ditemukan serta tombol kembali ke Beranda ("/").
```

---

### Bagian Dimas

#### Prompt Dimas 1: Refactoring Section Proyek Lama ke data/programs.js, Card.jsx, & Program.jsx
```text
Saya punya kode HTML kumpulan kartu proyek dari tugas minggu lalu.
Tolong bantu saya merombaknya ke dalam pola React yang bersih:
1. File src/data/programs.js: Pindahkan teks dan data proyek ke dalam bentuk array of objects (setiap objek memiliki id, title, description, image, techStack, link).
2. File src/components/Card.jsx: Buat komponen kartu reusable yang menerima data melalui props (title, description, image, techStack, link).
3. File src/components/Section.jsx: Buat komponen pembungkus dengan props title, subtitle, dan children.
4. File src/pages/Program.jsx: Impor data dari programs.js, lalu tampilkan daftar Card menggunakan perulangan data.map().
Gunakan Tailwind CSS yang rapi dan sertakan komentar kode.
```

#### Prompt Dimas 2: Refactoring Section About Lama ke Halaman Tentang.jsx dan Footer.jsx
```text
Tolong bantu saya memindahkan codingan lama menjadi komponen React:
1. src/pages/Tentang.jsx: Memindahkan konten cerita latar belakang dan daftar keahlian/skills dari tugas Week 1 ke halaman mandiri ini. Tambahkan styling yang rapi dan konsisten dengan Tailwind CSS.
2. src/components/Footer.jsx: Mengubah tag <footer> HTML lama menjadi komponen React yang memuat hak cipta tahun 2026 dan 3 tautan media sosial.
```

#### Prompt Dimas 3: Membuat Modal Pop-up Interaktif
```text
Tolong buatkan komponen pop-up src/components/Modal.jsx menggunakan ReactJS dan Tailwind CSS.
Kriterianya:
1. Menerima props: isOpen, onClose, title, dan children.
2. Gunakan conditional rendering: jika isOpen false, kembalikan null.
3. Jika isOpen true, tampilkan backdrop gelap semi-transparan fixed di tengah layar, kotak dialog putih/gelap rapi, tombol 'X' di pojok kanan atas, serta tombol tutup di bawah.
4. Berikan contoh cara memanggilnya dari komponen halaman menggunakan useState.
```

#### Prompt Dimas 4: Membuat Form Kontak & Integrasi API POST
```text
Tolong buatkan komponen src/components/ContactForm.jsx dan halaman src/pages/Kontak.jsx menggunakan ReactJS dan Tailwind CSS.
Ketentuannya:
1. Form memiliki 3 field input yang dikontrol dengan useState:
   - Nama Pengirim ("author", minimal 2 karakter)
   - Subjek Pesan ("title", minimal 3 karakter)
   - Isi Pesan ("content", minimal 10 karakter)
2. Buat validasi karakter: jika tidak memenuhi batas minimal saat dikirim, tampilkan pesan error merah di bawah input terkait.
3. Kirim data saat onSubmit menggunakan fetch (POST) ke:
   https://devx2026-post.vercel.app/api/posts
   Headers wajib:
   - 'Content-Type': 'application/json'
   - 'Authorization': 'Bearer DEVX2026'
   Body JSON:
   {
     "title": state_subjek,
     "content": state_pesan,
     "author": state_nama
   }
4. Penanganan respons:
   - Status 201: Tampilkan notifikasi hijau berhasil dan reset form.
   - Status 400: Tampilkan pesan error dari server ke layar.
   - Status 401: Tampilkan pesan bahwa akses ditolak/token salah.
5. Berikan komentar jelas pada setiap alur penanganan respons.
```

---

## 6. Persiapan Deploy Vercel

Buat file `vercel.json` di root project dengan isi:
```json
{
  "rewrites": [
    {
      "source": "/(.*)",
      "destination": "/index.html"
    }
  ]
}
```

---

## 7. Checklist Pengumpulan Tugas (Deadline: 4 Oktober 2026 pukul 23:59 WIB)
- [ ] Seluruh bagian website Week 1 berhasil dipindahkan ke komponen React dan halaman yang sesuai.
- [ ] Navbar memiliki 4 tautan halaman aktif yang dapat berpindah tanpa reload browser.
- [ ] Halaman 404 (NotFound) aktif jika memasukkan URL yang tidak terdaftar.
- [ ] Minimal 6 komponen reusable telah dibuat di folder `src/components/`.
- [ ] Data proyek di-render menggunakan `.map()` dari file `programs.js`.
- [ ] Fitur interaktif berfungsi normal: hamburger menu (`useState`), pop-up modal (`useState`), dan form kontak (`useState`).
- [ ] Form kontak berhasil mengirim data ke endpoint API DevX dan memunculkan status penanganan respon.
- [ ] File `vercel.json` ada di root folder dan website tidak error 404 saat di-refresh di Vercel.
- [ ] Repository GitHub memiliki commit bertahap, link Vercel aktif, dan dikirimkan sebelum batas waktu.
