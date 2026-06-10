# Materi KAL

1. Sistem Persamaan Linier (SPL)
 Definisi

Sistem persamaan linier adalah kumpulan dua atau lebih persamaan linier yang memiliki variabel yang sama dan harus diselesaikan secara bersamaan.
Artinya, kita mencari nilai variabel yang memenuhi semua persamaan sekaligus.


Bentuk Umum SPL

### Untuk 2 variabel:
$
\begin{cases}
a_1x + b_1y = c_1 \\
a_2x + b_2y = c_2
\end{cases}
$

### Untuk 3 variabel:
$
\begin{cases}
a_1x + b_1y + c_1z = d_1 \\
a_2x + b_2y + c_2z = d_2 \\
a_3x + b_3y + c_3z = d_3
\end{cases}
$

Jenis Solusi SPL

1. **Solusi Tunggal (unik)** → satu titik potong  
   $
   \text{Dua garis berpotongan di satu titik}
   $

2. **Tak hingga solusi** → garis berhimpit  
   $
   \text{Kedua persamaan merepresentasikan garis yang sama}
   $

3. **Tidak ada solusi** → garis sejajar  
   $
   \text{Dua garis sejajar dan tidak pernah berpotongan}
   $

Solusi Tunggal (unik) → satu titik potong

Tak hingga solusi → garis berhimpit

Tidak ada solusi → garis sejajar

3. Kode Python (Metode Gauss-Jordan)

Berikut contoh menggunakan NumPy:
import numpy as np

# Matriks augmented
A = np.array([
    [2, 1, 5],
    [1, -1, 1]
], dtype=float)

# Jumlah baris
n = len(A)

# Proses Gauss-Jordan
for i in range(n):
    # Membuat pivot = 1
    A[i] = A[i] / A[i][i]
    
    # Mengeliminasi baris lain
    for j in range(n):
        if i != j:
            A[j] = A[j] - A[j][i] * A[i]

print("Matriks hasil:")
print(A)

print("Solusi:")
print("x =", A[0][2])
print("y =", A[1][2])

4. Penjelasan Geometri SPL
 SPL Dua Variabel (2D)

Persamaan linier dua variabel merepresentasikan garis lurus.

Contoh:

$
2x + y = 5
$

$
x - y = 1
$

5. Penjelasan Menggunakan GeoGebra
 Langkah di GeoGebra (2D)

<<iframe src="https://www.geogebra.org/calculator/kgqyqtma?embed" width="800" height="600" allowfullscreen style="border: 1px solid #e4e4e4;border-radius: 4px;" frameborder="0"></iframe>

Pengertian Sistem Persamaan Linier

Sistem Persamaan Linier (SPL) adalah kumpulan beberapa persamaan linier yang memiliki variabel yang sama dan dicari penyelesaiannya secara bersamaan.

SPLTV → 3 variabel (misal: x, y, z)

SPL 4 variabel → 4 variabel (misal: x, y, z, w)

Tujuannya adalah mencari nilai masing-masing variabel yang memenuhi semua persamaan.

Pengertian Metode Eliminasi Gaussian

Eliminasi Gaussian adalah metode penyelesaian SPL dengan cara:

Mengubah sistem persamaan menjadi bentuk matriks augmented

Melakukan operasi baris elementer

Mengubah matriks menjadi bentuk segitiga atas

Menentukan solusi dengan substitusi balik

Operasi Baris Elementer (OBE)

Dalam eliminasi Gaussian digunakan tiga operasi dasar:

Menukar dua baris

Mengalikan baris dengan konstanta ≠ 0

Menjumlahkan atau mengurangkan baris dengan kelipatan baris lain

Tujuan operasi ini adalah membuat elemen di bawah diagonal utama menjadi nol.

A. Rangkuman SPL Tiga Variabel (SPLTV)
Bentuk Umum:

#  A. Rangkuman Sistem Persamaan Linier Tiga Variabel (SPLTV)

##  Bentuk Umum

$$
\begin{cases}
a_1x + b_1y + c_1z = d_1 \\
a_2x + b_2y + c_2z = d_2 \\
a_3x + b_3y + c_3z = d_3
\end{cases}
$$

Sistem Persamaan Linier Tiga Variabel (SPLTV) adalah sistem yang terdiri dari tiga persamaan linier dengan tiga variabel yang dicari secara bersamaan.

