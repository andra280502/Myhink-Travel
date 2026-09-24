✈️ Myhink Travel

Sistem Informasi Operasional Terpadu (Reservasi, Penyewaan Armada, dan Point of Sale)

📌 Deskripsi Proyek

Myhink Travel adalah aplikasi berbasis web yang dibangun menggunakan framework Laravel untuk mendigitalisasi proses bisnis agen perjalanan. Sistem ini mengintegrasikan tiga modul utama: transaksi kasir offline (POS), reservasi paket open trip, dan manajemen penyewaan armada kendaraan pariwisata dalam satu dashboard yang terpusat.

Proyek ini dikembangkan sebagai pemenuhan Tugas/Asistensi Praktikum Pemrograman Web.

🚀 Fitur Utama & Progres Pengembangan

1. Modul Point of Sale (POS) & Kasir

[ ] Manajemen katalog suvenir dan tiket on-the-spot.

[ ] Keranjang belanja (Cart) dan kalkulasi total harga otomatis.

[ ] Pembuatan struk digital (E-Receipt) atau faktur pembayaran.

2. Modul Pemesanan Paket Wisata (Open Trip)

[ ] Manajemen CRUD katalog paket wisata.

[ ] Sistem potong kuota peserta otomatis saat terjadi pemesanan.

[ ] Riwayat booking pelanggan.

3. Modul Penyewaan Armada (Rental)

[ ] Manajemen data inventaris kendaraan (Hiace, Elf, dll).

[ ] Pengecekan ketersediaan armada berdasarkan rentang tanggal (date range).

[ ] Ubah status kendaraan (Tersedia / Sedang Disewa) untuk mencegah double booking.

🗄️ Struktur Database Utama

Aplikasi ini menggunakan desain database relasional dengan tabel inti sebagai berikut:

users : Mengelola hak akses (Admin, Kasir, Pelanggan).

paket_wisatas : Menyimpan data destinasi, harga, dan sisa kuota.

armadas : Menyimpan inventaris kendaraan pariwisata beserta status ketersediaannya.

produk_p_o_s : Menyimpan data barang fisik (suvenir/tiket).

transaksis : Tabel sentral yang merekam aktivitas reservasi, penyewaan, maupun penjualan POS.

🛠️ Prasyarat Sistem (Prerequisites)

Sebelum menjalankan aplikasi ini, pastikan sistem Anda telah memasang perangkat lunak berikut:

PHP (Minimal versi 8.1)

Composer (Dependency Manager untuk PHP)

MySQL atau PostgreSQL (Database)

Node.js & NPM (Untuk kompilasi asset frontend)

⚙️ Panduan Instalasi (Installation Guide)

Ikuti langkah-langkah di bawah ini untuk menjalankan aplikasi di environment lokal (localhost):

Clone Repositori:

git clone https://github.com/andra280502/Myhink-Travel.git
cd Myhink-Travel


Install Dependensi PHP & Frontend:

composer install
npm install
npm run build


Konfigurasi Environment:
Salin file konfigurasi bawaan dan sesuaikan kredensial database Anda.

cp .env.example .env


Buka file .env dan atur bagian ini sesuai database lokal Anda:

DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=myhink_travel
DB_USERNAME=root
DB_PASSWORD=


Generate Application Key & Migrasi Database:

php artisan key:generate
php artisan migrate


Jalankan Aplikasi:

php artisan serve


Aplikasi dapat diakses melalui browser pada http://localhost:8000.

📸 Tampilan Antarmuka (Screenshots)

(Screenshot halaman Dashboard, Kasir, dan Halaman Utama akan ditambahkan di sini setelah tahap pengembangan UI selesai).

👨‍💻 Dikembangkan Oleh

Andra Syailendra Perdana - 2318901

Mahasiswa Teknik Informatika
