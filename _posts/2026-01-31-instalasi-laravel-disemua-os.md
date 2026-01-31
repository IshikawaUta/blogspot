---
title: Panduan Lengkap Instalasi Laravel 12 di Windows, macOS, dan Linux
layout: post
date: '2026-01-31 12:39:08'
categories:
- Tutorial
image: https://images.unsplash.com/photo-1498050108023-c5249f4df085
---

Laravel 12 hadir dengan berbagai peningkatan performa dan fitur baru yang memudahkan developer. Artikel ini akan membimbing Anda melakukan instalasi dari nol hingga berhasil membuat website pertama.

### Persyaratan Sistem
Sebelum memulai, pastikan perangkat Anda memenuhi syarat minimum:
* **PHP >= 8.3**
* **Composer** (Dependency Manager untuk PHP)
* **Database** (MySQL, PostgreSQL, atau SQLite)

---

### 1. Instalasi Berdasarkan Sistem Operasi

### **Windows**
Cara termudah di Windows adalah menggunakan **Laravel Herd** atau **XAMPP**.
1. Unduh dan instal [Laravel Herd](https://herd.laravel.com) (Sangat direkomendasikan karena sudah termasuk PHP dan Composer).
2. Jika menggunakan XAMPP, pastikan ekstensi `mbstring`, `openssl`, dan `curl` sudah aktif di `php.ini`.

### **macOS**
Gunakan **Laravel Herd** untuk pengalaman "zero-config" atau menggunakan Homebrew:
```bash
brew install php composer
```

### **Linux (Ubuntu/Debian)**

Jalankan perintah berikut di terminal:

```bash
sudo apt update
sudo apt install php php-cli php-common php-xml php-zip php-mysql php-mbstring curl unzip
# Instal Composer
curl -sS [https://getcomposer.org/installer](https://getcomposer.org/installer) | php
sudo mv composer.phar /usr/local/bin/composer
```

---

### 2. Menginstal Laravel Installer

Setelah Composer terpasang, instal Laravel secara global agar Anda bisa menggunakan perintah `laravel new`:

```bash
composer global require laravel/installer
```

*Pastikan direktori bin composer sudah masuk ke dalam `$PATH` sistem Anda.*

---

### 3. Membuat Website Pertama Anda

Sekarang, mari kita buat proyek pertama kita bernama `my-awesome-site`.

### Langkah 1: Buat Proyek Baru

Buka terminal/command prompt dan ketik:

```bash
laravel new my-awesome-site
```

Anda akan diberikan beberapa pilihan:

* **Starter Kit:** Pilih `Breeze` (untuk login/register sederhana) atau `None`.
* **Database:** Pilih `SQLite` jika ingin cepat tanpa setting database server.

### Langkah 2: Jalankan Server Lokal

Masuk ke direktori proyek dan jalankan server pengembangan:

```bash
cd my-awesome-site
php artisan serve
```

Buka browser dan akses `http://127.0.0.1:8000`. Selamat! Anda sudah melihat halaman sambutan Laravel.

---

### 4. Membuat Halaman "Hello World"

Mari kita modifikasi sedikit untuk membuat halaman kustom.

### Edit Route

Buka file `routes/web.php` dan ubah isinya menjadi:

```php
use Illuminate\Support\Facades\Route;

Route::get('/', function () {
    return view('welcome', ['name' => 'Developer Muda']);
});
```

### Edit Tampilan (Blade)

Buka file `resources/views/welcome.blade.php`. Cari bagian body dan tambahkan:

```html
<h1>Halo, {{ $name }}! Selamat datang di website Laravel pertama saya.</h1>
```

---

### Kesimpulan

Instalasi Laravel 12 kini jauh lebih mudah dengan alat seperti Herd. Dengan struktur folder yang rapi dan ekosistem yang luas, Anda siap membangun aplikasi web yang luar biasa.

<div class="back-navigation">
  <a href="{{ '/' | relative_url }}" class="btn-back">
    <i class="fa-solid fa-arrow-left"></i> Kembali ke Beranda
  </a>
</div>
