# Business Intelligence Inventory System

## Deskripsi

Proyek ini adalah implementasi sistem Business Intelligence untuk manajemen inventory menggunakan data warehouse. Sistem ini dirancang untuk menganalisis data inventory, penjualan, dan supply chain menggunakan dimensi seperti produk, gudang, supplier, dan waktu. Menggunakan MySQL sebagai database utama dan Pentaho Data Integration (PDI) untuk proses ETL (Extract, Transform, Load).

## Struktur Data Warehouse

Data warehouse ini menggunakan skema star dengan tabel dimensi dan fact table berikut:

### Dimensi Tables
- **dim_gudang**: Informasi gudang (ID gudang, alamat gudang)
- **dim_produk**: Detail produk (ID produk, nama produk, kategori, harga satuan, status)
- **dim_supplier**: Data supplier (ID supplier, nama supplier)
- **dim_waktu**: Dimensi waktu (date key, tanggal, tahun, bulan, hari, kuartal)

### Fact Table
- **fact_inventaris**: Data inventory utama yang menghubungkan semua dimensi dengan metrik seperti:
  - Jumlah stok
  - Level reorder
  - Volume penjualan
  - Rasio perputaran
  - Estimasi nilai stok

## File Pentaho ETL

- `UAS BI JOB.kjb`: Job utama yang mengorkestrasi semua transformasi ETL
- `uas bi- 1.ktr` sampai `uas bi- 5.ktr`: Transformasi individual untuk memproses data dari berbagai sumber

## Setup dan Instalasi

### Persyaratan Sistem
- MySQL 8.0 atau versi yang kompatibel
- Pentaho Data Integration (PDI) Spoon
- phpMyAdmin atau tool database management lainnya

### Langkah Setup
1. **Setup Database**:
   - Buat database baru dengan nama `dw_inventory`
   - Import struktur tabel dari file `dw_inventory-structur.sql`
   - Import data sample dari file `dw_inventory_data.sql`

2. **Setup Pentaho**:
   - Buka Pentaho Data Integration (Spoon)
   - Load job file `UAS BI JOB.kjb`
   - Konfigurasi koneksi database sesuai dengan setup MySQL Anda
   - Jalankan job untuk memproses data ETL

3. **Data Sample**:
   - File CSV (`dim_gudang.csv`, `dim_produk.csv`, dll.) berisi data sample untuk testing
   - `Grocery_Inventory new v1.csv`: Data inventory utama

## Penggunaan

1. Jalankan job Pentaho untuk memuat dan mentransformasi data ke data warehouse
2. Query data warehouse untuk analisis BI menggunakan SQL atau tools reporting
3. Gunakan metrik dari fact_inventaris untuk dashboard inventory management

## Teknologi yang Digunakan

- **Database**: MySQL 8.0
- **ETL Tool**: Pentaho Data Integration (PDI)
- **Data Format**: CSV untuk data source, SQL untuk database dumps
- **Database Management**: phpMyAdmin

## Kontribusi

Untuk berkontribusi pada proyek ini:
1. Fork repository
2. Buat branch fitur baru
3. Commit perubahan
4. Push ke branch
5. Buat Pull Request

## Lisensi

Proyek ini dibuat untuk tujuan edukasi dan akademik.