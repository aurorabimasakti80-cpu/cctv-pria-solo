# Panduan Onlinekan CCTV Pria Solo di GitHub Pages

Setelah selesai, website Anda akan punya alamat publik seperti:

```
https://USERNAME.github.io/cctv-pria-solo/
```

Ganti `USERNAME` dengan nama pengguna GitHub Anda. Alamat ini **gratis**, **HTTPS**, dan bisa dibuka siapa saja.

---

## Yang Anda butuhkan

- Akun GitHub (gratis) — daftar di <https://github.com/signup>
- File `index.html` (sudah tersedia di workspace, juga ada di dalam `deploy/` atau `cctv-pria-solo-github.zip`)
- Koneksi internet

> File `index.html` sudah **mandiri** (CSS, JavaScript, dan semua foto tertanam di dalamnya). Jadi Anda **hanya perlu satu file** — tidak ada gambar atau folder yang bisa hilang.

---

## METODE A — Lewat browser (paling mudah, tanpa install apa pun)

### 1. Buat repository baru
1. Buka <https://github.com> lalu login.
2. Klik tombol **`+`** di kanan atas → **New repository**.
3. Isi:
   - **Repository name:** `cctv-pria-solo`
   - **Description:** (opsional) `Website toko CCTV Pria Solo — jual, servis, pasang CCTV`
   - **Visibility:** pilih **Public** ← wajib agar GitHub Pages gratis aktif
   - **Jangan** centang "Add a README file", ".gitignore", atau "license"
4. Klik **Create repository**.

### 2. Unggah file website
1. Di halaman repo yang masih kosong, klik tautan biru **"uploading an existing file"**
   (atau menu **Add file → Upload files**).
2. Unduh dulu `index.html` dari workspace ini (tombol download di penampil file), lalu **seret file itu** ke area unggah.
3. Di kotak pesan bawah, tulis: `Website CCTV Pria Solo`
4. Klik **Commit changes**.

### 3. Aktifkan GitHub Pages
1. Di halaman repo, klik tab **Settings**.
2. Di menu kiri, klik **Pages**.
3. Bagian **Build and deployment**:
   - **Source:** `Deploy from a branch`
   - **Branch:** `main` dan folder `/ (root)`
4. Klik **Save**.
5. Tunggu **1–2 menit**, lalu **refresh** halaman Settings → Pages.
   Akan muncul tulisan: *"Your site is live at https://USERNAME.github.io/cctv-pria-solo/"*

### 4. Buka linknya
Klik link tersebut. Selesai — website Anda sudah online. 🎉

---

## METODE B — Lewat terminal / Git CLI

Cocok jika Git sudah terpasang di komputer Anda.

```bash
# 1. masuk ke folder yang berisi index.html
cd path/ke/folder/cctv-pria-solo

# 2. inisialisasi repo
git init
git add index.html .nojekyll
git commit -m "Website CCTV Pria Solo"

# 3. hubungkan ke GitHub (buat dulu repo kosong bernama cctv-pria-solo di github.com)
git branch -M main
git remote add origin https://github.com/USERNAME/cctv-pria-solo.git
git push -u origin main
```

Setelah itu aktifkan Pages seperti **Metode A langkah 3**.

> Jika `git push` meminta password, gunakan **Personal Access Token** (Settings → Developer settings → Personal access tokens → Generate new token, centang `repo`), bukan password akun.

---

## METODE C — Lewat GitHub Desktop (GUI)

1. Install <https://desktop.github.com>.
2. **File → Add local repository** → pilih folder berisi `index.html`.
3. Klik **Publish repository**, pilih nama `cctv-pria-solo`, **hilangkan centang "Keep this code private"**.
4. Aktifkan Pages seperti **Metode A langkah 3**.

---

## Cara memperbarui website nanti

1. Buka repo → klik `index.html` → ikon **pensil** (Edit).
2. Ubah teks/harga yang diinginkan, atau klik **Add file → Upload files** untuk mengganti dengan versi baru.
3. **Commit changes**.
4. Tunggu ±1 menit, lalu refresh situs Anda (gunakan **Ctrl + Shift + R** / hard refresh agar tidak kena cache).

---

## Alamat link: kapan berubah?

| Nama repository | Alamat website |
|---|---|
| `cctv-pria-solo` | `https://USERNAME.github.io/cctv-pria-solo/` |
| `USERNAME.github.io` | `https://USERNAME.github.io/` (langsung di root) |
| `website-toko` | `https://USERNAME.github.io/website-toko/` |

Pastikan nama repo ditulis **huruf kecil semua** agar link-nya rapi.

---

## Memakai domain sendiri (opsional, misal `cctvpriasolo.com`)

1. Beli domain di registrar (Niagahoster, DomaiNesia, Namecheap, Cloudflare, dsb.).
2. Di repo → **Settings → Pages → Custom domain**, isi `cctvpriasolo.com` → **Save**.
3. Di pengaturan DNS domain Anda, tambahkan:
   - **CNAME** untuk `www` → `USERNAME.github.io`
   - **A record** untuk `@` → `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
4. Tunggu propagasi DNS (5 menit – 24 jam), lalu centang **Enforce HTTPS**.

---

## Troubleshooting

| Masalah | Penyebab & solusi |
|---|---|
| Halaman 404 | Belum aktif Pages, atau file tidak bernama persis `index.html`, atau branch bukan `main`. Cek Settings → Pages. |
| Muncul tampilan tanpa warna/gambar | File terunggah bukan versi lengkap. Pastikan ukurannya ±553 KB dan diunggah utuh. |
| Link masih tampilan lama | Cache browser. Tekan **Ctrl + Shift + R** atau buka di jendela incognito. |
| Deploy lama selesai | Biasanya 1–2 menit, kadang sampai 10 menit pada deploy pertama. Cek tab **Actions** untuk melihat prosesnya. |
| Tombol WhatsApp tidak terbuka | Normal bila dibuka di pratinjau aplikasi (iframe diblokir jaringan). Di link GitHub Pages yang asli tombol berfungsi normal. |
| Ingin repo privat | GitHub Pages untuk repo privat hanya tersedia di paket GitHub Pro. Untuk gratis, repo harus **Public**. |

---

## Checklist sebelum dipublikasikan

- [ ] Ganti alamat toko & link Google Maps dengan lokasi asli (`src/index.template.html` → `#kontak` dan footer, lalu `python3 build.py`)
- [ ] Sesuaikan harga paket di katalog & kalkulator
- [ ] Ganti testimoni contoh dengan ulasan asli pelanggan
- [ ] Pastikan nomor WhatsApp `0823-2354-4523` sudah benar
- [ ] Tambahkan link website ke bio Instagram/Google Business Profile toko

---

## Tips tambahan

- **Meta description** sudah terpasang, jadi saat link dibagikan di WhatsApp/Instagram akan muncul judul dan deskripsi yang rapi.
- Ingin terindeks Google: buka <https://search.google.com/search-console>, tambahkan URL situs, lalu minta *Request indexing*.
- Simpan salinan `index.html` di komputer sebagai cadangan sebelum melakukan perubahan besar.
