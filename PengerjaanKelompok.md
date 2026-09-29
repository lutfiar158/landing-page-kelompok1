# Laporan Pengerjaan Kelompok - Week 2: Refactoring with ReactJS and Deploy on Vercel

## Anggota Kelompok
1. **[Nama Lengkap Lutfi]** (NIM: ................)
2. **[Nama Lengkap Dimas]** (NIM: ................)

*(Catatan: Aditya sudah tidak berada di dalam kelompok)*

---

## Peta Refactoring dari Tugas Week 1 ke Week 2

Tugas Week 2 adalah merombak website landing page HTML & Tailwind CSS dari Week 1 menjadi website modern berbasis ReactJS (Vite), React Router DOM, dan dideploy ke Vercel. 

Setiap anggota bertanggung jawab mengonversi bagian yang sudah dikerjakannya di Week 1 menjadi komponen React, ditambah fitur-fitur baru Week 2 yang dibagi rata 50:50:

---

### 1. Tugas Lutfi (Refactoring Bagian Atas & Setup Arsitektur React)

Lutfi mengonversi pekerjaan Week 1 miliknya (Navbar dan Hero) serta membangun fondasi arsitektur React:

1. **Refactoring Kode Week 1 Milik Lutfi:**
   - **Navbar:** Mengubah tag `<nav>` HTML lama menjadi `src/components/Navbar.jsx` menggunakan `NavLink`, serta menambahkan state `useState` untuk toggle hamburger menu di layar HP.
   - **Hero Section:** Mengubah tag `<header>` Hero lama menjadi komponen `src/components/Hero.jsx` yang menerima data lewat props, lalu dipasang di `src/pages/Home.jsx`.
2. **Tugas Baru Week 2:**
   - Inisialisasi project ReactJS menggunakan Vite dan setup Tailwind CSS.
   - Setup konfigurasi React Router DOM pada `src/App.jsx` untuk semua rute (`/`, `/program`, `/tentang`, `/kontak`, `*`).
   - Membuat layout bersama `src/layouts/MainLayout.jsx` (Navbar + `<Outlet />` + Footer).
   - Membuat halaman 404 `src/pages/NotFound.jsx`.
   - Menyiapkan file `vercel.json` agar routing SPA tidak error 404 saat di-refresh.
   - Menulis panduan setup lokal di `README.md`.

> **Tips buat Lutfi:** Salin prompt siap pakai pada `PRD.md` bagian "Prompt Lutfi 1", "Prompt Lutfi 2", dan "Prompt Lutfi 3" untuk mempermudah pembuatan kodenya.

---

### 2. Tugas Dimas (Refactoring Konten/Karya & Fitur Interaktif API)

Dimas mengonversi pekerjaan Week 1 miliknya (Section About, Section Proyek, dan Footer) serta membangun fitur interaktif modal dan formulir kontak API:

1. **Refactoring Kode Week 1 Milik Dimas:**
   - **Section 1 (Tentang & Keahlian):** Mengubah section About lama menjadi halaman mandiri `src/pages/Tentang.jsx`.
   - **Section 2 (3 Kartu Proyek):** Memisahkan data teks ke file array `src/data/programs.js`, membuat kartu modular `src/components/Card.jsx`, dan menampilkannya di halaman `src/pages/Program.jsx` menggunakan perulangan `.map()`.
   - **Footer:** Mengubah tag `<footer>` HTML lama menjadi komponen modular `src/components/Footer.jsx`.
2. **Tugas Baru Week 2:**
   - Membuat komponen pembungkus `src/components/Section.jsx` dengan props `title`, `subtitle`, dan `children`.
   - Membuat komponen pop-up interaktif `src/components/Modal.jsx` menggunakan state `useState` (buka/tutup modal).
   - Membuat halaman `src/pages/Kontak.jsx` dan `src/components/ContactForm.jsx`.
   - Mengelola state 3 input (`author`, `title`, `content`) dengan validasi panjang karakter.
   - Mengintegrasikan pengiriman form via `POST` ke API DevX (`https://devx2026-post.vercel.app/api/posts`) dengan header `Authorization: Bearer DEVX2026`.
   - Menangani pesan respons API: status 201 (sukses), status 400 (error validasi), dan status 401 (unauthorized).
   - Melengkapi dokumentasi endpoint API dan AI yang digunakan di `README.md`.

> **Tips buat Dimas:** Salin prompt siap pakai pada `PRD.md` bagian "Prompt Dimas 1", "Prompt Dimas 2", "Prompt Dimas 3", dan "Prompt Dimas 4" untuk mempermudah pengerjaan logika data dan integrasi API.

---

## Tahapan Eksekusi Bersama
1. **Langkah 1 (Setup Bersama):** Lutfi menyiapkan instalasi Vite React, Tailwind, dan struktur folder.
2. **Langkah 2 (Migrasi Kode Lama):** Lutfi mengonversi Navbar dan Hero; Dimas mengonversi Tentang, Proyek (Card + mapping array), dan Footer.
3. **Langkah 3 (Penambahan Fitur Baru):** Lutfi memasang Router di `App.jsx`, `MainLayout.jsx`, dan halaman 404; Dimas menambahkan Modal dan Formulir Kontak API.
4. **Langkah 4 (Pengujian & Responsivitas):** Uji coba bersama di layar desktop dan mobile (pastikan tidak ada error di console).
5. **Langkah 5 (Deploy & Kumpul):** Push ke GitHub dan deploy ke Vercel sebelum deadline: **Sabtu, 4 Oktober 2026 pukul 23:59 WIB**.