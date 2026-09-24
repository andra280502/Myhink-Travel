<div align="center">
  
  <img src="https://capsule-render.vercel.app/api?type=waving&color=38B2AC&height=150&section=header&text=Myhink%20Travel&fontSize=50&fontAlignY=35&animation=twinkling&fontColor=ffffff" width="100%" />

  # ✈️ Myhink Travel Application
  **Sistem Informasi Operasional Terpadu (Reservasi, Penyewaan Armada, dan Point of Sale)**

  [![Laravel](https://img.shields.io/badge/Laravel-FF2D20?style=for-the-badge&logo=laravel&logoColor=white)](https://laravel.com)
  [![PHP](https://img.shields.io/badge/PHP-777BB4?style=for-the-badge&logo=php&logoColor=white)](https://www.php.net/)
  [![MySQL](https://img.shields.io/badge/MySQL-005C84?style=for-the-badge&logo=mysql&logoColor=white)](https://www.mysql.com/)
  [![TailwindCSS](https://img.shields.io/badge/Tailwind_CSS-38B2AC?style=for-the-badge&logo=tailwind-css&logoColor=white)](https://tailwindcss.com/)
  
  *Proyek ini dikembangkan sebagai pemenuhan Tugas/Asistensi Praktikum Pemrograman Web.*

</div>

<br />

<details>
  <summary>📝 <b>Daftar Isi (Table of Contents)</b></summary>
  <ol>
    <li><a href="#-deskripsi-proyek">Deskripsi Proyek</a></li>
    <li><a href="#-fitur-unggulan">Fitur Unggulan</a></li>
    <li><a href="#-arsitektur-database-erd">Arsitektur Database (ERD)</a></li>
    <li><a href="#-prasyarat-sistem">Prasyarat Sistem</a></li>
    <li><a href="#-panduan-instalasi">Panduan Instalasi</a></li>
    <li><a href="#-galeri-antarmuka">Galeri Antarmuka</a></li>
    <li><a href="#-pengembang">Pengembang</a></li>
  </ol>
</details>

---

## 📌 Deskripsi Proyek
**Myhink Travel** adalah aplikasi berbasis web yang dirancang untuk mendigitalisasi proses bisnis agen perjalanan secara terpusat (*All-in-One Dashboard*). Sistem ini mengintegrasikan tiga modul utama yang saling mendukung: transaksi kasir *offline* (POS), reservasi paket *open trip*, dan manajemen penyewaan armada kendaraan pariwisata.

Pendekatan *multi-module* ini dibuat untuk mencegah terjadinya redudansi data, mencegah *double-booking* pada penyewaan kendaraan, serta mempermudah rekapitulasi pendapatan kasir secara *real-time*.

## 🚀 Fitur Unggulan

<div align="center">

| 🛒 Modul Point of Sale (POS) | 🏖️ Modul Open Trip | 🚐 Modul Rental Armada |
| :--- | :--- | :--- |
| - Manajemen inventaris suvenir<br>- Kalkulasi transaksi *real-time*<br>- Cetak struk/E-Receipt kasir<br>- Auto-potong stok | - CRUD Katalog paket wisata<br>- Manajemen kuota peserta<br>- Cek ketersediaan tiket<br>- Riwayat pemesanan *user* | - Manajemen data kendaraan<br>- Cek status ketersediaan armada<br>- Sistem *lock* tanggal sewa<br>- Hitung otomatis biaya sewa |

</div>

## 📊 Arsitektur Database (ERD)
*Skema relasi database di bawah ini digenerate secara dinamis menggunakan Mermaid.js:*

```mermaid
erDiagram
    TRANSAKSI ||--o{ PAKET_WISATA : "memesan"
    TRANSAKSI ||--o{ ARMADA : "menyewa"
    TRANSAKSI ||--o{ PRODUK_POS : "membeli"
    
    TRANSAKSI {
        bigint id PK
        string kode_transaksi
        string nama_pelanggan
        enum jenis_transaksi "Reservasi, Rental, POS"
        bigint paket_wisata_id FK
        bigint armada_id FK
        bigint produk_pos_id FK
        int qty
        int total_harga
        enum status_pembayaran
    }
    
    PAKET_WISATA {
        bigint id PK
        string nama_paket
        int harga
        int kuota_peserta
    }
    
    ARMADA {
        bigint id PK
        string nama_kendaraan
        string plat_nomor
        int harga_sewa_per_hari
        enum status "Tersedia, Disewa"
    }
    
    PRODUK_POS {
        bigint id PK
        string nama_produk
        int harga
        int stok
    }
