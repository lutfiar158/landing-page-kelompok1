# Sistem Desain: Palet Warna & Panduan Anti-AI Slop

## 1. Perbandingan Hijau

| Parameter | `#01C654` (Neon Emerald) | `#134E4A` (Deep Forest Teal) |
| :--- | :--- | :--- |
| **Kontras vs `#FCF9EA` (Krim)** | 1.7:1 (Gagal WCAG, tidak terbaca) | 9.5:1 (Lolos WCAG AAA, sangat kontras) |
| **Porsi 20%** | Terlalu mencolok, menyilaukan mata | Stabil, solid, tidak bikin lelah mata |
| **Karakter Visual** | Web3, crypto, SaaS AI generik ("AI Slop") | Editorial, klasik, grounded, berbobot |
| **Keputusan** | **Tolak.** Cocok hanya untuk dot status 1%. | **Pilih.** Aman untuk tombol, badge, dan kartu aksen. |

---

## 2. Distribusi Warna (50 - 30 - 20)

### 50% Background Utama: `#FCF9EA` (Warm Cream)
- **Fungsi:** Body background, latar section, background input.
- **Karakter:** Hangat, tekstur kertas cetak, bukan putih klinis `#FFFFFF`.

### 30% Struktur & Teks: `#1C1E1F` (Charcoal Black)
- **Fungsi:** Teks utama (`body`), judul (`h1`, `h2`), border tegas (1px), footer.
- **Karakter:** Kontras tinggi di atas `#FCF9EA`, bukan hitam mati `#000000`.

### 20% Aksen: `#134E4A` (Deep Forest Teal)
- **Fungsi:** Tombol aksi utama (CTA), kartu sorotan, border aktif, tag/badge skill.
- **Karakter:** Memberi bobot visual tanpa merusak ketenangan halaman.

---

## 3. Variabel CSS & Panduan Implementasi

```css
:root {
  --bg-main: #FCF9EA;      /* 50% */
  --text-main: #1C1E1F;    /* 30% */
  --accent: #134E4A;       /* 20% */
  --accent-text: #FCF9EA;
  --border: #1C1E1F;
}

body {
  background-color: var(--bg-main);
  color: var(--text-main);
}

.btn-primary {
  background-color: var(--accent);
  color: var(--accent-text);
  border: 1px solid var(--border);
}
```

---

## 4. Aturan Anti-AI Slop

1. **Haram gradien ungu/hijau neon:** Jangan pakai `linear-gradient` neon khas template bot.
2. **Border tegas alih-alih glow blur:** Gunakan border 1px solid `#1C1E1F` dengan sudut tajam atau rounded kecil (`rounded-md`), bukan rounded pill raksasa dengan drop-shadow blur besar.
3. **Tipografi langsung:** Hindari subjudul berbunga-bunga. Gunakan hierarki jelas: judul tebal, deskripsi faktual.
4. **Ikon fungsional:** Gunakan ikon hanya saat memperjelas aksi, bukan hiasan acak.
