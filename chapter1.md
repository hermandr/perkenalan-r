--- 
title_meta  : Bab 1
title       : Pengenalan dasar
description : "Pada bab ini, Anda akan menjalankan langkah-langkah pertama dengan R. Anda akan belajar cara memakai konsol sebagai kalkulator dan juga cara menetapkan variabel. Anda juga akan mengenal tipe-tipe data dasar di R. Ayo kita mulai!"

--- type:NormalExercise xp:100 skills:1 key:15d729634a
## Cara kerja R

Tuliskan kode R di editor di sebelah kanan untuk menyelesaikan latihan ini. Begitu Anda menekan tombol 'Kirim Jawaban', seluruh baris kode akan ditafsirkan dan dijalankan oleh R. Anda akan menerima pesan bahwa kode Anda benar atau salah. Output kode R ditampilkan di konsol di sudut kanan bawah.

R menggunakan tanda `#` untuk menambahkan komentar supaya Anda atau orang lain mengerti maksud dari kode R itu. Sama seperti Twitter, komentar tidak dijalankan sebagai kode R sehingga hasilnya tidak akan terpengaruh. Contoh komentar yaitu _Calculate 3 + 4_ di editor sebelah kanan.

Anda juga bisa menjalankan perintah R langsung di konsol. Ini cara yang baik untuk bereksperimen dengan kode R karena kebenaran kode tidak akan diperiksa.

*** =instructions
- Di editor sebelah kanan sudah ada beberapa kode contoh. Bisakah Anda mengetahui baris yang merupakan kode R dan yang merupakan komentar?
- Tambahkan sebaris kode untuk menghitung 6 tambah 12, lalu tekan tombol 'Kirim Jawaban'.

*** =hint
Cukup tambahkan sebaris kode R yang menghitung 6 tambah 12, sama seperti contoh kode pada sampel!

*** =pre_exercise_code
```{r}
# no pec
```

*** =sample_code
```{r}
# Calculate 3 + 4
3 + 4

# Calculate 6 + 12

```

*** =solution
```{r}
# Calculate 3 + 4
3 + 4

# Calculate 6 + 12
6 + 12
```

*** =sct
```{r}
test_output_contains("18", incorrect_msg = "Make sure to add `6 + 12` on a new line. Do not start the line with a `#`, otherwise your R code is not executed!")
success_msg("Awesome! See how the console shows the result of the R code you submitted? Now that you're familiar with the interface, let's get down to R business!")
```

--- type:NormalExercise xp:100 skills:1 key:720745eda5
## Aritmetika dengan R

Dalam bentuknya yang paling dasar, R dapat dipakai sebagai kalkulator sederhana. Coba lihat operator aritmetika di bawah ini:

- Penjumlahan: `+`
- Pengurangan: `-`
- Perkalian: `*`
- Pembagian: `/`
- Pemangkatan: `^`
- Modulus: `%%`

Ini penjelasan untuk kedua operator terakhir:

- Operator `^` memangkatkan angka di kiri dengan angka di kanan, misal: `3^2` = 9.
- Modulus mengembalikan sisa pembagian angka di kiri dengan angka di kanan, misal: 5 modulus 3 atau `5 %% 3` = 2.

Sesuai informasi di atas, ikuti petunjuk di bawah ini untuk menyelesaikan latihan.

*** =instructions
- Tulis `2^5` di editor untuk menghitung 2 pangkat 5.
- Tulis `28 %% 6` untuk menghitung 28 modulus 6.
- Klik 'Kirim Jawaban' dan lihat output R di konsol.
- Perhatikan cara pemakaian simbol `#` untuk menambahkan komentar pada kode R.

*** =hint
Contoh lain dari operator modulus: `9 %% 2` = `1`.

*** =pre_exercise_code
```{r}
# no pec
```

*** =sample_code
```{r}
# An addition
5 + 5 

# A subtraction
5 - 5 

# A multiplication
3 * 5

 # A division
(5 + 5) / 2 

# Exponentiation


# Modulo

```

*** =solution
```{r}
# An addition
5 + 5

# A subtraction
5 - 5 

# A multiplication
3 * 5

 # A division
(5 + 5) / 2 

# Exponentiation
2 ^ 5

# Modulo
28 %% 6
```

*** =sct
```{r}
msg = "Do not remove the other arithmetic examples!"
test_output_contains("2^5", incorrect_msg = "The exponentiation example is not correct. Write `2 ^ 5` on a new line.")
test_output_contains("28 %% 6", incorrect_msg = "There seems to be an issue with the modulo example. Write `28 %% 6` on a new line.")
success_msg("Great! Head over to the next exercise.")
```


--- type:NormalExercise xp:100 skills:1 key:5f200ffd43
## Penetapan variabel

Konsep dasar dalam pemrograman (statistik) disebut **variabel**.

Berkat variabel, Anda dapat menyimpan nilai (mis. 4) atau objek (mis. deskripsi fungsi) di R. Nantinya, nama variabel ini dapat dipakai untuk kemudahan mengakses nilai atau objek yang telah tersimpan di dalamnya.

Anda dapat menetapkan nilai 4 pada variabel `my_var` dengan perintah:

```
my_var <- 4
```

*** =instructions
Sekarang, lengkapi kode di editor untuk menetapkan nilai 42 pada variabel `x` di editor. Klik 'Kirim Jawaban'. Perhatikan: ketika Anda meminta R untuk mencetak `x`, nilai 42 akan muncul.

*** =hint
Dalam tugas latihan, lihat bagaimana nilai 4 ditetapkan pada `my_variable` . Lakukan hal sama persis di editor dengan menetapkan 42 pada variabel `x`.

*** =pre_exercise_code
```{r}
# no pec
```

*** =sample_code
```{r}
# Assign the value 42 to x
x <- 

# Print out the value of the variable x
x
```

*** =solution
```{r}
# Assign the value 42 to x
x <- 42

# Print out the value of the variable x
x
```

*** =sct
```{r}
test_object("x", undefined_msg = "Make sure to define a variable `x`.",
            incorrect_msg = "Make sure that you assign the correct value to `x`.") 
success_msg("Good job! Have you noticed that R does not print the value of a variable to the console when you did the assignment? `x <- 42` did not generate any output, because R assumes that you will be needing this variable in the future. Otherwise you wouldn't have stored the value in a variable in the first place, right? Proceed to the next exercise!")
```


--- type:NormalExercise xp:100 skills:1 key:c5944b90eb
## Penetapan variabel (2)

Anggaplah Anda memiliki lima buah apel dalam keranjang. Sebagai analis data dalam pelatihan ini, Anda ingin menyimpan jumlah apel dalam sebuah variabel bernama `my_apples`.

*** = instructions
- Tulis kode berikut di editor: `my_apples <- 5`. Nilai 5 akan ditetapkan pada `my_apples`.
- Tulis: `my_apples` di bawah komentar kedua. Ini akan mencetak nilai `my_apples`.
- Klik 'Kirim Jawaban', lalu lihat di konsol: Anda melihat angka 5 dicetak. Jadi, R menautkan variabel `my_apples` dengan nilai 5.

*** =hint
Ingat: Jika Anda ingin menetapkan angka atau objek pada variabel di R, gunakan operator penugasan `<-`. Operator `<-` lebih suka dipakai oleh komunitas R daripada tanda `=`.

*** =pre_exercise_code
```{r}
# no pec
```

*** =sample_code
```{r}
# Assign the value 5 to the variable my_apples


# Print out the value of the variable my_apples

```

*** =solution
```{r}
# Assign the value 5 to the variable my_apples
my_apples <- 5

# Print out the value of the variable my_apples
my_apples
```

*** =sct
```{r}
test_object("my_apples", 
            undefined_msg = "Please make sure to define a variable `my_apples`.",
            incorrect_msg = "Make sure that you assign the correct value to `my_apples`.")
test_output_contains("my_apples", incorrect_msg = "Have you explicitly told R to print out the `my_apples` variable to the console?")
success_msg("Great! Continue to the next exercise!")
```


--- type:NormalExercise xp:100 skills:1 key:1c1bd25045
## Penetapan variabel (3)

Setiap keranjang buah yang lezat ini harus menampung buah jeruk. Anda akan menambahkan enam buah jeruk. Sebagai analis data, Anda segera membuat variabel baru:`my_oranges`, dan memberikan nilai 6 ke dalamnya. Selanjutnya, Anda ingin menghitung total buah yang ada. Karena semua nilai ini telah diberi nama yang bermakna, Anda kini dapat mengodekannya dengan cara yang jelas:

```
my_apples + my_oranges
```

