# CCTV Pria Solo — Website Interaktif

Website satu halaman (single-file) untuk toko **CCTV Pria Solo** dengan layanan **jual, beli/tukar tambah, servis, dan pemasangan CCTV**. Semua tombol pemesanan mengarah ke WhatsApp **0823-2354-4523**.

## File utama

| File | Keterangan |
|---|---|
| `index.html` | **Website final** — satu file mandiri (CSS, JS, dan semua gambar sudah tertanam di dalamnya). Bisa langsung dibuka di browser atau diunggah ke hosting apa pun. |
| `src/index.template.html` | Struktur HTML sumber (sebelum digabung). |
| `src/styles.css` | Seluruh desain/tampilan. |
| `src/app.js` | Logika interaktif (katalog, kalkulator, form, slider, dll). |
| `assets/` | Foto asli (hero, teknisi, ruang monitoring). |
| `build.py` | Skrip penggabung: CSS + JS + gambar → `index.html`. |
| `shots/` | Screenshot hasil pengecekan tampilan. |

## Cara pakai

1. **Langsung pakai:** buka `index.html` (klik dua kali) — semua fitur berjalan tanpa server.
2. **Unggah ke hosting:** unggah `index.html` ke Netlify, Vercel, GitHub Pages, cPanel, atau Hostinger. Tidak perlu database.
3. **Ubah isi lalu build ulang:**
   ```bash
   # edit dulu src/index.template.html, src/styles.css, atau src/app.js
   python3 build.py      # menghasilkan index.html baru
   ```

## Fitur interaktif

- **Hero "CCTV monitor"** — jam waktu Solo (WIB) berjalan, tombol mode **Siang/Malam** (night-vision).
- **Katalog 14 produk** — filter kategori (Paket / Kamera / Aksesori / Servis) + pencarian langsung.
- **Detail produk (modal)** — spesifikasi, isi paket, dan tombol pesan WhatsApp yang otomatis mengisi nama produk & harga.
- **Kalkulator estimasi biaya** — jenis sistem (Analog / IP PoE / WiFi), jumlah kamera 1–16, resolusi, media penyimpanan, plus opsi instalasi, bracket, perawatan, dan UPS. Total + DP 50% dihitung otomatis, lalu bisa dikirim ke WhatsApp sebagai ringkasan.
- **Form pengajuan servis** — validasi nama, nomor WhatsApp, dan keluhan; hasilnya dirangkum menjadi pesan WhatsApp (dengan opsi salin pesan bila WhatsApp tidak terbuka otomatis, misalnya di pratinjau).
- **Status buka/tutup toko** — dihitung otomatis dari jam Asia/Jakarta.
- **Slider testimoni**, **accordion FAQ**, **animasi angka**, **progress bar scroll**, **menu mobile**, dan **tombol WhatsApp/telepon mengambang**.

## Yang perlu disesuaikan (opsional)

- **Nomor WhatsApp:** sudah terpasang di mana-mana (`6282323544523` untuk link `wa.me`, `+6282323544523` untuk telepon, `0823-2354-4523` untuk tampilan). Jika berubah, cari dan ganti ketiga format tersebut di `src/index.template.html` dan `src/app.js`, lalu jalankan `python3 build.py`.
- **Alamat toko:** bagian kontak & footer memakai teks "Pria, Solo, Jawa Tengah" dan tautan pencarian Google Maps. Ganti dengan alamat/link Google Maps bisnis Anda yang sebenarnya.
- **Harga, paket, testimoni, dan statistik** (1.200+ instalasi, 9 tahun, rating 4,9) adalah contoh realistis untuk tampilan. Silakan sesuaikan dengan data toko Anda sebelum dipublikasikan.
- **Foto:** dapat diganti di `assets/` lalu build ulang.

## Catatan

- Halaman ini memakai foto hasil AI sebagai ilustrasi dan ikon SVG buatan sendiri, jadi tidak bergantung pada file eksternal.
- Pratinjau di aplikasi berjalan di iframe tanpa akses jaringan, sehingga tautan WhatsApp tidak bisa langsung terbuka di sana — gunakan tombol **Salin pesan** atau buka `index.html` di browser biasa.