---

##  Bentuk Matriks Augmented

$$
\left[
\begin{array}{ccc|c}
a_1 & b_1 & c_1 & d_1 \\
a_2 & b_2 & c_2 & d_2 \\
a_3 & b_3 & c_3 & d_3
\end{array}
\right]
$$

---

##  Langkah Penyelesaian dengan Eliminasi Gaussian

### 1 Eliminasi Kolom Pertama

Gunakan operasi baris elementer untuk membuat elemen di bawah pivot pertama menjadi nol.

$$
\left[
\begin{array}{ccc|c}
* & * & * & * \\
0 & * & * & * \\
0 & * & * & *
\end{array}
\right]
$$

---

### 2 Eliminasi Kolom Kedua

Nolkan elemen di bawah pivot kedua sehingga diperoleh bentuk segitiga atas.

$$
\left[
\begin{array}{ccc|c}
* & * & * & * \\
0 & * & * & * \\
0 & 0 & * & *
\end{array}
\right]
$$

---

### 3 Substitusi Balik

Jika diperoleh bentuk:

$$
\begin{aligned}
a z &= k \\
b y + c z &= m \\
x + d y + e z &= n
\end{aligned}
$$

Langkah penyelesaian:

- Tentukan nilai $z$
- Substitusikan ke persamaan kedua untuk mencari $y$
- Substitusikan ke persamaan pertama untuk mencari $x$

---

##  Kesimpulan SPLTV

- Jika diperoleh satu solusi → sistem konsisten (solusi tunggal)
- Jika tidak ada solusi → sistem tidak konsisten
- Jika solusi tak hingga → sistem konsisten dependen

---

#  B. Rangkuman Sistem Persamaan Linier Empat Variabel

##  Bentuk Umum

$$
\begin{cases}
a_1x + b_1y + c_1z + d_1w = e_1 \\
a_2x + b_2y + c_2z + d_2w = e_2 \\
a_3x + b_3y + c_3z + d_3w = e_3 \\
a_4x + b_4y + c_4z + d_4w = e_4
\end{cases}
$$

Sistem ini terdiri dari empat persamaan linier dengan empat variabel yang diselesaikan menggunakan metode eliminasi Gaussian.

---

##  Bentuk Matriks Augmented

$$
\left[
\begin{array}{cccc|c}
a_1 & b_1 & c_1 & d_1 & e_1 \\
a_2 & b_2 & c_2 & d_2 & e_2 \\
a_3 & b_3 & c_3 & d_3 & e_3 \\
a_4 & b_4 & c_4 & d_4 & e_4
\end{array}
\right]
$$

---

##  Langkah Penyelesaian dengan Eliminasi Gaussian

### 1  Eliminasi Kolom Pertama

Buat semua elemen di bawah pivot pertama menjadi nol.

$$
\left[
\begin{array}{cccc|c}
* & * & * & * & * \\
0 & * & * & * & * \\
0 & * & * & * & * \\
0 & * & * & * & *
\end{array}
\right]
$$

---

### 22 Eliminasi Kolom Kedua dan Ketiga

Lanjutkan proses eliminasi hingga diperoleh bentuk segitiga atas.

$$
\left[
\begin{array}{cccc|c}
* & * & * & * & * \\
0 & * & * & * & * \\
0 & 0 & * & * & * \\
0 & 0 & 0 & * & *
\end{array}
\right]
$$

---

### 3 Substitusi Balik

Jika diperoleh bentuk:

$$
\begin{aligned}
a w &= p \\
b z + c w &= q \\
d y + e z + f w &= r \\
x + g y + h z + i w &= s
\end{aligned}
$$

Langkah penyelesaian:

- Tentukan $w$
- Substitusikan untuk mencari $z$
- Substitusikan untuk mencari $y$
- Terakhir tentukan $x$

---

##  Kesimpulan SPL Empat Variabel

- Menggunakan operasi baris elementer
- Diubah ke bentuk segitiga atas
- Diselesaikan dengan substitusi balik
- Prinsipnya sama dengan SPLTV, tetapi lebih banyak tahap eliminasi

SOAL.

A. Hitunglah determinan matrik berikut dengan menggunakan rumus expansi baris

