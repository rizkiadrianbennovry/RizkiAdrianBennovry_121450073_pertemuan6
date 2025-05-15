
# 📘 Aplikasi Manajemen Matakuliah – REST API dengan Pyramid

Aplikasi ini dirancang untuk mengelola informasi matakuliah menggunakan Pyramid Framework, SQLAlchemy sebagai ORM, dan PostgreSQL sebagai sistem basis data, dengan dukungan penuh terhadap operasi RESTful API CRUD.

## 💡 Fitur yang Tersedia
- Menambahkan data matakuliah (POST)
- Menampilkan semua data matakuliah (GET)
- Mengambil data berdasarkan ID (GET)
- Memperbarui data matakuliah (PUT)
- Menghapus data matakuliah (DELETE)

## ⚙️ Konfigurasi Basis Data
Pastikan file development.ini memiliki pengaturan berikut:

sqlalchemy.url = postgresql://pyramid_user:pyramid_pass@localhost:5432/pyramid_matakuliah

## 🚀 Menjalankan Aplikasi
1. Aktifkan virtual environment:
   .\\venv\\Scripts\\activate

2. Lakukan migrasi skema database:
   alembic -c development.ini upgrade head

3. Jalankan server aplikasi:
   pserve development.ini --reload

Akses endpoint API di: http://localhost:6543/api/matakuliah

## 🔬 Pengujian API Menggunakan Postman

### GET semua matakuliah:
GET http://localhost:6543/api/matakuliah

### POST tambah matakuliah:
POST http://localhost:6543/api/matakuliah
Body JSON:
{
  "kode_mk": "IF101",
  "nama_mk": "Pemrograman Web",
  "sks": 3,
  "semester": 5
}

### GET berdasarkan ID:
GET http://localhost:6543/api/matakuliah/1

### PUT update matakuliah:
PUT http://localhost:6543/api/matakuliah/1
Body JSON:
{
  "nama_mk": "Pemrograman Web Lanjut",
  "sks": 4
}

### DELETE matakuliah:
DELETE http://localhost:6543/api/matakuliah/1

## 📂 Struktur Direktori
pyramid_matakuliah/
├── alembic/
│   └── versions/
├── pyramid_matakuliah/
│   ├── models/
│   ├── views/
│   ├── routes.py
│   └── __init__.py
├── development.ini
├── README.md

## 📌 Hal yang Perlu Diperhatikan
- Pastikan layanan PostgreSQL sudah aktif
- Jalankan proses migrasi sebelum memulai server
- Gunakan Postman Desktop Agent agar dapat mengakses localhost

Selamat berkarya! 🚀
