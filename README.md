<p align="center">
<a href="https://laravel.com" target="_blank">
<img src="https://raw.githubusercontent.com/laravel/art/master/logo-lockup/5%20SVG/2%20CMYK/1%20Full%20Color/laravel-logolockup-cmyk-red.svg" width="400" alt="Laravel Logo">
</a>
</p>

<p align="center">
<a href="https://github.com/kk-ketua/multi-role-laravel-api/actions"><img src="https://github.com/kk-ketua/multi-role-laravel-api/workflows/tests/badge.svg" alt="Build Status"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://img.shields.io/packagist/dt/laravel/framework" alt="Total Downloads"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://img.shields.io/packagist/v/laravel/framework" alt="Latest Stable Version"></a>
<a href="https://opensource.org/licenses/MIT"><img src="https://img.shields.io/badge/license-MIT-blue" alt="License"></a>
</p>

# Multi-Role Laravel REST API

Project ini adalah **REST API** berbasis Laravel 12 yang mendukung **multi-role authentication** untuk **user** dan **admin**.
Default role saat registrasi adalah `user`. API ini menggunakan **Laravel Sanctum** untuk token-based authentication.

---

## Fitur

- RESTful API untuk **register**, **login**, dan **logout**.  
- **Multi-role support** (`user` dan `admin`).  
- **Role-based middleware** untuk mengatur akses route.  
- Token-based authentication menggunakan **Laravel Sanctum**.  
- Mudah diintegrasikan dengan **SPA** atau **mobile app**.

---

## Instalasi

1. Clone repo:
```bash
git clone https://github.com/kk-ketua/multi-role-laravel-api.git
cd multi-role-laravel-api
```

2. Install dependencies:
```bash
composer install
```

3. Buat file `.env` dan sesuaikan database:
```env
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=multi_role_db
DB_USERNAME=root
DB_PASSWORD=
```

4. Jalankan migration:
```bash
php artisan migrate
```

5. Jalankan server:
```bash
php artisan serve
```

---

## API Endpoints

| Endpoint           | Method | Auth      | Role       | Keterangan                    |
|-------------------|--------|----------|-----------|--------------------------------|
| /api/register      | POST   | No       | -         | Register user baru             |
| /api/login         | POST   | No       | -         | Login user                     |
| /api/logout        | POST   | Yes      | user/admin| Logout dan hapus token         |
| /api/user-only     | GET    | Yes      | user      | Akses khusus user              |
| /api/admin-only    | GET    | Yes      | admin     | Akses khusus admin             |

---

## Struktur Role

- `user` → default saat registrasi. Bisa mengakses route user-only.  
- `admin` → role khusus, bisa mengakses route admin-only.

---

## License

Project ini dilisensikan di bawah **MIT License**. Lihat [LICENSE](LICENSE) untuk detail.

---

💡 **Catatan**: Ini adalah project contoh untuk belajar multi-role REST API di Laravel.  
Kalau Kak Ketua mau, bisa dikembangkan lagi untuk **role lebih banyak**, **permission**, atau **token expiration**. 😏💖
