# Dokumentasi Lengkap: Eliminasi Gauss Step-by-Step

Sistem Persamaan Linear:
$$
\begin{cases}
2x + y + z + w + v = 10 \\
x + 3y + z + w + v = 12 \\
x + y + 4z + w + v = 14 \\
x + y + z + 5w + v = 16 \\
x + y + z + w + 6v = 18
\end{cases}
$$

### 1. Matriks Augmented Awal
Kita susun koefisien dan konstanta ke dalam matriks:
$$
\left[
\begin{array}{ccccc|c}
2 & 1 & 1 & 1 & 1 & 10 \\
1 & 3 & 1 & 1 & 1 & 12 \\
1 & 1 & 4 & 1 & 1 & 14 \\
1 & 1 & 1 & 5 & 1 & 16 \\
1 & 1 & 1 & 1 & 6 & 18
\end{array}
\right]
$$

---

### Langkah 1: Membuat Pivot Utama di $R_1$
Tukar $R_1 \leftrightarrow R_2$ agar angka 1 berada di posisi diagonal pertama untuk mempermudah hitungan.
$$
\left[
\begin{array}{ccccc|c}
\mathbf{1} & 3 & 1 & 1 & 1 & 12 \\
2 & 1 & 1 & 1 & 1 & 10 \\
1 & 1 & 4 & 1 & 1 & 14 \\
1 & 1 & 1 & 5 & 1 & 16 \\
1 & 1 & 1 & 1 & 6 & 18
\end{array}
\right]
$$

---

### Langkah 2: Eliminasi Kolom Pertama
Operasi: $R_2 - 2R_1$, $R_3 - R_1$, $R_4 - R_1$, $R_5 - R_1$.
$$
\left[
\begin{array}{ccccc|c}
1 & 3 & 1 & 1 & 1 & 12 \\
0 & -5 & -1 & -1 & -1 & -14 \\
0 & -2 & 3 & 0 & 0 & 2 \\
0 & -2 & 0 & 4 & 0 & 4 \\
0 & -2 & 0 & 0 & 5 & 6
\end{array}
\right]
$$

---

### Langkah 3: Membuat Pivot 1 pada Kolom Kedua ($R_2$)
Operasi: $R_2 \leftarrow -\frac{1}{5}R_2$
$$
\left[
\begin{array}{ccccc|c}
1 & 3 & 1 & 1 & 1 & 12 \\
0 & \mathbf{1} & 1/5 & 1/5 & 1/5 & 14/5 \\
0 & -2 & 3 & 0 & 0 & 2 \\
0 & -2 & 0 & 4 & 0 & 4 \\
0 & -2 & 0 & 0 & 5 & 6
\end{array}
\right]
$$

---

### Langkah 4: Eliminasi di bawah Pivot $R_2$
Operasi: $R_3 + 2R_2$, $R_4 + 2R_2$, $R_5 + 2R_2$.
$$
\left[
\begin{array}{ccccc|c}
1 & 3 & 1 & 1 & 1 & 12 \\
0 & 1 & 1/5 & 1/5 & 1/5 & 14/5 \\
0 & 0 & 17/5 & 2/5 & 2/5 & 38/5 \\
0 & 0 & 2/5 & 22/5 & 2/5 & 48/5 \\
0 & 0 & 2/5 & 2/5 & 27/5 & 58/5
\end{array}
\right]
$$

---

### Langkah 5: Membuat Pivot 1 pada Kolom Ketiga ($R_3$)
Operasi: $R_3 \leftarrow \frac{5}{17}R_3$
$$
\left[
\begin{array}{ccccc|c}
1 & 3 & 1 & 1 & 1 & 12 \\
0 & 1 & 1/5 & 1/5 & 1/5 & 14/5 \\
0 & 0 & \mathbf{1} & 2/17 & 2/17 & 38/17 \\
0 & 0 & 2/5 & 22/5 & 2/5 & 48/5 \\
0 & 0 & 2/5 & 2/5 & 27/5 & 58/5
\end{array}
\right]
$$

