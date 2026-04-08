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

## HASIL PRAKTIKUM NYA
1. TAMPILAN HOME USER:
<img width="1076" height="950" alt="Screenshot 2026-04-07 224047" src="https://github.com/user-attachments/assets/12054fec-7f96-4a0c-8185-e7034202246e" />

TAMPILAN ARTIKEL:
<img width="1412" height="898" alt="Screenshot 2026-04-07 224114" src="https://github.com/user-attachments/assets/f69615ee-a24c-4bc8-b936-6e01a46b47ae" />

TAMPILAN ABOUT:
<img width="1496" height="916" alt="Screenshot 2026-04-07 224133" src="https://github.com/user-attachments/assets/ed8c0fea-3bfc-4270-9687-337dfdb85e85" />

TAMPILAN CONTACT:
<img width="1619" height="937" alt="Screenshot 2026-04-07 224155" src="https://github.com/user-attachments/assets/92ed0e77-f056-40a6-94b0-a5ab80d36b1a" />

2. DASHBOARD ADMIN:
<img width="1417" height="944" alt="Screenshot 2026-04-07 232052" src="https://github.com/user-attachments/assets/b284c40e-0943-415a-814f-6507ed4af24d" />

TAMPILAN TAMBAH ARTIKEL:
<img width="1373" height="930" alt="Screenshot 2026-04-07 224302" src="https://github.com/user-attachments/assets/00af3328-c788-46ff-b890-027dc212360c" />

TAMPILAH UBAH ARTIKEL:
<img width="1369" height="890" alt="Screenshot 2026-04-07 224323" src="https://github.com/user-attachments/assets/b0f7c5d1-75f3-4f08-b17f-e94fe881e485" />

TAMPILAN HALAMAN LOGIN:
<img width="1139" height="887" alt="Screenshot 2026-04-07 224358" src="https://github.com/user-attachments/assets/990779e6-1be7-43b6-b42e-47078bbc8468" />







   
