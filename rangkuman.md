# Rangkuman Proyek

Proyek ini terdiri dari dua bagian utama: aplikasi frontend mobile yang dibuat dengan Ionic/Vue.js dan backend API yang dibuat dengan Node.js/Express.

## Frontend (`ionicnewest`)

Aplikasi frontend adalah aplikasi mobile hybrid yang dibangun menggunakan framework Ionic dan Vue.js.

- **Framework**: Ionic dengan Vue.js 3.
- **Routing**: Menggunakan `@ionic/vue-router` untuk navigasi. Aplikasi ini memiliki tata letak berbasis tab.
- **Halaman**:
  - Halaman Login (`LoginPage.vue`)
  - Halaman Registrasi (`RegisterPage.vue`)
  - Halaman untuk membuat postingan (`CreatePostpage.vue`)
  - Tiga halaman tab (`Tab1Page.vue`, `Tab2Page.vue`, `Tab3Page.vue`)
- **Komunikasi dengan Backend**: Menggunakan `axios` untuk membuat permintaan HTTP ke API backend.

## Backend (`myapi`)

Backend adalah sebuah RESTful API yang dibangun dengan Node.js dan framework Express.

- **Framework**: Express.js.
- **Database**: Menggunakan `mysql2` untuk terhubung ke database MySQL bernama `dbapi`.
- **Autentikasi**:
  - Registrasi dan login pengguna dengan password yang di-hash menggunakan `bcrypt`.
  - Beberapa endpoint dilindungi dengan verifikasi token statis (Bearer Token).
- **Endpoint API**:

  - `POST /login`: Untuk login pengguna.
  - `POST /register`: Untuk registrasi pengguna baru.
  - `GET /data`: Mengambil data dari tabel `field_data` (memerlukan autentikasi).
  - `POST /data/post`: Menambahkan data baru ke tabel `field_data` (memerlukan autentikasi).
  - `POST /data/edit/:id`: Mengedit data dari tabel`field_data` (memerlukan autentikasi).
  - `POST /data/delete/:id`: menghapus data dari tabel `field_data` (memerlukan autentikasi).
  - `POST   /data/:id`: Mengambil satu data dari `field_data` untuk memodifikasi, menghapus dan lain lain (memerlukan autentikasi).

  /data/:id

- **Middleware**:
  - `cors`: Untuk mengizinkan permintaan dari domain yang berbeda (misalnya dari aplikasi Ionic yang berjalan di `localhost:8100`).

## Arsitektur Keseluruhan

- **Client**: Aplikasi `ionicnewest` yang berjalan di perangkat pengguna.
- **Server**: Aplikasi `myapi` yang menyediakan data dan layanan untuk aplikasi client.
