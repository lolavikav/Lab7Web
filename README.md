# Lab7Web
# Nama: Lola Seftyliani
# Nim: 312410339
# Kelas: I24ID
# Matkul: Pemograman Web

# Praktikum Pemrograman Sistem Informasi Portal Berita -Codelgniter 4

## Analisis Struktur Modul Praktikum
Di tahap awal, yang jadi fokus utama adalah mengubah cara kerja dari PHP Native ke penggunaan Framework.
- Alurnya: saat user mengakses URL, permintaan tersebut akan diarahkan oleh Routes.php ke Controller, lalu Controller akan memanggil View untuk ditampilkan.
- Penerapannya: membuat Controller bernama Page.php yang digunakan untuk mengatur halaman statis seperti Home, About, dan Contact.
- Hal penting yang dipelajari: logika bisnis sebaiknya tidak ditempatkan di dalam View, tapi dipisahkan agar struktur kode lebih rapi dan mudah dikelola.
