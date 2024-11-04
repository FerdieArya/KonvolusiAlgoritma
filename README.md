# KonvolusiAlgoritma
Berikut adalah kodingan untuk Algoritma Konvolusi :
```python
import numpy as np

# Definisikan matriks kernel/filter H (contoh: kernel 3x3)
H = np.array([
    [1, 1, 1],
    [1, 4, 1],
    [1, 1, 1]
])

# Definisikan matriks citra input X (contoh: matriks 5x5)
X = np.array([
    [1, 0, 0, 0],
    [1, 1, 1, 0],
    [1, 1, 1, 0],
    [1, 0, 0, 0]
])

# Dapatkan dimensi kernel dan citra input
nFilterX, nFilterY = H.shape
lebar_input, tinggi_input = X.shape

# Definisikan matriks citra output Y dengan ukuran sama seperti input, diisi dengan nol
Y = np.zeros((lebar_input, tinggi_input))

# Lakukan operasi konvolusi berdasarkan algoritma yang diberikan
for x in range(lebar_input - nFilterX + 1):
    for y in range(tinggi_input - nFilterY + 1):
        # Inisialisasi z(x,y) untuk posisi saat ini di output
        z = 0
        for k1 in range(nFilterX):
            for k2 in range(nFilterY):
                z += H[k1, k2] * X[x + k1, y + k2]
        Y[x, y] = z

# Cetak matriks citra output
print("Matriks Citra Output Y:")
print(Y)
```
Penjelasan Kode <br>
Kernel/Filter (H): Ini adalah matriks yang digunakan untuk konvolusi, yang menentukan transformasi yang diterapkan pada citra. <br>
Citra Input (X): Ini adalah matriks citra asli yang akan dikenakan operasi konvolusi. <br>
Citra Output (Y): Matriks ini menyimpan hasil dari konvolusi, diinisialisasi dengan nilai nol. <br>
Struktur Perulangan: Program mengiterasi setiap piksel dalam matriks input dan menerapkan filter dengan menghitung z(x, y) sesuai dengan algoritma. <br>
Hasil: Y berisi nilai-nilai hasil dari konvolusi.