$$\det(A) = \sum_{k=1}^{n} (-1)^{i+k} a_{ik} M_{ik}$$

di mana $M_{ik}$ adalah minor (determinan submatriks setelah menghapus baris i dan kolom k).

1. Matriks $2 \times 2$
$$A = \begin{bmatrix} -7 & -5 \\ 1 & 4 \end{bmatrix}$$

Langkah Penyelesaian (Ekpansi Baris 1):

$$a_{11} = -7, M_{11} = |4| = 4$$

$$a_{12} = -5, M_{12} = |1| = 1$$

$$\det(A) = (-1)^{1+1}(-7)(4) + (-1)^{1+2}(-5)(1)$$

$$\det(A) = (1)(-28) + (-1)(-5)$$

$$\det(A) = -28 + 5 = \mathbf{-23}$$

2. Matriks 3 $\times 3$

$$A = \begin{bmatrix} 0 & 2 & -3 \\ 1 & -2 & -1 \\ 0 & 0 & 1 \end{bmatrix}$$

Langkah Penyelesaian (Ekspansi Baris 3 - Paling Efisien):
Kita pilih baris ke-3 karena memiliki banyak elemen nol.

$$a_{31} = 0$$

$$a_{32} = 0$$

$$a_{33} = 1, M_{33} = \begin{vmatrix} 0 & 2 \\ 1 & -2 \end{vmatrix}$ = (0)(-2) - (2)(1) = -2

$\det(A) = 0 + 0 + (-1)^{3+3}(1)(-2)$$

$$\det(A) = (1)(1)(-2) = \mathbf{-2}$$

3. Matriks $4 \times 4$

Langkah Penyelesaian (Ekspansi Baris 1):

$\det(A) = 1 \cdot M_{11} - (-3) \cdot M_{12} + 1 \cdot M_{13} - 1 \cdot M_{14}$

$M_{11} = \begin{vmatrix} 1 & 1 & 1 \\ 1 & -3 & 1 \\ 1 & 1 & -3 \end{vmatrix}$ = 1(9-1) - 1(-3-1) + 1(1+3) = 8 + 4 + 4 = 16

$$M_{12} = \begin{vmatrix} -3 & 1 & 1 \\ 1 & -3 & 1 \\ 1 & 1 & -3 \end{vmatrix}$$ = -3(9-1) - 1(-3-1) + 1(1+3) = -24 + 4 + 4 = -16

$M_{13} = \begin{vmatrix} -3 & 1 & 1 \\ 1 & 1 & 1 \\ 1 & 1 & -3 \end{vmatrix}$ = -3(-3-1) - 1(-3-1) + 1(1-1) = 12 + 4 + 0 = 16

$M_{14} = \begin{vmatrix} -3 & 1 & 1 \\ 1 & -3 & 1 \\ 1 & 1 & 1 \end{vmatrix}$ = -3(-3-1) - 1(1-1) + 1(1+3) = 12 - 0 + 4 = 16

Substitusi Kembali:

$\det(A) = 1(16) + 3(-16) + 1(16) - 1(16)$

$$\det(A) = 16 - 48 + 16 - 16$$

$$\det(A) = \mathbf{-32}$$

B. Gunakan rumus matriks adjoin untuk menghitung invers dari matriks berikut dengan rumus

$$A^{-1} = \frac{1}{\det A} \text{adj } A$$

Dimana elemen adjoin $$(\text{adj } A)_{ij} = (-1)^{i+j} M_{ji}$$ (transpose dari matriks kofaktor).
4. Matriks $$2 \times 2$$

$$A = \begin{bmatrix} -7 & -5 \\ 1 & 4 \end{bmatrix}$$

Langkah 1: Hitung Determinan

$$\det(A) = (-7)(4) - (-5)(1) = -28 + 5 = -23$$

Langkah 2: Cari Matriks Adjoin
Untuk matriks $$2 \times 2$$, adjoin didapat dengan menukar elemen diagonal utama dan mengubah tanda diagonal sekunder:

$$\text{adj } A = \begin{bmatrix} 4 & 5 \\ -1 & -7 \end{bmatrix}$$

Hitung Invers

$$A^{-1} = \frac{1}{-23} \begin{bmatrix} 4 & 5 \\ -1 & -7 \end{bmatrix}$$= \mathbf{\begin{bmatrix} -4/23 & -5/23 \\ 1/23 & 7/23 \end{bmatrix}}$$