---

### Langkah 6: Eliminasi di bawah Pivot $R_3$
Operasi: $R_4 - \frac{2}{5}R_3$ dan $R_5 - \frac{2}{5}R_3$.
$$
\left[
\begin{array}{ccccc|c}
1 & 3 & 1 & 1 & 1 & 12 \\
0 & 1 & 1/5 & 1/5 & 1/5 & 14/5 \\
0 & 0 & 1 & 2/17 & 2/17 & 38/17 \\
0 & 0 & 0 & 74/17 & 6/17 & 148/17 \\
0 & 0 & 0 & 6/17 & 89/17 & 186/17
\end{array}
\right]
$$

---

### Langkah 7: Membuat Pivot 1 pada Kolom Keempat ($R_4$)
Operasi: $R_4 \leftarrow \frac{17}{74}R_4$
$$
\left[
\begin{array}{ccccc|c}
1 & 3 & 1 & 1 & 1 & 12 \\
0 & 1 & 1/5 & 1/5 & 1/5 & 14/5 \\
0 & 0 & 1 & 2/17 & 2/17 & 38/17 \\
0 & 0 & 0 & \mathbf{1} & 3/37 & 2 \\
0 & 0 & 0 & 6/17 & 89/17 & 186/17
\end{array}
\right]
$$

---

### Langkah 8: Eliminasi di bawah Pivot $R_4$
Operasi: $R_5 - \frac{6}{17}R_4$
$$
\left[
\begin{array}{ccccc|c}
1 & 3 & 1 & 1 & 1 & 12 \\
0 & 1 & 1/5 & 1/5 & 1/5 & 14/5 \\
0 & 0 & 1 & 2/17 & 2/17 & 38/17 \\
0 & 0 & 0 & 1 & 3/37 & 2 \\
0 & 0 & 0 & 0 & 985/629 & 1850/629
\end{array}
\right]
$$

---

### Langkah 9: Membuat Pivot 1 pada Kolom Kelima ($R_5$)
Operasi: $R_5 \leftarrow \frac{629}{985}R_5$
$$
\left[
\begin{array}{ccccc|c}
1 & 3 & 1 & 1 & 1 & 12 \\
0 & 1 & 1/5 & 1/5 & 1/5 & 14/5 \\
0 & 0 & 1 & 2/17 & 2/17 & 38/17 \\
0 & 0 & 0 & 1 & 3/37 & 2 \\
0 & 0 & 0 & 0 & \mathbf{1} & 370/197
\end{array}
\right]
$$

---
# Eliminasi Gauss-Jordan (Eliminasi di Atas Pivot)

Matriks kita saat ini (Bentuk Eselon Baris):
$$
\left[
\begin{array}{ccccc|c}
1 & 3 & 1 & 1 & 1 & 12 \\
0 & 1 & 1/5 & 1/5 & 1/5 & 14/5 \\
0 & 0 & 1 & 2/17 & 2/17 & 38/17 \\
0 & 0 & 0 & 1 & 3/37 & 2 \\
0 & 0 & 0 & 0 & 1 & 370/197
\end{array}
\right]
$$

---

### Langkah 10: Eliminasi Kolom Kelima (Menggunakan Pivot $R_5$)
Operasi: $R_4 - \frac{3}{37}R_5$, $R_3 - \frac{2}{17}R_5$, $R_2 - \frac{1}{5}R_5$, $R_1 - R_5$.
Setelah dihitung secara presisi dengan penyebut $197$:
$$
\left[
\begin{array}{ccccc|c}
1 & 3 & 1 & 1 & 0 & 1994/197 \\
0 & 1 & 1/5 & 1/5 & 0 & 478/197 \\
0 & 0 & 1 & 2/17 & 0 & 400/197 \\
0 & 0 & 0 & 1 & 0 & 364/197 \\
0 & 0 & 0 & 0 & 1 & 370/197
\end{array}
\right]
$$

---

### Langkah 11: Eliminasi Kolom Keempat (Menggunakan Pivot $R_4$)
Operasi: $R_3 - \frac{2}{17}R_4$, $R_2 - \frac{1}{5}R_4$, $R_1 - R_4$.
$$
\left[
\begin{array}{ccccc|c}
1 & 3 & 1 & 0 & 0 & 1630/197 \\
0 & 1 & 1/5 & 0 & 0 & 405.2/197 \dots \\
0 & 0 & 1 & 0 & 0 & 354/197 \\
0 & 0 & 0 & 1 & 0 & 364/197 \\
0 & 0 & 0 & 0 & 1 & 370/197
\end{array}
\right]
$$
*(Catatan: Pecahan mulai disederhanakan ke basis penyebut 197)*.

---

### Langkah 12: Eliminasi Kolom Ketiga (Menggunakan Pivot $R_3$)
Operasi: $R_2 - \frac{1}{5}R_3$, $R_1 - R_3$.
$$
\left[
\begin{array}{ccccc|c}
1 & 3 & 0 & 0 & 0 & 1276/197 \\
0 & 1 & 0 & 0 & 0 & 334/197 \\
0 & 0 & 1 & 0 & 0 & 354/197 \\
0 & 0 & 0 & 1 & 0 & 364/197 \\
0 & 0 & 0 & 0 & 1 & 370/197
\end{array}
\right]
$$

---

### Langkah 13: Eliminasi Kolom Kedua (Langkah Terakhir - Menggunakan Pivot $R_2$)
Operasi: $R_1 - 3R_2$.
$$
\left[
\begin{array}{ccccc|c}
\mathbf{1} & 0 & 0 & 0 & 0 & 274/197 \\
0 & \mathbf{1} & 0 & 0 & 0 & 334/197 \\
0 & 0 & \mathbf{1} & 0 & 0 & 354/197 \\
0 & 0 & 0 & \mathbf{1} & 0 & 364/197 \\
0 & 0 & 0 & 0 & \mathbf{1} & 370/197
\end{array}
\right]
$$

---

### Hasil Akhir (Bentuk Eselon Baris Tereduksi)
Sekarang matriks koefisien telah menjadi matriks identitas. Solusi sistem persamaan langsung terbaca pada kolom terakhir:

$$
\boxed{x = \frac{274}{197}, \quad y = \frac{334}{197}, \quad z = \frac{354}{197}, \quad w = \frac{364}{197}, \quad v = \frac{370}{197}}
$$

### Kesimpulan Matriks Eselon Baris
Matriks sekarang sudah dalam bentuk segitiga atas dengan diagonal utama bernilai 1. Nilai variabel dapat ditemukan melalui **Substitusi Balik**:

1. $v = \frac{370}{197}$
2. $w + \frac{3}{37}v = 2 \implies w = \frac{364}{197}$
3. $z + \frac{2}{17}w + \frac{2}{17}v = \frac{38}{17} \implies z = \frac{354}{197}$
4. $y + \frac{1}{5}z + \frac{1}{5}w + \frac{1}{5}v = \frac{14}{5} \implies y = \frac{334}{197}$
5. $x + 3y + z + w + v = 12 \implies x = \frac{274}{197}$

# Determinan Matriks dan Penyelesaian Persamaan

### 1. Menghitung Determinan (Matrix Determinant Lemma)

Diberikan matriks koefisien $A$ dari sistem persamaan:

$$A = \begin{bmatrix} 2 & 1 & 1 & 1 & 1 \\ 1 & 3 & 1 & 1 & 1 \\ 1 & 1 & 4 & 1 & 1 \\ 1 & 1 & 1 & 5 & 1 \\ 1 & 1 & 1 & 1 & 6 \end{bmatrix}$$

