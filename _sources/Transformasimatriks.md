# Transformasi Matriks

## 1. Pengertian Dasar Transformasi Matriks

Transformasi matriks adalah proses pemetaan atau perubahan koordinat suatu vektor (atau titik) dalam ruang menggunakan operasi perkalian matriks. Secara umum, persamaannya ditulis sebagai:

$$ \mathbf{y} = A \mathbf{x} $$

*   $A$ = Matriks transformasi
*   $\mathbf{x}$ = Vektor atau titik awal
*   $\mathbf{y}$ = Vektor atau titik hasil transformasi

## 2. Refleksi (Pencerminan) terhadap Sumbu Y

Refleksi adalah transformasi yang membalikkan objek melintasi suatu garis atau bidang. Dalam ruang 2D, jika kita melakukan pencerminan terhadap **Sumbu Y**, nilai koordinat sumbu $X$ akan berbalik tanda (menjadi negatifnya), sedangkan nilai koordinat sumbu $Y$ akan tetap sama.

Matriks transformasi standar untuk refleksi terhadap sumbu Y adalah:

$$ M_y = \begin{bmatrix} -1 & 0 \\ 0 & 1 \end{bmatrix} $$

## 3. Pembuktian Matematis Refleksi Sumbu Y

Misalkan kita memiliki titik awal $\mathbf{x} = \begin{bmatrix} x \\ y \end{bmatrix}$. Jika titik tersebut dikalikan dengan matriks refleksi sumbu Y ($M_y$), perhitungannya adalah:

$$ \begin{bmatrix} x' \\ y' \end{bmatrix} = \begin{bmatrix} -1 & 0 \\ 0 & 1 \end{bmatrix} \begin{bmatrix} x \\ y \end{bmatrix} $$

Melalui operasi perkalian baris kali kolom:

$$ \begin{bmatrix} x' \\ y' \end{bmatrix} = \begin{bmatrix} (-1 \cdot x) + (0 \cdot y) \\ (0 \cdot x) + (1 \cdot y) \end{bmatrix} $$

$$ \begin{bmatrix} x' \\ y' \end{bmatrix} = \begin{bmatrix} -x \\ y \end{bmatrix} $$

Sesuai dengan logika geometri visual: titik yang berada di sebelah kanan sumbu Y akan berpindah ke kiri, dan titik di sebelah kiri akan berpindah ke kanan, sementara ketinggian vertikalnya tetap.

## 4. Contoh Perhitungan Sederhana

