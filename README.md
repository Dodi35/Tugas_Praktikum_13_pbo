Praktikum 13 – Membangun Aplikasi Multi Komponen (POS) Mata Kuliah Pemrograman Berorientasi Objek – Praktikum (INF2143)

---
Identitas Mahasiswa • Nama : Dodi • NIM : 2411102441035 • Kelas : B

---
Proyek ini merupakan implementasi mini aplikasi Sistem Kasir (Point of Sale / POS) berbasis Python
sebagai simulasi integrasi beberapa komponen perangkat lunak dalam satu aplikasi.
Pengembangan aplikasi ini mengacu pada Modul Praktikum Pertemuan 13 dengan menerapkan prinsip
SOLID, khususnya Single Responsibility Principle (SRP),
Open/Closed Principle (OCP), dan Dependency Inversion Principle (DIP).

Pada proyek ini digunakan kembali abstraksi pembayaran IPaymentProcessor
sebagai penerapan prinsip SOLID yang diadaptasi dari sesi praktikum sebelumnya,
kemudian diintegrasikan ke dalam aplikasi POS sesuai struktur yang ditentukan pada modul.
---
Tujuan Praktikum
Tujuan dari praktikum ini adalah:
1. Membangun mini aplikasi POS berbasis Command Line Interface (CLI)
2. Menerapkan prinsip SOLID dalam pengembangan aplikasi
3. Mengintegrasikan beberapa komponen menggunakan Dependency Injection
4. Membuktikan penerapan Open/Closed Principle pada sistem pembayaran
5. Menerapkan version control dan dokumentasi menggunakan GitHub

Ruang Lingkup Sistem
Aplikasi POS ini memiliki ruang lingkup sebagai berikut:
Menampilkan daftar produk
Menambahkan produk ke dalam keranjang belanja
Menghitung total harga belanja
Melakukan proses pembayaran menggunakan metode pembayaran tertentu

Menampilkan hasil transaksi melalui output terminal

Aplikasi ini tidak terhubung ke database nyata dan hanya menggunakan data simulasi
sesuai kebutuhan praktikum.

---
Struktur Folder Proyek

Struktur folder proyek disusun sesuai dengan instruksi modul sebagai berikut:
.
├── models.py          # Model data (Product dan CartItem)
├── repositories.py    # Penyedia data produk (simulasi database)
├── services.py        # Business logic dan service pembayaran
├── main_app.py        # Orchestrator / aplikasi utama POS
└── README.md          # Dokumentasi proyek

---
Deskripsi Tiap File
models.py
Berisi representasi struktur data aplikasi, seperti produk dan item keranjang.
File ini hanya bertanggung jawab pada model data (SRP).

repositories.py
Berfungsi sebagai penyedia data produk (simulasi database).
Tidak mengandung logika bisnis.

services.py
Berisi logika bisnis aplikasi, termasuk:

Abstraksi IPaymentProcessor

Implementasi metode pembayaran

Service pengelolaan keranjang belanja

main_app.py
Berperan sebagai orchestrator, yaitu mengatur alur aplikasi POS
tanpa mengetahui detail implementasi pembayaran.

---
Prinsip SOLID yang Diterapkan
1. Single Responsibility Principle (SRP)

Setiap class dan file memiliki satu tanggung jawab utama.
Sebagai contoh:

Model hanya menangani data

Service hanya menangani logika bisnis

Aplikasi utama hanya mengatur alur program

2. Open/Closed Principle (OCP)

Sistem pembayaran dirancang agar dapat diperluas tanpa mengubah kode yang sudah ada.
Metode pembayaran baru dapat ditambahkan dengan membuat class baru
yang mengimplementasikan interface IPaymentProcessor.

3. Dependency Inversion Principle (DIP)

Aplikasi utama tidak bergantung pada implementasi konkret metode pembayaran,
melainkan bergantung pada abstraksi IPaymentProcessor.
Dependency Injection digunakan untuk menyuntikkan implementasi pembayaran ke dalam aplikasi.

---
Cara Menjalankan Program
Pastikan Python versi 3.x sudah terinstal
Buka folder proyek di terminal atau Visual Studio Code
Jalankan perintah berikut:

---
python main_app.py

---
Contoh Output Program
Berikut contoh output ketika program dijalankan:
=== DAFTAR PRODUK ===
1. Laptop - Rp8000000
2. Mouse - Rp150000
3. Keyboard - Rp300000
Pilih ID produk: 2
[CART] Added: Mouse (1 pcs)
Total belanja: Rp150000
Processing Debit Card Payment
Transaksi berhasil!

Output tersebut menunjukkan bahwa aplikasi berhasil:
Menampilkan produk
Menambahkan produk ke keranjang
Menghitung total belanja
Melakukan pembayaran

---
Version Control
Proyek ini dikelola menggunakan Git dan diunggah ke GitHub
sebagai bagian dari penerapan version control sesuai dengan instruksi modul praktikum.
Riwayat commit digunakan sebagai bukti proses pengembangan aplikasi.

---
Kesimpulan
Mini aplikasi POS ini berhasil mengintegrasikan beberapa komponen perangkat lunak
dengan struktur yang rapi dan modular.
Penerapan prinsip SOLID membuat aplikasi lebih mudah dikembangkan,
dipelihara, dan diperluas di masa mendatang.