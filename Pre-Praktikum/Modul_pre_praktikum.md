# Modul Pre-Praktikum
Modul ini dirancang sebagai penyegaran untuk mahasiswa terkait materi tentang pemrograman dasar khususnya materi **Perulangan** dan **Function**. Kedua materi ini dipilih karena akan sering digunakan pada modul-modul praktikum Struktur Data

## Perulangan (*Loop*)
Pada pemrograman perulangan (*Loop*) digunakan untuk memberikan perintah kepada komputer untuk menjalankan statement secara berulang-ulang. Terdapat dua jenis perulangan khususnya dalam bahasa pemrograman Python, yaitu `for` dan `while`. 

### Perulangan `for` 
Perulangan `for` sering kali disebut sebagai *counted loop* (perulangan yang terhitung), artinya perulangan menggunakan `for` dapat digunakan ketika kita mengetahui berapa kali statement (kode) harus diulang. 

bentuk umum / *syntaxnya* : 

```Python
for indeks in range(banyak_perulangan):
    # jalankan aksi ini
    # jalankan juga aksi ini
# aksi/kode/statemen ini bukan bagian dari for
```

contoh program (bisa dibuka [di sini](https://github.com/adamMaulachela/Kuliah_Struktur_data/blob/main/Pre-Praktikum/for_loop.ipynb)):

```Python
ulang = 10

for i in range(ulang):
    print(f'Perulangan ke - {i})
print("Akhir Perulangan \n")
```

Berikut penjelasannya : 
```python
ulang = 10
```
pertama terdapat variabel `ulang` dengan nilai `10`, artinya kita menentukan banyaknya perulangan sebanyak 10 kali. 

```Python
for i in range(ulang):
```
selanjutnya kita membuat statemen `for` berdasarkan variabel `ulang` dimana fungsi `range()` akan membuat `list` dengan batasan dari 0-10. Sementara `i` pada `for` berfungsi sebagai penampung indeks dari list yang sudah dibuat. Kemudian didalam `for` terdapat sebuah aksi yang dijalankan berulang yaitu 
```Python
    print(f'Perulangan ke - {i})
```

aksi/kode diatas akan mencetak string sebanyak 10 kali dengan menggunakan fungsi `str()` yang mengubah tipe data integer menjadi string. Sehingga hasilnya adalah : 
```Python
Perulangan Ke - 0
Perulangan Ke - 1
Perulangan Ke - 2
Perulangan Ke - 3
Perulangan Ke - 4
Perulangan Ke - 5
Perulangan Ke - 6
Perulangan Ke - 7
Perulangan Ke - 8
Perulangan Ke - 9
Akhir Perulangan
```

contoh berikutnya menggunakan range dangan batas bawah dan batas atas :

```python
for i in range(1,11):
    print(f'Perulangan ke - {i}')
print("Akhir Perulangan\n")
```

penjelasannya : 
perulangan dilakukan dalam `range(1,11)`, artinya batas bawah adalah 1, dan batas atas 11. Sehingga perulangan dilakukan sebanyak 10 kali (batas atas-1). 

hasilnya : 
```
Perulangan ke - 1
Perulangan ke - 2
Perulangan ke - 3
Perulangan ke - 4
Perulangan ke - 5
Perulangan ke - 6
Perulangan ke - 7
Perulangan ke - 8
Perulangan ke - 9
Perulangan ke - 10
Akhir Perulangan
```

contoh berikutnya menggunakan range dengan batas bawah, batas atas dan interval :

```python
for i in range(1,11,2):
   print(f'Perulangan ke - {i}')
print("Akhir Perulangan\n")
```

penjelasannya :
kali ini `range` memiliki tambahan value yaitu interval, sehingga `range(1,11,2)` berarti batas bawah 1, batas atas 11, dan interval 2. Sehingga akan terbentuk list `[1, 3, 5, 7, 9]`. Hasilnya adalah :
```
Perulangan ke - 1
Perulangan ke - 3
Perulangan ke - 5
Perulangan ke - 7
Perulangan ke - 9
Akhir Perulangan
```

contoh lainnya, kita akan melakukan perulangan terhadap sebuah variabel bertipe data `list`:
```Python
list = [0,1, 7, 12, 15, 18, 45]

for i in list:
    print(f"isi list -> {i}")
print("Akhir Perulangan\n")
```

hasilnya : 
```
isi list -> 0
isi list -> 1
isi list -> 7
isi list -> 12
isi list -> 15
isi list -> 18
isi list -> 45
Akhir Perulangan
```

### Perulangan `while`
Berbeda dengan perulangan `for` yang sudah diketahui berapa kali sebuah aksi dijalankan, perulangan `while` adalah perulangan yang memiliki syarat dan tidak ditentukan berapa kali perulangan akan dilakukan. Sehingga perulangan `while` sering disebut sebagai *uncounted-loop*. 

bentuk/*syntax* umumnya :
```python
while(True):
    # lakukan aksi ini
    # lakukan aksi ini juga
# aksi ini bukan bagian dari while
```

Contoh dapat dibuka [disini](https://github.com/adamMaulachela/Kuliah_Struktur_data/blob/main/Pre-Praktikum/while_loop.ipynb):
```python
ulang = 0

while ulang < 5:
    ulang += 1
    print(f'perulangan ke - {ulang}')
print("Akhir perulangan \n")
```
Penjelasannya : 

Terdapat variabel `ulang` yang bernilai `0`. 
```python
ulang = 0
```

kemudian dilakukan perulangan `while ulang < 5:` atau selama nilai `ulang` kurang dari 5. 
```python
while ulang < 5 :
```
lakukan aksi berikut: 
```python
    print(f'perulangan ke - {ulang}')
```
sehingga hasilnya : 
```
perulangan ke - 1
perulangan ke - 2
perulangan ke - 3
perulangan ke - 4
perulangan ke - 5
Akhir perulangan
```

Contoh lainnya : 
```Python
jawab = 'ya'
hitung = 0

while(jawab == 'ya'):
    hitung += 1
    jawab = input("Ulang lagi tidak? ")

print(f"Total perulagan: {hitung}")
```

hasilnya : 
```
Ulangi lagi atau tidak? ya
Ulangi lagi atau tidak? ya
Ulangi lagi atau tidak? ya
Ulangi lagi atau tidak? tidak
Total perulagan: 4
```

### Perulangan dengan `break`, dan `continue`
#### Perulangan dengan `break`
Kata kunci `break` digunakan untuk **menghentikan sebuah perulangan secara paksa**, meskipun kondisi perulangan masih terpenuhi atau batas akhir perulangan masih belum tercapai. 

contoh `for` dengan `break`:
```python
for i in range(1,10):
    if i == 5:
        break # keluar dari loop saat i = 5
    print(f'i saat ini - > {i}')
print("Akhir Perulangan\n")
```

penjelasannya : 

Terdapat sebuah `range(1,11)`, artinya perulangan akan dilakukan sebanyak 9 kali. Akan tetapi setiap kali perulangan sampai yang ke 5 `if i == 5` kali maka langsung keluar dari program atau `break`. Hasilnya : 

```python
i saat ini - > 1
i saat ini - > 2
i saat ini - > 3
i saat ini - > 4
Akhir Perulangan
```
contoh `while` dengan `break` : 
```python
i = 1
while i < 10:
    if i == 5:
        break  # keluar dari loop saat i = 5
    print(f'i saat ini - > {i}')
    i += 1
```

Penjelasannya : 

Terdapat sebuah variabel `i` yang nilai awalnya sama dengan `0`. Dilakukan perulangan selama `i` kurang dari `10` atau `while i < 10`. Jika `i` mencapai `5` maka `break` atau keluar dari program. Hasilnya : 

```
i saat ini - > 1
i saat ini - > 2
i saat ini - > 3
i saat ini - > 4
Akhir Perulangan
```
#### Perulangan dengan `continue`
Kata kunci `continue` digunakan untuk **melewati sebuah iterasi** dan **melanjutkan ke iterasi berikutnya**, tanpa menjalankan kode dibawahnya dalam loop. 

contoh `for` dengan `continue`:
```python
for i in range(1, 6):
    if i == 3:
        continue  # lewati i = 3
    print(f'i saat ini -> {i}')
print("Akhir Perulangan \n")
```

Penjelasannya : 
Terdapat sebuah `range(1,6)` berati akan dilakukan perulangan sebanyak 5 kali. Namun setiap kali nilai `i` sama dengan 3, maka iterasi ke 3 dilewati dan dilanjutkan ke iterasi berikutnya, sampai dengan kondisi batas akhir perulangan. 
Hasilnya : 

```
i saat ini -> 1
i saat ini -> 2
i saat ini -> 4
i saat ini -> 5
Akhir Perulangan
```

contoh `while` dengan `continue` :
```python
i = 0
while i < 5:
    i += 1
    if i == 3:
        continue  # lewati i = 3
    print(f'i saat ini -> {i}')
print("Akhir Perulangan\n")
```

Penjelasannya : 
Terdapat variabel `i` dengan nilai awal `0`. Kemudian dilakukan perulangan selama nilai `i` dibawah 5. Namun setiap kali nilai `i == 3`, maka iterasi ini dilewati dan dilanjutkan ke iterasi berikutnya. Hasilnya 
```
i saat ini -> 1
i saat ini -> 2
i saat ini -> 4
i saat ini -> 5
Akhir Perulangan
```

### Tugas Materi Perulangan 
#### Soal 1 : Login Sederhana
Buatlah program yang meminta user memasukkan username dan password. Program hanya memberikan 3 kali kesempatan. Jika login berhasil (username = admin, password = 12345), tampilkan pesan "Login berhasil" dan keluar dari perulangan. Jika salah, tampilkan "Login gagal, coba lagi". Setelah 3 kali gagal, tampilkan "Akun terkunci".

outputnya : 

```
Username: user
Password: pass
Login gagal, coba lagi

Username: admin
Password: salah
Login gagal, coba lagi

Username: admin
Password: 12345
Login berhasil
```

#### Soal 2 : Input Nilai Valid 
Buatlah program yang meminta user memasukkan 5 buah nilai (0–100). Jika nilai tidak valid (misal < 0 atau > 100), tampilkan pesan "Nilai tidak valid, ulangi" dan jangan dihitung sebagai input ke-berapa. 

Outputnya : 
```
Masukkan nilai ke-1: 80
Masukkan nilai ke-2: 110
Nilai tidak valid, ulangi.

Masukkan nilai ke-2: 90
Masukkan nilai ke-3: -5
Nilai tidak valid, ulangi.

Masukkan nilai ke-3: 75
Masukkan nilai ke-4: 100
Masukkan nilai ke-5: 85
Nilai yang dimasukkan: [80, 90, 75, 100, 85]
```

#### Soal 3 : Form Input Nama
Buat program yang meminta user memasukkan nama sebanyak 5 kali. Jika user memasukkan nama kosong (""), tampilkan pesan "Nama tidak boleh kosong" dan minta ulang input tersebut. Jika user memasukkan kata 'keluar', program langsung berhenti

Outputnya : 
```
Masukkan nama ke-1: Budi
Masukkan nama ke-2: 
Nama tidak boleh kosong.

Masukkan nama ke-2: Siti
Masukkan nama ke-3: keluar
Input dihentikan oleh pengguna.

Daftar nama yang dimasukkan: ['Budi', 'Siti']
```

## Function Pada Python
Fungsi atau *function* pada bahasa pemrograman python merupakan blok kode yang dapat digunakan ulang. Kita dapat **memanggil function** kapan saja untuk menjalankan tugas tertentu tanpa menulis ulang kode. 

Bentuk umum / *Syntax* :
```python
def nama_fungsi():
    print "Hello ini Fungsi"
```
![Gambar Function](https://github.com/adamMaulachela/Kuliah_Struktur_data/blob/main/img/fungsi.png)
sumber : [petanikode.com](https://petanikode.com)

Seperti pada gambar, sebuah fungsi memiliki nama fungsi, dan juga body/isi fungsi. Setiap body/isi dari fungsi harus diberikan indentasi (tab), jika tidak maka program akan error.  
contohnya : 
```python
def sapa():
    print("Halo, selamat datang!")

sapa()  # Memanggil fungsi
sapa()
sapa()
```
jika kita panggil fungsi ini sebanyak 3 kali maka, outputnya :
```
Halo, selamat datang!
Halo, selamat datang!
Halo, selamat datang!
```


