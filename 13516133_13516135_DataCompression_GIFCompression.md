# GIFCompression

Graphics Interchange Format (GIF) adalah format grafis yang sering digunakan untuk keperluan desain situs web. GIF memiliki kombinasi warna lebih sedikit dibanding JPEG, tetapi mampu menyimpan grafis dengan latar belakang (background) transparan ataupun dalam bentuk animasi sederhana.

## Bagaimana GIF Dikompresi ?

GIF diformat dengan kompresi algoritme LZW (Lempel Zev Welch) yang dimiliki oleh Unisys. Pemegang hak cipta GIF kini dipegang oleh CompuServe Incorporated. Awalnya GIF bebas royalti bagi semua pengguna namun tahun 1995. Unisys memutuskan menarik royalti pada vendor pengguna GIF.

## Penjelasan algoritma Lempel–Ziv–Welch

### Definisi

Algoritma LZW dikembangkan dari metode kompresi yang dibuat oleh Ziv dan Lempel pada tahun 1977. Algoritma ini melakukan kompresi dengan menggunakan dictionary, di mana fragmen-fragmen teks digantikan dengan indeks yang diperoleh dari sebuah “kamus”. Prinsip sejenis juga digunakan dalam kode Braille, di mana kode-kode khusus digunakan untuk merepresentasikan kata-kata yang ada. Pendekatan ini bersifat adaptif dan efektif karena banyak karakter dapat dikodekan dengan mengacu pada string yang telah muncul sebelumnya dalam teks. Prinsip kompresi tercapai jika referensi dalam bentuk pointer dapat disimpan dalam jumlah bit yang lebih sedikit dibandingkan string aslinya.

### Algoritma

Algoritma Lempel-Ziv-Welch untuk melakukan kompresi adalah sebagai berikut:

'''
1.	Dictionary diinisialisasi dengan semua karakter dasar yang ada, dan P adalah kosong. 
2.	C diisi dengan karakter selanjutnya di dalam teks
3.	Apakah string P+C terdapat dalam dictionary ?
  •	Jika ada, maka P = P+C
  •	Jika tidak, maka :
    i.	output P ke stream karakter
    ii.	Tambahkan string P+C ke dalam dictionary
    iii.	P diisi dengan C
4.	Apakah terdapat kode lagi di stream kode ?
  •	Jika ya, maka kembali ke langkah 2.
  •	Jika tidak, maka terminasi proses (stop).
'''

Tentunya algoritma ini juga memiliki cara untuk melakukan decoding suatu string yang telah dikompresi. Berikut adalah algoritma untuk decoding:
