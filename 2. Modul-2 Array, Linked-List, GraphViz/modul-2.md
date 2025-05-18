# Modul 2 : Array Vs Linked-List
Seluruh percobaan pada modul ini dapat diakses pada link ini

Modul ini secara khusus akan membahas materi dalam struktur data yang berkaitan dengan **Array**, **Linked-List**, dan **GraphViz**. 

Pada modul ini kita juga akan berkenalan dengan sebuah library python yang bernama numpy (Numerical Python) yang menyediakan fungsi yang siap dipakai untuk memudahkan dalam melakukan perhitungan saintifik, seperti matriks, aljabar, statistik, dan lainnya.

## NumPy (*Numerical Python*)
Sebelum kita masuk ke materi tentang `array` sebaiknya kita terlebih dahulu mempelajari tetang libaray `numpy` yang kita akan gunakan secara khusus pada modul ini untuk materi array. 

Mengapa kita perlu menggunakan `numpy`? Apakah penggunaan list dan modul math tidak cukup? Memang penggunaan list dan modul math untuk menangani masalah list dapat kita pakai untuk perhitungan saintifik. Akan tetapi masih kurang lengkap, karena beberapa perhitungan terpaksa harus dibuat secara manual. 

Untuk menggunakan NumPy terlebih dahulu kita perlu untuk menginstall libaray `numpy` ke dalam python kita. Untuk menginstallnya kita perlu menggunakan *package manager* `pip`. berikut caranya : 
```terminal
pip install numpy
```

Lalu bagaimana cara menggunakan NumPy? Menggunakan `numpy` sebenarnya cukup mudah yaitu dengan cara mengimpor library tersebut ke dalam program kita. Berikut contohnya : 
```python
import numpy as np
```
Pada contoh pemanggilan `numpy` dengan menggunakan perintah `import` dan menggunakan tambahan kata kunci `as` yang diletakkan setelah nama library yang kita panggil. Sementara `np` merupakan nama alias dari libaray `numpy` agar dalam proses penggunaan tidak memerlukan pemanggilan nama library secara utuh. 

Berikut ini fungsi-fungsi pada `numpy` yang umum digunakan antara lain adalah : 
| Fungsi         | Keterangan                      |
| -------------- | ------------------------------- |
| `np.zeros()`   | Membuat array dengan nilai nol  |
| `np.ones()`    | Membuat array dengan nilai satu |
| `np.arange()`  | Seperti `range()`, untuk array  |
| `np.reshape()` | Mengubah bentuk array           |
| `np.sum()`     | Menjumlahkan semua elemen       |
| `np.mean()`    | Rata-rata                       |
| `np.max()`     | Nilai maksimum                  |
| `np.min()`     | Nilai minimum                   |


## Array
**Array** adalah struktur data yang menyimpan **sekumpulan elemen dengan tipe data yang sama** dalam urutan tertentu. Dalam konteks algoritma, array digunakan untuk **penyimpanan linear** dan **akses data secara indeks**. Dengan ketentuan sebagai berikut ini : 
* Setiap elemen dapat diakses melalui **index**
* Operasi dasar : **akses**, **ubah**, **sisip**, **hapus**, **pencarian**, dan **transversal**. 
* Dalam python, array dapat digunakan melalui : 
  * `list` -> build-in, fleksibel tapi tidak efisien
  * `numpy` array -> array numerik berdimensi tinggi yang cepat dan efisien

### Cara Membuat Array dengan NumPy

Setalah kita mengimpor library `numpy` selanjutnya kita bisa dengan memcoba membuat array menggunakan contoh berikut ini : 
```python
# impor library numpy
import numpy as np

# membuat array dengan numpy
arr1 = np.array([1, 2, 3])           # 1D array
arr2 = np.array([[1, 2], [3, 4]])    # 2D array (matriks)
```

Praktek 1 : 
```python
# impor library numpy
import numpy as np

# membuat array dengan numpy
nilai_siswa = np.array([85, 55, 40, 90])

# akses data pada array
print(nilai_siswa[3])
```

### Operasi Dasar Array
Operasi paling dasar pada array yang **wajib** dipahami adalah bagaimana cara mengakses array, mengubah nilai pada elemen tertentu, dan mendapatkan informasi ukuran dan dimensi dari array. 

Praktek 2 : 
```python
# impor libaray numpy
import numpy as np

# membuat array dengan numpy
nilai_siswa_1 = np.array([75, 65, 45, 80])
nilai_siswa_2 = np.array([[85, 55, 40], [50, 40, 99]])

# cara akses elemen array
print(nilai_siswa_1[0])
print(nilai_siswa_2[1][1])

# mengubah nilai elemen array
nilai_siswa_1[0] = 88
nilai_siswa_2[1][1] = 70

# cek perubahannya dengan akses elemen array
print(nilai_siswa_1[0])
print(nilai_siswa_2[1][1])

# Cek ukuran dan dimensi array
print("Ukuran Array : ", nilai_siswa_1.shape)
print("Ukuran Array : ", nilai_siswa_2.shape)
print("Dimensi Array : ", nilai_siswa_2.ndim)
```
outputnya : 
```
75
40
88
70
Ukuran Array :  (4,)
Ukuran Array :  (2, 3)
Dimensi Array :  2
```

### Operasi Lanjutan pada Array
Setelah kita dapat memahami operasi dasar yang wajib kita pahami dalam array, selanjutnya kita akan mendalami lagi operasi-operasi lainnya yang digunakan pada array di bahasa pemrograman python. 

#### Operasi Artimatika
Sebagaimana tipe data yang lainnya array juga memiliki operasi artimatika, artinya kita dapat melakukan manipulasi terhadap nilai array dengan memanfaatkan operasi aritmatika seperti penjumlahan dan lainnya. 

Praktek 3 : 
```python
# impor library numpy
import numpy as np

# membuat array
a = np.array([1, 2, 3])
b = np.array([4, 5, 6])

# menggunakan operasi penjumlahan pada 2 array
print(a + b)       # array([5, 7, 9])

# Indexing dan Slicing pada Array
arr = np.array([10, 20, 30, 40])
print(arr[1:3])    # array([20, 30])


# iterasi pada array
for x in arr:
    print(x)
```
outputnya : 
```
[5 7 9]
[20 30]
10
20
30
40
```

### Traversal
Pada *array* **mengunjungi** satu per satu elemen *array* dari elemen pada indeks pertama sampai terakhir, disebut sebagai **Traversal**. Lalu apa tujuannya berkunjung ke setiap elemen array? Sebenarnya tidak ada tujuan yang khusus atau spesial, tujuannya untuk mencetak nilai tiap elemen dari array, atau melakukan operasi matematika. 

Mengunjungi array sangat penting untuk berbagai tugas dalam pemrograman, dan metode traversal yang paling umum mencakup iterasi melalui array menggunakan **loop** seperti `for`, atau `while`. Traversal yang efisien memainkan peran penting dalam algoritme yang memerlukan pemindaian atau manipulasi data. 

Bentuk **Traversal** paling sederhana terhadap array adalah mencetak nilai tiap elemen berikut contohnya : 
```python
arr_1 = [10, 20, 30, 40, 50]
print(arr_1)
```
outputnya : 
```
[10, 20, 30, 40, 50]
```

**Traversal** array terdiri dari dua jenis, yaitu :
1. Linear Traversal
2. Reverse Traversal

Mari kita bahas dua jenis **Traversal** diatas satu persatu 

**Linear Traversal**

Proses mengunjungi setiap elemen array **secara berurutan**, dimulai dari **elemen pertama** dan berlanjut ke **elemen terakhir**. Selama penelusuran ini, setiap elemen diproses (*dicetak, dimodifikasi, atau diperiksa*) **satu demi satu**, sesuai urutan penyimpanannya dalam array. Ini adalah c**ara yang paling umum dan mudah untuk mengakses elemen array**.

Praktek 4
```python
# membuat array
arr = [1, 2, 3, 4, 5]

# Linear Traversal ke tiap elemen arr
print("Linear Traversal: ", end=" ")
for i in arr:
    print(i, end=" ")
print()
```
Hasilnya : 
```
Linear Traversal:  1 2 3 4 5
```

**Reverse Traversal**

Proses mengunjungi setiap elemen array **mulai dari elemen terakhir dan bergerak menuju elemen pertama**. Metode ini berguna saat kita perlu memproses elemen array dalam urutan terbalik. Dalam jenis penelusuran ini, Anda mulai dari indeks terakhir (*elemen paling kanan*) dan terus ke indeks pertama (*elemen paling kiri*).

Praktek 5
```python
# membuat array
arr = [1, 2, 3, 4, 5]

# Reverse Traversal dari elemen akhir 
print("Reverse Traversal: ", end="")
for i in range(len(arr) - 1, -1, -1):
    print(arr[i], end=" ")
print()
```
Hasilnya : 
```
Reverse Traversal: 5 4 3 2 1
```
Untuk melakukan Traversal array dapat menggunakan metode perulangan `for`, atau `while`. Pada `praktek 4` dan `praktek 5` kita sudah menggunakan metode `for` untuk traversal ke tiap elemen array baik secara *linear* maupun *reverse*. Sekarang kita coba traversal menggunakan metode perulangan `while`

Praktek 7
```python
# membuat array
arr = [1, 2, 3, 4, 5]

# mendeklarasikan nilai awal
n = len(arr)
i = 0

print("Linear Traversal using while loop: ", end=" ")
# Linear Traversal dengan while
while i < n:
    print(arr[i], end=" ")
    i += 1
print()
```
Hasilnya : 
```
Traversal using while loop:  1 2 3 4 5
```

Praktek 8 
```python
# membuat array
arr = [1, 2, 3, 4, 5]

# mendeklarasikan nilai awal
start = 0
end = len(arr) - 1

print("Reverse Traversal using while loop: ", end=" ")
# Reverse Traversal dengan while
while start < end:
    
    arr[start], arr[end] = arr[end], arr[start]
    start += 1
    end -= 1
print(arr)
```
Hasilnya 
```
Reverse Traversal using while loop:  [5, 4, 3, 2, 1]
```

### Insertion
**Insertion** atau Penyisipan dalam array melibatkan **penempatan elemen pada indeks tertentu sambil menggeser elemen yang ada sesuai dengan itu**. Jika array memiliki cukup ruang yang dialokasikan, penyisipan elemen menjadi mudah. **​​Kompleksitas operasi ini bergantung pada posisi terjadinya penyisipan**.

Terdapat beberapa jenis insertion array, yaitu : 
1. Insertion **pada akhir** elemen array
2. Insertion **pada tengah** elemen array

**Insertion Pada Akhir Elemen Array**
Dalam *array* yang tidak diurutkan, operasi insertsion atau penyisipan lebih cepat dibandingkan dengan array yang diurutkan karena kita tidak perlu peduli dengan posisi di mana elemen akan ditempatkan. Perhatikan ilustrasi berikut ini : 

