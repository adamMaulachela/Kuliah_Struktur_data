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
### Function dengan Argument (Parameter)
Argument atau parameter merupakan data yang dikirim ke fungsi. Bentuk function ini kita gunakan ketika kita ingin memberikan input nilai ke dalam sebuah fungsi. 

![Gambar Parameter Function](https://github.com/adamMaulachela/Kuliah_Struktur_data/blob/main/img/parameter-fungsi.png)

sumber : [petanikode.com](https://petanikode.com)

contoh program (bisa buka [disini](https://github.com/adamMaulachela/Kuliah_Struktur_data/blob/e128af959d9d7020f406c00b5a9f15aeaff94a3a/Pre-Praktikum/function.ipynb)) :

```python
# function dengan 1 parameter
def sapa_nama(nama):
    print(f"Halo, {nama}!")

# Pemanggilan Function
sapa_nama("Adam")
```
Penjelasannya : 

pada contoh diatas kita membuat function dengan 1 parameter yaitu `nama`. dan memanggilnya dengan cara memanggil nama function `sapa_nama` dan memasukkan parameternya `Adam` atau lengkapnya `sapa_nama("Adam")`, sehingga outpunya : 
```
Halo, Adam!
```

Kemudian, apakah function hanya dapat menerima satu parameter saja, ataukan dapat menerima lebih dari satu parameter? 

Function dalam bahasa pemrograman python dapat menerima lebih dari satu parameter. Untuk memisahkan setiap parameter digunakan tanda `,` 

contoh program (bisa buka [disini](https://github.com/adamMaulachela/Kuliah_Struktur_data/blob/e128af959d9d7020f406c00b5a9f15aeaff94a3a/Pre-Praktikum/function.ipynb)) :

```python
# function dengan lebih dari 1 parameter
def luas_segitiga(alas, tinggi):
    luas = (alas * tinggi) / 2
    print("Luas segitiga: %f" % luas)

# Pemanggilan Function
luas_segitiga(4, 6)
```

Penjelasannya : 

Terdapat sebuah function dengan nama `luas_segitiga()` dengan dua parameter yaitu `alas` dan `tinggi`. Tentu saja function ini digunakan untuk menghitung luas segitiga dari inputan alas dan tinggi dari parameter. Hasilnya adalah : 
```
Luas segitiga: 12.000000
```

### Function Dengan Nilai Kembali (Return)
Nilai kembali atau `return`, digunakan untuk mengembalikan nilai dari function. Sementara jika sebuah function tidak mengembalikan nilai lebih sering disebut sebagai **Procedure**. 

![Gambar return](https://github.com/adamMaulachela/Kuliah_Struktur_data/blob/main/img/return.png)

sumber : [petanikode.com](https://petanikode.com)

Cara mengembalikan nilai pada sebuah function dengan menggunakan kata kunci `return` yang diikuti oleh nilai atau variabel yang ingin dikembalikan.

contoh program (bisa buka [disini](https://github.com/adamMaulachela/Kuliah_Struktur_data/blob/e128af959d9d7020f406c00b5a9f15aeaff94a3a/Pre-Praktikum/function.ipynb)) :

```python
def tambah(a, b):
    return a + b

# pemanggilan fungsi
hasil = tambah(3, 5)
print("Hasil:", hasil)
```

Penjelasaannya : 

percobaan diatas membuat function untuk menambahkan nilai dari dua buah variabel `a` dan `b`, kemudian mengembalikan nilainya dengan menggunakan `return a + b`. Hasilnya adalah : 
```
Hasil: 8
```
Contoh lainnya terlihat dibawah ini : 
```python 
def luas_persegi(sisi):
    luas = sisi * sisi
    return luas

# pemanggilan fungsi
print(f"Luas Persegi : {luas_persegi(6)}")
```
Penjelasannya : 

kita memiliki sebuah fungsi untuk menghitung luas lingkaran dengan parameter `sisi`. Kemudian mengembalikan nilai dari variabel `luas` yang merupakan hasil hitung dari `sisi * sisi`. Hasilnya ketika fungsi ini dipanggil adalah : 
```
Luas Persegi : 36
```

Selah satu keunggulan kita menggunakan function dengan return adalah kita dapat memanfaatkan sebuah function untuk pemrosesan pada function yang lain. 

Sebagai contoh kita akan menggunakan atau memanggil function `luas_persegi()` pada function lainnya yaitu `volume_persegi`. 

```python
# rumus sisi x sisi
def luas_persegi(sisi):
    luas = sisi * sisi
    return luas


# rumus: sisi x sisi x sisi
def volume_persegi(sisi):
    volume = luas_persegi(sisi) * sisi
    return volume

# pemanggilan fungsi
vol_persegi = volume_persegi(6)
print(f"Volume Persegi = {vol_persegi})
```

Penjelasannya : 

pada contoh diatas kita memanggil fungsi `luas_persegi()` didalam fungsi `volume_persegi` untuk mengghitung volumen persegi. Hasilnya : 
```
Volumen Persegi = 216
```

### Function Dengan Default Argument 
Pada bahasa pemrograman python kita dapat memberikan nilai default pada parameter. Jika function tersebut dipanggil tanpa memberikan argumen atau parameter, maka argumen atau parameter yang dipakai adalah nilai default yang telah ditentukan. 

Bentuk umumnya : 
```Python 
def function_name(param1, param2=default_value2, param3=default_value3)
```

Sebagai contoh : 
```python
def student(firstname, lastname ='Mark', standard ='Fifth'):
    print(firstname, lastname, 'studies in', standard, 'Standard')
```

Penjelasannya : 

pada function `student` kita memiliki 3 argumen yang dapat digunakan, yaitu `firstname`, `lastname`, dan `standard`. Dua diantaranya memiliki default argument yaitu `lastname` dan `standard`. 

Oleh karena itu kita juga memiliki, 3 cara pemanggilan yaitu : 
```python
# pemanggilan function, dengan 1 argumen
student("Wallberg")

# pemanggilan function, dengan 3 argumen
student('John', 'Gates', 'Seventh')  

# pemanggilan function dengan 2 argumen
student('John', 'Gates')               
student('John', 'Seventh')
```
Penjelasannya : 

Pada panggilan pertama, hanya ada satu argumen yang diperlukan dan argumen lainnya menggunakan nilai default. Pada panggilan kedua, nilai argumen lastname dan standard diganti dari nilai default ke nilai baru yang lewat. Kita dapat melihat urutan argumen penting dari panggilan fungsi ke-2, ke-3, dan ke-4.

outputnya : 

```
Wallberg Mark studies in Fifth Standard
John Gates studies in Seventh Standard
John Gates studies in Fifth Standard
John Seventh studies in Fifth Standard
```

### Type Hints Pada Function
Type hints digunakan untuk memberikan petunjuk tipe data yang digunakan untuk parameter dan return value. Type hint bersifat opsional dan tidak mandatory (wajib), namun sangat berguna untuk dokumentasi dan penanganan error (error handling). 

sebagai contoh : 
```python
def kali(a: int, b: int) -> int:
    return a * b

# Pemanggilan function
print("Hasil = " ,kali(3, 4))
print("Tipe Data : ", type(kali(3,4)))
```

Penjelasannya : 

Terdapat sebuah function `kali` yang menerima dua parameter `a,b` yang bertipe data `int`, dan hasil perkalian dari dua variabel ini juga akan bertipe data `int`. Outputnya adalah : 

```
Hasil =  12
Tipe Data :  <class 'int'>
```

### Function Dengan *args dan **kwargs
Dalam Python sebuah fungsi dapat menerima banyak argumen atau parameter (dalam bentuk tuple), dengan memanfaatkan `*args` dan menerima banyak argumen dalam bentuk kunci-nilai (key-value) dalam bentuk dictionary dengan memanfaatkan `**kwargs`. Keduanya memberikan fleksibilitas lebih besar saat merancang fungsi yang perlu menangani berbagai jumlah masukan.

**Python** `*args` **(Non-Keyword Arguments)**

Syntax `*args` ini digunakan untuk meneruskan sejumlah variabel argumen/parameter ke dalam sebuah fungsi. Output yang dihasilkan dalam bentuk tuple

Contohnya : 
```python
# *args untuk argumen bervariasi
def myFun(*argv):
    for arg in argv:
        print(arg)

myFun('Hello', 'Selamat Datang', 'Di', 'PTI UNDIKMA')
```
Penjelasannya : 

fungsi `myFun` adalah untuk menampilkan beberapa argumen yang kita gunakan pada saat memanggil fungsi `myFun`, dalam contoh tersebut kita memanggil empat buat argumen dan menampilkannya kelayar sesuai urutannya. Outputnya : 
```
Hello
Selamat Datang
Di
PTI UNDIKMA
```

Contoh lainnya : 
```python
def jumlahkan(*angka):
    total = sum(angka)
    print("Total:", total)

jumlahkan(1, 2, 3)
jumlahkan(5, 10, 15, 20)
```

outputnya : 

```
Total: 6
Total: 50
```

Contoh berikut ini memberikan fleksibilitas bagi sebuah fungsi untuk tidak hanya menggunakan `*args` akan tetapi menambahkannya dengan sebuah ekstra argumen :
```python
# *args dengan ekstra argumen
def fun(arg1, *argv):
    print("First argument :", arg1)
    for arg in argv:
        print("Argument *argv :", arg)

# pemanggilan fungsi
fun('Hello', 'Selamat Datang', 'di', 'PTI UNDIKMA')
```

Penjelasannya : 

Pada fungsi `fun` terdapat argumen `*args` yaitiu `*argv`, dan juga ekstra argumen yaitu `arg1`. Pada fungsi isi `arg1` dicetak, sementara argumen yang ada dalam `*argv` dicetak menggunakan looping `for` sampai dengan seluruhnya tercetak. Hasilnya : 
```
First argument : Hello
Argument *argv : Selamat Datang
Argument *argv : di
Argument *argv : PTI UNDIKMA
```

**Python** `*kwargs` **(Keyword Arguments)**

`**kwargs` digunakan agar function dapat menerima banyak argumen dalam bentuk kunci-nilai (key-value). Output yang dihasilkan dari function dengan `**kwargs` dalam bentuk dictionary. 

Contohnya :
```python
def info_mahasiswa(**data):
    for key, value in data.items():
        print(f"{key}: {value}")

# Pemanggilan function
info_mahasiswa(nama="Rina", jurusan="TI", angkatan=2022)
```

Penjelasannya : 

Pada function diatas akan menampilkan pasangan kunci dan nilai dari pemanggilan function `info_mahasiswa`. Outputnya :
```
nama: Rina
jurusan: TI
angkatan: 2022
```

Kita juga dapat mengkombinasikan penggunaan syntax `*args` dan `**kwargs` dalam satu function untuk menghasilkan luaran yang lebih kompleks, seperti contoh berikut ini :
```python
# kombinasi syntax *args dan **kwargs dalam satu function
def fun(*args, **kwargs):
    print("Positional arguments:", args)
    print("Keyword arguments:", kwargs)

# Pemanggilan function
fun(1, 2, 3, a=4, b=5)
```
outputnya : 
```
Positional arguments: (1, 2, 3)
Keyword arguments: {'a': 4, 'b': 5}
```

### Variabel Global dan Lokal Python
Selanjutnya kita perlu memahami apa yang dimaksud dengan variabel lokal dan global. Variabel global adalah variabel yang bisa diakses oleh semua fungsi. Sementara Variabel Lokal adalah variabel yang hanya bisa diakses pada fungsi itu sendiri. 

**Variabel Global**
Variabel global memiliki ciri sebagai berikut : 
1. Didefinisikan **di luar fungsi**
2. Bisa diakses oleh **fungsi manapun** dalam file tersebut

contohnya :
```python
nama = "Budi"  # variabel global

def sapa():
    print("Halo,", nama)

# memanggil function
sapa()
```
Outputnya : 

```python
Halo, Budi
```

**Variabel Lokal**
Variabel lokal memiliki ciri sebagai berikut : 
1. Didefinisikan **di dalam fungsi**
2. Hanya bisa digunakan **di dalam fungsi itu sendiri**
3. Tidak bisa diakses dari luar fungsi

Contohnya : 
```python
def halo():
    pesan = "Halo dari dalam fungsi!"  # variabel lokal
    print(pesan)

# memanggil function
halo()
print(pesan)  # ❌ Error! variabel 'pesan' tidak dikenali di luar fungsi
```
outputnya : 
```
Halo dari dalam fungsi!
NameError: name 'pesan' is not defined
```

**LGB (Local, Global, Build-In)**
Pada python, urutan pengaksesan variabel (*scope*) dikenal dengan sebuatan LGB (Local, Global, Build-In). Jadi Program python mulai mencari variabel lokal terlebih dahulu, kalau ada maka itu yang akan digunakan. 

Jika tidak ada, maka pencarian trus ke variabel global, dan build-in. Variabel build-in merupakan variabel yang sudah ada di dalam python. 

Contoh Program : 
```Python
# membuat variabel global
nama = "UNDIKMA"
versi = "1.0.0"

def help():
    # ini variabel lokal
    nama = "Programku"
    versi = "1.0.2"
    # mengakses variabel lokal
    print "Nama: %s" % nama
    print "Versi: %s" % versi


# mengakses variabel global
print "Nama: %s" % nama
print "Versi: %s" % versi

# memanggil fungsi help()
help()
```

Penjelasannya : 

Perhatikan variabel `nama` pada program diatas berada di dalam dan juga di luar function `help()`. Nah `nama` yang berada di dalam function `help()` dapat kita sebut sebagai variabel lokal. Sementara yang berada diluar function adalah variabel global. 

Jadi ketika kita memanggil function `help()`, maka nilai dalam variabel `nama` yang tampil adalah variabel lokal. 

Mengapa bukan variabel global yang tampil? ya karena ada urutan pencarian variabel LGB tadi. Nah jika sebuah variabel tidak ditemukan di dalam urutan LGB, maka akan terjadi error `NameError` atau variabel tidak temukan

### Contoh Program Dengan Fungsi
Kita akan membuat program untuk menampung data judul buku dalam bentuk list pada variabel global. 
```python
# variabel global untuk menyimpan data buku
buku = []
```
Selanjutnya program ini akan memiliki 4 buah fungsi untuk : 
1. Melihat isi list `buku` dengan nama fungsi `show_data()`
2. Menambahkan isi list `buku` dengan nama fungsi `insert_buku()`
3. Mengedit isi list `buku` dengan nama fungsi `edit_buku()`
4. Menghapus isi list `buku` dengan nama fungsi `delete_buku()`

**Fungsi `show_data()`**

```python
# Fungsi untuk menampilkan semua data buku
def show_data():
    if len(buku) <=0 :
        print("DATA BUKU BELUM ADA")
    else:
        for indeks in range(len(buku)):
            print("[%d] %s" % (indeks, buku[indeks]))
```

pada fungsi diatas kita akan mengecek isi dari list buku, jika isinya kosong `len(buku) <= 0` maka tampilkan `DATA BUKU BELUM ADA`

Namun jika data buku tersedia maka lakukan perulangan sebanyak jumlah buku dan tampilkan isi buku dengan pasangan indeks dan judul buku. 

**Fungsi `insert_data()`**
```python 
def insert_data():
    buku_baru = input("Judul Buku : ")
    buku.append(buku_baru)
```

Pada fungsi diatas user diminta untuk memasukkan judul buku ke dalam list `buku` dengan menggunakan fungsi `.append()`, yang berfungsi menambahkan item ke dalam bagian akhir list. 

**Fungsi `edit_data()`**
```python
def edit_data():
    show_data()
    indeks = int(input("Inputkan ID Buku : "))
    if(indeks > len(buku)):
        print("ID Buku Tidak Ditemukan")
    else:
        judul_baru = input("Judul Baru : ")
        buku[indeks] = judul_baru
```

Fungsi diats digunakan untuk mengedit item dari list `buku`. Namun agar memudahkan pengguna sebelum melakukan editing, seluruh data yang ada pada list `buku` akan ditampilkan. 

Baru setelah itu user diminta untuk memilih indeks dari buku yang dikehendaki untuk diubah. Untuk meminimalisir potensi user melakukan kesalahan pada saat memilih, mana fungsi ini akan melakukan pengecekan apakah indeks yang dimasukkan oleh user lebih besar dari pada panjang list `buku` (`indeks > len(buku)`). Jika `ya` maka muncul pesatn `ID Buku Tidak Ditemukan`. 

Namun jika `tidak`, maka user diminta untuk memasukkan judul baru dan menyimpannya sesuai dengan ID yang dipilih. 

**Fungsi `delete_data()`**
```python
def delete_data():
    show_data()
    indeks = int(input("Inputkan ID Buku : "))
    if(indeks > len(buku)):
        print("ID Buku Tidak Ditemukan")
    else:
        buku.remove(buku[indeks])
        print(f"Buku dengan ID {indeks} Terhapus")
```

Pada perinsipnya cara kerja pada function ini mirip dengan fungsi `edit_data()`. Yang membedakan hanyalah jika indeks buku yang dipilih ada dalam list `buku` maka lakukan `buku.remove(buku[indeks])`. Artinya buku dengan indeks terpilih dihapus dari list `buku`, setelah itu beri informasi indeks buku yang barusan terhapus dari list. 

Agar terlihat lebih baik kita perlu menambhkan 2 fungsi baru yaitu `show_menu()` untuk menampilkan pilihan aktivitas oleh pengguna, dan fungsi `exit()` yang digunakan untuk keluar dari program. 
```python
def show_menu():
    print("\n")
    print(5*"-","MENU", 5*"-")
    print("[1] Show Data")
    print("[2] Insert Data")
    print("[3] Edit Data")
    print("[4] Delete Data")
    print("[5] Exit")
    
    menu = int(input("PILIH MENU : "))
    print("\n")
    if menu == 1:
        show_data()
    elif menu == 2:
        insert_data()
    elif menu == 3:
        edit_data()
    elif menu == 4:
        delete_data()
    elif menu == 5:
        exit()
    else:
        print("Pilihan Anda Salah!")
```

Agar setiap kali user selesai melakukan aktivitas program tidak keluar, maka kita akan membuat main loop yaitu : 
```python
if __name__ == "__main__":
    while(True):
        show_menu()
```

## Tugas Function
Buatlah sebuah program Python untuk mengelola data mahasiswa (berupa nama) dengan fitur CRUD sederhana, yaitu:
1. Create: Menambahkan nama mahasiswa ke dalam list.
2. Read: Menampilkan semua data mahasiswa.
3. Update: Mengubah nama mahasiswa berdasarkan indeks.
4. Delete: Menghapus nama mahasiswa berdasarkan indeks.

Program harus menggunakan:
1. Fungsi untuk setiap aksi (create, read, update, delete)
2. Variabel global untuk menyimpan data mahasiswa
3. Variabel lokal untuk input/input sementara di dalam fungsi
4. Memiliki menu untuk memilih aktivitas, dengan fungsi `exit()` untuk keluar dari program
5. Memiliki main loop