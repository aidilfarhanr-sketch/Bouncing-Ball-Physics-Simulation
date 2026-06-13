# Simulasi Bola Memantul 2D

Proyek ini merupakan simulasi animasi **bola memantul dalam ruang 2D** menggunakan Python, NumPy, Matplotlib, dan `FuncAnimation`. Simulasi ini menerapkan konsep dasar fisika seperti gravitasi, gesekan lantai, pantulan dinding, tumbukan antar bola, koefisien restitusi, serta perubahan warna bola saat terjadi tabrakan.

Proyek ini dibuat dalam bentuk Jupyter Notebook sehingga cocok digunakan untuk pembelajaran **grafika komputer**, **animasi berbasis Python**, dan **simulasi fisika sederhana**.

---

## Preview Konsep

Simulasi menampilkan dua bola neon yang bergerak di dalam area 2D dengan latar belakang gradien gelap. Bola akan memantul ketika menyentuh dinding, lantai, atau bertabrakan dengan bola lain. Saat dua bola saling bertabrakan, warna bola akan berubah secara otomatis dan efek glow ikut menyesuaikan warna bola tersebut.

---

## Fitur Utama

- Simulasi gerak bola dalam ruang 2D.
- Animasi interaktif menggunakan `matplotlib.animation.FuncAnimation`.
- Penerapan gravitasi pada gerakan bola.
- Penerapan gesekan lantai saat bola menyentuh bagian bawah area simulasi.
- Pantulan bola terhadap dinding kiri, kanan, atas, dan bawah.
- Deteksi tabrakan antar dua bola.
- Perhitungan pantulan menggunakan konsep vektor normal dan tangent.
- Koefisien restitusi untuk mengatur elastisitas pantulan.
- Koreksi posisi agar bola tidak saling menempel setelah tabrakan.
- Perubahan warna bola saat terjadi tabrakan.
- Efek glow neon pada setiap bola.
- Latar belakang gradien gelap agar visual lebih estetis.
- Tampilan animasi langsung di Jupyter Notebook menggunakan HTML/JavaScript.

---

## Teknologi yang Digunakan

- Python
- NumPy
- Matplotlib
- Matplotlib Animation
- IPython Display
- Jupyter Notebook

---

## Struktur File

```text
Simulasi-Bola-Memantul-2D/
│
├── Bola_memantul(1).ipynb
└── README.md
```

---

## Library yang Digunakan

```python
import numpy as np
import matplotlib.pyplot as plt
from matplotlib.animation import FuncAnimation
from IPython.display import HTML, display
```

Keterangan:

- `NumPy` digunakan untuk operasi vektor, posisi, kecepatan, jarak, dan perhitungan fisika.
- `Matplotlib` digunakan untuk membuat area simulasi, objek bola, background, dan visualisasi.
- `FuncAnimation` digunakan untuk membuat animasi frame-by-frame.
- `IPython.display` digunakan untuk menampilkan animasi dalam format HTML di Jupyter Notebook.

---

## Konsep Simulasi

### 1. Area Simulasi

Area simulasi dibuat dalam bidang koordinat 2D dengan batas:

```python
WINDOW_LIMITS = {
    'x': (0, 10),
    'y': (0, 6)
}
```

Bola hanya dapat bergerak di dalam area tersebut. Ketika menyentuh batas area, bola akan memantul kembali.

---

### 2. Gravitasi

Gravitasi diberikan sebagai vektor ke bawah:

```python
GRAVITY = np.array([0, -0.01])
```

Nilai gravitasi akan memengaruhi kecepatan bola setiap frame sehingga bola terlihat jatuh secara alami ke bawah.

---

### 3. Gesekan Lantai

Saat bola menyentuh lantai, kecepatan horizontal bola dikurangi menggunakan nilai gesekan:

```python
FLOOR_FRICTION = 0.95
```

Hal ini membuat gerakan bola menjadi lebih realistis karena bola tidak terus bergerak secara horizontal tanpa pengurangan energi.

---

### 4. Data Bola

Setiap bola memiliki data berupa:

- Posisi awal.
- Kecepatan awal.
- Radius.
- Koefisien restitusi.
- Warna utama.
- Warna alternatif.
- Index warna aktif.

Contoh data bola:

```python
{
    'pos': np.array([2.0, 5.0]),
    'vel': np.array([0.5, 0.0]),
    'radius': 0.5,
    'cor': 0.85,
    'colors': ['#00FFFF', '#FA6D0E'],
    'color_index': 0
}
```

---

### 5. Deteksi Tabrakan Antar Bola

Tabrakan antar bola dihitung berdasarkan jarak antar pusat bola. Jika jarak antar pusat lebih kecil dari jumlah radius kedua bola, maka terjadi tabrakan.

```python
distance < radius_a + radius_b
```

Setelah tabrakan terdeteksi, kecepatan bola dihitung ulang menggunakan konsep vektor normal dan tangent.

---

### 6. Perubahan Warna Saat Tabrakan

Ketika dua bola bertabrakan, warna masing-masing bola akan berubah secara otomatis. Efek glow juga ikut berubah mengikuti warna terbaru bola.

Fitur ini membuat animasi terlihat lebih hidup, interaktif, dan menarik secara visual.

---

## Cara Menjalankan Project

### 1. Clone Repository

```bash
git clone https://github.com/username/Simulasi-Bola-Memantul-2D.git
```

Ganti `username` dengan username GitHub kamu.

---

### 2. Masuk ke Folder Project

```bash
cd Simulasi-Bola-Memantul-2D
```

---

### 3. Install Library yang Dibutuhkan

```bash
pip install numpy matplotlib notebook
```

Jika menggunakan Google Colab, biasanya library utama sudah tersedia dan notebook bisa langsung dijalankan.

---

### 4. Jalankan Notebook

Buka file notebook:

```text
Bola_memantul(1).ipynb
```

Lalu jalankan semua cell dari atas ke bawah menggunakan:

```text
Run All
```

Animasi akan tampil langsung di output notebook.

---

## Output Project

Output dari proyek ini adalah animasi dua bola yang:

- Bergerak dalam bidang 2D.
- Dipengaruhi gravitasi.
- Memantul terhadap dinding dan lantai.
- Mengalami gesekan saat menyentuh lantai.
- Bertabrakan satu sama lain.
- Mengubah warna saat terjadi tabrakan.
- Memiliki efek glow neon.
- Ditampilkan secara interaktif di Jupyter Notebook.

---

## Pembelajaran yang Didapat

Dari proyek ini, beberapa konsep yang dapat dipelajari antara lain:

- Dasar animasi menggunakan Python.
- Penggunaan `FuncAnimation` pada Matplotlib.
- Simulasi gerak dalam bidang 2D.
- Konsep posisi, kecepatan, dan percepatan.
- Konsep gravitasi dalam animasi sederhana.
- Deteksi tumbukan antar objek lingkaran.
- Koefisien restitusi pada pantulan.
- Pemanfaatan vektor normal dan tangent.
- Pembuatan visual yang lebih menarik menggunakan warna neon dan glow effect.

---

## Potensi Pengembangan

Project ini masih dapat dikembangkan lebih lanjut, misalnya:

- Menambahkan lebih banyak bola.
- Menambahkan massa berbeda pada setiap bola.
- Menggunakan rumus momentum untuk massa yang berbeda.
- Menambahkan slider untuk mengatur gravitasi dan gesekan.
- Menambahkan kontrol start, pause, dan reset.
- Menambahkan suara saat bola bertabrakan.
- Menambahkan trail effect pada bola.
- Membuat versi web interaktif menggunakan JavaScript atau Pygame.
- Membuat simulasi dengan banyak partikel.
- Mengoptimalkan deteksi tabrakan menggunakan spatial hashing atau quad-tree.

---

## Author

**Aidil Farhan Rares**

Proyek ini dibuat sebagai latihan simulasi fisika sederhana dan animasi grafika komputer menggunakan Python.

---

## Kesimpulan

Simulasi Bola Memantul 2D ini menunjukkan bagaimana konsep fisika sederhana dapat divisualisasikan menggunakan Python. Dengan kombinasi NumPy, Matplotlib, animasi frame-by-frame, gravitasi, gesekan, tumbukan, perubahan warna, dan efek glow, proyek ini dapat menjadi contoh pembelajaran yang menarik untuk memahami dasar grafika komputer dan simulasi fisika.
