# Eliminasi Gauss

### 1. Sistem Persamaan Linear
Diberikan sistem persamaan berikut:

$$
\begin{cases}
x_1 + x_2 + x_3 + x_4 + x_5 = 15 \\
2x_1 + x_2 + x_3 + x_4 + x_5 = 16 \\
x_1 + 2x_2 + x_3 + x_4 + x_5 = 17 \\
x_1 + x_2 + 2x_3 + x_4 + x_5 = 18 \\
x_1 + x_2 + x_3 + 2x_4 + x_5 = 19
\end{cases}
$$

### 2. Matriks Augmented Awal
Bentuk matriks dari sistem persamaan di atas:

$$
\left[ \begin{array}{ccccc|c}
1 & 1 & 1 & 1 & 1 & 15 \\
2 & 1 & 1 & 1 & 1 & 16 \\
1 & 2 & 1 & 1 & 1 & 17 \\
1 & 1 & 2 & 1 & 1 & 18 \\
1 & 1 & 1 & 2 & 1 & 19
\end{array} \right]
$$

### 3. Proses Eliminasi Gauss

**Langkah 1:** $R_2 - 2R_1, R_3 - R_1, R_4 - R_1, R_5 - R_1$
$$
\left[ \begin{array}{ccccc|c}
1 & 1 & 1 & 1 & 1 & 15 \\
0 & -1 & -1 & -1 & -1 & -14 \\
0 & 1 & 0 & 0 & 0 & 2 \\
0 & 0 & 1 & 0 & 0 & 3 \\
0 & 0 & 0 & 1 & 0 & 4
\end{array} \right]
$$

**Langkah 2:** $R_2 = -R_2$
$$
\left[ \begin{array}{ccccc|c}
1 & 1 & 1 & 1 & 1 & 15 \\
0 & 1 & 1 & 1 & 1 & 14 \\
0 & 1 & 0 & 0 & 0 & 2 \\
0 & 0 & 1 & 0 & 0 & 3 \\
0 & 0 & 0 & 1 & 0 & 4
\end{array} \right]
$$

**Langkah 3:** $R_3 = R_3 - R_2$
$$
\left[ \begin{array}{ccccc|c}
1 & 1 & 1 & 1 & 1 & 15 \\
0 & 1 & 1 & 1 & 1 & 14 \\
0 & 0 & -1 & -1 & -1 & -12 \\
0 & 0 & 1 & 0 & 0 & 3 \\
0 & 0 & 0 & 1 & 0 & 4
\end{array} \right]
$$

**Langkah 4:** $R_3 = -R_3$
$$
\left[ \begin{array}{ccccc|c}
1 & 1 & 1 & 1 & 1 & 15 \\
0 & 1 & 1 & 1 & 1 & 14 \\
0 & 0 & 1 & 1 & 1 & 12 \\
0 & 0 & 1 & 0 & 0 & 3 \\
0 & 0 & 0 & 1 & 0 & 4
\end{array} \right]
$$

**Langkah 5:** $R_4 = R_4 - R_3$
$$
\left[ \begin{array}{ccccc|c}
1 & 1 & 1 & 1 & 1 & 15 \\
0 & 1 & 1 & 1 & 1 & 14 \\
0 & 0 & 1 & 1 & 1 & 12 \\
0 & 0 & 0 & -1 & -1 & -9 \\
0 & 0 & 0 & 1 & 0 & 4
\end{array} \right]
$$

**Langkah 6:** $R_4 = -R_4$
$$
\left[ \begin{array}{ccccc|c}
1 & 1 & 1 & 1 & 1 & 15 \\
0 & 1 & 1 & 1 & 1 & 14 \\
0 & 0 & 1 & 1 & 1 & 12 \\
0 & 0 & 0 & 1 & 1 & 9 \\
0 & 0 & 0 & 1 & 0 & 4
\end{array} \right]
$$

**Langkah 7:** $R_5 = R_5 - R_4$
$$
\left[ \begin{array}{ccccc|c}
1 & 1 & 1 & 1 & 1 & 15 \\
0 & 1 & 1 & 1 & 1 & 14 \\
0 & 0 & 1 & 1 & 1 & 12 \\
0 & 0 & 0 & 1 & 1 & 9 \\
0 & 0 & 0 & 0 & -1 & -5
\end{array} \right]
$$

**Langkah 8:** $R_5 = -R_5$
$$
\left[ \begin{array}{ccccc|c}
1 & 1 & 1 & 1 & 1 & 15 \\
0 & 1 & 1 & 1 & 1 & 14 \\
0 & 0 & 1 & 1 & 1 & 12 \\
0 & 0 & 0 & 1 & 1 & 9 \\
0 & 0 & 0 & 0 & 1 & 5
\end{array} \right]
$$

### 4. Hasil Akhir (Reduced Row Echelon Form)
Setelah proses substitusi balik (atau Eliminasi Gauss-Jordan secara penuh), didapatkan matriks identitas:

$$
\left[ \begin{array}{ccccc|c}
1 & 0 & 0 & 0 & 0 & 1 \\
0 & 1 & 0 & 0 & 0 & 2 \\
0 & 0 & 1 & 0 & 0 & 3 \\
0 & 0 & 0 & 1 & 0 & 4 \\
0 & 0 & 0 & 0 & 1 & 5
\end{array} \right]
$$

**Solusi:**
$$
x = \begin{bmatrix} x_1 \\ x_2 \\ x_3 \\ x_4 \\ x_5 \end{bmatrix} = \begin{bmatrix} 1 \\ 2 \\ 3 \\ 4 \\ 5 \end{bmatrix}
$$