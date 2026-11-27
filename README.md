# Portfolio Sadam Muhammad Hakiki

Situs ini adalah **portfolio pribadi** Sadam Muhammad Hakiki, seorang IT Support di Depok, Jawa Barat, dengan latar belakang pendidikan Teknik Komputer dan Jaringan (TKJ). Isinya ringkasan kerja: apa yang dikerjakan sehari-hari, keahlian yang dipakai, beberapa proyek nyata, dan cara menghubungi.

Tujuannya satu: memberi perekrut atau calon pemberi kerja gambaran cepat sebelum mereka menghubungi. Karena itu halaman ini sengaja dibuka langsung dalam Bahasa Indonesia, dengan versi Bahasa Inggris untuk pembaca yang lebih nyaman berbahasa Inggris.

## Siapa yang dituju

- Perekrut dan HR di perusahaan yang mencari IT Support, teknisi jaringan, atau staf infrastruktur.
- Tim teknis yang ingin melihat jenis pekerjaan yang pernah ditangani sebelum tahap wawancara.
- Diri sendiri sebagai catatan: setiap proyek yang selesai tinggal ditambahkan ke bagian Proyek.

## Isi halaman

| Bagian | Yang ditampilkan |
|---|---|
| Hero | Nama, potret, ringkasan singkat peran dan latar belakang, tombol WhatsApp dan Lihat CV. |
| Pengalaman | Riwayat kerja terbaru di PT Toyib Karya Utama, dari dukungan pengguna dan perawatan printer sampai jaringan, server, CCTV, dan website internal. |
| Keahlian | Tiga kelompok: jaringan, sistem dan keamanan, serta dukungan dan tata kelola. |
| Proyek Saya | Tiga kasus utama: infrastruktur jaringan perusahaan, IP PBX/CCTV/access control, serta website perusahaan dan yayasan. |
| Kontak | Email, telepon, dan WhatsApp. |
| Footer | Tahun berjalan dan tautan ke versi bahasa lain. |

Ada dua berkas halaman: `index.html` (Indonesia) dan `en.html` (Inggris). Strukturnya sama; yang berbeda hanya teks dan atribut `alt` gambar.

## Detail kontak

Kontak yang dipakai halaman ini terduplikasi di beberapa tempat, jadi ubah semuanya kalau ada yang berubah:

- WhatsApp / telepon: `+62 878 8335 1852` (`https://wa.me/6287883351852`, `tel:+6287883351852`).
- Email: `sadamhakiki0@gmail.com` — muncul di tautan `mailto:` pada bagian kontak.

## Berkas di folder ini

| Berkas | Keterangan |
|---|---|
| `index.html` | Halaman portfolio versi Indonesia. |
| `en.html` | Versi Inggris, struktur dan gaya sama. |
| `foto-cutout.png` | Potret di hero, latar transparan, dipotong di dada. |
| `favicon.svg` | Ikon tab peramban: lingkaran gelap berisi motif hatch 45°, sama dengan logo di navbar. |
| `cv_sadammhakiki.pdf` | CV yang dibuka di tab baru lewat tombol "Lihat CV". |
| `DESIGN.md` | Catatan desain: token warna, tipografi, motif, dan guardrail. Sempat dihapus dari Git; sekarang lokal saja, tidak ikut di-push. |

## Menjalankan

Tidak ada build step. Buka `index.html` di browser, atau jalankan server statis sederhana:

```sh
python -m http.server 8000
```

Lalu buka `http://localhost:8000`. Server diperlukan kalau ingin mencoba di ponsel lewat jaringan lokal.

## Cara halaman ini bekerja

Tailwind dimuat lewat CDN browser (`@tailwindcss/browser@4`), dan tema ditulis di blok `<style type="text/tailwindcss">` dalam masing-masing berkas HTML. Tidak ada `package.json`, `node_modules`, atau proses kompilasi: yang dirilis adalah berkas HTML itu sendiri.

Kalau Tailwind dimatikan lewat pemblokir skrip, halaman tetap terbaca karena memakai font dan warna dasar browser, hanya tata letaknya yang hilang.

Halaman memakai satu tema gelap saja. Warna, font, dan motif hatch didefinisikan satu kali di blok `@theme` dan `@utility`; ubah di sana, bukan di class.

## Mengubah isi

- Ganti teks di kedua berkas. Kalau hanya mengubah satu, versi Indonesia dan Inggris jadi tidak sinkron.
- Bagian Pengalaman dan Proyek berupa daftar atau kartu; menambah satu entri cukup menyalin blok entri yang ada dan mengganti isinya, termasuk `id` dan `aria-labelledby` pada kartu proyek.
- Tanggal di footer diisi otomatis dari tahun berjalan.
- Mengganti foto: timpa `foto-cutout.png`, lalu sesuaikan atribut `width` dan `height` di tag `<img>` supaya tidak ada pergeseran tata letak saat gambar dimuat.
- Mengganti CV: timpa `cv_sadammhakiki.pdf`. Tombol "Lihat CV" membukanya di tab baru (`target="_blank"`), jadi nama berkas aslinya yang tampil di tab.

## Deploy

Situs ini statis, bisa diunggah apa adanya ke GitHub Pages, Netlify, Vercel, atau hosting biasa. Tidak ada konfigurasi tambahan yang dibutuhkan.
