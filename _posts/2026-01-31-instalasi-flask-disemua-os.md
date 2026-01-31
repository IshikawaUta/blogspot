---
title: Panduan Lengkap Instalasi Flask di Windows, macOS, dan Linux
layout: post
date: 2026-01-31T12:39:08+07:00
categories:
  - Tutorial
image: https://images.unsplash.com/photo-1498050108023-c5249f4df085
---
Flask adalah micro-framework berbasis Python yang ringan namun sangat bertenaga untuk membangun aplikasi web. Artikel ini akan membimbing Anda melakukan instalasi dari nol hingga berhasil membuat website pertama Anda.

### Persyaratan Sistem
Sebelum memulai, pastikan perangkat Anda memenuhi syarat minimum:
* **Python >= 3.8**
* **Pip** (Package Installer untuk Python)
* **Virtual Environment** (Sangat direkomendasikan untuk isolasi proyek)

---

### 1. Instalasi Berdasarkan Sistem Operasi

### **Windows**
1. Unduh installer dari [python.org](https://www.python.org/).
2. Saat instalasi, **pastikan centang "Add Python to PATH"**.
3. Buka PowerShell atau CMD, cek instalasi dengan: `python --version`.

### **macOS**
Gunakan Homebrew untuk instalasi Python versi terbaru:
```bash
brew install python

```

### **Linux (Ubuntu/Debian)**

Jalankan perintah berikut di terminal:

```bash
sudo apt update
sudo apt install python3 python3-pip python3-venv

```

---

### 2. Menyiapkan Lingkungan Proyek (Virtual Environment)

Sangat disarankan untuk tidak menginstal Flask secara global agar tidak bentrok dengan proyek lain.

1. Buat folder proyek: `mkdir my-flask-site && cd my-flask-site`
2. Buat environment:
* **Windows:** `python -m venv venv`
* **macOS/Linux:** `python3 -m venv venv`


3. Aktifkan environment:
* **Windows:** `venv\Scripts\activate`
* **macOS/Linux:** `source venv/bin/activate`



Setelah aktif, terminal Anda akan menampilkan tanda `(venv)`.

---

### 3. Menginstal Flask dan Membuat Website Pertama

### Langkah 1: Instal Flask

Gunakan pip untuk mengunduh Flask ke dalam environment Anda:

```bash
pip install Flask

```

### Langkah 2: Buat Kode Aplikasi

Buat file baru bernama `app.py` di dalam folder proyek Anda, lalu masukkan kode berikut:

```python
from flask import Flask, render_template

app = Flask(__name__)

@app.route("/")
def hello_world():
    return "<h1>Halo, Developer Muda!</h1><p>Selamat datang di website Flask pertama saya.</p>"

if __name__ == "__main__":
    app.run(debug=True)

```

### Langkah 3: Jalankan Server Lokal

Kembali ke terminal, jalankan aplikasi Anda:

```bash
python app.py

```

Buka browser dan akses `http://127.0.0.1:5000`. Selamat! Aplikasi Flask Anda sudah berjalan.

---

### 4. Menggunakan Template (Opsi Lanjutan)

Agar kode lebih rapi, Flask menggunakan engine template bernama **Jinja2**.

1. Buat folder bernama `templates`.
2. Di dalamnya, buat file `index.html`:
```html
<h1>Halo, {{ name }}!</h1>

```


3. Ubah `app.py` Anda:
```python
@app.route("/")
def index():
    return render_template('index.html', name='Developer Muda')

```



---

### Kesimpulan

Instalasi Flask sangat cepat karena sifatnya yang minimalis. Anda memiliki kontrol penuh atas komponen apa saja yang ingin ditambahkan ke dalam aplikasi Anda. Siap untuk membangun API atau web app impian Anda?

<div class="back-navigation">
  <a href="{{ '/' | relative_url }}" class="btn-back">
    <i class="fa-solid fa-arrow-left"></i> Kembali ke Beranda
  </a>
</div>