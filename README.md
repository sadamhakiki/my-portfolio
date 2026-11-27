# Portfolio Sadam Muhammad Hakiki

Satu halaman portfolio untuk IT Support: Pengalaman, Keahlian, Proyek, dan Kontak. Ada dua versi, `index.html` (Indonesia) dan `en.html` (Inggris). Markup keduanya sama; yang berbeda hanya teks dan `alt`.

## Isi folder

| File | Keterangan |
|---|---|
| `index.html` | Versi Indonesia. Dibuka langsung di browser. |
| `en.html` | Versi Inggris, struktur sama. |
| `foto-cutout.png` | Potret di hero. Latar transparan, dipotong di dada. |
| `cv_sadammhakiki.pdf` | File yang diunduh lewat tombol "Unduh CV". |
| `DESIGN.md` | Catatan desain: token warna, tipografi, motif, dan guardrail. |

## Menjalankan

Tidak ada build step. Buka `index.html` di browser, atau jalankan server statis sederhana:

```sh
python -m http.server 8000
```

Lalu buka `http://localhost:8000`. Server diperlukan kalau ingin mencoba di ponsel lewat jaringan lokal.

## Cara kerja halaman

Tailwind dimuat lewat CDN browser (`@tailwindcss/browser@4`) dan tema ditulis di blok `<style type="text/tailwindcss">` dalam masing-masing file HTML. Tidak ada `package.json`, `node_modules`, atau proses kompilasi: yang dirilis adalah file HTML itu sendiri.

Kalau Tailwind dimatikan lewat pemblokir skrip, halaman tetap terbaca karena memakai font dan warna dasar browser, hanya tata letaknya yang hilang.

Halaman memakai satu tema gelap saja. Warna, font, dan motif halftone didefinisikan satu kali di blok `@theme` dan `@utility`; ubah di sana, bukan di class.

## Mengubah isi

- Ganti teks di kedua file. Kalau hanya mengubah satu, versi Indonesia dan Inggris jadi tidak sinkron.
- Tanggal di footer diisi otomatis dari tahun berjalan.
- Mengganti foto: timpa `foto-cutout.png`, lalu sesuaikan atribut `width` dan `height` di tag `<img>` supaya tidak ada pergeseran tata letak saat gambar dimuat.
- Mengganti CV: timpa `cv_sadammhakiki.pdf`. Nama unduhan sudah diatur lewat atribut `download`, jadi nama file aslinya tidak berpengaruh.

## Deploy

Situs ini statis, bisa diunggah apa adanya ke GitHub Pages, Netlify, Vercel, atau hosting biasa. Tidak ada konfigurasi tambahan yang dibutuhkan.
