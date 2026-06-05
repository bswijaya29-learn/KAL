# QR Iteration untuk Matriks $A=\begin{bmatrix}2 & 1\\ 1 & 2\end{bmatrix}$

## 1. Tujuan Algoritma
Algoritma QR iteration digunakan untuk mencari eigenvalue dari sebuah matriks secara bertahap.  
Pada setiap iterasi, matriks dipisahkan menjadi:

$$
A_k = Q_k R_k
$$

lalu dibalik urutannya menjadi:

$$
A_{k+1} = R_k Q_k
$$

Proses ini diulang beberapa kali sampai matriks mendekati bentuk diagonal.

---

## 2. Matriks Awal

Kita mulai dari matriks:

$$
A_0 =
\begin{bmatrix}
2 & 1\\
1 & 2
\end{bmatrix}
$$

Kolom-kolom matriks ini adalah:

$$
c_1 =
\begin{bmatrix}
2\\
1
\end{bmatrix},
\qquad
c_2 =
\begin{bmatrix}
1\\
2
\end{bmatrix}
$$

---

## 3. Langkah QR dengan Gram-Schmidt

Untuk membentuk $Q$ dan $R$, kita gunakan proses Gram-Schmidt.

### Langkah 1: Hitung $r_{11}$
Panjang vektor kolom pertama adalah:

$$
r_{11} = \|c_1\| = \sqrt{2^2 + 1^2} = \sqrt{5}
$$

### Langkah 2: Hitung $q_1$
Vektor satuan pertama:

$$
q_1 = \frac{c_1}{r_{11}}
=
\begin{bmatrix}
\frac{2}{\sqrt{5}}\\
\frac{1}{\sqrt{5}}
\end{bmatrix}
$$

### Langkah 3: Hitung $r_{12}$
Proyeksi kolom kedua ke arah $q_1$:

$$
r_{12} = q_1^T c_2
=
\begin{bmatrix}
\frac{2}{\sqrt{5}} & \frac{1}{\sqrt{5}}
\end{bmatrix}
\begin{bmatrix}
1\\
2
\end{bmatrix}
=
\frac{4}{\sqrt{5}}
$$

### Langkah 4: Hitung $u_2$
Komponen kolom kedua yang tegak lurus terhadap $q_1$:

$$
u_2 = c_2 - r_{12}q_1
$$

$$
u_2 =
\begin{bmatrix}
1\\
2
\end{bmatrix}
-
\frac{4}{\sqrt{5}}
\begin{bmatrix}
\frac{2}{\sqrt{5}}\\
\frac{1}{\sqrt{5}}
\end{bmatrix}
=
\begin{bmatrix}
-\frac{3}{5}\\
\frac{6}{5}
\end{bmatrix}
$$

### Langkah 5: Hitung $r_{22}$
Panjang dari $u_2$ adalah:

$$
r_{22} = \|u_2\|
=
\sqrt{\left(-\frac{3}{5}\right)^2 + \left(\frac{6}{5}\right)^2}
=
\frac{3}{\sqrt{5}}
$$

### Langkah 6: Hitung $q_2$
Vektor satuan kedua:

$$
q_2 = \frac{u_2}{r_{22}}
=
\begin{bmatrix}
-\frac{1}{\sqrt{5}}\\
\frac{2}{\sqrt{5}}
\end{bmatrix}
$$

---

## 4. Matriks $Q$ dan $R$

Dari hasil di atas, diperoleh:

$$
Q =
\begin{bmatrix}
\frac{2}{\sqrt{5}} & -\frac{1}{\sqrt{5}}\\[4pt]
\frac{1}{\sqrt{5}} & \frac{2}{\sqrt{5}}
\end{bmatrix}
$$

dan

$$
R =
\begin{bmatrix}
\sqrt{5} & \frac{4}{\sqrt{5}}\\[4pt]
0 & \frac{3}{\sqrt{5}}
\end{bmatrix}
$$

---

## 5. Iterasi Pertama

QR iteration menghasilkan:

$$
A_1 = RQ
$$

Substitusi bentuk $R$ dan $Q$:

$$
A_1 =
\begin{bmatrix}
\sqrt{5} & \frac{4}{\sqrt{5}}\\[4pt]
0 & \frac{3}{\sqrt{5}}
\end{bmatrix}
\begin{bmatrix}
\frac{2}{\sqrt{5}} & -\frac{1}{\sqrt{5}}\\[4pt]
\frac{1}{\sqrt{5}} & \frac{2}{\sqrt{5}}
\end{bmatrix}
$$

Hasilnya:

$$
A_1 =
\begin{bmatrix}
\frac{14}{5} & \frac{3}{5}\\[4pt]
\frac{3}{5} & \frac{6}{5}
\end{bmatrix}
$$

---

## 6. Bentuk Umum Iterasi ke-$k$

Secara umum, pada iterasi ke-$k$:

$$
A_k = Q_k R_k
$$

lalu:

$$
A_{k+1} = R_k Q_k
$$

Proses ini diulang 10 kali untuk mendapatkan matriks yang semakin mendekati bentuk diagonal.

---

## 7. Interpretasi Hasil

Untuk matriks ini, iterasi QR akan mendekati:

$$
\begin{bmatrix}
3 & 0\\
0 & 1
\end{bmatrix}
$$

karena eigenvalue dari matriks awal adalah:

$$
\lambda^2 - 4\lambda + 3 = 0
$$

$$
(\lambda - 3)(\lambda - 1) = 0
$$

sehingga:

$$
\lambda_1 = 3,\qquad \lambda_2 = 1
$$

Maka diagonal akhir dari iterasi QR merepresentasikan eigenvalue matriks.
# QR Iteration pada Matriks 
# $A=\begin{bmatrix}2 & 1\\1 & 2\end{bmatrix}$

## 1. Tujuan Program

Program ini digunakan untuk melakukan proses **QR Iteration** pada matriks:

$$
A=
\begin{bmatrix}
2 & 1\\
1 & 2
\end{bmatrix}
$$

QR Iteration bertujuan untuk mencari eigenvalue matriks secara numerik.  
Metode ini bekerja dengan cara:

1. Memfaktorkan matriks menjadi:
   
$$
A_k = Q_kR_k
$$

2. Kemudian urutannya dibalik:

$$
A_{k+1}=R_kQ_k
$$

3. Proses diulang berkali-kali hingga matriks mendekati bentuk diagonal.

Diagonal akhir akan mendekati eigenvalue matriks.

---

# 2. Kode Program

```python
from sympy import Matrix, sqrt, simplify, pretty

# Matriks awal
A = Matrix([[2, 1],
            [1, 2]])

# Menyimpan matriks iterasi saat ini
A_k = A.copy()

print("A0 =")
print(pretty(A_k))
print()

# Iterasi sebanyak 10 kali
for k in range(1, 11):

    # Mengambil kolom pertama matriks
    c1 = Matrix([A_k[0, 0],
                 A_k[1, 0]])

    # Mengambil kolom kedua matriks
    c2 = Matrix([A_k[0, 1],
                 A_k[1, 1]])

    # =========================================
    # LANGKAH GRAM-SCHMIDT
    # =========================================

    # Menghitung panjang vektor c1
    r11 = sqrt((c1.T * c1)[0])

    # Membentuk vektor satuan pertama
    q1 = c1 / r11

    # Menghitung proyeksi c2 terhadap q1
    r12 = (q1.T * c2)[0]

    # Menghilangkan komponen c2 yang sejajar q1
    u2 = c2 - r12 * q1

    # Menghitung panjang u2
    r22 = sqrt((u2.T * u2)[0])

    # Membentuk vektor satuan kedua
    q2 = u2 / r22

    # =========================================
    # MEMBENTUK MATRKS Q DAN R
    # =========================================

    Q = Matrix.hstack(q1, q2)

    R = Matrix([
        [r11, r12],
        [0,   r22]
    ])

    # =========================================
    # QR ITERATION
    # =========================================

    A_k = simplify(R * Q)

    print(f"Iterasi {k}")

    print("Q =")
    print(pretty(Q))

    print("R =")
    print(pretty(R))

    print("A_next =")
    print(pretty(A_k))

    print("-"*30)