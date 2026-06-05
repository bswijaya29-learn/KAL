# Perhitungan Determinan dengan Ekspansi Baris

## 1.
$$
\sum_{k=1}^n (-1)^{i+k} a_{ik} M_{ik}
$$

$$
A = \begin{pmatrix}
-7 & -5 \\
1 & 4
\end{pmatrix}
$$

$$
\det(A) = (-7)(4) - (-5)(1) = -28 + 5 = -23
$$

**Hasil:** $\det(A) = -23$

---

## 2.

$$
A = \begin{pmatrix}
0 & 2 & -3 \\
1 & -2 & -1 \\
0 & 0 & 1
\end{pmatrix}
$$

Ekspansi pada baris ke-3:

$$
\begin{aligned}
\det(A) &= 1 \cdot 
\begin{vmatrix}
0 & 2 \\
1 & -2
\end{vmatrix} \\
&= 1 \cdot \left( (0)(-2) - (2)(1) \right) \\
&= -2
\end{aligned}
$$

**Hasil:** $\det(A) = -2$

---

## 3.

$$
A = \begin{pmatrix}
1 & -3 & 1 & 1 \\
-3 & 1 & 1 & 1 \\
1 & 1 & -3 & 1 \\
1 & 1 & 1 & -3
\end{pmatrix}
$$

Perhatikan bahwa jika matriks $A$ dikalikan dengan vektor kolom berisi angka $1$, hasilnya adalah vektor nol:

$$
A \cdot 
\begin{pmatrix}
1 \\
1 \\
1 \\
1
\end{pmatrix}
=
\begin{pmatrix}
0 \\
0 \\
0 \\
0
\end{pmatrix}
$$

Sehingga terdapat *eigenvalue* $0$, maka:

$$
\det(A) = 0
$$

**Hasil:** $\det(A) = 0$

# Invers Matriks dengan Adjoin

## Rumus

$$
\begin{aligned}
A^{-1} &= \frac{1}{\det(A)} \, \text{adj}(A) \\[6pt]
C_{ij} &= (-1)^{i+j} M_{ij}
\end{aligned}
$$

---

## 4.

$$
\begin{aligned}
A &= 
\begin{pmatrix}
-7 & -5 \\
1 & 4
\end{pmatrix} \\[8pt]
\det(A) &= -23 \\[8pt]
\text{adj}(A) &=
\begin{pmatrix}
4 & 5 \\
-1 & -7
\end{pmatrix} \\[8pt]
A^{-1} &=
\begin{pmatrix}
-4/23 & -5/23 \\
1/23 & 7/23
\end{pmatrix}
\end{aligned}
$$

---

## 5.

$$
\begin{aligned}
A &=
\begin{pmatrix}
0 & 2 & -3 \\
1 & -2 & -1 \\
0 & 0 & 1
\end{pmatrix} \\[8pt]
\det(A) &= -2 \\[8pt]
\text{adj}(A) &=
\begin{pmatrix}
-2 & -2 & -8 \\
-1 & 0 & -3 \\
0 & 0 & -2
\end{pmatrix} \\[8pt]
A^{-1} &=
\begin{pmatrix}
1 & 1 & 4 \\
1/2 & 0 & 3/2 \\
0 & 0 & 1
\end{pmatrix}
\end{aligned}
$$

---

## 6.

$$
\begin{aligned}
A &=
\begin{pmatrix}
1 & -3 & 1 & 1 \\
-3 & 1 & 1 & 1 \\
1 & 1 & -3 & 1 \\
1 & 1 & 1 & -3
\end{pmatrix} \\[8pt]
\det(A) &= 0
\end{aligned}
$$

Karena $\det(A) = 0$ (matriks singular), maka **$A^{-1}$ tidak ada.**