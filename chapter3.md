--- 
title_meta  : Bab 3
title       : Matriks
description : Dalam bab ini, Anda akan mengetahui cara kerja matriks di R. Pada akhir bab ini, Anda akan bisa menciptakan matriks serta memahami cara melakukan komputasi dasar dengan matriks. Untuk menggambarkan penggunaan matriks di R, kita akan menganalisis angka box office Star Wars. Semoga kekuatan ada bersama Anda!

--- type:NormalExercise xp:100 skills:1 key:d61aeba84c
## Apa itu matriks

Dalam R, sebuah matriks adalah kumpulan elemen berisi tipe data yang sama (numerik, karakter, atau logis) yang disusun menjadi sejumlah baris dan kolom tetap. Karena kita hanya bekerja dengan baris dan kolom, matriks disebut dua dimensi.

Anda bisa membuat matriks di R dengan fungsi [`matrix()`](http://www.rdocumentation.org/packages/base/functions/matrix). Perhatikan contoh di bawah ini:

```
matrix(1:9, byrow = TRUE, nrow = 3)
```

Dalam fungsi [`matrix()`](http://www.rdocumentation.org/packages/base/functions/matrix):

- Argumen pertama adalah kumpulan elemen yang disusun ke dalam baris dan kolom matriks. Sekarang, kita memakai `1: 9`, yaitu jalan pintas untuk `c(1, 2, 3, 4, 5, 6, 7, 8, 9)`.
- Argumen `byrow` menunjukkan bahwa matriks diisi per baris. Argumen `byrow = FALSE` dipakai agar matriks diisi per kolom.
- Argumen ketiga: `nrow`, menunjukkan bahwa matriks harus memiliki tiga baris.

*** =instructions
Buatlah matriks dengan 3 baris, berisi angka 1-9, diisi per baris.

*** =hint
Bacalah tugasnya dengan cermat, karena jawabannya sudah ada!

*** =pre_exercise_code
```{r}
# no pec
```

*** =sample_code
```{r}
# Construct a matrix with 3 rows that contain the numbers 1 up to 9
```

*** =solution
```{r}
# Construct a matrix with 3 rows that contain the numbers 1 up to 9
matrix(1:9, byrow = TRUE, nrow = 3)
```

*** =sct
```{r}
test_function("matrix", c("data", "byrow", "nrow"),
              incorrect_msg = "Sudahkah anda membuat matriks dengan benar? Lihat lagi tugasnya karena jawabannya sudah ada!")
test_output_contains("matrix(1:9, byrow=TRUE, nrow=3)",
                     incorrect_msg = "Tampaknya ada masalah dengan definisi matriks. Lihat lagi tugasnya karena jawabannya sudah ada!")
success_msg("Bagus! Lanjutkan ke latihan berikutnya.")
```


--- type:NormalExercise xp:100 skills:1 key:effc2fb945
## Saatnya menganalisis matriks

Sekarang saatnya mengutak-atik matriks. Dalam latihan ini, Anda akan menganalisis angka box office waralaba Star Wars. Semoga kekuatan ada bersama Anda!

Tiga vektor didefinisikan di dalam editor. Setiap vektor mewakili angka box office dari ketiga film Star Wars pertama. Elemen pertama setiap vektor menunjukkan pendapatan box office AS, sedangkan elemen kedua untuk pendapatan box office di luar AS (sumber: Wikipedia).

Pada latihan ini, Anda menggabungkan semua angka ke dalam satu vektor tunggal. Lalu, Anda membangun matriks dari vektor itu.

*** =instructions
- Gunakan `c (new_hope, empire_strikes, return_jedi)` untuk menggabungkan ketiga vektor. Namai vektor ini: `box_office`.
- Buatlah matriks dengan 3 baris; setiap baris mewakili sebuah film. Gunakan fungsi `matrix()` untuk ini. Argumen pertama adalah vektor `box_office` yang berisi seluruh angka box office. Selanjutnya, tentukan `nrow = 3` dan `byrow = TRUE`. Namai matriks yang dihasilkan ini `star_wars_matrix`.

*** =hint
- `box_office <- c (new_hope, empire_strikes, return_jedi)` akan menggabungkan seluruh angka pada banyak vektor menjadi satu vektor berisi 6 elemen.
- `matrix (box_office, nrow = ..., by_row ...)` adalah templat jawaban untuk instruksi kedua.

*** =pre_exercise_code
```{r}
# no pec
```

*** =sample_code
```{r}
# Box office Star Wars (in millions!)
new_hope <- c(460.998, 314.4)
empire_strikes <- c(290.475, 247.900)
return_jedi <- c(309.306, 165.8)

# Create box_office
box_office <- 

# Construct star_wars_matrix
star_wars_matrix <- 
```

*** =solution
```{r}
# Box office Star Wars (in millions!)
new_hope <- c(460.998, 314.4)
empire_strikes <- c(290.475, 247.900)
return_jedi <- c(309.306, 165.8)

# Create box_office
box_office <- c(new_hope, empire_strikes, return_jedi)

# Construct star_wars_matrix
star_wars_matrix <- matrix(box_office, nrow = 3, byrow = TRUE) 
```

*** =sct
```{r}
msg <- "Jangan ganti apa pun tentang variabel box office ini: `new_hope`, `empire_strikes`, dan `return_jedi`!"
test_object("new_hope", undefined_msg = msg, incorrect_msg = msg)
test_object("empire_strikes", undefined_msg = msg, incorrect_msg = msg)
test_object("return_jedi", undefined_msg = msg, incorrect_msg = msg)

test_object("box_office", incorrect_msg = "Sudahkah Anda menggabungkan nilai-nilai `new_hope`, `empire_strikes`, dan `return_jedi` ke dalam vektor `box_office` dengan benar?")

test_function("matrix", c("data", "nrow", "byrow"),
              incorrect_msg = "Pastikan Anda menentukan dengan benar argumen-argumen yang Anda masukkan ke `matrix()`: `box_office`, `nrow = 3`, `by_row = TRUE`.")

test_object("star_wars_matrix",
            incorrect_msg = "Apakah Anda menetapkan hasil dari pemanggilan `matrix()` ke `star_wars_matrix`?")

success_msg("Kekuatan memang milik Anda! Lanjutkan ke latihan berikutnya.")
```


--- type:NormalExercise xp:100 skills:1 key:f734e8bf74
## Menamai matriks

Untuk memudahkan Anda mengingat apa yang disimpan di `star_wars_matrix`, tambahkan judul film ke baris tersebut. Hal ini tidak hanya memudahkan Anda membaca data, tetapi juga berguna untuk memilih elemen tertentu dari matriks.

Sama seperti vektor, Anda bisa menambahkan nama untuk baris dan kolom sebuah matriks

```
rownames(my_matrix) <- row_names_vector
colnames(my_matrix) <- col_names_vector
```

Kita lanjut menyiapkan dua vektor untuk Anda: `region` dan `titles`. Anda memerlukan keduanya untuk menamai kolom dan baris `star_wars_matrix`.

*** =instructions
- Gunakan `colnames()` untuk menamai kolom `star_wars_matrix` dengan vektor `region`.
- Gunakan `rownames()` untuk menamai baris `star_wars_matrix` dengan vektor `title`.
- Cetak `star_wars_matrix` untuk melihat hasil pekerjaan Anda.

*** =hint
Anda bisa memakai `colnames(star_wars_matrix) <- region` untuk menamai kolom `star_wars_matrix`. Lakukan hal yang sama untuk menamai baris.

*** =pre_exercise_code
```{r}
# no pec
```

*** =sample_code
```{r}
# Box office Star Wars (in millions!)
new_hope <- c(460.998, 314.4)
empire_strikes <- c(290.475, 247.900)
return_jedi <- c(309.306, 165.8)

# Construct matrix
star_wars_matrix <- matrix(c(new_hope, empire_strikes, return_jedi), nrow = 3, byrow = TRUE)

# Vectors region and titles, used for naming
region <- c("US", "non-US")
titles <- c("A New Hope", "The Empire Strikes Back", "Return of the Jedi")

# Name the columns with region


# Name the rows with titles


# Print out star_wars_matrix
```

*** =solution
```{r}
# Box office Star Wars (in millions!)
new_hope <- c(460.998, 314.4)
empire_strikes <- c(290.475, 247.900)
return_jedi <- c(309.306, 165.8)

# Construct matrix
star_wars_matrix <- matrix(c(new_hope, empire_strikes, return_jedi), nrow = 3, byrow = TRUE)

# Vectors region and titles, used for naming
region <- c("US", "non-US")
titles <- c("A New Hope", "The Empire Strikes Back", "Return of the Jedi")

# Name the columns with region
colnames(star_wars_matrix) <- region

# Name the rows with titles
rownames(star_wars_matrix) <- titles

# Print out star_wars_matrix
star_wars_matrix
```

*** =sct
```{r}
msg <- "Jangan ganti apa pun tentang variabel box office ini: `new_hope`, `empire_strikes`, dan `return_jedi`!"
test_object("new_hope", undefined_msg = msg, incorrect_msg = msg)
test_object("empire_strikes", undefined_msg = msg, incorrect_msg = msg)
test_object("return_jedi", undefined_msg = msg, incorrect_msg = msg)
msg <- "Jangan ganti isi `star_wars_matrix`; hanya boleh ganti nama baris dan kolom!" 
test_object("star_wars_matrix", incorrect_msg = msg)
msg <- "Jangan ganti apa pun tentang vektor `region` dan `titles` yang telah didefinisikan untuk Anda."
test_object("region", undefined_msg = msg, incorrect_msg = msg)
test_object("titles", undefined_msg = msg, incorrect_msg = msg)
test_object("star_wars_matrix", eq_condition = "equal",
            incorrect_msg = "Apakah Anda menamai baris dan kolom `star_wars_matrix` dengan benar? Gunakan `colnames (star_wars_matrix) <- region` untuk nama-nama kolom; Lakukan hal serupa untuk menamai baris.")
test_output_contains("star_wars_matrix", incorrect_msg = "Jangan lupa untuk mencetak `star_wars_matrix` setelah Anda menamai baris dan kolom.")
success_msg("Bagus! Anda akan segera menjadi jedi R! Lanjutkan ke latihan berikutnya.")
```


--- type:NormalExercise xp:100 skills:1 key:3fd7499a12
## Menghitung box office di seluruh dunia

Satu hal terpenting agar sebuah film segera menjadi legenda di Tinseltown adalah dengan angka perolehan box office film itu di seluruh dunia.

Untuk menghitung total pendapatan box office untuk ketiga film Star Wars, jumlahkan kolom pendapatan AS dan kolom pendapatan di luar AS.

Dalam R, fungsi [`rowSums()`](http://www.rdocumentation.org/packages/base/functions/colSums) mampu menghitung total untuk setiap baris matriks dengan mudah. Fungsi ini menciptakan vektor baru:

```
rowSums(my_matrix)
```

*** =instructions
Hitung angka box office di seluruh dunia untuk ketiga film tadi dan simpan di vektor ini dengan nama 'worldwide_vector`.

*** =hint
`rowSums(star_wars_matrix)` akan menghitung jumlah setiap baris untuk mendapatkan total box office setiap film.

*** =pre_exercise_code
```{r}
# no pec
```

*** =sample_code
```{r}
# Construct star_wars_matrix
box_office <- c(460.998, 314.4, 290.475, 247.900, 309.306, 165.8)
star_wars_matrix <- matrix(box_office, nrow = 3, byrow = TRUE,
                           dimnames = list(c("A New Hope", "The Empire Strikes Back", "Return of the Jedi"), 
                                           c("US", "non-US")))

# Calculate worldwide box office figures
worldwide_vector <- 
```

*** =solution
```{r}
# Construct star_wars_matrix
box_office <- c(460.998, 314.4, 290.475, 247.900, 309.306, 165.8)
star_wars_matrix <- matrix(box_office, nrow = 3, byrow = TRUE,
                           dimnames = list(c("A New Hope", "The Empire Strikes Back", "Return of the Jedi"), 
                                           c("US", "non-US")))

# Calculate worldwide box office figures
worldwide_vector <- rowSums(star_wars_matrix)
```

*** =sct
```{r}
msg <- "Jangan ganti apa pun tentang variabel prasetel `box_office_all` dan `star_wars_matrix`!"
test_object("box_office", undefined_msg = msg, incorrect_msg = msg)
test_object("star_wars_matrix", undefined_msg = msg, incorrect_msg = msg)
test_object("worldwide_vector", incorrect_msg = "Panggil `rowSums()` pada `star_wars_matrix` dan simpan hasilnya di `worldwide_vector`.")
success_msg("Selamat! Lanjutkan ke latihan berikutnya.")
```


--- type:NormalExercise xp:100 skills:1 key:86b87a8545
## Menambahkan kolom untuk box office di seluruh dunia

Dalam latihan sebelumnya, Anda telah menghitung vektor berisi angka box office di seluruh dunia untuk ketiga film Star Wars. Namun, vektor ini belum menjadi bagian dari `star_wars_matrix`.

Anda bisa menambahkan satu atau banyak kolom ke matriks dengan fungsi [`cbind()`](http://www.rdocumentation.org/packages/base/functions/cbind), yang menggabungkan matriks dan/atau vektor berdasarkan kolom. Sebagai contoh:

```
big_matrix <- cbind(matrix1, matrix2, vector1 ...)
```

*** =instructions
Tambahkan `worldwide_vector` sebagai kolom baru pada `star_wars_matrix`, lalu tetapkan hasilnya pada `all_wars_matrix`. Gunakan fungsi [`cbind()`](http://www.rdocumentation.org/packages/base/functions/cbind).

*** =hint
Dalam latihan ini, Anda harus memasukkan dua variabel ke `cbind()`: `star_wars_matrix` dan` worldwide_vector` secara berurutan. Tetapkan hasilnya pada `all_wars_matrix`.

*** =pre_exercise_code
```{r}
# no pec
```

*** =sample_code
```{r}
# Construct star_wars_matrix
box_office <- c(460.998, 314.4, 290.475, 247.900, 309.306, 165.8)
star_wars_matrix <- matrix(box_office, nrow = 3, byrow = TRUE,
                           dimnames = list(c("A New Hope", "The Empire Strikes Back", "Return of the Jedi"), 
                                           c("US", "non-US")))

# The worldwide box office figures
worldwide_vector <- rowSums(star_wars_matrix)

# Bind the new variable worldwide_vector as a column to star_wars_matrix
all_wars_matrix <- 
```

*** =solution
```{r}
# Construct star_wars_matrix
box_office <- c(460.998, 314.4, 290.475, 247.900, 309.306, 165.8)
star_wars_matrix <- matrix(box_office, nrow = 3, byrow = TRUE,
                           dimnames = list(c("A New Hope", "The Empire Strikes Back", "Return of the Jedi"), 
                                           c("US", "non-US")))

# The worldwide box office figures
worldwide_vector <- rowSums(star_wars_matrix)

# Bind the new variable worldwide_vector as a column to star_wars_matrix
all_wars_matrix <- cbind(star_wars_matrix, worldwide_vector)
```

*** =sct
```{r}
msg <- "Jangan ganti apa pun tentang variabel prasetel `box_office_all` dan `star_wars_matrix`!"
test_object("box_office", undefined_msg = msg, incorrect_msg = msg)
test_object("star_wars_matrix", undefined_msg = msg, incorrect_msg = msg)
test_object("worldwide_vector",
            incorrect_msg = "Simpan hasil `rowSums(star_wars_matrix)` di `worldwide_vector`.")

msg <- "Sudahkah anda menggunakan `cbind()` dengan benar untuk menambahkan `worldwide_vector` ke `star_wars_matrix`? Anda harus memasukkan `star_wars_matrix` dan `world_wide_vector` ke dalam `cbind()` secara  berurutan. Matriks yang dihasilkan: `all_wars_matrix`, akan terdiri dari tiga baris dan tiga kolom."
test_object("all_wars_matrix", incorrect_msg = msg)
success_msg("Bagus! Setelah menambahkan kolom ke matriks, langkah logis selanjutnya yaitu menambahkan baris. Pelajari caranya di latihan berikutnya.");
```


--- type:NormalExercise xp:100 skills:1 key:bcadb29139
## Menambahkan baris

Setiap tindakan punya reaksi. setiap [`cbind()`](http://www.rdocumentation.org/packages/base/functions/cbind) juga punya [`rbind()`](http://www.rdocumentation.org/packages/base/functions/cbind).

Ruang kerja R Anda, yang semua variabelnya Anda definisikan 'langsung' ([baca lagi definisi ruang kerja](http://www.statmethods.net/interface/workspace.html)), telah diinisialisasi dan berisi dua matriks:

- `star_wars_matrix` yang telah kita gunakan selama ini, untuk data tentang trilogi pertama,
- `star_wars_matrix2`, untuk data serupa tentang trilogi kedua.

Tulis nama matriks ini di konsol, lalu tekan Enter untuk melihat lebih detail. Jika Anda ingin melihat isi ruang kerja, tulis `ls()` di konsol.

*** =instructions
Gunakan `rbind()` untuk menyisipkan 'star_wars_matrix` dan `star_wars_matrix2` secara berurutan. Tetapkan matriks yang dihasilkan pada `all_wars_matrix`.

*** =hint
Ikat dua matriks bersama seperti ini:
```
rbind(matrix1, matrix2)
```
Tetapkan hasilnya pada `all_wars_matrix`.


*** =pre_exercise_code
```{r}
# Construct matrix
box_office_all <- c(461, 314.4, 290.5, 247.9, 309.3, 165.8)
movie_names <- c("A New Hope","The Empire Strikes Back","Return of the Jedi")
col_titles <- c("US","non-US")
star_wars_matrix <- matrix(box_office_all, nrow = 3, byrow = TRUE, dimnames = list(movie_names, col_titles))

# Construct matrix2
box_office_all2 <- c(474.5, 552.5, 310.7, 338.7, 380.3, 468.5)
movie_names2 <- c("The Phantom Menace", "Attack of the Clones", "Revenge of the Sith")
star_wars_matrix2 <- matrix(box_office_all2, nrow=3, byrow = TRUE, dimnames = list(movie_names2, col_titles))

# remove all except all_wars_matrix
rm(box_office_all)
rm(movie_names)
rm(col_titles)
rm(box_office_all2)
rm(movie_names2)
```

*** =sample_code
```{r}
# star_wars_matrix and star_wars_matrix2 are available in your workspace
star_wars_matrix  
star_wars_matrix2 

# Combine both Star Wars trilogies in one matrix
all_wars_matrix <- 
```

*** =solution
```{r}
# star_wars_matrix and star_wars_matrix2 are available in your workspace
star_wars_matrix  
star_wars_matrix2 

# Combine both Star Wars trilogies in one matrix
all_wars_matrix <- rbind(star_wars_matrix, star_wars_matrix2)
```

*** =sct
```{r}
msg = "Jangan menimpa variabel yang telah didefinisikan di ruang kerja (`star_wars_matrix` dan `star_wars_matrix2`)."
test_object("star_wars_matrix", eq_condition = "equal", undefined_msg = msg, incorrect_msg = msg)
test_object("star_wars_matrix2", eq_condition = "equal", undefined_msg = msg, incorrect_msg = msg)
test_object("all_wars_matrix", incorrect_msg = "Apakah Anda menggunakan `rbind()` dengan benar untuk membuat `all_wars_matrix ()`? `rbind()` harus mengambil dua argumen ini: `star_wars_matrix` dan `star_wars_matrix2` secara berurutan.")

success_msg("Hebat! Lanjutkan dengan latihan berikutnya dan cari tahu cara menggabungkan hasil fungsi `rbind()` dengan fungsi `colSums()`!")
```


--- type:NormalExercise xp:100 skills:1 key:1bfe5ae096
## Total pendapatan box office untuk seluruh episode

Setiap [`cbind()`](http://www.rdocumentation.org/packages/base/functions/cbind) punya [`rbind()`](http://www.rdocumentation.org/packages/base/functions/cbind), dan setiap [`colSums()`](http://www.rdocumentation.org/packages/base/functions/colSums) punya [`rowSums()`](http://www.rdocumentation.org/packages/base/functions/colSums). Ruang kerja R sudah berisi `all_wars_matrix` yang Anda bangun dalam latihan sebelumnya; tulis `all_wars_matrix` untuk melihat-lihat. Mari kita hitung total pendapatan box office untuk seluruh episode.

*** =instructions
- Hitung total pendapatan untuk wilayah AS dan di luar AS, lalu tetapkan `total_revenue_vector`. Anda bisa menggunakan fungsi [`colSums()`](http://www.rdocumentation.org/packages/base/functions/colSums).
- Cetak `total_revenue_vector` untuk melihat hasilnya.

*** =hint
Anda harus menggunakan fungsi [`colSums()`](http://www.rdocumentation.org/packages/base/functions/colSums) dengan `star_wars_matrix` sebagai argumen untuk menemukan total box office per wilayah.

*** =pre_exercise_code
```{r}
load(url("http://s3.amazonaws.com/assets.datacamp.com/course/intro_to_r/all_wars_matrix.RData"))
```

*** =sample_code
```{r}
# all_wars_matrix is available in your workspace
all_wars_matrix

# Total revenue for US and non-US
total_revenue_vector <- 
  
# Print out total_revenue_vector
```

*** =solution
```{r}
# all_wars_matrix is available in your workspace
all_wars_matrix

# Total revenue for US and non-US
total_revenue_vector <- colSums(all_wars_matrix)

# Print out total_revenue_vector
total_revenue_vector
```

*** =sct
```{r}
msg = "Jangan ganti isi `all_wars_matrix` yang sudah dibuat untuk Anda di ruang kerja."
test_object("all_wars_matrix", eq_condition = "equal", undefined_msg = msg, incorrect_msg = msg)
test_function("colSums", "x", incorrect_msg = "Did you use the `colSums()` function on the all_wars_matrix?")
test_object("total_revenue_vector",
            incorrect_msg = "Sudahkah anda menetapkan hasil 'colSums(all_wars_matrix)` pada `total_revenue_vector`?")
test_output_contains("total_revenue_vector", incorrect_msg = "Jangan lupa untuk mencetak `total_revenue_vector`!")
success_msg("Bagus! Pergilah ke latihan berikutnya untuk belajar tentang penjabaran matriks.")
```


--- type:NormalExercise xp:100 skills:1 key:41d9d69713
## Seleksi elemen matriks

Sama seperti vektor, Anda bisa menggunakan kurung siku `[]` untuk memilih satu atau banyak elemen matriks. Vektor memiliki satu dimensi, sedangkan matriks memiliki dua dimensi. Oleh sebab itu, gunakan koma untuk memisahkan apa yang harus dipilih dari baris dari apa yang ingin Anda pilih dari kolom. Sebagai contoh:

- `my_matrix [1,2]` memilih elemen pada baris pertama dan kolom kedua.
- `my_matrix [1:3,2:4]` menghasilkan matriks dengan data pada baris 1, 2, 3 dan kolom 2, 3, 4.

Untuk memilih seluruh elemen dari sebuah baris atau kolom, Anda tidak memerlukan angka sebelum atau sesudah koma:

- `my_matrix [,1]` memilih semua elemen dari kolom pertama.
- `my_matrix [1,]` memilih semua elemen dari baris pertama.

Kembalilah ke Star Wars dengan ilmu baru ini! Seperti latihan sebelumnya, `all_wars_matrix` sudah tersedia di ruang kerja.

*** =instructions
- Pilih pendapatan di luar AS untuk seluruh film (seluruh kolom kedua `all_wars_matrix`), simpan hasilnya sebagai `non_us_all`.
- Gunakan `mean()` pada `non_us_all` untuk menghitung pendapatan rata-rata luar AS untuk semua film. Cukup cetak hasilnya.
- Kali ini, pilih pendapatan luar AS untuk dua film pertama di `all_wars_matrix`. Simpan hasilnya sebagai `non_us_some`.
- Gunakan `mean ()` lagi untuk mencetak rata-rata nilai di `non_us_some`.

*** =hint
Anda bisa memilih seluruh kolom kedua dari matriks `my_matrix` dengan `my_matrix [,2]`.

*** =pre_exercise_code
```{r}
load(url("http://s3.amazonaws.com/assets.datacamp.com/course/intro_to_r/all_wars_matrix.RData"))
```

*** =sample_code
```{r}
# all_wars_matrix is available in your workspace
all_wars_matrix

# Select the non-US revenue for all movies
non_us_all <- 
  
# Average non-US revenue

  
# Select the non-US revenue for first two movies
non_us_some <- 
  
# Average non-US revenue for first two movies

```

*** =solution
```{r}
# all_wars_matrix is available in your workspace
all_wars_matrix

# Select the non-US revenue for all movies
non_us_all <- all_wars_matrix[,2]
  
# Average non-US revenue
mean(non_us_all)
  
# Select the non-US revenue for first two movies
non_us_some <- all_wars_matrix[1:2,2]
  
# Average non-US revenue for first two movies
mean(non_us_some)
```

*** =sct
```{r}
msg = "Jangan ganti isi `all_wars_matrix`; matriks ini sudah dibuat untuk Anda di ruang kerja."
test_object("all_wars_matrix", undefined_msg = msg, incorrect_msg = msg)

test_object("non_us_all",
            incorrect_msg = "Apakah Anda menetapkan seluruh kolom kedua` all_wars_matrix` pada `non_us_all`? Anda bisa menggunakan `[,2]` untuk ini!")
test_output_contains("mean(non_us_all)",
                     incorrect_msg = "Sudahkah anda menghitung rata-rata nilai di `non_us_all` dengan memanggil `mean(non_us_all)`? Cukup cetak hasilnya.")
test_object("non_us_some",
            incorrect_msg = "Apakah Anda menetapkan pendapatan di luar AS untuk dua film pertama pada `non_us_some`? Anda bisa menggunakan `[1:2,2]` untuk ini!")
test_output_contains("mean(non_us_some)",
                     incorrect_msg = "Sudahkah Anda menghitung rata-rata nilai dalam `non_us_some` dengan memanggil `mean(non_us_some)`? Cukup cetak hasilnya.")
success_msg("Bagus! Lanjutkan ke latihan berikutnya.")
```


--- type:NormalExercise xp:100 skills:1 key:c81c656f06
## Sedikit aritmetika dengan matriks

Mirip dengan apa yang telah Anda pelajari dengan vektor, operator-operator standar seperti `+`, `-`, `/`, `*`, dan lainnya bekerja sesuai elemen pada matriks di R.

Sebagai contoh, `2 * my_matrix` akan mengalikan setiap elemen `my_matrix` dengan dua.

Sebagai analis data yang baru bekerja di Lucasfilm, tugas Anda adalah mengetahui jumlah penonton setiap film pada setiap wilayah geografis. Anda sudah memiliki total angka pendapatan di `all_wars_matrix`. Anggaplah bahwa harga tiket adalah 5 dolar. Cukup bagi angka box office dengan harga tiket untuk menghasilkan jumlah penonton.

*** =instructions
- Bagi 'all_wars_matrix` dengan 5 untuk mencari jumlah penonton dalam jutaan. Tetapkan matriks yang dihasilkan ke `visitors`.
- Cetak `visitors` sehingga Anda bisa melihat-lihat.

*** =hint
Jumlah pengunjung sama dengan `all_wars_matrix` dibagi dengan 5.

*** =pre_exercise_code
```{r}
load(url("http://s3.amazonaws.com/assets.datacamp.com/course/intro_to_r/all_wars_matrix.RData"))
``` 

*** =sample_code
```{r}
# all_wars_matrix is available in your workspace
all_wars_matrix

# Estimate the visitors
visitors <- 
  
# Print the estimate to the console

```

*** =solution
```{r}
# all_wars_matrix is available in your workspace
all_wars_matrix

# Estimate the visitors
visitors <- all_wars_matrix / 5

# Print the estimate to the console
visitors
```

*** =sct
```{r}
msg = "Jangan ganti isi `all_wars_matrix`; matriks ini sudah dibuat untuk Anda di ruang kerja."
test_object("all_wars_matrix", undefined_msg = msg, incorrect_msg = msg)

test_object("visitors",
            incorrect_msg = "Sepertinya `visitors` tidak benar. Bagi `all_wars_matrix` dengan 5 lalu simpan matriks yang dihasilkan sebagai`visitors`.")
test_output_contains("visitors", incorrect_msg = "Jangan lupa juga untuk mencetak `visitors` sehingga Anda bisa melihat-lihat.")
success_msg("Hebat! Apa yang bisa Anda ketahui dari hasil ini? Ada 92 juta orang yang terkagum-kagum setelah menonton A New Hope di bioskop-bioskop AS! Lanjutkan ke latihan berikutnya.")
```


--- type:NormalExercise xp:100 skills:1 key:1e0b39d6e9
## Sedikit aritmetika dengan matriks (2)

Jika `2 * my_matrix` mengalikan setiap elemen `my_matrix` dengan dua, `my_matrix1 * my_matrix2` membuat matriks baru yang setiap elemen di dalamnya adalah hasil dari elemen-elemen terkait di `my_matrix1` dan `my_matrix2`.

Setelah melihat hasil latihan sebelumnya, bos besar Lucas mengetahui bahwa harga tiket terus naik dari waktu ke waktu. Dia meminta Anda mengulang analisis berdasarkan harga yang ada di `ticket_prices_matrix` (sumber: imajinasi).

_Bagi Anda yang akrab dengan matriks harus mengingat bahwa ini bukan perkalian matriks standar. Untuk itu, Anda harus memakai `%*%` di R._

*** =instructions
- Bagi 'all_wars_matrix` dengan `ticket_prices_matrix` untuk mendapatkan perkiraan jumlah pengunjung AS dan di luar AS untuk keenam film. Tetapkan hasilnya pada `visitors`.
- Dari matriks `visitors`, pilih seluruh kolom pertama yang mewakili jumlah pengunjung di AS. Simpan sebagai `us_visitors`.
- Hitung jumlah rata-rata pengunjung AS; cetak hasilnya.

*** =hint
- Anda bisa menggunakan fungsi `mean ()` untuk menghitung rata-rata input pada fungsi.
- Untuk mendapatkan jumlah pengunjung di AS, pilih kolom pertama `visitors` memakai `visitors [,1] `.

*** =pre_exercise_code
```{r}
load(url("http://s3.amazonaws.com/assets.datacamp.com/course/intro_to_r/all_wars_matrix.RData"))
movie_names <- c("A New Hope","The Empire Strikes Back","Return of the Jedi", "The Phantom Menace", "Attack of the Clones", "Revenge of the Sith")
col_titles <- c("US","non-US")
ticket_prices_matrix <- matrix(c(5, 5, 6, 6, 7, 7, 4, 4, 4.5, 4.5, 4.9, 4.9), nrow = 6, byrow = TRUE, dimnames = list(movie_names,col_titles))
```

*** =sample_code
```{r}
# all_wars_matrix and ticket_prices_matrix are available in your workspace
all_wars_matrix
ticket_prices_matrix

# Estimated number of visitors
visitors <- 

# US visitors
us_visitors <- 

# Average number of US visitors

```

*** =solution
```{r}
# all_wars_matrix and ticket_prices_matrix are available in your workspace
all_wars_matrix
ticket_prices_matrix

# Estimated number of visitors
visitors <- all_wars_matrix / ticket_prices_matrix

# US visitors
us_visitors <- visitors[ ,1]

# Average number of US visitors
mean(us_visitors)
```

*** =sct
```{r}
msg <- "Jangan ganti isi `all_wars_matrix`; matriks ini sudah dibuat untuk Anda di ruang kerja."
test_object("all_wars_matrix", undefined_msg = msg, incorrect_msg = msg)
msg <- "Jangan ganti isi `ticket_prices_matrix`; matriks ini sudah dibuat untuk Anda di ruang kerja."
test_object("ticket_prices_matrix", undefined_msg = msg, incorrect_msg = msg)

test_object("visitors",
            incorrect_msg = "Sudahkah anda membuat matriks `visitors` dengan benar? Anda harus membagi `all_wars_matrix` dengan` ticket_prices_matrix` untuk itu.")
test_object("us_visitors", incorrect_msg = "Anda harus memilih seluruh kolom pertama `visitors` dengan benar untuk membuat `us_visitors`. Anda bisa memakai `[,1]` untuk ini!")
test_output_contains("mean(us_visitors)", incorrect_msg = "Setelah `us_visitors` dibuat, Anda bisa menggunakan `mean()` untuk menghitung jumlah rata-rata pengunjung di AS. Pastikan Anda mencetak hasilnya.")

success_msg("Faktanya: kekuatan R ada bersama Anda! Latihan ini menyimpulkan bab tentang matriks. Perhentian Anda berikutnya di bahasa R: faktor.")
```