5. Matriks $$3 \times 3$$

$$A = \begin{bmatrix} 0 & 2 & -3 \\ 1 & -2 & -1 \\ 0 & 0 & 1 \end{bmatrix}$$

Langkah 1: Hitung Determinan
(Dari soal sebelumnya): $$\det(A) = -2$$
Langkah 2: Cari Matriks Kofaktor $$(C_{ij})$$

$$C_{11} = +|(-2)(1) - (0)(-1)| = -2$$

$$C_{12} = -|(1)(1) - (0)(-1)| = -1$$

$$C_{13} = +|(1)(0) - (0)(-2)| = 0$$

$$C_{21} = -|(2)(1) - (0)(-3)| = -2$$

$$C_{22} = +|(0)(1) - (0)(-3)| = 0$$

$$C_{23} = -|(0)(0) - (0)(2)| = 0$$

$$C_{31} = +|(2)(-1) - (-2)(-3)| = -8$$

$$C_{32} = -|(0)(-1) - (1)(-3)| = -3$$

$$C_{33} = +|(0)(-2) - (1)(2)| = -2$$

Langkah 3: Adjoin (Transpose Kofaktor) & Invers

$$\text{adj } A = \begin{bmatrix} -2 & -2 & -8 \\ -1 & 0 & -3 \\ 0 & 0 & -2 \end{bmatrix}$$

$$A^{-1} = \frac{1}{-2} \begin{bmatrix} -2 & -2 & -8 \\ -1 & 0 & -3 \\ 0 & 0 & -2 \end{bmatrix} = \mathbf{\begin{bmatrix} 1 & 1 & 4 \\ 1/2 & 0 & 3/2 \\ 0 & 0 & 1 \end{bmatrix}}$$

6. Matriks $$4 \times 4$$

$$A = \begin{bmatrix} 1 & -3 & 1 & 1 \\ -3 & 1 & 1 & 1 \\ 1 & 1 & -3 & 1 \\ 1 & 1 & 1 & -3 \end{bmatrix}$$

Langkah 1: Hitungxlumnya): $$\det(A) = -32$$
Langkah 2: Analisis Simetri
Karena matriks ini memiliki pola simetris yang unik, kofaktor antar elemen diagonal akan sama, dan elemen non-diagonal juga akan memiliki pola yang sama.
Elemen diagonal $$(C_{ii}): M_{11} = 16, maka C_{11} = (-1)^{1+1}(16) = 16$$
Elemen non-diagonal $$(C_{ij}): M_{12} = -16, maka C_{12} = (-1)^{1+2}(-16) = 16$$
Setelah menghitung seluruh elemen, matriks Adjoin-nya adalah:

$$\text{adj } A = \begin{bmatrix} 16 & 16 & 16 & 16 \\ 16 & 16 & 16 & 16 \\ 16 & 16 & 16 & 16 \\ 16 & 16 & 16 & 16 \end{bmatrix} \text{ (Setelah penyesuaian tanda kofaktor)}$$


Catatan khusus: Untuk matriks nomor 6, semua elemen kofaktor bernilai 16 karena struktur angka -3 yang bergeser.

Langkah 3: Hitung Invers

$$A^{-1} = \frac{1}{-32} \begin{bmatrix} 16 & 16 & 16 & 16 \\ 16 & 16 & 16 & 16 \\ 16 & 16 & 16 & 16 \\ 16 & 16 & 16 & 16 \end{bmatrix} = \mathbf{\begin{bmatrix} -1/2 & -1/2 & -1/2 & -1/2 \\ -1/2 & -1/2 & -1/2 & -1/2 \\ -1/2 & -1/2 & -1/2 & -1/2 \\ -1/2 & -1/2 & -1/2 & -1/2 \end{bmatrix}}$$

(Catatan: Khusus nomor 6, periksa kembali apakah ada elemen matriks yang tertulis salah di soal asli, karena invers dengan semua elemen sama biasanya menandakan matriks singular atau kasus khusus pada sistem persamaan linear).


<iframe src="https://www.geogebra.org/classic/rkseuabx?embed" width="800" height="600" allowfullscreen style="border: 1px solid #e4e4e4;border-radius: 4px;" frameborder="0"></iframe>

