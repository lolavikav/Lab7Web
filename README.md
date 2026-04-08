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

## Modul 3: Templating (View Layout & View Cell)
Pada tahap ini, diterapkan prinsip DRY (Don't Repeat Yourself) supaya kode lebih rapi dan tidak berulang-ulang.

Untuk tampilan, digunakan konsep View Layout dengan satu file utama `layout/main.php.` Halaman lain cukup mengisi bagian tertentu saja menggunakan `$this->extend()`, jadi tidak perlu membuat struktur dari awal lagi.

Selain itu, dibuat View Cell berupa komponen modular seperti `ArtikelTerkini`. Komponen ini bisa dipanggil di berbagai halaman tanpa harus menulis ulang query database di setiap Controller.

Manfaatnya, kalau ada perubahan pada bagian seperti Header atau Footer, cukup ubah di satu file saja tanpa harus edit semua halaman.

## Modul 4: Autentikasi & Security Filter
Tahap ini berfokus pada pengamanan area penting seperti Dashboard Admin agar tidak bisa diakses sembarangan.

Alurnya: proses login dilakukan dengan memvalidasi username dan password menggunakan Session.

Pengamanan: diterapkan `AuthFilter.php.` Jika ada user yang mencoba mengakses halaman `/admin` tanpa login, sistem akan otomatis mengarahkan kembali ke halaman `/login.`

Database: dibuat tabel `user` untuk menyimpan data akun dan kredensial admin.

## Modul 5: Optimasi UX (Pagination & Searching)
Tahap ini berfokus pada peningkatan tampilan dan performa saat jumlah data sudah banyak.

- Pagination: penggunaan `findAll()` diganti dengan `paginate(10)` agar data ditampilkan per halaman, sehingga mencegah browser menjadi lambat ketika data sudah sangat banyak.
- Searching: memanfaatkan metode `like()` pada query SQL untuk mencari dan memfilter judul artikel sesuai kata kunci yang dimasukkan user.
- Persistence: menggunakan `pager->only(['q'])` supaya ketika user berpindah halaman (misalnya ke halaman 2), kata kunci pencarian tetap tersimpan dan hasilnya tidak hilang.

## Cara Instalasi Proyek
1. Clone & Setup:
`https://github.com/lolavikav/Lab7Web.git`

2. Database:
   - Buat Database bernama `lab_ci4`
   - import file `.sql` yang ada di folder `database/`
  
3. Environment:
   - Rename `env` menjadi `.env`
   - Atur `database.default.username` dan `databse.default.password` sesuaI XAMPP masing-masing.

4. Run:
 
   ```php spark serve```
   
