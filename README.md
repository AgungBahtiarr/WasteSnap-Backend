
# 🧠 WasteSnap Backend

Ini adalah backend dari aplikasi WasteSnap, dibangun menggunakan Node.js dan Express.js. Backend ini menangani autentikasi, manajemen data event, peta lokasi, dan menyediakan REST API yang diakses oleh frontend.

## 🚀 Fitur Utama

- **Autentikasi Pengguna**: Sistem login dan registrasi dengan JWT
- **Manajemen Event**: CRUD operasi untuk data event sampah
- **Manajemen Lokasi**: Pengelolaan data peta dan lokasi tempat sampah
- **Middleware Keamanan**: Otorisasi dan validasi request
- **Database Integration**: Terhubung dengan MySQL menggunakan Sequelize

## 📁 Struktur Folder

```
WasteSnap-Backend-main/
├── config/               # Konfigurasi database
│   └── db.js
├── controllers/          # Logika bisnis dari setiap route
│   ├── authController.js
│   ├── eventController.js
│   └── mapController.js
├── middlewares/          # Middleware untuk validasi & otorisasi
│   └── authMiddleware.js
├── models/               # Model Sequelize untuk MySQL
│   ├── userModel.js
│   ├── eventModel.js
│   └── mapModel.js
├── routes/               # Definisi routing API
│   ├── authRoutes.js
│   ├── eventRoutes.js
│   └── mapRoutes.js
├── .env                  # Variabel lingkungan (jangan commit!)
├── .gitignore           # File yang diabaikan Git
├── server.js            # Entry point server
├── package.json         # Konfigurasi npm dan dependensi
└── README.md            # Dokumentasi proyek
```

## 🛠️ Persyaratan Sistem

- **Node.js** versi 14.x atau lebih baru
- **MySQL** versi terbaru
- **npm** atau **yarn** sebagai package manager

## ⚡ Cara Menjalankan

### 1. Clone Repository
```bash
git clone https://github.com/username/WasteSnap-Backend.git
cd WasteSnap-Backend-main
```

### 2. Install Dependencies
```bash
npm install
```

### 3. Konfigurasi Environment Variables
Buat file `.env` di root folder dengan isi berikut:
```env
PORT=5000
DB_HOST=localhost
DB_USER=root
DB_PASSWORD=your_mysql_password
DB_NAME=wastesnap
JWT_SECRET=your_super_secret_jwt_key_here
NODE_ENV=development
```

### 4. Jalankan MySQL
Pastikan MySQL berjalan di sistem Anda:
```bash
# Untuk Ubuntu/Debian
sudo service mysql start

# Untuk macOS (Homebrew)
brew services start mysql

# Untuk Windows, pastikan MySQL service aktif
```

### 5. Jalankan Server
```bash
# Mode development dengan auto-reload
npm run dev

# Mode production
npm start
```

Server akan berjalan di `http://localhost:5000`

## 📚 API Documentation
[View in Swagger UI](https://petstore.swagger.io/?url=https://raw.githubusercontent.com/Capstone-Project-WasteSnap/WasteSnap-Backend/main/apidoc/Story-api.yaml)

<details>
<summary>🔍 Preview</summary>
  
![API Docs Preview](https://petstore.swagger.io/?url=https://raw.githubusercontent.com/Capstone-Project-WasteSnap/WasteSnap-Backend/main/apidoc/Story-api.yaml&output=image)</details>

## 📬 API Endpoints

### Authentication
| Method | Endpoint | Deskripsi |
|--------|----------|-----------|
| POST | `/api/auth/register` | Registrasi pengguna baru |
| POST | `/api/auth/login` | Login pengguna |
| GET | `/api/auth/profile` | Ambil profil pengguna |

### Events Management
| Method | Endpoint | Deskripsi |
|--------|----------|-----------|
| GET | `/api/events` | Ambil semua event |
| POST | `/api/events` | Tambah event baru |
| GET | `/api/events/:id` | Ambil event berdasarkan ID |
| PUT | `/api/events/:id` | Update event |
| DELETE | `/api/events/:id` | Hapus event |

### Maps & Locations
| Method | Endpoint | Deskripsi |
|--------|----------|-----------|
| GET | `/api/maps` | Ambil semua data lokasi |
| POST | `/api/maps` | Tambah lokasi baru | 
| GET | `/api/maps/:id` | Ambil lokasi berdasarkan ID | 
| PUT | `/api/maps/:id` | Update lokasi |
| DELETE | `/api/maps/:id` | Hapus lokasi |

## 🔧 Scripts NPM

```bash
# Jalankan server dalam mode development
npm run dev

# Jalankan server dalam mode production
npm start

# Jalankan tests
npm test

# Linting kode
npm run lint

# Format kode
npm run format
```

## 🏗️ Tech Stack

- **Runtime**: Node.js
- **Framework**: Express.js
- **Database**: MySQL
- **ORM**: Sequelize
- **Authentication**: JSON Web Token (JWT)
- **Environment**: dotenv
- **Development**: nodemon

## 🤝 Kontribusi

1. Fork repository ini
2. Buat branch untuk fitur baru (`git checkout -b feature/AmazingFeature`)
3. Commit perubahan Anda (`git commit -m 'Add some AmazingFeature'`)
4. Push ke branch (`git push origin feature/AmazingFeature`)
5. Buat Pull Request

## 📋 Panduan Development

### Menambah Endpoint Baru
1. Buat controller di folder `controllers/`
2. Definisikan model di folder `models/` jika diperlukan
3. Tambahkan route di folder `routes/`
4. Import dan gunakan route di `server.js`

### Environment Variables
Jangan lupa menambahkan variabel environment baru ke file `.env.example` untuk dokumentasi.

## 🐛 Troubleshooting

### Port Sudah Digunakan
```bash
# Cek process yang menggunakan port 5000
lsof -i :5000

# Kill process tersebut
kill -9 <PID>
```

### MySQL Connection Error
- Pastikan MySQL service berjalan
- Cek konfigurasi `DB_HOST`, `DB_USER`, `DB_PASSWORD`, dan `DB_NAME` di file `.env`
- Pastikan database `wastesnap` sudah dibuat

### JWT Token Issues
- Pastikan `JWT_SECRET` di `.env` tidak kosong
- Cek format token di header: `Authorization: Bearer <token>`

## 📞 Support

Jika Anda mengalami masalah atau memiliki pertanyaan:

- Hubungi tim development melalui email: wilnaufi@gmail.com

## 📄 Lisensi

Proyek ini dilindungi hak cipta oleh tim WasteSnap. Untuk informasi lisensi dan kontribusi, silakan hubungi pengembang utama.

---

**Dibuat dengan ❤️ oleh Tim WasteSnap**