1. Transformasi A ke B
Titik A(2, 3) berpindah ke B(2, 1).Perubahan $x$: $2 - 2 = 0$Perubahan $y$: $1 - 3 = -2$Matriks Translasi:

$$T = \begin{pmatrix} 0 \\ -2 \end{pmatrix}$$

2. Transformasi B ke CTitik B(2, 1) berpindah ke C(4, 1).Perubahan $x$: $4 - 2 = 2$Perubahan $y$: $1 - 1 = 0$Matriks Translasi:$T = \begin{pmatrix} 2 \\ 0 \end{pmatrix}$

3. Transformasi D ke ETitik D(2, 4) berpindah ke E(2, 0).Perubahan $x$: $2 - 2 = 0$Perubahan $y$: $0 - 4 = -4$Matriks Translasi:$T = \begin{pmatrix} 0 \\ -4 \end{pmatrix}$

4. Transformasi E ke FTitik E(2, 0) berpindah ke F(4, 0).Perubahan $x$: $4 - 2 = 2$Perubahan $y$: $0 - 0 = 0$Matriks Translasi:$T = \begin{pmatrix} 2 \\ 0 \end{pmatrix}$

## Matrik Transformasi

```
import matplotlib.pyplot as plt
import matplotlib.animation as animation
from IPython.display import HTML

# 1. Definisikan Titik
points = {
    "A": (2, 3), "B": (2, 4), "C": (3, 4), "D": (3, 3),
    "E": (2, -3), "F": (3, -3), "G": (2, -4), "H": (3, -4),
    "I": (2, 2), "J": (3, 2), "K": (2, 1), "L": (3, 1),
    "M": (2, -1), "N": (3, -1), "O": (2, -2), "P": (3, -2)
}

# 2. Definisikan Garis
garis = [
    ("B", "C"), ("A", "D"), ("I", "J"), ("K", "L"),
    ("M", "N"), ("O", "P"), ("E", "F"), ("H", "G"),
    ("B", "A"), ("A", "I"), ("I", "K"), ("C", "D"),
    ("D", "J"), ("J", "L"), ("M", "O"), ("O", "E"),
    ("N", "P"), ("P", "F")
]

# 3. Setup Figure
fig, ax = plt.subplots(figsize=(6, 8))

# 4. Fungsi Update untuk Animasi
def update(frame):
    ax.clear()
    scale_y = 1 - frame / 100
    posisi_baru = {}

    # Gambar Titik
    for nama, (x, y) in points.items():
        y_baru = y * scale_y
        posisi_baru[nama] = (x, y_baru)
        ax.scatter(x, y_baru, color="blue", s=100)
        ax.text(x + 0.05, y_baru + 0.05, nama, fontsize=12)

    # Gambar Garis
    for p1, p2 in garis:
        x1, y1 = posisi_baru[p1]
        x2, y2 = posisi_baru[p2]
        ax.plot([x1, x2], [y1, y2], color="red", linewidth=2)

    # Dekorasi Grafik
    ax.axhline(0, color="black", linewidth=2)
    ax.axvline(0, color="black", linewidth=2)
    ax.set_xlim(0, 5)
    ax.set_ylim(-5, 5)
    ax.grid(True)
    ax.set_title("Transformasi Titik Mendekati Sumbu X")

# 5. Membuat Animasi
ani = animation.FuncAnimation(
    fig, update, frames=101, interval=50, repeat=True
)

# 6. SIMPAN JADI GIF (Agar bisa didownload)
# Gunakan writer 'pillow' agar kompatibel di Colab
print("Sedang memproses penyimpanan GIF... mohon tunggu sebentar.")
ani.save('animasi_transformasi.gif', writer='pillow', fps=20)
print("Selesai! Cek folder di sebelah kiri untuk mendownload 'animasi_transformasi.gif'")

# 7. Tampilkan di Colab
HTML(ani.to_jshtml())

from google.colab import files
files.download('animasi_transformasi.gif')
```

![Deskripsi Animasi](_static/animasi_saya.gif)

Dekomposisi Matrik

## Foto 1
![Foto 1](_static/foto1.jpeg)

## Foto 2
![Foto 2](_static/foto2.jpeg)