![Penyisipan array di akhir](https://media.geeksforgeeks.org/wp-content/cdn-uploads/Insert-Operation-in-Unorted-Array.png)

Pada gambar terlihat bahwa terdapat sebuah array yang memiliki lima elemen dengan isi elemen `[5,1,4,2,6]`. Kemudian akan disisipkan sebuah nilai baru pada akhir elemen yaitu `3`, maka elemen array akan menjadi `[5,1,4,2,6,3]`. 

Mari kita implementasikan penyisipan array pada akhir elemen menggunakan `.append()` melalui code python berikut ini :

Praktek 9
```python
# membuat array
arr = [12, 16, 20, 40, 50, 70]

# cetak arr sebelum penyisipan
print("Array Sebelum Insertion : ", arr)

# cetak panjang array sebelum penyisipan
print("Panjang Array : ", len(arr))

# menyisipkan array di akhir elemen menggunakan .append()
arr.append(26)

# cetak arr setelah penyisipan
print("Array Setelah Insertion : ", arr)

# cetak panjang array setelah penyisipan
print("Panjang Array : ", len(arr))
```
Hasilnya : 
```
Array Sebelum Insertion :  [12, 16, 20, 40, 50, 70]
Panjang Array :  6
Array Setelah Insertion :  [12, 16, 20, 40, 50, 70, 26]
Panjang Array :  7
```
**Insertion Pada Tengah Elemen Array**

Operasi penyisipan ke dalam array pada posisi mana pun (*ditengah, bukan awal atau akhir elemen*) dapat dilakukan dengan **menggeser elemen ke kanan**, yang berada di sisi kanan posisi yang diperlukan. Perhatikan ilustrasi dibawah ini

![sisip tengah](https://media.geeksforgeeks.org/wp-content/uploads/20190826133603/Insert-an-element-at-a-specific-position-in-an-Array.jpg)

Perhatikan terapat sebuah array dengan 10 elemen dengan isi `[1,2,3,4,5,6,7,8,9,10]`, kemudian dilakukan penyisipan (insertion) `50` pada tengah elemen, yaitu pada elemen ke 4 atau `array[4]`. Maka nilai pada elemen ke 5 yaitu `6` digeser ke kanan menjadi elemen ke-6 dan nilai `50` disisipkan menjadi elemen ke 5. Sehingga array akan menjadi `[1,2,3,4,50,5,6,7,8,9,10]`. 

Sekarang coba kita implementasikan pada code python menggunakan `.insert(pos, x)`, berikut ini 

Praktek 10
```python
# membuat array
arr = [12, 16, 20, 40, 50, 70]

# cetak arr sebelum penyisipan
print("Array Sebelum Insertion : ", arr)

# cetak panjang array sebelum penyisipan
print("Panjang Array : ", len(arr))

# menyisipkan array pada tengah elemen menggunakan .insert(pos, x)
arr.insert(4, 5)

# cetak arr setelah penyisipan
print("Array Setelah Insertion : ", arr)

# cetak panjang array setelah penyisipan
print("Panjang Array : ", len(arr))
```
Hasilnya : 
```
Array Sebelum Insertion :  [12, 16, 20, 40, 50, 70]
Panjang Array :  6
Array Setelah Insertion :  [12, 16, 20, 40, 5, 50, 70]
Panjang Array :  7
```

**Deletion (Penghapusan)**

Dalam Python elemen dalam array/list tidak hanya bisa disisipkan tetapi juga dapat dihapus. Terdapat tiga cara untuk menghapus elemen dari array/list, yaitu : 
1. `remove()`, menghapus elemen **array yang pertama kali muncul**
2. `pop()`, menghapus elemen array **pada indeks yang spesifik** atau bisa juga menghapus **elemen terakhir dari array** jika indeksnya tidak spesifik ditentukan
3. `del_statement`, menghapus elemen array pada **indeks yang spesifik**

Praktek 11
```python
# membuat array
a = [10, 20, 30, 40, 50]
print("Array Sebelum Deletion : ", a)

# menghapus elemen array pertama yang nilainya 30
a.remove(30)  
print("Setelah remove(30):", a)

# menghapus elemen array pada index 1 (20)
popped_val = a.pop(1)  
print("Popped element:", popped_val)
print("Setelah pop(1):", a) 

# Menghapus elemen pertama (10)
del a[0]  
print("Setelah del a[0]:", a)
```
Hasilnya : 
```
Array Sebelum Deletion :  [10, 20, 30, 40, 50]
Setelah remove(30): [10, 20, 40, 50]
Popped element: 20
Setelah pop(1): [10, 40, 50]
Setelah del a[0]: [40, 50]
```
### Array Multidimensi / Matriks dengan Numpy
Array multidimensi pada matematika sering disebut sebagai matriks. Pada bahasa pemrograman python kita dapat mengelola matriks dengan menggunakan `numpy`. 

Matriks dalam kode program pada umumnya dibuat dengan menggunakan array dua dimensi, karena matriks memiliki dua komponen utama yaitu **baris (*row*)** dan **kolom (*column*)**. 

![Matriks](https://www.petanikode.com/img/python-numpy/matriks.avif)

sumber : [Petanikode.com](https://petanikode.com)

contoh : 
```python
matriks = [[1,2,3],
           [4,5,6],
           [7,8,9]]
```

Terlihat pada contoh diatas sebuah matriks yang memiliki dua dimensi, yaitu dimensi **baris** (*row*) dan dimensi **kolom** (*column*). Nah apabila kita ingin membuat matriks dengan menggunakan `numpy` maka kita dapat membuatnya seperti contoh berikut : 

Praktek 12
```python
# impor library numpy
import numpy as np

# membuat matiks dengan numpy
matriks_np = np.array([[1,2,3],
                        [4,5,6],
                        [7,8,9]])
```

lalu bagaimana cara mengakses matriks? misalnya kita ingin mengambil nilai `5` maka yang perlu kita lakukan pertama adalah menggenatuhi berada di indeks baris dan kolom berapa lokasi nilai yang ingin kita ambil. 

Nilai `5` terlihat berada pada baris ke-1 dan kolom ke-1. Kok indeks-nya 1 (baris/kolom)? Seperti `list` indeks array juga dimulai dari nol. Lalu bagaimana jika kita ingim mengakses angka atau nilai `9` dari matriks?

Nilai `9` berada pada baris ke-3 dan kolom ke-3, karna indeks matrik dimulai dari nol maka berada pada indeks ke `[2][2]`. 

```python
print(matriks_np[2][2])
```

### Operasi Matriks dengan Numpy
Operasi pada matriks yang dibuat dengan `numpy` sama seperti matriks yang dibuat menggunakan `list`, yaitu operasi aritmatika, dan operasi lainnya. Akan tetapi jika kita melakukan operasi aritmatika terhadap matriks yang dibuat menggunakan `list` prosesnya cukup rumit. 

**Operasi Penjumlahan Matriks**

Bagaimana caranya menjumlahkan dua matriks, Perhatikan gambar dibawah ini : 

![penjumlahan matriks](https://github.com/adamMaulachela/Kuliah_Struktur_data/blob/main/img/matriks_add.png)

Operasi penjumlahan matriks pada dasarnya memiliki syarat utama yaitu d**ua matriks yang dijumlahkan harus memiliki ordo (dimensi) yang sama**. Seperti pada gambar diatas terdapat dua matriks yaitu A dan B, yang keduanya memiliki dimensi yang sama yaitu 2 x 2. Cara menjumlahkannya cukup mudah dimana indeks pertama pada matriks A yaitu `a1` ditambahkan dengan indeks petama matrik B yaitu `b1` atau `a1 + b1`, dan seterusnya. 

Untuk lebih memahami kita akan coba praktek 5 menjumlahkan dua matriks dengan `list` dan matriks dari `numpy`. 

Praktek 13 
```python
# Program penjumlahan matriks yang dibuat dari list

X = [[12,7,3],
    [4,5,6],
    [7,8,9]]

Y = [[5,8,1],
    [6,7,3],
    [4,5,9]]

result = [[0,0,0],
         [0,0,0],
         [0,0,0]]

# proses penjumlahan dua matriks menggunakan nested loop
# mengulang sebanyak row (baris)
for i in range(len(X)):
   # mengulang sebanyak column (kolom)
   for j in range(len(X[0])):
       result[i][j] = X[i][j] + Y[i][j]

print("Hasil Penjumlahan Matriks dari LIST") 

# cetak hasil penjumlahan secara iteratif
for r in result:   
   print(r)

```

Hasilnya : 
```
Hasil Penjumlahan Matriks dari LIST
[17, 15, 4]
[10, 12, 9]
[11, 13, 18]
```
Jika kita perhatikan kumpulan baris kode diatas, terlihat proses penjumlahan dua matrik sangat rumit ketika kita matriks yang dijumlahkan dibuat dari `list`. 

Lalu bagaimana jika matriks yang dibuat dari `numpy`? coba perhatikan Praktek 6 berikut ini : 

Praktek 14 
```Python
# impor library numpy
import numpy as np

# Membuat matriks dengan numpy
X = np.array([
    [12,7,3],
    [4,5,6],
    [7,8,9]])

Y = np.array(
    [[5,8,1],
    [6,7,3],
    [4,5,9]])

# Operasi penjumlahan dua matrik numpy
result = X + Y

# cetak hasil
print("Hasil Penjumlahan Matriks dari NumPy")
print(result)
```
Hasilnya : 
```
Hasil Penjumlahan Matriks dari NumPy
[[17 15  4]
 [10 12  9]
 [11 13 18]]
```

**Operasi Pengurangan Matriks**

Setelah kita memahami cara penjumlahan matriks selanjutnya kita akan mempelajari bagaimana cara melakukan operasi pengurangan matriks. Berikut ilustrasinya : 

![minus](https://github.com/adamMaulachela/Kuliah_Struktur_data/blob/main/img/minus.png)

Operasi pengurangan matriks kurang lebih sama dengan operasi penjumlahan matriks. Disini yang berubah hanya operator aritmatikanya saja. Lalu bagaimana operasi pengurangan matriks di python menggunakan `numpy`?

Praktek 15
```Python
# impor library numpy
import numpy as np

# Membuat matriks dengan numpy
X = np.array([
    [12,7,3],
    [4,5,6],
    [7,8,9]])

Y = np.array(
    [[5,8,1],
    [6,7,3],
    [4,5,9]])

# Operasi pengurangan dua matrik numpy
result = X - Y

# cetak hasil
print("Hasil Pengurangan Matriks dari NumPy")
print(result)
```

outputnya : 
```
Hasil Pengurangan Matriks dari NumPy
[[ 7 -1  2]
 [-2 -2  3]
 [ 3  3  0]]
```

**Operasi Perkalian Matriks**

Selanjutnya adalah operasi perkalian matriks yang dihasilkan dari `numpy`, berikut prakteknya : 

Praktek 16
```python
# impor library numpy
import numpy as np

# Membuat matriks dengan numpy
X = np.array([
    [12,7,3],
    [4,5,6],
    [7,8,9]])

Y = np.array(
    [[5,8,1],
    [6,7,3],
    [4,5,9]])

# Operasi perkalian dua matrik numpy
result = X * Y

# cetak hasil
print("Hasil Perkalian Matriks dari NumPy")
print(result)
```
Hasilnya : 
```
Hasil Perkalian Matriks dari NumPy
[[60 56  3]
 [24 35 18]
 [28 40 81]]
```

**Operasi Pembagian Matriks**

Terakhir kita akan melakukan operasi pembagian matriks yang dihasilkan dari `numpy`, berikut prakteknya: 

Praktek 9
```python
# Praktek 17 : Operasi Pembagian Matriks dengan numpy
# impor library numpy
import numpy as np

# Membuat matriks dengan numpy
X = np.array([
    [12,7,3],
    [4,5,6],
    [7,8,9]])

Y = np.array(
    [[5,8,1],
    [6,7,3],
    [4,5,9]])

# Operasi pembagian dua matrik numpy
result = X / Y

# cetak hasil
print("Hasil Pembagian Matriks dari NumPy")
print(result)
```
Hasilnya : 
```
Hasil Pembagian Matriks dari NumPy
[[2.4        0.875      3.        ]
 [0.66666667 0.71428571 2.        ]
 [1.75       1.6        1.        ]]
```

### Transformasi Matriks dengan NumPy
Transformasi matriks artinya mengubah bentuk matriks menjadi bentuk yang berbeda atau bentuk lainnya. Dalam `numpy` terdapat tiga fungsi yang digunakan untuk melakukan transformasi matriks, yaitu : 
1. `transpose()`, berfungsi untuk **membalik matriks**
2. `reshape()`, berfungsi untuk mengubah dimensi matriks menjadi **ukuran tertentu**
3. `flatten()`, dan `reval()`, untuk **mengubah matriks** menjadi **list** atau dalam matematika disebut **vektor**


**Membalik Matriks `transpose()`**

Konsep membalik matriks menggunakan fungsi `transpose()` adalah membalik posisi baris (*row*) menjadi kolom (*column*) dan otomatis kolom (*column*) menjadi baris (*row*). Berikut contohnya : 

Praktek 18 
```python
# impor library numpy
import numpy as np

# membuat matriks
matriks_a = np.array([
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]
])

# cetak matriks
print("Matriks Sebelum Transpose")
print(matriks_a)

# transpose matriks_a
balik = matriks_a.transpose()

# cetak matriks setelah dibalik
print("Matriks Setelah Transpose")
print(balik)
```
Hasilnya : 
```
Matriks Sebelum Transpose
[[1 2 3]
 [4 5 6]
 [7 8 9]]
Matriks Setelah Transpose
[[1 4 7]
 [2 5 8]
 [3 6 9]]
```

**Mengubah Dimensi Matriks `reshape()`
Fungsi `reshape()` dalam `numpy` berfungsi untuk mengubah ukuran matriks dalam ordo tertentu. 

Praktek 19
```python
# impor library numpy
import numpy as np

# membuat array 1 dimensi
arr_1d = np.array([50, 70, 89, 99, 103, 35])

# cetak matriks sebelum reshape
print("Matriks Sebelum Reshape")
print(arr_1d)
print("Ukuran Matriks : ", arr_1d.shape)
print("\n")

# mengubah matriks menjadi ordo 3 x 2
ubah = arr_1d.reshape(3, 2)

# cetak matriks setelah reshape ke ordo 3 x 2
print("Matriks Setelah Reshape")
print(ubah)
print("Ukuran Matriks : ", ubah.shape)
```
hasilnya : 
```
Matriks Sebelum Reshape
[ 50  70  89  99 103  35]
Ukuran Matriks :  (6,)


Matriks Setelah Reshape
[[ 50  70]
 [ 89  99]
 [103  35]]
Ukuran Matriks :  (3, 2)
```

Pada praktek 19 diatas terdapat sebuah matriks dengan ordo 6 x 1 artinya ada 6 kolom dan hanya 1 baris, dengan nama `arr_1d`. Selanjutnya diubah ordonya menjadi 2 x 3 sehingga terdapat 2 kolom dan 3 baris. 

**Mengubah Matriks Menjadi Vektor dengan `flatten()`**

Sebelum kita mencoba fungsi `flatten()` ada baiknya kita kenalan dulu dengan vektor. Vektor adalah matriks khusus yang hanya memiliki 1 dimensi yaitu 1 baris atau 1 kolom. Oleh karena itu terdapat dua jenis vektor yaitu vektor baris, artinya hanya ada 1 baris, vektor kolom artinya hanya ada 1 kolom saja. 

Praktek 20  
```python
# vektor baris
vek_1 = np.array([1, 2, 3])

# vektor kolom
vek_2 = np.array([1], 
                 [2],
                 [3])
# atau menggunakan transpose()
vek_3 = np.array([1, 2, 3]).T

print("Vektor Baris")
print(vek_1)
print("vektor Kolom")
print(vek_2)
print("Vektor Kolom dengan transpose()")
print(vek_3)
```
outputnya : 
```
Vektor Baris
[1 2 3]
vektor Kolom
[[1]
 [2]
 [3]]
Vektor Kolom dengan transpose()
[[1]
 [2]
 [3]]
```

Nah fungsi `flatten()` secara umum berfungsi untuk meratakan atau mengubah data multidimensi menjadi data satu dimensi. 

Praktek 21 
```python
# impor library numpy
import numpy as np

# membuat matriks
matriks_a = np.array([
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]
])

# cetak matriks awal
print("Matriks Awal")
print(matriks_a)
print("Ukuran : ", matriks_a.shape)
print("\n")

# ubah matriks menjadi vektor
jd_vektor = matriks_a.flatten()

# cetak vektor
print("Hasil Konversi Matriks ke Vektor")
print(jd_vektor)
print("Ukuran : ", jd_vektor.shape)
```
hasilnya : 
```
Matriks Awal
[[1 2 3]
 [4 5 6]
 [7 8 9]]
Ukuran :  (3, 3)


Hasil Konversi Matriks ke Vektor
[1 2 3 4 5 6 7 8 9]
Ukuran :  (9,)
```

Kita bisa melihat dari `praktek 21` awalnya matriks berordo 3 x 3 kemudian setelah dilakukan konversi dengan fungsi `flatten()` ukuran matrik menjadi vektor baris dengan orde 9 x 1

## Linked-List
Merupakan **koleksi linear dari data**, yang disebut sebagai `nodes` Setiap `nodes` akan menunjuk pada `node` melalui sebuah `pointer`. *Linked-list* juga bisa didefinisikan sebagai kumpulan `nodes` yang merepresentasikan sebuah **sequence** atau urutan. 

Terdapat 2 jenis *linked-list* yaitu : 
1. Single *linked-list*
2. Double *linked-list*

### Singel Linked-List 
Sebuah *linked-list* akan memiliki 1 penghubung ke `node` lain yang disebut *single linked-list*. Di dalam *linked-list* ada 1 pointer yang menjadi gambaran utama yakni *pointer* `HEAD`, yang menunjuk pada `node` pertama di dalam *linked-list* itu sendiri.

Bagaimana struktur `node` dari *linked-list*? 

Pada *Single Linked-list*, setiap `node` terdiri dari dua bagian: 
1. `data`, menyimpan data atau nilai atau value dari `node`, dan 
2. Pointer atau `next` yang berisi petunjuk ke `node` berikutnya. 

Struktur ini memungkinkan `nodes` untuk ditautkan secara dinamis, membentuk urutan seperti rantai. Perhatikan ilustrasi dibawah ini!

![single_ll](https://media.geeksforgeeks.org/wp-content/uploads/20240917161540/Singly-Linked-List.webp)

Lalu bagaimana penerapan *linked-list* pada bahasa pemrograman **python**? Perhatikan struktur kode berikut ini !

```python
# Struktur node dan inisialisasi linked-list
def create_node(data):
    return {'data': data, 'next': None}

# Head awal dari linked list
head = None
```
Pada kode diatas, kelas `Node` berisi bidang `data` integer (data) untuk menyimpan informasi dan pointer ke Node lain (`next`) untuk membuat tautan ke `node` berikutnya dalam *linked-list*. Jika node berikutnya tidak ada maka isi dari `next` adalah `NULL`. 

Sekarang mari kita praktekkan bagaimana kita membuat sebuah `node`, menambahkan node, dan menampilkan `node` dengan Python. Untuk mengimplementasinya dalam python kita perlu memanfaatkan `function` dalam python. 

Praktek 22
```python
# function untuk membuat node
def buat_node(data):
    return {'data': data, 'next': None}

# menambahkan node di akhir list
def tambah_node(head, data):
    new_node = buat_node(data)
    if head is None:
        return new_node
    current = head
    while current['next'] is not None:
        current = current['next']
    current['next'] = new_node
    return head

# menampilkan linked-list
def cetak_linked_list(head):
    current = head
    print('Head', end=' → ')
    while current is not None:
        print(current['data'], end=' → ')
        current = current['next']
    print("NULL")

# Contoh Penerapan
# Head awal dari linked-list
head = None

# Tambah node
head = tambah_node(head, 10)
head = tambah_node(head, 11)
head = tambah_node(head, 12)

# cetak linked-list
print('Linked-List : ')
cetak_linked_list(head)
```
hasilnya : 
```
Linked-List : 
head → 10 → 11 → 12 → NULL
```

Penjelasannya : 

Pada kode diatas setiap `node` direpresentasikan dalam dictionary python, contohnya adalah : 
```python
{'data': 5, 'next': None}
```
***dictionary*** diatas menunjukkan sebuah `node` dengan data berisi 5 dan `next` atau pointer selanjutnya adalah `None` atau tidak ada. 

Untuk menambah `node` maka dijalankan fungsi `def tambah_node(head, data)`. Fungsi ini menerima dua parameter yaitu 
1. `head` sebagai `node` pertama dalam linked-list (nilainya bisa `None` jika list masih kosong) dan  
2. `data` sebagai penampung nilai yang ditambahkan ke list

Dalam fungsi `tambah_node`, terdapat kode berikut ini : 
```python
new_node = buat_node(data)
```
kode ini digunakan untuk membuat `node` baru menggunakan fungsi `buat_node(data)`, yang hasil pembuatannya disimpan dalam variabel `new_node`. Selanjutnya adalah 
```python
if head is None:
    return new_node
```
kode diatas menunjukkan jika `head` bernilai `None`, artinya list masih **kosong**, jadi `node` yang baru dibuat adalah satu-satunya `node` (sekaligus menjadi `head`). 

Kemudian jika list tidak kosong (`head is not None`), maka lakukan kode dibawah ini : 
```python
    current = head
    while current['next'] is not None:
        current = current['next']
```
jadi selama `current['next']` pada `node` tidak `None`, `node` akan berpindah ke node berikutnya sampai node terakhir ditemukan atau `current['next'] == None`. Nah setelah `node` terakhir ditemukan lakukan kode dibawah ini :
```python
current['next'] = new_node
```
Ubah nilai bagian `next` dari `node` terakhir menjadi `node` baru. Selanjutnya kembalikan nilai `head` agar struktur linked-list tetap utuh dari `head` sampai dengan `tail`. 

#### Traversal Single Linked-List
Traversal Single *Linked-List* merupakan salah satu operasi dasar, di mana kita melakukan traversal atau mengunjungi setiap `node` dari *linked-list*. Perhatikan ilustrasi berikut ini !

![traversal_sll](https://media.geeksforgeeks.org/wp-content/uploads/20240726234303/Traversal-of-Singly-Linked-List.gif)

Traversal pada umumnya digunakan untuk :
1. Mencetak isi linked-list
2. Menghitung jumlah elemen
3. Mencari nilai tertentu

Nah bagaimana algoritma dari traversal pada linked-list, berikut algoritmanya : 
1. Mulai dari node pertama (`head`)
2. Selama `node` tidak kosong (`None`): 
   * Proses node tersebut (misalnya mencetak `data` pada `node`)
   * Lanjutkan ke `node` berikutnya (`next`)
3. Jika `next` sama dengan `none`, maka hentikan traversal

Sekarang coba kita implementasi algoritma diatas dengan pyhton. Perhatikan kode dibawah ini !

Praktek 23
```python
# function untuk membuat node
def buat_node(data):
    return {'data': data, 'next': None}

# menambahkan node di akhir list
def tambah_node(head, data):
    new_node = buat_node(data)
    if head is None:
        return new_node
    current = head
    while current['next'] is not None:
        current = current['next']
    current['next'] = new_node
    return head

# traversal untuk cetak isi linked-list
def traversal_to_display(head):
    current = head
    print('Head', end=' → ')
    while current is not None:
        print(current['data'], end=' → ')
        current = current['next']
    print("NULL")
    
# traversal untuk menghitung jumlah elemen dalam linked-list
def traversal_to_count_nodes(head):
    count = 0
    current = head
    while current is not None:
        count += 1
        current = current['next']
    return count

# traversal untuk mencari dimana tail (node terakhir)
def traversal_to_get_tail(head):
    if head is None:
        return None
    current = head
    while current['next'] is not None:
        current = current['next']
    return current

# Penerapan
head = None
head = tambah_node(head, 10)
head = tambah_node(head, 15)
head = tambah_node(head, 117)
head = tambah_node(head, 19)

# cetak isi linked-list
print("Isi Linked-List")
traversal_to_display(head)

# cetak jumlah node 
print("Jumlah Nodes = ", traversal_to_count_nodes(head))

# cetak HEAD node
print("HEAD Node : ", head['data'])

# cetak TAIL NODE
print("TAIL Node : ", traversal_to_get_tail(head)['data'])
```
Hasilnya : 
```
Isi Linked-List
Head → 10 → 15 → 117 → 19 → NULL
Jumlah Nodes =  4
HEAD Node :  10
TAIL Node :  19
```

Bagian penjelasan ini akan menjabarkan 3 traversal yang dilakukan pada kode diatas, yaitu traversal untuk mencetak linked-list, traversal untuk menghitung jumlah `node`, dan traversal untuk mencetak `node` yang menjadi TAIL atau `node` terakhir. 

**Penjelasan fungsi traversal cetak linked-list :**

Perhatikan potongan kode berikut ini 
```python
# traversal untuk cetak isi linked-list
def traversal_to_display(head):
    current = head
    print('Head', end=' → ')
    while current is not None:
        print(current['data'], end=' → ')
        current = current['next']
    print("NULL")
```

Fungsi `traversal_to_display()` bertujuan untuk **menampilkan isi linked list** dari awal sampai akhir dengan cara menelusuri (traversal) setiap node satu per satu.
```python
def traversal_to_display(head)
```

Fungsi ini hanya memiliki 1 parameter yaitu `head`, yaitu node pertama (awal) dari linked list. Selanjutnya perhatikan kode berikut ini : 
```python
    current = head
```
Kita buat variabel current untuk mulai penelusuran dari `node` pertama (`head`). Selanjutnya kita akan mencetak penanda untuk `head` ("Head ->") dari linked-list, agar secara visual kita dapat mengetahui `node` awal. 
```python
    print('Head', end=' → ')
```
Selanjutnya perhatikan kode berikut : 
```python
    while current is not None:
```
potongan kode ini menunjukkan selama `current` belum mencapai akhir dari likend-list (yaitu `current == None`), kita akan terus menelusuri node-node yang ada dalam linked-list.

Selanjutnya perhatikan kode dalam `while` dibawah ini 
```python
        print(current['data'], end=' → ')
```
selama kita menelusuri tiap `node` yang ada dalam linked-list, maka cetak tiap `node` bagian `data` dari `node` tersebut, tambahkan tanda `→` untuk menunjukkan adanya hubungan antar `node`. 

Selanjutnya perhatikan kode dibawah ini
```python
        current = current['next']
```
sesudah kita mencetak `data` dari `node`, lakukan perubahan nilai variabel `current` dengan menggambil bagian `next` dari `node` yang sedang kita kunjungi. 

Selanjutnya perhatikan kode dibawah ini 
```python
    print("NULL")
```

artiya jika kita sudah keluar dari `while` maka kita suah berada di ujung dari linked-list (`current == None`) dan semua `node` sudah tercetak, sehingga kita bisa mencetak nilai `next` dari `node` terakhir berupa `NULL`

**Penjelasan fungsi traversal hitung jumlah node linked-list :**

Perhatikan potongan kode berikut ini :
```python
def traversal_to_count_nodes(head):
    count = 0
    current = head
    while current is not None:
        count += 1
        current = current['next']
    return count
```

Fungsi `traversal_to_count_nodes(head)` digunakan untuk **menghitung jumlah node** (simpul) dalam sebuah *singly linked-list*. Jadi, berapa banyak data yang ada dalam *linked-list* itulah yang dihitung.

```python
def traversal_to_count_nodes(head):
```
fungsi ini hanya memiliki satu parameter saja yaitu `head` yaitu `node` pertama dari *linked-list*. Selanjutnya perhatikan baris kode didalam fungsi `traversal_to_count_nodes()` berikut ini:

Selanjutnya perhatikan kode berikut ini 
```python 
    count = 0
    current = head
```
Pada kode diatas fungsi `traversal_to_count_nodes()` dimulai dengan sebuah variabel `count` untuk menyimpan jumlah node, dan pada awalnya kita set lebih dulu dengan angka nol. 

Selanjutnya kita deklarasikan juga variabel `current` untuk menyimpan data `node` yang akan dikunjungi dan digunakan untuk traversal ke elemen *linked-list*, dan dimulai dari `node` pertama(`head`). Berikutnya perhatikan kode berikut ini : 
```python
    while current is not None:
```
Berikutnya kita akan melakukan perulangan selama node `current` belum bernilai `None`, tujuannya agar kita bisa traversal dari satu `node` ke `node` yang lain. 
```python
        count += 1
        current = current['next']
```
selama melakukan perulangan dan melewati `node`, nilai `count` ditambahkan sebanyak 1, dan lanjutkan ke `node` berikutnya dengan mengambil referensi atau pointer dari setiap `node` atau `current['next']`. 

Selanjutnya perhatikan kode berikut ini 
```python
return count
```
jika traversal sudah selesai semua, maka fungsi `traversal_to_count_nodes()` akan mengembalikan nilai `count` yang sudah dijumlahkan dari hasil kunjungan/traversal ke setiap `node`. 

**Penjelasan Fungsi Traversal Mencari Ekor (Tail) Linked-List**

Fungsi ini bertujuan untuk menemukan `node` terakhir pada *linked-list* dan menentukan `node` tersebut sebagai ekor (`tail`) dari rangkaian *linked-list*. 
```python
def traversal_to_get_tail(head):
```

Pada awalnya kita mendefinsikan sebuah fungsi yang menerima satu parameter yaitu `head` yaitu `node` pertama dalam *linked-list*. Selanjutnya perhatikan potongan kode berikut ini : 
```python
    if head is None:
        return None
```
jika `head` bernilai `None`, artinya *linked-list* kosong, maka langsung kembalikan None (tidak ada `tail`).  
```Python
    current = head
```
Variabel `current` digunakan untuk mulai traversal dari `node` pertama (`head`).
```python
    while current['next'] is not None:
        current = current['next']
```
Selama `node` saat ini (`current`) masih memiliki `node` berikutnya, kita pindah ke `node` tersebut. Jadi kita terus melompat dari satu `node` ke `node` berikutnya, sampai menemukan `node` yang tidak punya "`next`" lagi. Node terakhir adalah `node` yang `current['next'] == None`.
```python
    return current
```
Setelah keluar dari `loop`, berarti current adalah **node terakhir** (`tail`), maka kita kembalikan `node` itu.

#### Insert Single Linekd-List
Penyisipan node adalah proses menambahkan data baru ke dalam linked-list. bisa di : 
1. Awal *linked-list* -> disebut **prepend**
2. Lokasi tertentu (misal setelah `node` ke-2) -> disebut **insert at any position**

**1. Penyisipan Diawal Linked-List**

Untuk menyisipkan `node` baru di bagian depan, kita buat `node` baru dan arahkan referensi berikutnya ke `head` `linked-list` saat ini. Kemudian, kita perbarui `head` tersebut menjadi `node` baru ini. Operasi ini efisien karena hanya memerlukan penyesuaian beberapa penunjuk.

![Insert Front](https://media.geeksforgeeks.org/wp-content/uploads/20240726172733/Insertion-at-the-Beginning-of-Singly-Linked-List.webp)

**Algoritmanya :**
1. Jadikan `node` pertama Linked-List yang terhubung ke `node` baru
2. Hapus `head` dari `node` pertama Linked-List
3. Jadikan `node` baru sebagai `head` Linked-List.

Berikut ini adalah implementasi pada bahasa pemrograman python untuk penyisipan `node` di depan *linked-list*, adalah sebagai berikut : 

Praktek 24
```python
# membuat node baru
def sisip_depan(head, data):
    new_node = {'data': data, 'next': head}
    return new_node

# menampilkan linked-list
def cetak_linked_list(head):
    current = head
    print('Head', end=' → ')
    while current is not None:
        print(current['data'], end=' → ')
        current = current['next']
    print("NULL")

# Penerapan membuat linked-list awal
head = None
head = sisip_depan(head, 30)
head = sisip_depan(head, 20)
head = sisip_depan(head, 10)

# cetak isi linked-list awal
print("Isi Linked-List Sebelum Penyisipan di Depan")
cetak = cetak_linked_list(head)

# Penyisipan node 
data = 99
head = sisip_depan(head, data)

print("\nData Yang Disispkan : ", data)

# cetak isi setelah penyisipan node baru di awal 
print("\nIsi Linked-List Setelah Penyisipan di Depan")
cetak_linked_list(head)
```
Hasilnya : 
```
Isi Linked-List Sebelum Penyisipan di Depan
Head → 10 → 20 → 30 → NULL

Data Yang Disisipkan : 99

Isi Linked-List Setelah Penyisipan di Depan
Head → 99 → 10 → 20 → 30 → NULL
```
Penjelasannya : 

Perhatiakan potongan kode ini : 
```python
# membuat node baru
def sisip_depan(head, data):
    new_node = {'data': data, 'next': head}
    return new_node
```

fungsi `sisip_depan(head, data)` adalah sebuah fungsi yang memiliki dua buah parameter yaitu `head` dan `data`. Kedua parameter itu disimpan dalam variabel `new_node` dan bertipe data *dictionary*. Melalui fungsi ini node baru akan dibuat dan selalu diletakkan pada posisi awal *linked-list*. 

**2. Penyisipan di Posisi Tertentu**

Diberikan sebuah *single linked-list*, sebuah posisi pos, dan data, tugasnya adalah memasukkan data tersebut ke dalam *linked-list* pada posisi yang diberikan. 

![sisip_tengah](https://media.geeksforgeeks.org/wp-content/uploads/20240902143425/Insertion-at-a-Specific-Position-of-the-Singly-Linked-List-copy.webp)

Selanjutnya berikut ini adalah algoritmanya : 

* Buat `node` baru, 
* Traversal ke `node` posisi ke-(`n-1`) (karena kita ingin menyisipkan setelah `node` ke-`n`).
* Ubah `next` dari `node` sebelumnya dan `node` baru:
  * Perbarui `new_node.next` = `current.next`
  * Perbarui `current.next` = `new_node`

Berikut ini adalah implementasi dari algoritma penyisipan node pada posisi tertentu dalam bahasa pemrograman python : 

Praktek 25
```python
# membuat node baru
def sisip_depan(head, data):
    new_node = {'data': data, 'next': head}
    return new_node

# sisip node diposisi mana saja
def sisip_dimana_aja(head, data, position):
    new_node = {'data': data, 'next': None}
    
    # cek jika posisi di awal pakai fungsi sisip_depan() 
    if position == 0:
        return sisip_depan(head, data)
    
    current = head
    index = 0
    
    # traversal menuju posisi yang diinginkan dan bukan posisi 0
    while current is not None and index < position - 1:
        current = current['next']
        index += 1
    
    if current is None:
        print("Posisi melebihi panjang linked list!")
        return head

    # ubah next dari node sebelumnya menjadi node baru
    new_node['next'] = current['next']
    current['next'] = new_node
    return head

## menampilkan linked-list
def cetak_linked_list(head):
    current = head
    print('Head', end=' → ')
    while current is not None:
        print(current['data'], end=' → ')
        current = current['next']
    print("NULL")

# Penerapan 
# membuat linked-list awal 
head = None
head = sisip_depan(head, 30)
head = sisip_depan(head, 20)
head = sisip_depan(head, 10)
head = sisip_depan(head, 50)
head = sisip_depan(head, 70)

# cetak isi linked-list awal
print("Isi Linked-List Sebelum Penyisipan")
cetak = cetak_linked_list(head)

# Penyisipan node 
data = 99
pos = 3
head = sisip_dimana_aja(head, data, pos)

print("\nData Yang Disispkan : ", data)
print("Pada posisi : ", pos, "")

# cetak isi setelah penyisipan node baru di awal 
print("\nIsi Linked-List Setelah Penyisipan di tengah")
cetak_linked_list(head)
```

Hasilnya : 
```
Isi Linked-List Sebelum Penyisipan
Head → 70 → 50 → 10 → 20 → 30 → NULL

Data Yang Disispkan :  99
Pada posisi :  3 

Isi Linked-List Setelah Penyisipan di tengah
Head → 70 → 50 → 10 → 99 → 20 → 30 → NULL
```

Penjelasannya : 
```python
def sisip_dimana_aja(head, data, position):
    new_node = {'data': data, 'next': None}
    
    # cek jika posisi di awal pakai fungsi sisip_depan() 
    if position == 0:
        return sisip_depan(head, data)
    
    current = head
    index = 0
    
    # traversal menuju posisi yang diinginkan dan bukan posisi 0
    while current is not None and index < position - 1:
        current = current['next']
        index += 1
    
    if current is None:
        print("Posisi melebihi panjang linked list!")
        return head

    # ubah next dari node sebelumnya menjadi node baru
    new_node['next'] = current['next']
    current['next'] = new_node
    return head
```
fungsi `sisip_dimana_aja(head, data, position)` befungsi untuk menyisipkan `node` baru pada posisi dimana saja di dalam *linked-list*. Selanjutnya perhatikan potongan kode berikut ini : 
```python
    new_node = {'data': data, 'next': None}
```
Potongan kode diatas menunjukkan pembuatan `node` baru dalam bentuk *dictionary*, dengan pasangan *key-value* `data` dan `next`. Selanjutnya :
```python
    # cek jika posisi di awal pakai fungsi sisip_depan() 
    if position == 0:
        return sisip_depan(head, data)
```

jika nilai `position` sama dengan 0 (`True`) tandanya `node` baru berada diawal *linked-list*. Oleh karena itu kembali ke fungsi `sisip_depan()` dengan nilai `head` dan `data` sebagai parameter. Selanjutnya jika nilai `position != 0` jalankan potongan kode berikut ini 
```python
    # perbarui variabel current dan deklarasi index = 0
    current = head
    index = 0

    # traversal menuju posisi yang diinginkan dan bukan posisi 0
    while current is not None and index < position - 1:
        current = current['next']
        index += 1
```
Potongan kode diatas menunjukkan proses traversal dengan dua kondisi yang harus dipenuhi, yaitu : 
1. Nilai `current is not None`, dan 
2. `index < position -1`

Selama dua kondisi ini terpenuhi maka perbarui `current = current['next']` dan perbarui nilai variabel `index = index + 1`. Selanjutnya perhatikan potongan kode dibawah ini  
```python
    if current is None:
        print("Posisi melebihi panjang linked list!")
        return head
```
pada potongan kode diatas menyatakan bahwa jika nilai `current is None` maka posisi yang dimasukkan melebihi panjang dari *linked-list*. Selanjutnya perhatikan kode berikut ini :
```python
    # ubah next dari node sebelumnya menjadi node baru
    new_node['next'] = current['next']
    current['next'] = new_node
    return head
```
Pada potongan kode diatas adalah proses perubahan posisi dari `node` baru yang disisipkan dengan `node` yang sudah ada dalam *linked-list*. Selanjutnya fungsi diakhir dengan mengembalikan nilai `head`. 

#### Deleting Single Linked-List

Terdapat dua jenis penghapusan atau deleting dalam singel linked-list yaitu : 
1. Penghapusan pada awal node dalam linked-list 
2. Penghapusan pada akhir node dalam linked-list
3. Penghapusan pada bagian tertentu (tengah) dari linked-list. 

**1. Penghapusan Pada Awal (`Head`) Node Dalam Linked-List**

Untuk menghapus `node` pertama dari suatu *linked-list*, simpan `head` saat ini dalam variabel sementara (`temp`), pindahkan penunjuk `head` ke `node` berikutnya, hapus `node` `head` sementara, dan terakhir, kembalikan `head` baru dari *linked-list*.

![delete_sll](https://media.geeksforgeeks.org/wp-content/uploads/20240827131844/Deletion-at-beginning-.webp)

Berikut algoritmanya : 
1. Periksa apakah `node` kosong -> jika ya, berarti linked-list kosong
2. Geser `head` ke `head.next` (`node` berikutnya)
3. Selesai

Praktek 26
```python
# membuat node baru
def sisip_depan(head, data):
    new_node = {'data': data, 'next': head}
    return new_node

# sisip node diposisi mana saja
def sisip_dimana_aja(head, data, position):
    new_node = {'data': data, 'next': None}
    
    # cek jika posisi di awal pakai fungsi sisip_depan() 
    if position == 0:
        return sisip_depan(head, data)
    
    current = head
    index = 0
    
    # traversal menuju posisi yang diinginkan dan bukan posisi 0
    while current is not None and index < position - 1:
        current = current['next']
        index += 1
    
    if current is None:
        print("Posisi melebihi panjang linked list!")
        return head

    # ubah next dari node sebelumnya menjadi node baru
    new_node['next'] = current['next']
    current['next'] = new_node
    return head

# menghapus head node dan mengembalikan head baru
def hapus_head(head):
    # cek apakah list kosong
    if head is None:
        print("Linked-List kosong, tidak ada yang bisa")
        return None
    print(f"\nNode dengan data '{head['data']}' dihapus dari head linked-list")
    return head['next']

## menampilkan linked-list
def cetak_linked_list(head):
    current = head
    print('Head', end=' → ')
    while current is not None:
        print(current['data'], end=' → ')
        current = current['next']
    print("NULL")

# Penerapan 
# membuat linked-list awal 
head = None
head = sisip_depan(head, 30) # tail
head = sisip_depan(head, 20)
head = sisip_depan(head, 10)
head = sisip_depan(head, 50)
head = sisip_depan(head, 70) # head 

# cetak isi linked-list awal
print("Isi Linked-List Sebelum Penghapusan")
cetak_linked_list(head)

# Penghapusan head linked-list
head = hapus_head(head)

# cetak isi setelah hapus head linked-list 
print("Isi Linked-List Setelah Penghapusan Head ")
cetak_linked_list(head)
```

Hasilnya : 
```
Isi Linked-List Sebelum Penghapusan
Head → 70 → 50 → 10 → 20 → 30 → NULL

Node dengan data '50' dihapus dari head linked-list
Isi Linked-List Setelah Penghapusan Head 
Head → 50 → 10 → 20 → 30 → NULL
```

Penjelasannya : 

Perhatikan potongan kode berikut ini !
```python
# menghapus head node dan mengembalikan head baru
def hapus_head(head):
    # cek apakah list kosong
    if head is None:
        print("Linked-List kosong, tidak ada yang bisa")
        return None
    print(f"\nNode dengan data '{head['data']}' dihapus dari head linked-list")
    return head['next']
```
Fungsi ini `def hapus_head(head)`, bertujuan untuk menghapus `node` yang berada di `head` *linked-list*, dengan satu parameter yaitu `head`. Di dalam fungsi ini terdapat kode dibawah ini: 
```python
    if head is None:
        print("Linked-List kosong, tidak ada yang bisa")
        return None
```
potongan kode ini mengecek apakah linked-list kosong, `head is None` berarti tidak ada `node` sama sekali dalam list. Jika linked-list kosong tampilkan pesan, dan mengembalikan nilai None sebagai tanda bahwa linked-list kosong setelah penghapusan  dan biasanya hasil `return` ini akan disimpan kembali di variabel `head` di program utama. Berikutnya perhatikan potongan kode berikut ini : 
```python
    print(f"\nNode dengan data '{head['data']}' dihapus dari head linked-list")
    return head['next']
```
Jika `head` tidak kosong, maka tampilkan data dari `node` yang akan dihapus. Bagian `'{head['data']}'` mengambil isi data dari `node` pertama. Selanjutnya `return head['next']` adalah bagian inti dari penghapusan `node` pertama. Fungsi ini mengembalikan `node` kedua(yaitu `head.next`), dengan cara ini `node` pertama terlepas dari *linked-list* dan secara otomatis akan dihapus. 

**2. Penghapusan Pada Akhir (`Tail`) Linked-List**

Untuk melakukan operasi penghapusan di akhir *linked-list*, kita perlu menelusuri `list` untuk menemukan `node` kedua terakhir, lalu mengatur pointer berikutnya ke `null`. Jika `list` kosong, maka tidak ada `node` yang akan dihapus atau hanya memiliki satu `node` yang mengarah ke `null`.

Berikut algoritmanya : 

1. Jika `head` kosong -> kembalikan `None`
2. Jika `head['next']` adalah `None` -> artinya hanya ada 1 `node` -> hapus `node` itu
3. Traversal : cari `node` yang `next.next` -nya adalah `None`
4. Atur `node` tersebut supaya `next`-nya menjadi `None`


Praktek 27 
```python
# membuat node baru
def sisip_depan(head, data):
    new_node = {'data': data, 'next': head}
    return new_node

# menghapus head node dan mengembalikan head baru
def hapus_tail(head):
    # cek apakah head node == None
    if head is None:
        print('Linked-List Kosong, tidak ada yang bisa dihapus!')
        return None
    
    # cek node hanya 1 
    if head['next'] is None:
        print(f"Node dengan data '{head['data']}' dihapus. Linked list sekarang kosong.")
        return None
    
    current = head
    while current['next']['next'] is not None:
        current = current['next']
        
    print(f"\nNode dengan data '{current['next']['data']}' dihapus dari akhir.")
    current['next'] = None
    return head    

## menampilkan linked-list
def cetak_linked_list(head):
    current = head
    print('Head', end=' → ')
    while current is not None:
        print(current['data'], end=' → ')
        current = current['next']
    print("NULL")

# Penerapan 
# membuat linked-list awal 
head = None
head = sisip_depan(head, 30) # tail
head = sisip_depan(head, 20)
head = sisip_depan(head, 10)
head = sisip_depan(head, 50)
head = sisip_depan(head, 70) # head 

# cetak isi linked-list awal
print("Isi Linked-List Sebelum Penghapusan")
cetak_linked_list(head)

# Penghapusan tail linked-list
head = hapus_tail(head)

# cetak isi setelah hapus Tail linked-list 
print("Isi Linked-List Setelah Penghapusan Tail ")
cetak_linked_list(head)
```
Hasilnya : 
```
Isi Linked-List Sebelum Penghapusan
Head → 70 → 50 → 10 → 20 → 30 → NULL

Node dengan data '30' dihapus dari akhir.
Isi Linked-List Setelah Penghapusan Tail 
Head → 70 → 50 → 10 → 20 → NULL
```

Penjelasannya : 

Untuk menyelesaikan kasus penghapusan ekor (`tail`) dari *linked-list* kita akan menggunakan fungsi `hapus_tail()` berikut ini : 
```python
def hapus_tail(head):
    # cek apakah head node == None
    if head is None:
        print('Linked-List Kosong, tidak ada yang bisa dihapus!')
        return None
    
    # cek node hanya 1 
    if head['next'] is None:
        print(f"Node dengan data '{head['data']}' dihapus. Linked list sekarang kosong.")
        return None
    
    current = head
    while current['next']['next'] is not None:
        current = current['next']
        
    print(f"\nNode dengan data '{current['next']['data']}' dihapus dari akhir.")
    current['next'] = None
    return head    
```

Jika kita bedah isi dari fungsi `hapus_tail()` diatas, pertama fungsi ini menerima hanya satu parameter saja yaitu `head` yang merepresentasikan `node` pertama dari *linked-list*. 
```python
def hapus_tail(head):
```

Didalam fungsi ini diawali dengan cek apakah *linked-list* saat ini kosong atau tidak, dan jika ya maka cetak pesan bahwa *linked-list* kosong serta kembalikan nilai `None`, yang artinya `list` kosong. 
```python
    # cek apakah head node == None
    if head is None:
        print('Linked-List Kosong, tidak ada yang bisa dihapus!')
        return None
```

Selanjutnya fungsi ini mengecek apakah *linked-list* hanya memiliki 1 `node` saja,  `head['next'] is None` berarti `node` tersebut tidak menunjuk ke `node` lain, maksudnya tidak ada `node` berikutnya. 
```python
    # cek node hanya 1 
    if head['next'] is None:
        print(f"Node dengan data '{head['data']}' dihapus. Linked list sekarang kosong.")
        return None
```
jika benar `node` tidak memiliki pointer ke `node` berikutnya, maka cetak pesan bahwa `node` dengan isi dari `node` `head('data)` akan dihapus dari *linked-list*. Jika sudah terhapus maka *linked-list* kosong dan `None` dikembalikan sebagai nilai baru `head`. 

Selanjutnya jika *linked-list* tidak kosong, dan tidak hanya punya satu `node`, maka kita perlu melakukan traversal (penelusuran) untuk menemukan `tail` atau ekor dari *linked-list*. Perhatian potongan kode berikut : 
```python
    current = head
    while current['next']['next'] is not None:
        current = current['next']
```

kode `current = head` menunjukkan kita akan menggunakan variabel `current` untuk menelusuri (traversal) *linked-list*, dan penelusurannya diawali dengan `node` pertama (`head`). Selanjutnya kode ini `while current['next']['next'] is not None` merupakan perulangan untuk mencari `node` terakhir. 

`current['next']` merupakan `node` setelah `current` atau setelah `head` (pada perulangan pertama), sementara `current['next]['next']` merupakan `node` setelah `node` setelahnya (dua langkah ke depan). `is not None` menunjukkan bahwa `node` dua langkah ke depan itu tidak bernilai `None` atau masih ada `node` berikutnya. 

Sederhananya perintah `while current['next']['next'] is not None` berarti selama `node` setelah `current` masih memiliki `node` berikutnya maka lanjutnkan penelusuran (traversal). Dengan kata lain jangan berhenti sampai `current` berada di `node` kedua terakhir atau jika 2 `node` didepan `current` tidak ada `node` berikutnya maka hentikan perulangan. 

ilustrasinya seperti ini : 
```python
head = {
    'data': 10,
    'next': {
        'data': 20,
        'next': {
            'data': 30,
            'next': None
        }
    }
}
```
Selanjutnya perhatikan kode berikut ini : 
```python
    print(f"\nNode dengan data '{current['next']['data']}' dihapus dari akhir.")
    current['next'] = None
    return head
```

perintah `print(f"\nNode dengan data '{current['next']['data']}' dihapus dari akhir.")` dijalankan ketika proses perulangan `while current['next']['next'] is not None` sudah tidak terpenuhi lagi, maka kita sudah mengetahui `node` terakhir dari *linked-list*, dan kita munculkan pesan bahwa data pada `node` terakhir inilah yang akan kita hapus. 

Bagaimana cara menghapusnya adalah dengan mengubah isi `next` dari `node` sebelah kita menjadi `None`. Setelah penghapusan `node` terakhir, kita kembalikan `head` lama. Karena `head` tidak berubah, tapi isi *linked-list*-nya sudah diperbarui (`node` terakhir telah dihapus).

**3. Penghapusan Pada Posisi Tengah Linked-List**

Penghapusan pada posisi tertentu dalam *linked-list* melibatkan penghapusan `node` dari indeks/posisi tertentu, yang bisa menjadi `node` tengah diantara `node` pertama dan akhir. 

![hapus_tangah](https://media.geeksforgeeks.org/wp-content/uploads/20240729185435/Deletion-specific-At-End--.webp)

Pada tipe penghapusan ini konsepnya adalah sebagai berikut : 
1. Kita akan menghapus node pada **posisi tertentu yang bukan posisi pertama (`head`) dan akhir (`tail`)**. 
2. Caranya adalah dengan : 
   * Menelusuri sampai ke **`node` sebelum posisi yang ingin dihapus**
   * Menyambungkan `node` tersebut ke `node` **setelah `node` yang akan dihapus**
   * **Melewati `node` yang dihapus**, sehingga secara tidak langsung `node` terbuang
  
Algoritmanya adalah sebagai berikut : 
1. Jika list kosong -> Kembalikan None
2. Jika posisi < 0 tidak valid
3. jika posisi = 0 kita gunakan fungsi `hapus_head`
4. Telusuri `node` sampai satu `node` sebelum target
5. Putuskan sambungan ke `node` target, dan sambungkan ke `node` setelahnya. 

Mari kita implementasikan dalam bahasa pemrograman python : 
Praktek 28
```python
# Praktek 28 : Menghapus node di posisi manapun (tengah)
# membuat node baru
def sisip_depan(head, data):
    new_node = {'data': data, 'next': head}
    return new_node

# menghapus head node dan mengembalikan head baru
def hapus_head(head):
    # cek apakah list kosong
    if head is None:
        print("Linked-List kosong, tidak ada yang bisa")
        return None
    print(f"\nNode dengan data '{head['data']}' dihapus dari head linked-list")
    return head['next']

# menghapus node pada posisi manapun (tengah)
def hapus_tengah(head, position):
    # cek apakah head node == None
    if head is None:
        print('\nLinked-List Kosong, tidak ada yang bisa dihapus!')
        return None
    
    # cek apakah posisi < 0
    if position < 0:
        print('\nPosisi Tidak Valid')
        return head
    
    # Cek apakah posisi = 0 
    if position == 0:
        print(f"Node dengan data '{head['data']}' dihapus dari posisi 0.")
        hapus_head(head)
        return head['next']
    
    current = head
    index = 0
    
    # cari node sebelum posisi target
    while current is not None and index < position -1:
        current = current['next']
        index += 1
        
    # Jika posisi yang diinputkan lebih besar dari panjang list
    if current is None or current['next'] is None:
        print("\nPosisi melebih panjang dari linked-list")
        return head
    
    print(f"\nNode dengan data '{current['next']['data']}' dihapus dari posisi {position}.")
    current['next'] = current['next']['next']
    return head

## menampilkan linked-list
def cetak_linked_list(head):
    current = head
    print('Head', end=' → ')
    while current is not None:
        print(current['data'], end=' → ')
        current = current['next']
    print("NULL")

# Penerapan 
# membuat linked-list awal 
head = None
head = sisip_depan(head, 30) # tail
head = sisip_depan(head, 20)
head = sisip_depan(head, 10)
head = sisip_depan(head, 50)
head = sisip_depan(head, 70) # head 

# cetak isi linked-list awal
print("Isi Linked-List Sebelum Penghapusan")
cetak_linked_list(head)

# Penghapusan ditengah linked-list
head = hapus_tengah(head, 2)

# cetak isi setelah hapus tengah linked-list 
print("\nIsi Linked-List Setelah Penghapusan Tengah ")
cetak_linked_list(head)
```

Hasilnya : 
```
Isi Linked-List Sebelum Penghapusan
Head → 70 → 50 → 10 → 20 → 30 → NULL

Node dengan data '10' dihapus dari posisi 2.

Isi Linked-List Setelah Penghapusan Tengah 
Head → 70 → 50 → 20 → 30 → NULL
```

Penjelasannya : 

Perhatikan potongan kode dari fungsi `hapus_tengah()` berikut ini: 
```python
# menghapus node pada posisi manapun (tengah)
def hapus_tengah(head, position):
    # cek apakah head node == None
    if head is None:
        print('\nLinked-List Kosong, tidak ada yang bisa dihapus!')
        return None
    
    # cek apakah posisi < 0
    if position < 0:
        print('\nPosisi Tidak Valid')
        return head
    
    # Cek apakah posisi = 0 
    if position == 0:
        print(f"Node dengan data '{head['data']}' dihapus dari posisi 0.")
        hapus_head(head)
        return head['next']
    
    current = head
    index = 0
    
    # cari node sebelum posisi target
    while current is not None and index < position -1:
        current = current['next']
        index += 1
        
    # Jika posisi yang diinputkan lebih besar dari panjang list
    if current is None or current['next'] is None:
        print("\nPosisi melebih panjang dari linked-list")
        return head
    
    print(f"\nNode dengan data '{current['next']['data']}' dihapus dari posisi {position}.")
    current['next'] = current['next']['next']
    return head
```
Fungsi ini memiliki tujuan untuk menghapus `node` pada posisi tertentu (misalnya node ke-1, ke-2, dst.) dalam *linked-list*. Posisi dimulai dari 0 (seperti indeks pada `list` Python).

Oke, mari kita mulai dari bagaian awal, fungsi `hapus_tengah()` menerima dua parameter yaitu `head` dan `position`. Dimana `head` adalah `node` pertama dalam *linked-list* sementara `position` sebagai posisi index dari `node` yang ingin dihapus. 
```python
def hapus_tengah(head, position):
```

Selanjutnya dalam fungsi ini ada beberapa pengecekan validitas yang pertama adalah mengecek apakah *linked-list* kosong 
```python
    # cek apakah head node == None
    if head is None:
        print('\nLinked-List Kosong, tidak ada yang bisa dihapus!')
        return None
```
jika `head` == `None`, maka list kosong, dan tidak ada node yang bisa dihapus. Tetapi jika tidak lanjutkan ke pengecekan validitas berikutnya 
```python
    # cek apakah posisi < 0
    if position < 0:
        print('\nPosisi Tidak Valid')
        return head
```
Pada kode diatas pengecekan validitas dilakukan ketika user memasukkan parameter posisi kurang nail 0 atau nilai negatif `if position < 0:`, maka program akan mengeluarkan pesan bahwa posisi yang dimasukkan tidak valid `print('\nPosisi Tidak Valid')`, dan tidak terjadi penghapusan sehingga kembali ke *linked-list* semula `return head`.

Selanjutnya dilakukan pengecekan validitas yang ke-tiga seperti pada potongan kode dibawah ini : 
```python
    # Cek apakah posisi = 0 
    if position == 0:
        print(f"Node dengan data '{head['data']}' dihapus dari posisi 0.")
        hapus_head(head)
        return head['next']
```
Pada potongan kode diatas kita akan melakukan pengecekan validitas ketika user memamsukkan posisi node adalah 0 `if position == 0`, maka program akan memberi pesan bahwa node dengan data tertentu dihapus dari posisi 0 `print(f"Node dengan data '{head['data']}' dihapus dari posisi 0.")` dan menjalankan fungsi `hapus_head(head)` yang terpisah dari fungsi ini. Kemudian mengembalikan `node` seteleh `head` menjadi `head` baru. 

Selanjutnya ketika semua pengecekan validitas sudah dilewati, maka kita masuk ke proses transversal untuk mengetahui posisi `node` di tengah *linked-list* yang ingin dihapus. Perhatikan potongan kode berikut ini : 
```python
    # inisialisasi pointer/transversal 
    current = head
    index = 0
    
    # cari node sebelum posisi target
    while current is not None and index < position -1:
        current = current['next']
        index += 1
```

Pada bagian awal kita inisialisasi pointer `current` pada `node` pertama (`head`), dan `current` akan digunakan untuk menelusuri *linked-list*, selanjutnya `index = 0` merupakan penanda awal posisi saat traversal, dan digunakan untuk membandingkan `posisition`. 

Berikutnya adalah melakukan perulangan untuk menemukan `node` sebelum posisi target. Kemudian `position - 1` dimaksudkan untuk menghentikan perulangan ketika menemukan satu `node` sebelum `node` yang ingin dihapus. contohnya jika kita ingin menghapus `node` ke dua maka perulangan akan dihentikan pada ketika mencapai `node` ke satu. 

Selama kondisi perulangan diatas masih terpenuhi maka jalankan perintah `current = current['next']`, artinya pindahkan `current` ke `node` berikutnya, dan perbarui nilai `index += 1`. 

Selanjutnya perhatikan potongan kode berikut ini : 
```python
    # Jika posisi yang diinputkan lebih besar dari panjang list
    if current is None or current['next'] is None:
        print("\nPosisi melebih panjang dari linked-list")
        return head
```

potongan kode diatas merupakan sebuah pengecekan validitas yang berfungsi untuk memastikan posisi node yang diinputkan tidak melebih panjang dari *linked-list* `if current is None or current['next'] is None`. Jika kondisi ini terpenuhi maka cetak pesan `print("\nPosisi melebih panjang dari linked-list")` dan kembalikan nilai *linked-list* yang awal. 

Selanjutnya perhatikan lagi potongan kode akhir berikut ini : 
```python
    print(f"\nNode dengan data '{current['next']['data']}' dihapus dari posisi {position}.")
    current['next'] = current['next']['next']
    return head
```

potongan kode diatas `print(f"\nNode dengan data '{current['next']['data']}' dihapus dari posisi {position}.")` diawali pemberitahuan kepada user bahwa `node` yang berada pada posisi yang dimaksud akan dihapus. Kode `current['next']['data']` → itulah `node` target yang ingin kita hapus. dan mengembalikan nilai `head` *linked-list* setelah `node` yang terpilih dihapus. 

### Double Linked-List
Double *Linked-List* merupakan struktur data yang lebih kompleks daripada single *linked-list*, tetapi menawarkan beberapa keuntungan. Keuntungan utama dari Double *Linked-List* adalah memungkinkan traversal `list` yang efisien di kedua arah. Hal ini karena setiap `node` dalam `list` berisi pointer ke `node` sebelumnya dan pointer ke `node` berikutnya. Hal ini memungkinkan penyisipan dan penghapusan `node` dari `list` dengan cepat dan mudah, serta `traversal` daftar yang efisien di kedua arah.

![double_ll](https://media.geeksforgeeks.org/wp-content/uploads/20240809123741/Insertion-at-the-End-in-Doubly-Linked-List-copy.webp)

Berbeda dengan single *linked-list*, doubly *linked-list* direpresentasi dalam bentuk yang berbeda, dimana setiap satu node memiliki 3 bagian utama yaitu : 
1. Data
2. Pointer untuk `node` berikutnya (`next`)
3. Pointer untuk `node` sebelumnya (`prev`)

Artinya pada double *linked-list* proses traversal dapat bergerak maju (`next`) dan dapat bergerak mundur (`prev`)

Berikut ilustrasinya : 
![double_ll](https://media.geeksforgeeks.org/wp-content/uploads/20240809124907/Node-Structure-of-Doubly-Linked-List.webp)

Dalam bahasa pemrograman python double *linked-list* direpresentasikan dengan *dictionary* sebagai berikut : 
```python
node = {
    'data': 10,
    'prev': None,
    'next': None
}
```

Bentuk dasar dari pembuatan `node` pada *double linked-list* dalam bahasa pemrograman python : 
```python
def create_node(data):
    return {'data': data, 
            'prev': None, 
            'next': None}
```
#### Penyisipan `node` pada Awal Double *Linked-List*. 

Untuk menyisipkan `node` baru di awal/depan *double linked-list*, kita buat `node` baru dengan penunjuk/pointer sebelumnya (`prev`) sebagai `NULL` dan penunjuk/pointer berikutnya (`next`) ke `head` *double linked-list* saat ini. Kemudian, kita periksa apakah *linked-list* tidak kosong, lalu kita perbarui penunjuk/pointer sebelumnya (`prev`) dari `head` saat ini ke `node` baru. Terakhir, kita kembalikan `node` baru sebagai `head` *linked-list*.

![sisip_dll](https://media.geeksforgeeks.org/wp-content/uploads/20240806180443/Insertion-at-the-Beginning-in-Doubly-Linked-List.webp)

Berikut ini adalah algoritma dari penyisipan 
1. Buat node baru
2. Tetapkan `next` pointer dari node baru dengan `head`, `new_node['next'] = head`
3. Tetapkan `prev` pointer dari node baru dengan `None`, `new_node['prev'] = None`, karena `node` baru adalah `node` pertama
4. Jika *linked-list* tidak kosong, atur head sebelumnya mengarah ke node baru
5. Kembalikan `node` baru sebagai `head` dan perbarui *linked-list*. 


Kita coba mengimplementasikan algoritma penyisipan node di awal *double linked-list* pada praktek 29 dibawah ini : 

Praktek 29 
```python
# Praktek 29 : Membuat Double Linked-List
# membuat node baru
def buat_node_double(data):
    return {'data': data, 'prev': head, 'next': None}

# Menambahkan node baru di awal double linked-list
def tambah_node_depan(head, data):
    new_node = buat_node_double(data)
    new_node['next'] = head
    new_node['prev'] = None
    
    if head is not None:
        head['prev'] = new_node
        
    return new_node

# Mencetak double linked-list dengan traversal maju
def cetak_dll(head):
    current = head
    print('HEAD', end=' <-> ')
    while current:
        print(current['data'], end=' <-> ')
        current = current['next']
    print('NULL')
    
# Penerapannya 
# Head awal dari linked-list
head = None

# Tambah Node
head = tambah_node_depan(head, 16) # 16
head = tambah_node_depan(head, 19) # 16 <-> 19

# Cetak double linked-list sebelum penyisipan di awal node
print("Double Linked-list Awal Sebelum Penyisipan : \n", end='')
cetak_dll(head)

# Tambah Node didepan double linked-list
head = tambah_node_depan(head, 22) # 16 <-> 19 <-> 22
head = tambah_node_depan(head, 99) # 16 <-> 19 <-> 22 <-> 99

# Cetak double linked-list setelah penyisipan di awal node
print("\nDouble Linked-list Awal Setelah Penyisipan: \n", end='')
cetak_dll(head)
```
Hasilnya : 
```
Double Linked-list Awal Sebelum Penyisipan : 
HEAD <-> 19 <-> 16 <-> NULL

Double Linked-list Awal Setelah Penyisipan: 
HEAD <-> 99 <-> 22 <-> 19 <-> 16 <-> NULL
```

Penjelasannya sebagai berikut : 

Kita mulai dengan memperhatikan potongan kode berikut ini : 
```python
# membuat node baru
def buat_node_double(data):
    return {'data': data, 'prev': None, 'next': None}
```

Kode diatas adalah sebuah fungsi dengan nama `buat_node_double(data)`, yang menerima satu parameter yaitu `data`. Dimana `node` baru ini nantinya akan memiliki komponen seperti ini 
```python 
node = {
    'data': data, # bergantung pada value yang diinputkan
    'prev': None,
    'next': None
}
```
Selanjutnya perhatikan potongan kode berikut ini : 
```python 
# Menambahkan node baru di awal double linked-list
def tambah_node_depan(head, data):
    new_node = buat_node_double(data)
    new_node['next'] = head
    new_node['prev'] = None
    
    if head is not None:
        head['prev'] = new_node
        
    return new_node
```
Pada potongan kode diatas terdapat 5 langkah, yang terdiri dari : 
1. Langkah 1 : membuat `node` baru dengan memanggil fungsi `buat_node_double(data)`
2. Langkah 2 : setelah `node` baru terbuat, ubah nilai dari bagaian `next` dari `node` untuk menyambungkannya dengan `head` sebelumnya. 
3. Langkah 3 : prev dari `node` baru diberi nilai None
4. Langkah 4 : jika list tidak kosong, `head['prev']` node sebelumnya arahkan ke `node` baru
5. Langkah 5 : `node` baru menjadi `head` baru


#### Penyisipan `node` pada Akhir Double *Linked-List*. 
Penyisipan di akhir melibatkan penelusuran seluruh *linked-list* hingga mencapai `node` terakhir. Kemudian, kita tetapkan referensi berikutnya (`next`) dari `node` terakhir untuk menunjuk ke `node` baru dan referensi sebelumnya (`prev`) dari `node` baru untuk menunjuk ke `node` terakhir. Dengan demikian, `node` baru menjadi elemen terakhir dalam *linked-list*.

![akhir_dll](https://media.geeksforgeeks.org/wp-content/uploads/20240807153259/Insertion-at-the-End-in-Doubly-Linked-List.webp)

Berikut ini adalah algoritmanya : 
1. Buat `node` baru (`new_node`) dengan data yang baru
2. cek apakah `head` kosong :
   * Jika kosong -> `node` baru langsung jadi `head`
3. Jika tidak kosong :
   * Traversal (jelajahi) dari `head` ke `tail` (`node` akhir)
   * Atur : 
     * `tail['next'] = new_node`
     * `new_node['prev'] = tail`
4. Kembalikan `head` (karena `head` tidak berubah)

Berikut adalah implementasi algoritma penyisipan `node` baru di akhir *double linked-list* :

Praktek 30 
```python
# Praktek 30 : Membuat Double Linked-List di Akhir
# membuat node baru
def buat_node_double(data):
    return {'data': data, 'prev': head, 'next': None}

# Menambahkan node baru di akhir double linked-list
def tambah_node_akhir(head, data):
    new_node = buat_node_double(data)

    # Jika list kosong
    if head is None:
        return new_node

    # Jika list tidak kosong, cari node terakhir
    current = head
    while current['next'] is not None:
        current = current['next']

    # Sambungkan node terakhir ke node baru
    current['next'] = new_node
    new_node['prev'] = current

    return head


# Mencetak double linked-list dengan traversal maju
def cetak_dll(head):
    current = head
    print('HEAD', end=' <-> ')
    while current:
        print(current['data'], end=' <-> ')
        current = current['next']
    print('NULL')
    
# Penerapannya 
# Head awal dari linked-list
head = None

# Tambah Node
head = tambah_node_depan(head, 16) # 16
head = tambah_node_depan(head, 19) # 19 <-> 16

# Cetak double linked-list sebelum penyisipan di akhir node
print("Double Linked-list Sebelum Penyisipan diakhir: \n", end='')
cetak_dll(head)

# Tambah Node diakhir double linked-list
head = tambah_node_akhir(head, 22) # 19 <-> 16 <-> 22 
head = tambah_node_akhir(head, 99) # 19 <-> 16 <-> 22  <-> 19 

# Cetak double linked-list setelah penyisipan di akhir node
print("\nDouble Linked-list Setelah Penyisipan diakhir: \n", end='')
cetak_dll(head)
```
Hasilnya : 
```
Double Linked-list Sebelum Penyisipan diakhir: 
HEAD <-> 19 <-> 16 <-> NULL

Double Linked-list Setelah Penyisipan diakhir: 
HEAD <-> 19 <-> 16 <-> 22 <-> 99 <-> NULL
```
Penjelasannya : 

Perhatikan fungsi `tambah_node_akhir(head, data)` dibawah ini : 
```python 
# Menambahkan node baru di akhir double linked-list
def tambah_node_akhir(head, data):
    new_node = buat_node_double(data)

    # Jika list kosong
    if head is None:
        return new_node

    # Jika list tidak kosong, cari node terakhir
    current = head
    while current['next'] is not None:
        current = current['next']

    # Sambungkan node terakhir ke node baru
    current['next'] = new_node
    new_node['prev'] = current

    return head
```
fungsi ini :
```python
def tambah_node_akhir(head, data):
```
bertujuan untuk membuat `node` baru dengan nilai `data` pada akhir *double linked-list*. Terdapat dua parameter yaitu : 
1. `head` yang merupakan `node` pertama (awal) dari *linked-list*
2. `data` yang merupakan nilai (isi) yang akan dimasukkan dalam `node` baru

Selanjutnya didalam fungsi ini terdapat sebuah perintah berikut ini : 
```python
    new_node = buat_node_double(data)
```
baris kode ini digunakan untuk membuat `node` baru dengan memanggil fungsi diluar yaitu `buat_node_double(data)`. Variabel `new_node` menjadi *dictionary* yang mewakili `node` baru, misalnya : 
```pyhton
{'data': 50, 'prev': None, 'next': None}
```
`node` baru dengan nilai `data = 50`, `prev = None`, dan `next = None`. Nilai `prev` dan `next` masih bernilai `None` karena belum terhubung dengan `node` lainnya. 

Selanjutnya potongan kode berikut ini : 
```python 
# Jika list kosong
    if head is None:
        return new_node
```
Potongan kode ini berfungsi untuk pengecekan validitas, apakah `list` dalam kondisi kosong atau tidak, jiak iya maka `new_node` yang baru dibuat, langsung menjadi `head` dari *double linked-list*, dan kemudian `node` baru dikembalikan `return`. 

Berikutnya bagaimana jika `list` tidak kosong, perhatikan kode berikut : 
```python 
    # Jika list tidak kosong, cari node terakhir
    current = head
    while current['next'] is not None:
        current = current['next']
```
dengan potongan kode diatas kita akan menjelajahi (traversal) dari `node` pertama sama akhir. Sebelum penjelajahan dimulai pertama kita buat variabel bantuan yaitu `current` yang akan menampung pointer dari setiap `node` dalam hal ini karena penjelajahan dilakukan maju jadi yang dibutuhkan hanya bagian pointer `next` saja. 

Selanjutnya `while current['next'] is not None:` atau selama isi dari `next` pointer tidak `None`, maka perintah `current = current['next']` dijalankan, artinya pindah ke `node` berikutnya. Perulangan ini akan dilakuakan sampai dengan `current['next'] == None` atau sudah tidak ada `node` lagi (`node` terakhir). 

Selanjutnya ketika kita sudah sampai di `node` akhir, maka perhatikan potongan kode berikut ini :
```python
    # Sambungkan node terakhir ke node baru
    current['next'] = new_node
    new_node['prev'] = current
```

kita akan menyambungkan pointer `next` dari `node` terakhir yang awalnya `None` menjadi `new_node`, `current['next'] = new_node`, dan pointer `prev` dari `new_node` menjadi `current`, `new_node['prev'] = current`. 

Terakhir kita kembalikan nilai `head` dari *linked-list*.


#### Penyisipan `node` pada Tengah atau Posisi Spesifik Double *Linked-List*. 
Idenya adalah untuk menelusuri (traversal) *linked list* guna menemukan `node` pada posisi - 1, katakanlah `node` saat ini. Jika posisinya valid, buat `node` baru dengan data yang diberikan dan perbarui pointer-nya: Tetapkan pointer `next` dari `node` baru ke `next` dari `node` saat ini dan pointer `prev` dari `node` baru ke `node` saat ini. Demikian pula, perbarui pointer `next` dari `node` saat ini ke `node` baru dan pointer `prev` dari node `baru` di `next` ke `node` baru.

![any_dll](https://media.geeksforgeeks.org/wp-content/uploads/20240807121739/Insertion-at-a-Specific-Position-in-Doubly-Linked-List.webp)

Algoritmanya adalah sebagai berikut ini : 
1. Buat `node` baru dengan data baru
2. Lakukan pengecekan validitas, jika posisi node = 1, maka gunakan fungsi sisip depan
3. Jika posisi < 0, maka munculkan pesan error posisi tidak valid
4. jika posisi bukan 0, atau kurang dari 0, maka lakukan traversal dari head sampai dengan posisi yang diinginkan
5. sisipkan node baru diantara dua node
6. update pointer next dan prev dari node baru agar terhubung
7. kembalikan nilai head

Berikut ini implementasi dari algoritma diatas, yaitu : 

Praktek 31
```python 
# membuat node baru
def buat_node_double(data):
    return {'data': data, 'prev': head, 'next': None}

# Menambahkan node baru di awal double linked-list
def tambah_node_depan(head, data):
    new_node = buat_node_double(data)
    new_node['next'] = head
    new_node['prev'] = None
    
    if head is not None:
        head['prev'] = new_node
        
    return new_node

# sisip node diposisi mana saja
def sisip_double_dimana_aja(head, data, position):
    # membuat node baru
    new_node = buat_node_double(data)
    
    # cek jika posisi = 0 gunakan fungsi tambah_node_depan()
    if position == 0:
        return tambah_node_depan(head, data)
    
    # cek jika posisi < 0, input tidak valid
    if position < 0:
        print('\nPosisi Tidak Valid')
        return head
    
    # deklarasi node pertama
    current = head
    index = 1
    
    # traversal menuju posisi yang diinginkan dan bukan posisi 0
    while current is not None and index < position - 1:
        current = current['next']
        index += 1
        
    # validasi posisi
    if current is None:
        print("Posisi melebihi panjang linked list!")
        return head
    
    # sisipkan node diantara current dan current.next
    next_node = current['next']
    current['next'] = new_node
    new_node['prev'] = current
    new_node['next'] = next_node
    if next_node is not None:
        next_node['prev'] = new_node
        
        
    return head

# Mencetak double linked-list dengan traversal maju
def cetak_dll(head):
    current = head
    print('HEAD', end=' <-> ')
    while current:
        print(current['data'], end=' <-> ')
        current = current['next']
    print('NULL')
    
# Penerapannya 
# Head awal dari linked-list
head = None

# Tambah Node
head = tambah_node_depan(head, 16) # 16
head = tambah_node_depan(head, 19) # 16 <-> 19

# Cetak double linked-list sebelum penyisipan di awal node
print("Double Linked-list Awal Sebelum Penyisipan Tengah: \n", end='')
cetak_dll(head)

# Tambah Node pada posisi mana saja, di double linked-list
head = sisip_double_dimana_aja(head, 22, 1) # 19 <-> 22 <-> 16
head = sisip_double_dimana_aja(head, 10, 2) # 19 <-> 10 <-> 22 <-> 16
head = sisip_double_dimana_aja(head, 30, 3) # 9 <-> 10 <-> 30 <-> 22 <-> 16

# Cetak double linked-list setelah penyisipan di awal node
print("\nDouble Linked-list Awal Setelah Penyisipan Tengah: \n", end='')
cetak_dll(head)
```

Hasilnya : 
```
Double Linked-list Awal Sebelum Penyisipan Tengah: 
HEAD <-> 19 <-> 16 <-> NULL

Double Linked-list Awal Setelah Penyisipan Tengah: 
HEAD <-> 19 <-> 10 <-> 30 <-> 22 <-> 16 <-> NULL
```
Penjelasannya adalah : 

Perhatikan fungsi `sisip_double_dimana_aja(head, data, position)` dibawah ini : 
```python
# sisip node diposisi mana saja
def sisip_double_dimana_aja(head, data, position):
    # membuat node baru
    new_node = buat_node_double(data)
    
    # cek jika posisi = 0 gunakan fungsi tambah_node_depan()
    if position == 0:
        return tambah_node_depan(head, data)
    
    # cek jika posisi < 0, input tidak valid
    if position < 0:
        print('\nPosisi Tidak Valid')
        return head
    
    # deklarasi node pertama
    current = head
    index = 1
    
    # traversal menuju posisi yang diinginkan dan bukan posisi 0
    while current is not None and index < position - 1:
        current = current['next']
        index += 1
        
    # validasi posisi
    if current is None:
        print("Posisi melebihi panjang linked list!")
        return head
    
    # sisipkan node diantara current dan current.next
    next_node = current['next']
    current['next'] = new_node
    new_node['prev'] = current
    new_node['next'] = next_node
    if next_node is not None:
        next_node['prev'] = new_node
                
    return head
```

Fungsi ini :
```python
def sisip_double_dimana_aja(head, data, position):
```
bertujuan untuk menambahkan atau menyisipkan sebuah `node` ditengah *double linked-list*. Fungsi ini menerima tiga parameter yaitu : 
1. `head`, merupakan `node` pertama dari *linked-list*
2. `data`, merupakan nilai pada `node` yang akan disisipkan
3. `position`, merupakan posisi (indeks, mulai dari 0) dimana lokasi `node` baru akan disispkan ke ``*linked-list*

Selanjutnya dalam fungsi ini terdapat sebuah perintah sebagai berikut ini :
``` python
    # membuat node baru
    new_node = buat_node_double(data)
```

perintah ini digunakan untuk membuat `node` baru dengan memanggil fungsi `buat_node_double(data)` diluar fungsi ini, dan akan mengembalikan nilai berupa *dictionary* seperti dibawah ini : 
```python 
{'data': data, 'prev': None, 'next': None}
```
`node` baru dengan nilai `data = 50`, `prev = None`, dan `next = None`. Nilai `prev` dan `next` masih bernilai `None` karena belum terhubung dengan `node` lainnya.

Selanjutnya setelah `node` baru tercipta maka selanjutnya kita akan melakukan validasi posisi dimana `node` baru itu ingin diletakkan. Perhatikan potongan kode berikut ini : 
```python
# cek jika posisi = 0 gunakan fungsi tambah_node_depan()
    if position == 0:
        return tambah_node_depan(head, data)
```
Potongan kode ini akan melakukan pengecekan validitas posisi `node`, dimana jika posisi yang diinputkan adalah sama dengan 0 `if position == 0`, artinya `node` baru ingin diletakkan pada awal *linked-list*. Oleh karena itu kita akan memanggil fungsi `tambah_node_depan()` untuk melakukannya. 

Jika tidak (`position != 0`), maka perhatikan potongan kode berikutnya
```python
    # cek jika posisi < 0, input tidak valid
    if position < 0:
        print('\nPosisi Tidak Valid')
        return head
```
Potongan kode diatas adalah pengecekan validatas inputan dari user, yang mana mengecek apakah posisi node kurang dari 0 (`if position < 0`>), jika ya, maka tampilkan pesan `print('\nPosisi Tidak Valid')` dan kembalikan nilai `head` semula. Potongan kode ini bertujuan untuk mengantisipasi user memasukkan posisi kurang dari 0. 

Selanjutnya bagaimana jika `node` baru ternyata melewati kedua pengecekan tersebut? Ini berarti `node` baru ingin disisipkan di posisi tengah *linked-list*. Jika demikian, maka jalankan potongan kode berikut ini : 

```python
    # deklarasi node pertama
    current = head
    index = 1
    
    # traversal menuju posisi yang diinginkan dan bukan posisi 0
    while current is not None and index < position - 1:
        current = current['next']
        index += 1
```
pertama adalah kita deklarasikan lebih dulu variabel `current` sebagai variabel sementara yang kita gunakan untuk memulai proses traversal, dimana variabel ini diberi nilai awal `node` pertama (`current = head`). Selain itu kita buat juga variabel penghitung posisi yaitu `index` yang diberi nilai awal adalah 1, yang menunjukkan proses traversal dimulai dari node berindex 1. 

Berikutnya `while current is not None and index < position - 1`, selama `current` tidak sama dengan `None` dan `index` kurang dari `position -1` maka perintah `current = current['next']` dijalankan artinya pindah ke `node` berikutnya. Selain itu update juga nilai dari `index` dengan menambahkan 1, `index +=1` agar kita tahu ada diposisi ke berapa. Perulangan ini akan berhenti sampai `node` sebelum index `node` yang menjadi tujuan kita. Contoh `node` baru akan disisipkan pada index ke 3 maka, traversal akan berhenti tepat satu `node` sebelumnya, yaitu pada index ke 2. 

Selanjutnya terdapat pengecekan validitas lagi, perhatikan potongan kode ini : 
```python
    # validasi posisi
    if current is None:
        print("Posisi melebihi panjang linked list!")
        return head
```

potongan kode diatas untuk mengecek validitas posisi yang diinputkan oleh user tidak melebih panjang dari *linked-list*, maka tampilkan pesan `print("Posisi melebihi panjang linked list!")` dan kembalikan nilai `head` semula

Selanjutnya jika kita sudah sampai pada tujuan, kita akan menyisipkan `node` baru melalui potongan kode berikut ini : 
```python 
    # sisipkan node diantara current dan current.next
    next_node = current['next']
    current['next'] = new_node
    new_node['prev'] = current
    new_node['next'] = next_node
    if next_node is not None:
        next_node['prev'] = new_node
```

Lalu bagaimana cara menyisipkannya? Sederhananya kita akan menyisipkan sebuah `node` diantar dua `node` yaitu : 
1. Setelah `current`, dan
2. Sebelum `current['next']` yang kita sebut `next_node`

kode `next_node = current['next']` berfungsi memindahkan `node` pada posisi sebelum `node` yang ingin sisipkan ke dalam variabel `next_node`. Artinya ini adalah `node` setelah `node` yang akan disispkan. 

Sebagai analogi, Misalkan kita ingin menyisipkan seorang siswa baru (`new_node`) di barisan antara siswa bernama **Andi** (`current`) dan **Budi** (`next_node`). kita simpan dulu informasi tentang siapa Budi `next_node = current['next']`, agar tidak "terlupakan" setelah kita ubah koneksi antara Andi dan siswa baru nanti

Selanjutnya kode `current['next'] = new_node` untuk mengubah koneksi `current`, sehingga `current` sekarang `node` berikutnya dalah `new_node`. Analoginya kita meminta **siswa baru** untuk baris di belakang **Andi**. Artinya setelah Andi ada siswa baru dibelakangya. 

Lalu `node` baru harus mengetahui `node` apa yang ada didepannya oleh karena itu kode `new_node['prev'] = current`. Analoginya **siswa baru** mengetahui **Andi** berada didepannya yang artinya Andi adalah `node` sebelum **siswa baru**. 

Nah selanjutnya **siswa baru** juga harus tahu siapa setelah dia, karenanya kode `new_node['next'] = next_node` digunakan agar `node` baru terkoneksi dengan `node` setelahnya ,yaitu `next_node`. Analoginya ketika **siswa baru** ditanya siapa setelahnya dia tahu **Budi** setelahnya. 

Selanjutnya kita perlu memvalidasi apakah `node` setelah `node` baru benar-benar ada `if next_node is not None`, jika `next_node == None` berarti `node_baru` ditempatkan di akhir list. Namun jika `next_node is not None` maka kita perlu `next_node` perlu mengubah pointernya agar `node` sebelumnya adalah `new_node`. Analoginya kita memberi tahu **Budi** bahwa siswa sebelum dia adalah **siswa baru** dan bukan **Andi** lagi. 