*** =instructions
- Menetapkan nilai 6 pada `my_oranges` .
- Menjumlahkan variabel `my_apples` dan` my_oranges`, dan menyuruh R untuk mencetak hasilnya.
- Menetapkan hasil penjumlahan `my_apples` dan` my_oranges` pada sebuah variabel baru: `my_fruit`.

*** =hint
`My_fruit` hanyalah jumlah` my_apples` dan `my_oranges`. Anda dapat memakai operator `+` untuk menjumlahkan keduanya dan operator `<-` untuk menetapkan nilai tersebut pada variabel` my_fruit`.

*** =pre_exercise_code
```{r}
# no pec
```

*** =sample_code
```{r}
# Assign a value to the variables my_apples and my_oranges
my_apples <- 5


# Add these two variables together


# Create the variable my_fruit

```

*** =solution
```{r}
# Assign a value to the variables my_apples and my_oranges
my_apples  <- 5
my_oranges <- 6

# Add these two variables together
my_apples + my_oranges

# Create the variable my_fruit
my_fruit <- my_apples + my_oranges
```

*** =sct
```{r}
test_object("my_apples", incorrect_msg = "Keep the line that assigns 5 to `my_apples`.")
test_object("my_oranges", incorrect_msg = "Keep the line that assigns 6 to `my_oranges`.")
test_output_contains("my_apples + my_oranges",
                     incorrect_msg = "Make sure to print out the result of adding `my_apples` and `my_oranges`. The code example in the description already gives away the answer to this instruction!")
msg <- "Have you used `my_fruit <- my_apples + my_oranges` to create the `my_fruit` variable?"
test_object("my_fruit", undefined_msg = msg, incorrect_msg = msg)
success_msg("Nice one! The great advantage of doing calculations with variables is reusability. If you just change `my_apples` to equal 12 instead of 5 and rerun the script, `my_fruit` will automatically update as well. Continue to the next exercise.")
```


--- type:NormalExercise xp:100 skills:1 key:915fcc7c99
## Apel dan jeruk

Anda telah mempertimbangkan untuk tidak menambahkan apel dan jeruk. Namun, itu yang baru saja Anda lakukan, bukan? :-) Variabel `my_apples` dan` my_oranges` sama-sama berisi angka pada latihan sebelumnya. Operator `+` bekerja untuk variabel numerik di R. Jika Anda benar-benar menjumlahkan "apples" dan "oranges", lalu menetapkan nilai teks pada variabel `my_oranges` (lihat editor), artinya Anda menetapkan penjumlahan variabel numerik dan karakter pada variabel `my_fruit`. Hal ini mustahil.

*** =instructions
- Klik 'Kirim Jawaban' dan baca pesan kesalahannya. Pastikan Anda memahami pesan kesalahan tersebut.
- Sesuaikan kode sehingga R mengetahui bahwa Anda memiliki 6 buah jeruk sehingga ada 11 buah di dalam keranjang.

*** =hint
Anda harus menetapkan nilai numerik `6` pada variabel` my_oranges` alih-alih karakter `"six"`. Perhatikan cara pemakaian tanda petik untuk menunjukkan bahwa `"six"` adalah karakter.

*** =pre_exercise_code
```{r}
# no pec
```

*** =sample_code
```{r}
# Assign a value to the variable my_apples
my_apples <- 5 

# Fix the assignment of my_oranges
my_oranges <- "six" 

# Create the variable my_fruit and print it out
my_fruit <- my_apples + my_oranges 
my_fruit
```

*** =solution
```{r}
# Assign a value to the variable my_apples
my_apples <- 5  

# Fix the assignment of my_oranges
my_oranges <- 6

# Create the variable my_fruit and print it out
my_fruit <- my_apples + my_oranges 
my_fruit
```

*** =sct
```{r}
test_error(incorrect_msg = "You can do this by setting the `my_oranges` variable to a numeric value, not a string!")
test_object("my_apples", incorrect_msg = "Make sure that `my_apples` still contains `5`.")
test_object("my_oranges", incorrect_msg = "Make sure that `my_oranges` is equal to `6`.")
test_object("my_fruit", incorrect_msg = "The value of `my_fruit` is not correct. It should be 11, the sum of `my_apples` and `my_oranges`.")
test_output_contains("my_fruit", incorrect_msg = "Don't remove the line that prints out `my_fruit`.")
success_msg("Awesome, keep up the good work! Continue to the next exercise.")
```