Misalkan kita memiliki sebuah titik koordinat di $A(3, 5)$. Kita ingin mencari titik bayangannya ($A'$) setelah dicerminkan terhadap sumbu Y.

Representasi vektor awal:
$$ \mathbf{x} = \begin{bmatrix} 3 \\ 5 \end{bmatrix} $$

Maka hasil transformasinya:
$$ \mathbf{y} = \begin{bmatrix} -1 & 0 \\ 0 & 1 \end{bmatrix} \begin{bmatrix} 3 \\ 5 \end{bmatrix} = \begin{bmatrix} -3 \\ 5 \end{bmatrix} $$

Jadi, titik $A(3, 5)$ berpindah ke $A'(-3, 5)$.

## 5. Implementasi pada Bangun Datar (Matriks Koordinat)

Dalam grafika komputer atau geometri komputasional, kita jarang memproses titik satu per satu. Jika ingin merefleksikan sebuah bangun utuh, kita bisa menyusun semua titiknya ke dalam satu matriks besar dan mengalikannya sekaligus.

Misalkan kita memiliki bangun dengan tiga titik sudut: $P(1, 2)$, $Q(4, 2)$, dan $R(2, 5)$. Kita susun matriks $\mathbf{X}$ (baris atas adalah $X$, baris bawah adalah $Y$):

$$ \mathbf{X} = \begin{bmatrix} 1 & 4 & 2 \\ 2 & 2 & 5 \end{bmatrix} $$

Kalikan matriks refleksi $M_y$ dengan matriks koordinat $\mathbf{X}$:

$$ \mathbf{Y} = \begin{bmatrix} -1 & 0 \\ 0 & 1 \end{bmatrix} \begin{bmatrix} 1 & 4 & 2 \\ 2 & 2 & 5 \end{bmatrix} $$

$$ \mathbf{Y} = \begin{bmatrix} -1 & -4 & -2 \\ 2 & 2 & 5 \end{bmatrix} $$

Koordinat bayangan bangun tersebut terbentuk di $P'(-1, 2)$, $Q'(-4, 2)$, dan $R'(-2, 5)$.

## 6. Sifat Penting dari Matriks Refleksi

*   **Pembalikan Orientasi (Orientation Reversing):** Transformasi refleksi mengubah arah orientasi objek. Jika kamu membaca teks pada objek asli dari kiri ke kanan, pada hasil refleksinya teks akan terbalik (seperti efek di depan cermin).
*   **Determinan Negatif:** Matriks refleksi murni selalu memiliki nilai determinan $-1$.
  $$ \det(M_y) = (-1)(1) - (0)(0) = -1 $$
  Tanda minus inilah yang secara aljabar melambangkan bahwa orientasi ruang telah dibalik. 
*   **Luas dan Jarak Tetap (Isometri):** Karena nilai absolut determinannya adalah $|-1| = 1$, matriks ini hanya memindahkan titik tanpa menskalakan, merusak, atau mengubah luas area bangun aslinya.

# Visual dari transformasi matriks
link di bawah ini merupakan code python yang akan memvisualisasikan mattriksnya cara pemakaiannya bisa ke terminal atau ke code editor yang ada 
catatan: code python ini tidak bisa di jalankan di google collab dikarenakan collab tidak mampu memvisualisasikan 

[https://drive.google.com/drive/folders/1VVVGQYT29kh6HSrfapJJFawRbhlifkyJ?usp=drive_link]

# 📘 Panduan Menjalankan Aplikasi

## 2D Vector Engine: Reflection & Translation

---

## 🧾 Deskripsi

Aplikasi ini merupakan program berbasis **Python + PyQt5** yang digunakan untuk memvisualisasikan transformasi geometri 2D, khususnya:

* Refleksi terhadap sumbu Y
* Translasi (pergeseran posisi bangun)
* Manipulasi titik secara interaktif (drag & drop)

Aplikasi menampilkan bangun (polygon) berdasarkan titik-titik yang diinput oleh pengguna, serta hasil transformasinya secara real-time.

---

## ⚙️ Kebutuhan Sistem

Pastikan sistem memiliki:

* Python 3.x
* Terminal / Command Prompt
* Sistem operasi dengan GUI (Windows/Linux/Mac)

---

## 📦 Instalasi Dependency

Install library yang dibutuhkan dengan perintah berikut:

```bash
pip install numpy matplotlib PyQt5
```

Jika menggunakan multiple Python version:

```bash
py -m pip install numpy matplotlib PyQt5
```

---

## 📂 Struktur File

Pastikan file utama tersedia, misalnya:

```
main.py
```

---

## ▶️ Cara Menjalankan Program

### 1. Buka Terminal / CMD

### 2. Masuk ke folder yang berisi file .py 

```bash
cd  "tempat file nya"
```

### 3. Jalankan program

```bash
python transformasimatriks.py
```

atau:

```bash
py transformasimatriks.py
```

---

## 🖥️ Tampilan Aplikasi

Setelah dijalankan, akan muncul window GUI yang terdiri dari:

* Panel kiri → Input & kontrol
* Panel kanan → Grafik kartesius

---

## 🧩 Cara Menggunakan Aplikasi

### 🔹 1. Mengatur Jumlah Titik

Gunakan **spin box** untuk menentukan jumlah titik yang membentuk bangun.

---

### 🔹 2. Input Koordinat

Masukkan nilai:

* Kolom X → koordinat sumbu X
* Kolom Y → koordinat sumbu Y

Bangun akan otomatis terbentuk pada grafik.

---

### 🔹 3. Visualisasi Bangun

* Garis biru → bangun asli
* Garis merah putus-putus → hasil refleksi (sumbu Y)

---

### 🔹 4. Translasi (Navigasi)

Gunakan tombol:

| Tombol | Fungsi         |
| ------ | -------------- |
| ▲      | Geser ke atas  |
| ▼      | Geser ke bawah |
| ◀      | Geser ke kiri  |
| ▶      | Geser ke kanan |

Semua titik akan berpindah sesuai arah.

---

### 🔹 5. Drag & Drop Titik

* Klik titik pada grafik
* Tahan dan geser
* Bangun akan berubah
* Refleksi ikut menyesuaikan secara real-time

---

## 🔄 Konsep Transformasi

### Refleksi Sumbu Y

Transformasi yang digunakan:

```
(x, y) → (-x, y)
```

Matriks:

```
[-1  0]
[ 0  1]
```

---

### Translasi

Perpindahan posisi titik:

```
(x, y) → (x + dx, y + dy)
```

---

## ⚠️ Troubleshooting

### ❌ Program tidak jalan

* Pastikan Python sudah terinstall
* Cek dengan:

```bash
python --version
```

---

### ❌ ModuleNotFoundError

Install ulang dependency:

```bash
pip install numpy matplotlib PyQt5
```

---

### ❌ Tidak muncul GUI

Kemungkinan:

* Menjalankan di Google Colab (tidak didukung)
* Environment tidak memiliki GUI

---

### ❌ File tidak ditemukan

Gunakan:

```bash
dir
```

untuk memastikan file `transformasimatriks.py` ada di folder tersebut.

---

## 🚫 Catatan Penting

Aplikasi ini **tidak dapat dijalankan di Google Colab** karena membutuhkan GUI desktop.

---

## 🎯 Kesimpulan

Aplikasi ini memungkinkan pengguna untuk:

* Memvisualisasikan bangun 2D
* Melakukan refleksi dan translasi
* Berinteraksi langsung dengan titik

Program dijalankan melalui terminal menggunakan perintah:

```bash
python transformasimatriks.py
```

---

## 📌 Saran Pengembangan

* Menambahkan rotasi dan scaling
* Auto-scaling grafik
* Export hasil ke file
* Upgrade ke versi berbasis web (Streamlit)

---