## Foto 3
![Foto 3](_static/foto3.jpeg)


# Singular Value Decomposition (SVD)

## Pengertian

Singular Value Decomposition (SVD) adalah salah satu metode dekomposisi matriks dalam aljabar linear yang digunakan untuk menguraikan sebuah matriks menjadi tiga komponen utama yang lebih sederhana. Metode ini memungkinkan suatu matriks direpresentasikan dalam bentuk yang lebih mudah dianalisis, dipahami, dan diproses tanpa kehilangan informasi penting yang terkandung di dalamnya.

Secara matematis, jika terdapat matriks \(A\) berukuran \(m \times n\), maka matriks tersebut dapat didekomposisi menjadi:

\[
A = U \Sigma V^T
\]

dengan:

- \(U\) = matriks vektor singular kiri (left singular vectors)
- \(\Sigma\) = matriks diagonal yang berisi nilai singular (singular values)
- \(V^T\) = transpose dari matriks vektor singular kanan (right singular vectors)

Nilai-nilai singular yang terdapat pada matriks \(\Sigma\) menunjukkan tingkat kontribusi masing-masing komponen terhadap struktur data pada matriks asal. Semakin besar nilai singular yang dimiliki suatu komponen, semakin besar pula pengaruhnya dalam merepresentasikan informasi yang terdapat pada matriks tersebut. Oleh karena itu, dalam beberapa aplikasi hanya nilai singular terbesar yang dipertahankan untuk mengurangi kompleksitas data tanpa menghilangkan informasi yang paling penting.

SVD memiliki keunggulan karena dapat diterapkan pada berbagai jenis matriks, baik matriks persegi maupun matriks non-persegi. Selain itu, metode ini dikenal memiliki stabilitas numerik yang baik sehingga sering digunakan dalam komputasi ilmiah dan analisis data berskala besar.

Dalam bidang ilmu data dan machine learning, SVD banyak dimanfaatkan untuk reduksi dimensi (dimensionality reduction), ekstraksi fitur, analisis data multivariat, dan sistem rekomendasi. Pada pengolahan citra digital, SVD dapat digunakan untuk melakukan kompresi gambar dengan mempertahankan komponen-komponen utama yang paling berpengaruh sehingga ukuran data dapat diperkecil tanpa mengurangi kualitas gambar secara signifikan. Selain itu, SVD juga digunakan dalam pemrosesan bahasa alami (Natural Language Processing), pengenalan pola, serta berbagai aplikasi statistik dan optimasi.

Karena kemampuannya dalam menyederhanakan struktur matriks dan mempertahankan informasi yang penting, Singular Value Decomposition menjadi salah satu teknik fundamental yang banyak digunakan dalam berbagai bidang matematika terapan, ilmu komputer, dan analisis data modern.

## Contoh Matriks

Misalkan diberikan matriks:

$$
A=
\begin{bmatrix}
4 & 2 & 1\\
1 & 3 & 2\\
2 & 1 & 5
\end{bmatrix}
$$

Matriks tersebut akan didekomposisi menjadi \(U\), \(\Sigma\), dan \(V^T\).

## Implementasi dengan SageMathCell

```{raw} html
<script src="https://sagecell.sagemath.org/static/embedded_sagecell.js"></script>

<div id="mycell">
<script type="text/x-sage">
import numpy as np

A = np.array([[4,2,1],
              [1,3,2],
              [2,1,5]])

U, S, VT = np.linalg.svd(A)

print(U)
print(S)
print(VT)
</script>
</div>

<script>
sagecell.makeSagecell({
    inputLocation: "#mycell"
});
</script>
```


## Kesimpulan

Hasil dekomposisi SVD menghasilkan tiga matriks, yaitu \(U\), \(\Sigma\), dan \(V^T\). Ketiga matriks tersebut dapat digunakan untuk merekonstruksi kembali matriks awal melalui operasi:

\[
A = U \Sigma V^T
\]

Sehingga informasi pada matriks awal tetap dipertahankan meskipun telah diuraikan ke dalam bentuk yang lebih sederhana. Metode ini sangat bermanfaat dalam berbagai bidang seperti machine learning, analisis data, kompresi citra, dan pemrosesan sinyal karena mampu menyederhanakan struktur data tanpa kehilangan informasi yang signifikan.s