--- type:NormalExercise xp:100 skills:1 key:0f23107394
## Tipe-tipe data dasar dalam R

R bekerja dengan beragam jenis tipe data. Beberapa tipe data yang paling dasar untuk diketahui yaitu:

- Nilai desimal, misal: `4.5` disebut **numerik**.
- Angka natural, misal: `4` disebut **integer** (bilangan bulat). Integer juga numerik.
- Nilai boolean:`TRUE` (benar) atau` FALSE` (salah) disebut **logikal**.
- Nilai teks (atau string) disebut **karakter**.

Perhatikan: tanda petik di sebelah kanan menunjukkan bahwa "sebagian teks" berupa karakter.

*** =instructions
Gantilah nilai-nilai:

- variabel `my_numeric` menjadi `42`.
- variabel `my_character` menjadi `"universe"`. Perhatikan: tanda petik menunjukkan bahwa `"universe"` adalah karakter.
- variabel `my_logical` menjadi `FALSE`.

Perhatikan: R bersifat case sensitive (peka huruf)!

*** =hint 
Ganti nilai-nilai di editor dengan nilai-nilai yang telah disediakan dalam latihan. Sebagai contoh:
`My_numeric <- 42` menetapkan nilai 42 pada variabel` my_numeric`.

*** =pre_exercise_code
```{r}
# no pec
```

*** =sample_code
```{r}
# Change my_numeric to be 42
my_numeric <- 42.5

# Change my_character to be "universe"
my_character <- "some text"

# Change my_logical to be FALSE
my_logical <- TRUE
```

*** =solution
```{r}
# Change my_numeric to be 42
my_numeric <- 42

# Change my_character to be "universe"
my_character <- "universe"

# Change my_logical to be FALSE
my_logical <- FALSE
```

*** =sct
```{r}
test_object("my_numeric", incorrect_msg = "Have you correctly changed the declaration of `my_numeric` so it contains the value 42?")
test_object("my_character", incorrect_msg = "Have you correctly changed `my_character` to `\"universe\"`? Don't forget the quotes!")
test_object("my_logical", incorrect_msg = "Have you correctly changed `my_logical` to `FALSE`? All letters of `FALSE` should be capitalized!")
success_msg("Great work! Continue to the next exercise.")
```


--- type:NormalExercise xp:100 skills:1 key:99b549229d
## Apa itu tipe data?

Masih ingat sewaktu Anda menjumlahkan `5 + "six"` lalu muncul kesalahan karena ketidakcocokan tipe data? Hindari situasi memalukan seperti ini dengan cara memeriksa jenis data variabel sebelumnya. Lakukan hal ini dengan fungsi `class ()`, seperti yang ditunjukkan pada kode di sebelah kanan.

*** =instructions
Lengkapi kode di editor dan cetak juga kelas `my_character` dan` my_logical`.

*** =hint
Kode untuk mencetak tipe data `my_numeric` sudah disertakan; Lakukan hal serupa untuk `my_character` dan` my_logical`.

*** =pre_exercise_code
```{r}
# no pec
```

*** =sample_code
```{r}
# Declare variables of different types
my_numeric <- 42
my_character <- "universe"
my_logical <- FALSE 

# Check class of my_numeric
class(my_numeric)

# Check class of my_character


# Check class of my_logical

```

*** =solution
```{r}
# Declare variables of different types:
my_numeric <- 42
my_character <- "universe"
my_logical <- FALSE

# Check class of my_numeric
class(my_numeric)

# Check class of my_character
class(my_character)

# Check class of my_logical
class(my_logical)
```

*** =sct
```{r}
msg <- "Do not change the declaration of the variables!"
lapply(c("my_numeric", "my_character", "my_logical"), test_object, undefined_msg = msg, incorrect_msg = msg)
patt <- "Have you included `class(%1$s)` to print out the data type of `%1$s`?"
test_output_contains("class(my_numeric)",
                     incorrect_msg = "Do not remove the code that prints out the type of `my_numeric`.")
test_output_contains("class(my_character)",
                     incorrect_msg = sprintf(patt, "my_character"))
test_output_contains("class(my_logical)",
                     incorrect_msg = sprintf(patt, "my_logical"))
success_msg("Congratulations! This was the last exercise for this chapter. Head over to the next chapter to get immersed in the world of vectors!")
```



