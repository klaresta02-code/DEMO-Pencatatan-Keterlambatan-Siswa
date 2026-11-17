# Sistem Keterlambatan Siswa - Login Berdasarkan Role

Aplikasi web PHP + MySQL dengan login dan 3 role (admin, guru piket, guru BK).

**Demo online:** https://USERNAME.github.io/NAMA-REPO/
(Ganti `USERNAME` dan `NAMA-REPO` dengan milik Anda. Demo ini versi statis dengan data contoh, jalan di browser tanpa server.)

## Akun

| Role | Username | Password | Halaman |
|------|----------|----------|---------|
| Admin | admin | admin123 | Ringkasan data dan 10 keterlambatan terbaru |
| Guru Piket | piket | piket123 | Catat siswa terlambat dan riwayatnya |
| Guru BK | bk | bk123 | Siswa dengan 3 keterlambatan atau lebih |

Tiap role hanya bisa membuka dashboard miliknya. Membuka dashboard role lain menampilkan "Akses ditolak".

## Struktur

- `docs/index.html` - versi demo statis (dipakai GitHub Pages)
- `*.php`, `style.css` - versi lengkap PHP + MySQL
- `database/keterlabatan_siswa.sql` - struktur database dan akun login

## Menjalankan versi lengkap (PHP + MySQL)

1. Install XAMPP, nyalakan Apache dan MySQL.
2. Salin folder proyek ke `C:\xampp\htdocs\login-keterlambatan`.
3. Di phpMyAdmin, buat database `keterlabatan_siswa`, lalu import `database/keterlabatan_siswa.sql`.
4. Buka `http://localhost/login-keterlambatan/` dan masuk dengan akun di atas.

## Keamanan versi PHP

- Password disimpan dengan `password_hash()` dan dicek dengan `password_verify()`.
- Query memakai prepared statement (PDO).
- Setiap halaman dicek rolenya lewat `wajib_login()` di `auth.php`.
- Output dibersihkan dengan `htmlspecialchars()`.

Catatan: versi demo di `docs/` hanya simulasi untuk peragaan. Pengecekan login di sana berjalan di browser sehingga tidak aman untuk data nyata.