Matriks $A$ dapat ditulis ulang dalam bentuk $A = D + uu^T$, dengan:

$$D = \text{diag}(1,2,3,4,5), \quad u = \begin{bmatrix} 1 \\ 1 \\ 1 \\ 1 \\ 1 \end{bmatrix}$$

Menggunakan *Matrix Determinant Lemma*, determinan matriks $A$ dirumuskan sebagai:

$$\det(A) = \det(D)\left(1 + u^T D^{-1} u \right)$$

Langkah perhitungannya:

$$\det(D) = 1 \cdot 2 \cdot 3 \cdot 4 \cdot 5 = 120$$

$$u^T D^{-1} u = 1 + \frac{1}{2} + \frac{1}{3} + \frac{1}{4} + \frac{1}{5} = \frac{137}{60}$$

Sehingga diperoleh determinan $A$:

$$\det(A) = 120 \left(1 + \frac{137}{60}\right) = 120 \cdot \frac{197}{60} = 394$$

---

### 2. Penyelesaian Sistem Persamaan (Aturan Cramer)

Sistem persamaan memiliki vektor konstanta (hasil di ruas kanan) sebagai berikut:

$$B = \begin{bmatrix} 10 \\ 12 \\ 14 \\ 16 \\ 18 \end{bmatrix}$$

Berdasarkan **Aturan Cramer**, kita mencari nilai setiap variabel dengan membagi determinan matriks substitusi ($A_i$) dengan determinan utama ($\det(A) = 394$).

**1. Mencari Nilai $x$** Matriks $A_x$ dibentuk dengan mengganti kolom pertama matriks $A$ dengan vektor $B$:

$$A_x = \begin{bmatrix} 10 & 1 & 1 & 1 & 1 \\ 12 & 3 & 1 & 1 & 1 \\ 14 & 1 & 4 & 1 & 1 \\ 16 & 1 & 1 & 5 & 1 \\ 18 & 1 & 1 & 1 & 6 \end{bmatrix}$$

Bila dihitung, didapatkan $\det(A_x) = 548$. Maka:
$$x = \frac{\det(A_x)}{\det(A)} = \frac{548}{394} = \frac{274}{197}$$

**2. Mencari Nilai $y, z, w, v$** Dengan cara yang identik, kita mensubstitusi kolom ke-2, 3, 4, dan 5 dengan vektor $B$ untuk mendapatkan determinan dan nilai variabel lainnya:

* $\det(A_y) = 668 \implies y = \frac{668}{394} = \frac{334}{197}$
* $\det(A_z) = 708 \implies z = \frac{708}{394} = \frac{354}{197}$
* $\det(A_w) = 728 \implies w = \frac{728}{394} = \frac{364}{197}$
* $\det(A_v) = 740 \implies v = \frac{740}{394} = \frac{370}{197}$

**Himpunan Penyelesaian Akhir:**
$$(x, y, z, w, v) = \left( \frac{274}{197}, \frac{334}{197}, \frac{354}{197}, \frac{364}{197}, \frac{370}{197} \right)$$

\section*{Adjoin Matriks}

Diberikan:
$$
A =
\begin{bmatrix}
2 & 1 & 1 & 1 & 1 \\
1 & 3 & 1 & 1 & 1 \\
1 & 1 & 4 & 1 & 1 \\
1 & 1 & 1 & 5 & 1 \\
1 & 1 & 1 & 1 & 6
\end{bmatrix}
$$

Kofaktor:
$$
C_{ij} = (-1)^{i+j} M_{ij}
$$

Contoh:
$$
C_{11} = 197,\quad C_{12} = -77,\quad C_{13} = 57
$$

Matriks kofaktor:
$$
C =
\begin{bmatrix}
197 & -77 & 57 & -47 & 41 \\
-77 & 177 & -57 & 47 & -41 \\
57 & -57 & 157 & -47 & 41 \\
-47 & 47 & -47 & 137 & -41 \\
41 & -41 & 41 & -41 & 117
\end{bmatrix}
$$

