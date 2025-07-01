# BimaMall

BimaMall adalah sebuah platform e-commerce sederhana yang dibuat untuk menampilkan produk digital, memungkinkan pengguna untuk mendaftar, login, dan melihat daftar produk dengan fitur pembelian langsung melalui harga produk. Proyek ini menggunakan teknologi modern untuk frontend, backend, dan database.

---

## Fitur Utama

- **Autentikasi Pengguna**: Sistem login dan pendaftaran dengan validasi.
- **Produk Digital**: Menampilkan 6 produk unggulan dengan harga yang dapat diklik untuk pembelian.
- **Navigasi Dinamis**: Menggunakan Vue Router untuk navigasi antar halaman.
- **Responsif**: Antarmuka yang responsif untuk berbagai perangkat.
- **Manajemen Data**: Data pengguna dan produk tersimpan di MongoDB.

---

## Instalasi dan Penggunaan

Berikut adalah langkah-langkah untuk menjalankan proyek ini secara lokal:

### 1. **Clone Repository**
Clone repository ini ke komputer Anda:
git clone : https://github.com/username/bimamall.git

### 2. **Instalasi Dependensi**
Pastikan Node.js dan npm telah terinstal di sistem Anda. Kemudian, jalankan perintah berikut untuk menginstal semua dependensi: npm install

### 3. **Menjalankan MongoDB**
Pastikan MongoDB sudah berjalan di komputer Anda. Jika belum, jalankan MongoDB dengan perintah berikut (tergantung instalasi Anda): mongod

### 4. **Konfigurasi Database**
Buat file .env di root proyek untuk menyimpan konfigurasi MongoDB Anda: MONGO_URI=mongodb://localhost:27017/bimamall
PORT=5000

### 5. **Menjalankan Server**
Jalankan server backend menggunakan perintah berikut: node server.js

### 6. **Menjalankan Frontend**
Jalankan frontend dengan perintah berikut: npm run dev
Akses aplikasi di http://localhost:5173.


## Fitur Halaman
### 1. Login

Pengguna dapat login dengan email dan password. Validasi input dilakukan sebelum mengirim data ke server.

### 2. Register

Pengguna baru dapat mendaftar dengan email, nama, dan password. Data disimpan di MongoDB.

### 3. Home

Halaman utama menampilkan informasi umum tentang aplikasi.

### 4. Products

Menampilkan daftar 6 produk unggulan dengan nama, gambar, dan harga. Harga produk dapat diklik untuk memulai pembelian.

### 5. Dashboard

Menampilkan daftar harga produk.

### 6. Navigasi

Navigasi antarmuka yang dinamis dengan Vue Router. Header dan Footer digunakan untuk navigasi global.
