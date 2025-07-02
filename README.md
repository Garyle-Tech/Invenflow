# Invenflow - Warehouse Management System

![Invenflow Logo](docs/images/invenflow-logo.png)

Invenflow adalah sistem manajemen gudang (Warehouse Management System) yang komprehensif dengan tiga komponen utama: Mobile Application, Web CMS, dan REST API. Sistem ini dirancang untuk memudahkan pengelolaan inventori, tracking pergerakan barang, dan menghasilkan laporan real-time.

## 🚀 Fitur Utama

### 📱 Mobile Application
- **Login & Authentication** - Sistem autentikasi yang aman untuk pengguna mobile
- **Stock Opname** - Melakukan penghitungan stok fisik dengan scan RFID/Barcode
- **Inbound Management** - Pencatatan barang masuk dengan scan otomatis
- **Outbound Management** - Pencatatan barang keluar dengan validasi stok

### 💻 Web CMS
- **Dashboard** - Overview real-time kondisi gudang
- **Master Data Management**
  - Manajemen Produk (CRUD produk dengan SKU, deskripsi, kategori)
  - Manajemen Gudang (multiple warehouse support)
  - Manajemen Lokasi (rak, slot, area penyimpanan)
  - Manajemen User (role-based access control)
- **Inventory Operations**
  - Penerimaan Barang (Inbound) dengan referensi PO
  - Pengeluaran Barang (Outbound) dengan referensi SO
  - Stock Opname Management
- **Reporting**
  - Laporan stok real-time
  - Riwayat pergerakan barang
  - Export ke Excel/PDF
- **System Configuration**

### 🔧 REST API
- RESTful API untuk integrasi Mobile dan CMS
- Authentication dengan JWT/Sanctum
- Real-time stock synchronization
- Batch processing untuk scan results

## 🛠️ Tech Stack

### Mobile Application
- **Platform**: Android Native
- **Language**: Kotlin
- **UI Framework**: Jetpack Compose
- **Architecture**: Clean Architecture + MVVM
- **Libraries**: 
  - Retrofit untuk networking
  - Hilt untuk dependency injection
  - Room untuk local database
  - CameraX untuk barcode scanning

### Backend (API + CMS)
- **Framework**: Laravel 12
- **Language**: PHP 8.3+
- **Database**: MySQL/PostgreSQL
- **Cache**: Redis
- **Queue**: Laravel Queue
- **Frontend CMS**: Blade Templates + Alpine.js/Livewire

## 📋 Requirements

### Mobile Development
- Android Studio Arctic Fox atau lebih baru
- Android SDK minimum API 24 (Android 7.0)
- Kotlin 1.9+

### Backend Development
- PHP 8.3 atau lebih baru
- Composer 2.x
- MySQL 8.0+ atau PostgreSQL 13+
- Node.js 18+ & NPM
- Redis (optional, untuk caching)

## 🚀 Installation

### laravel-monolith Setup

```bash
# Clone repository
git clone https://github.com/Garyle-Tech/Invenflow.git
cd invenflow/laravel-monolith

# Install dependencies
composer install
npm install

# Setup environment
cp .env.example .env
php artisan key:generate

# Configure database di .env
DB_CONNECTION=mysql/pgsql
DB_HOST=127.0.0.1
DB_PORT=3306/5432
DB_DATABASE=invenflow_db
DB_USERNAME=root
DB_PASSWORD=

# Run migrations
php artisan migrate --seed

# Build assets
npm run build

# Start development server
php artisan serve
```

### Mobile Setup

```bash
cd invenflow/mobile-app

# Buka dengan Android Studio
# Sync gradle dependencies
# Configure API base URL di local.properties atau BuildConfig
# Run aplikasi di emulator atau device
```

## 📱 Usage

### Mobile App
1. Login dengan kredensial yang telah dibuat di CMS
2. Pilih operasi yang diinginkan (Stock Opname/Inbound/Outbound)
3. Scan barcode/RFID produk
4. Konfirmasi dan submit data
5. Data akan tersinkronisasi dengan server

### Web CMS
1. Akses `http://localhost:8000`
2. Login sebagai admin/staff
3. Setup master data (produk, gudang, lokasi)
4. Monitor operasional gudang
5. Generate laporan sesuai kebutuhan

## 🔐 Security

- Authentication menggunakan Laravel Sanctum/JWT
- Role-based access control (Admin & Staff)
- API rate limiting
- HTTPS enforcement di production
- Input validation dan sanitization

## 📊 Excalidraw ...

Lihat [Excalidraw](shared/excalidraw/invenflow.excalidraw).

## 🤝 Contributing

1. Fork repository
2. Buat feature branch (`git checkout -b feature/username-github/AmazingFeature`)
3. Commit changes dengan mengikuti conventional commit (`git commit -m 'feat: Add some AmazingFeature'`)
4. Push ke branch (`git push origin feature/username-github/AmazingFeature`)
5. Buat Pull Request

## 📝 API Documentation

API documentation tersedia di:
- Postman Collection: [shared/api/postman_collection.json](shared/api/postman_collection.json)
- Swagger/OpenAPI (coming soon)

## 🐛 Known Issues

- Lihat [Issues](https://github.com/Garyle-Tech/Invenflow/issues) untuk bug yang diketahui dan feature requests

## 👥 Team

- **Backend Developer**: [Bimo](https://github.com/prmdyabimo)
- **Mobile Developer**: [Prana](https://github.com/prana10)

## 📞 Contact

Garyle Tech - garyletech@gmail.com

Project Link: [https://github.com/Garyle-Tech/Invenflow](https://github.com/Garyle-Tech/Invenflow)