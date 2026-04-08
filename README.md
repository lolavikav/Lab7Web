# Lab7Web
# Nama: Lola Seftyliani
# Nim: 312410339
# Kelas: I24ID
# Matkul: Pemograman Web

# Praktikum Pemrograman Sistem Informasi Portal Berita -Codelgniter 4

## Analisis Struktur Modul Praktikum
## Modul 1: Fondasi MVC & Routing
Di tahap awal, yang jadi fokus utama adalah mengubah cara kerja dari PHP Native ke penggunaan Framework.
- Alurnya: saat user mengakses URL, permintaan tersebut akan diarahkan oleh Routes.php ke Controller, lalu Controller akan memanggil View untuk ditampilkan.
- Penerapannya: membuat Controller bernama Page.php yang digunakan untuk mengatur halaman statis seperti Home, About, dan Contact.
- Hal penting yang dipelajari: logika bisnis sebaiknya tidak ditempatkan di dalam View, tapi dipisahkan agar struktur kode lebih rapi dan mudah dikelola.

## Modul 2: CRUD & Interaksi Database
Di tahap ini, website dikembangkan menjadi lebih dinamis dengan menambahkan fitur pengelolaan data menggunakan MySQL.
Alurnya: dibuat `ArtikelModel.php` yang berfungsi sebagai penghubung antara aplikasi dengan tabel `artikel` di database.
Fitur pada Admin:
- Create: menyediakan form untuk menambahkan data berita baru.
- Read: menampilkan data dari database ke dalam bentuk tabel HTML.
- Update: mengambil data berdasarkan ID untuk kemudian bisa diedit kembali.
- Delete: menghapus data secara permanen dari database.

Konfigurasi: melakukan pengaturan koneksi database melalui file `.env.`