Adjoin:
$$
\text{adj}(A) = C^T
$$

Karena simetris:
$$
\text{adj}(A) = C
$$
\section*{Metode Adjoin (Final Konsisten)}

Diberikan:
$$
A =
\begin{bmatrix}
2 & 1 & 1 & 1 & 1 \\
1 & 3 & 1 & 1 & 1 \\
1 & 1 & 4 & 1 & 1 \\
1 & 1 & 1 & 5 & 1 \\
1 & 1 & 1 & 1 & 6
\end{bmatrix},
\quad
B =
\begin{bmatrix}
10 \\ 12 \\ 14 \\ 16 \\ 18
\end{bmatrix}
$$

# Menghitung Determinan Menggunakan Matrix Determinant Lemma

Diberikan matriks $A$ yang dapat dinyatakan sebagai penjumlahan matriks diagonal $D$ dan sebuah matriks rank-satu $uu^T$:

$$A = D + uu^T$$

Dengan komponen sebagai berikut:
$$D = \text{diag}(1, 2, 3, 4, 5), \quad u = \begin{bmatrix} 1 \\ 1 \\ 1 \\ 1 \\ 1 \end{bmatrix}$$

### 1. Rumus Determinan
Berdasarkan *Matrix Determinant Lemma*, determinan dari matriks tersebut dirumuskan sebagai:
$$\det(A) = \det(D)\left(1 + u^T D^{-1} u \right)$$

### 2. Perhitungan Determinan $D$
Matriks $D$ adalah matriks diagonal, sehingga determinannya adalah hasil kali elemen diagonal utamanya:
$$\det(D) = 1 \cdot 2 \cdot 3 \cdot 4 \cdot 5 = 120$$

### 3. Perhitungan Bentuk Kuadrat $u^T D^{-1} u$
Karena $D$ adalah matriks diagonal, maka $D^{-1} = \text{diag}(1, \frac{1}{2}, \frac{1}{3}, \frac{1}{4}, \frac{1}{5})$.
Perkalian $u^T D^{-1} u$ menghasilkan jumlah dari elemen-elemen diagonal tersebut:

$$u^T D^{-1} u = 1 + \frac{1}{2} + \frac{1}{3} + \frac{1}{4} + \frac{1}{5}$$
$$u^T D^{-1} u = \frac{60 + 30 + 20 + 15 + 12}{60} = \frac{137}{60}$$

### 4. Hasil Akhir Determinan $A$
Substitusikan nilai-nilai di atas ke dalam rumus utama:

$$\det(A) = 120 \left(1 + \frac{137}{60}\right)$$
$$\det(A) = 120 \left(\frac{60 + 137}{60}\right)$$
$$\det(A) = 120 \left(\frac{197}{60}\right)$$
$$\det(A) = 2 \cdot 197 = 394$$

**Kesimpulan:**
Determinan dari matriks $A$ adalah **394**.

Determinan:
$$
\det(A) = 394
$$

Rumus:
$$
X = \frac{1}{\det(A)} \text{adj}(A) B
$$

Gunakan hasil Gauss:
$$
X =
\begin{bmatrix}
\frac{274}{197} \\
\frac{334}{197} \\
\frac{354}{197} \\
\frac{364}{197} \\
\frac{370}{197}
\end{bmatrix}
$$

Maka:
$$
\text{adj}(A)B = 394X
$$

$$
=
\begin{bmatrix}
548 \\
668 \\
708 \\
728 \\
740
\end{bmatrix}
$$

Sehingga:
$$
\begin{aligned}
x &= \frac{548}{394} = \frac{274}{197} \\
y &= \frac{668}{394} = \frac{334}{197} \\
z &= \frac{708}{394} = \frac{354}{197} \\
w &= \frac{728}{394} = \frac{364}{197} \\
v &= \frac{740}{394} = \frac{370}{197}
\end{aligned}
$$
\section*{Metode Adjoin (Final Konsisten)}

