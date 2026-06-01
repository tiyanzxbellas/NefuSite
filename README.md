<div align="center">
  <img src="https://c.tiyan.biz.id/pazA.webp" alt="NefuSite Banner" width="600"/>
</div>

<h1 align="center">NefuSite - Proyek Super Hemat 🚀</h1>

<p align="center">
  Sebuah aplikasi web multifungsi yang berfungsi sebagai <strong>CDN (Content Delivery Network)</strong> dan <strong>ShortURL</strong>, dibangun dengan konsep "super hemat" dengan memanfaatkan repositori dan Gist GitHub sebagai "database" gratisnya.
</p>

<p align="center">
  <strong>Creator: LippWangsaff by NefuSoft Team 𖥸</strong>
</p>

---

## 💡 Fitur Utama

-   **🌐 ShortURL**: Persingkat URL panjang menjadi tautan pendek menggunakan domain Anda. Bisa membuat kode acak atau kustom.
-   **🗂️ CDN**: Unggah dan sajikan file apa saja (gambar, video, zip, js, css, dll) langsung dari domain Anda, dengan GitHub sebagai penyimpanannya.
-   **💸 Super Hemat**: Tidak memerlukan database tradisional atau biaya hosting file. Cukup manfaatkan *free tier* dari GitHub dan platform hosting seperti Vercel/Netlify.
-   **✨ Antarmuka Minimalis**: UI yang bersih, modern, dan responsif dengan gaya Neobrutalism.

## 🛠️ Teknologi yang Digunakan

-   **Backend**: Node.js, Express.js
-   **Frontend**: EJS (Embedded JavaScript templates), CSS3, Vanilla JavaScript
-   **"Database"**: GitHub Repository & GitHub Gist
-   **API**: Axios untuk berinteraksi dengan GitHub API

## 📝 Langkah-langkah Instalasi & Konfigurasi

Ikuti langkah-langkah ini dengan detail untuk menjalankan proyek di komputer Anda sendiri!

### **Langkah 1: Persiapan di GitHub 🐙**

Sebelum meng-clone proyek, Anda perlu menyiapkan "database" di akun GitHub Anda.

1.  **Buat Repositori untuk CDN:**
    -   Buat sebuah repositori **publik** baru di GitHub. Contoh nama: `my-cdn-files`.
    -   Repositori ini **biarkan kosong**, tidak perlu `README` atau file lainnya. Repositori inilah yang akan menampung semua file yang Anda unggah.

2.  **Buat Gist untuk ShortURL:**
    -   Pergi ke [gist.github.com](https://gist.github.com).
    -   Buat sebuah Gist **publik** baru.
    -   **Nama File Gist**: `links.json`
    -   **Isi File Gist**:
        ```json
        {}
        ```
    -   Klik "Create public gist". Setelah dibuat, salin **ID Gist** dari URL-nya.
        > Contoh: `https://gist.github.com/LippWangsaff/`**`777ed6bd1adf6b6f2fe892aeeec2e6f6`** -> ID-nya adalah yang dicetak tebal.

3.  **Buat GitHub Personal Access Token (PAT):**
    -   Pergi ke **Settings** > **Developer settings** > **Personal access tokens** > **Tokens (classic)**.
    -   Klik "**Generate new token**" > "**Generate new token (classic)**".
    -   Beri nama token (misal: `nefusite-app`).
    -   Atur **Expiration** sesuai kebutuhan Anda.
    -   Beri izin (**scope**) pada:
        -   `[x] repo` (Untuk mengakses dan menulis ke repositori CDN)
        -   `[x] gist` (Untuk membaca dan menulis ke Gist ShortURL)
    -   Klik "**Generate token**".
    -   **🚨 PENTING:** Salin token yang muncul dan simpan di tempat yang aman. Anda **tidak akan bisa melihatnya lagi** setelah meninggalkan halaman ini!

### **Langkah 2: Konfigurasi Lokal 💻**

Sekarang, kita siapkan proyek di komputer Anda.

1.  **Clone Repositori Proyek:**
    ```bash
    git clone https://github.com/alip-jmbd/NefuSite.git
    ```

2.  **Masuk ke Direktori Proyek:**
    ```bash
    cd NefuSite
    ```
    > Yup, `NamaFolder` di sini adalah `NefuSite`, sesuai dengan nama repositori yang di-clone.

3.  **Buat dan Isi File `.env`:**
    -   Di dalam folder `NefuSite`, Anda akan menemukan file bernama `.env.example`.
    -   Salin file tersebut dan ubah namanya menjadi `.env`.
    -   Buka file `.env` dan isi dengan informasi yang sudah Anda siapkan di Langkah 1.

    ```ini
    # GITHUB CREDENTIALS - WAJIB DIISI
    GITHUB_TOKEN="ghp_TOKEN_GITHUB"
    GITHUB_USER="username-github"
    CDN_REPO="cdn-files" # Nama repo CDN
    GIST_ID="777edxxxxxxx" # ID Gist

    # KONFIGURASI APLIKASI
    APP_DOMAIN="http://localhost:3000"
    ```

4.  **Kustomisasi Tampilan (Opsional):**
    -   Buka file `config.js`.
    -   Ubah nilai-nilai di dalamnya sesuai keinginan Anda untuk mengubah nama situs, gambar profil, banner, dll.

### **Langkah 3: Menjalankan Aplikasi ✨**

Hampir selesai! Tinggal jalankan aplikasinya.

1.  **Instal Semua Dependensi:**
    ```bash
    npm install
    ```

2.  **Jalankan Server:**
    ```bash
    npm start
    ```

3.  **Selesai! 🎉**
    -   Buka browser Anda dan kunjungi [http://localhost:3000](http://localhost:3000).
    -   Aplikasi Anda sekarang sudah berjalan secara lokal!

---

## ☁️ Langkah Mengisi Environment Variables di Vercel

Saat deployment ke Vercel, ikuti langkah-langkah berikut untuk mengisi Key dan Value:

### Langkah 4: Masuk ke Environment Variables

1. Buka dashboard project di [vercel.com](https://vercel.com)
2. Klik menu **Settings**
3. Klik **Environment Variables** di sebelah kiri

### Langkah 5: Tambah Key dan Value Satu Per Satu

Klik tombol **Add New**, lalu isikan:

| Key | Value |
|-----|-------|
| `GITHUB_TOKEN` | `ghp_xxxxx` (contoh: `ghp_5aRu8`) |
| `GITHUB_USER` | `tiyanzxbellas` |
| `CDN_REPO` | `my-cdn-files` |
| `GIST_ID` | `a857...` (contoh: `a857`) |
| `APP_DOMAIN` | `https://namaprojectmu.vercel.app` |

**Untuk setiap Key, pilih Environment:**
- ☑ Production
- ☑ Preview
- ☑ Development

Setelah mengisi satu Key, klik **Add** dan ulangi untuk Key berikutnya.

### Langkah 6: Redeploy

Setelah semua Key dan Value terisi:
1. Buka tab **Deployments**
2. Klik 3 titik (⋯) pada deployment terakhir
3. Pilih **Redeploy**

> ⚠️ **Catatan:** Gunakan token dan Gist ID asli milik kamu, jangan yang contoh. Ganti `APP_DOMAIN` dengan domain Vercel asli kamu setelah deploy selesai!

---

Selamat mencoba dan semoga berhasil dengan proyek super hemat Anda! (´• ω •\`) ♡