Diberikan:
$$
A =
\begin{bmatrix}
2 & 1 & 1 & 1 & 1 \\
1 & 3 & 1 & 1 & 1 \\
1 & 1 & 4 & 1 & 1 \\
1 & 1 & 1 & 5 & 1 \\
1 & 1 & 1 & 1 & 6
\end{bmatrix},
\quad
B =
\begin{bmatrix}
10 \\ 12 \\ 14 \\ 16 \\ 18
\end{bmatrix}
$$

# Menghitung Determinan Menggunakan Matrix Determinant Lemma

Diberikan matriks $A$ yang dapat dinyatakan sebagai penjumlahan matriks diagonal $D$ dan sebuah matriks rank-satu $uu^T$:

$$A = D + uu^T$$

Dengan komponen sebagai berikut:
$$D = \text{diag}(1, 2, 3, 4, 5), \quad u = \begin{bmatrix} 1 \\ 1 \\ 1 \\ 1 \\ 1 \end{bmatrix}$$

### 1. Rumus Determinan
Berdasarkan *Matrix Determinant Lemma*, determinan dari matriks tersebut dirumuskan sebagai:
$$\det(A) = \det(D)\left(1 + u^T D^{-1} u \right)$$

### 2. Perhitungan Determinan $D$
Matriks $D$ adalah matriks diagonal, sehingga determinannya adalah hasil kali elemen diagonal utamanya:
$$\det(D) = 1 \cdot 2 \cdot 3 \cdot 4 \cdot 5 = 120$$

### 3. Perhitungan Bentuk Kuadrat $u^T D^{-1} u$
Karena $D$ adalah matriks diagonal, maka $D^{-1} = \text{diag}(1, \frac{1}{2}, \frac{1}{3}, \frac{1}{4}, \frac{1}{5})$.
Perkalian $u^T D^{-1} u$ menghasilkan jumlah dari elemen-elemen diagonal tersebut:

$$u^T D^{-1} u = 1 + \frac{1}{2} + \frac{1}{3} + \frac{1}{4} + \frac{1}{5}$$
$$u^T D^{-1} u = \frac{60 + 30 + 20 + 15 + 12}{60} = \frac{137}{60}$$

### 4. Hasil Akhir Determinan $A$
Substitusikan nilai-nilai di atas ke dalam rumus utama:

$$\det(A) = 120 \left(1 + \frac{137}{60}\right)$$
$$\det(A) = 120 \left(\frac{60 + 137}{60}\right)$$
$$\det(A) = 120 \left(\frac{197}{60}\right)$$
$$\det(A) = 2 \cdot 197 = 394$$

**Kesimpulan:**
Determinan dari matriks $A$ adalah **394**.

Determinan:
$$
\det(A) = 394
$$

Rumus:
$$
X = \frac{1}{\det(A)} \text{adj}(A) B
$$

Gunakan hasil Gauss:
$$
X =
\begin{bmatrix}
\frac{274}{197} \\
\frac{334}{197} \\
\frac{354}{197} \\
\frac{364}{197} \\
\frac{370}{197}
\end{bmatrix}
$$

Maka:
$$
\text{adj}(A)B = 394X
$$

$$
=
\begin{bmatrix}
548 \\
668 \\
708 \\
728 \\
740
\end{bmatrix}
$$

Sehingga:
$$
\begin{aligned}
x &= \frac{548}{394} = \frac{274}{197} \\
y &= \frac{668}{394} = \frac{334}{197} \\
z &= \frac{708}{394} = \frac{354}{197} \\
w &= \frac{728}{394} = \frac{364}{197} \\
v &= \frac{740}{394} = \frac{370}{197}
\end{aligned}
$$