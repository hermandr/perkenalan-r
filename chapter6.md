--- 
title_meta  : Bab 6
title       : `list`
description : Berlawanan dengan vektor, `list` dapat menampung komponen-komponen tipenya berbeda, mirip seperti daftar tugas di rumah atau di kantor. Bab ini akan mengajari Anda cara membuat, menamai, dan mengolah subset `list`.

--- type:NormalExercise xp:100 skills:1 key:2afcdb6a76ec91bf266de9b2ac295d844d7bb004
## Mengapa `list` diperlukan?

Selamat! Sampai sini, Anda sudah memahami hal-hal berikut di dalam kursus ini:

- **Vektor** (larik satu dimensi): dapat menampung nilai numerik, karakter, atau logis. Seluruh elemen di dalam vektor memiliki tipe data yang sama.
- **Matriks** (larik dua dimensi): dapat menampung nilai numerik, karakter, atau logis. Seluruh elemen di dalam matriks memiliki tipe data yang sama.
- **Frame data** (objek dua dimensi): dapat menampung nilai numerik, karakter, atau logis. Seluruh elemen di dalam kolom memiliki tipe data yang sama, tetapi kolom-kolom yang berbeda dapat memiliki tipe-tipe data yang berbeda pula.

Lumayan untuk seorang pemula R, kan? ;-)

*** =instructions
Klik 'Kirim Jawaban' untuk mulai belajar segala hal tentang `list`!

*** =hint
Cukup klik tombol 'Kirim Jawaban'.

*** =pre_exercise_code
```{r}
# no pec
```

*** =sample_code
```{r}
# Just click the 'Submit Answer' button.
```

*** =solution
```{r}
# Just click the 'Submit Answer' button.
```

*** =sct
```{r}
success_msg("Siap, sedia, mulai! Lanjutkan ke latihan berikutnya.")
```


--- type:NormalExercise xp:100 skills:1 key:68f93c5c504616bd18876da52cd123277d56fc8b
## Mengapa `list` diperlukan? (2)

**`list`** di R mirip dengan daftar tugas di kantor atau sekolah; sejumlah item dalam `list` kemungkinan besar memiliki perbedaan dalam durasi, karakteristik, jenis kegiatan yang harus selesai, dan sebagainya.

Pada `list`, Anda dapat mengumpulkan berbagai objek menjadi satu nama (yaitu, nama `list`) secara berurutan. Objek bisa berupa matriks, vektor, frame data, `list` lain, dan seterusnya. Seluruh objek ini bahkan tidak harus terkait satu sama lain dengan cara apa pun.

Bisa disimpulkan bahwa `list` adalah sejenis tipe data super; hampir semua informasi dapat ditampung di dalamnya!

*** =instructions
Klik 'Kirim Jawaban' untuk memulai latihan pertama tentang `list`.

*** =hint
Klik 'Kirim Jawaban' untuk memulai latihan pertama tentang `list`.

*** =pre_exercise_code
```{r}
# no pec
```

*** =sample_code
```{r}
# Click 'Submit Answer' to start the first exercise on `list`s.
```

*** =solution
```{r}
# Click 'Submit Answer' to start the first exercise on `list`s.
```

*** =sct
```{r}
success_msg("Keren. Sekarang saatnya mengutak-atik!")
```


--- type:NormalExercise xp:100 skills:1 key:4beee9cb532c889903218b49b83ab5ef133eac83
## Membuat `list`

Saatnya membangun `list` pertama! Gunakan fungsi [``list`()`](http://www.rdocumentation.org/packages/base/functions/`list`) untuk membuat `list`:

```
my_`list` <- `list`(comp1, comp2 ...)
```

Argumen-argumen pada `list` fungsi merupakan `list` komponen. Ingat, komponen bisa berupa matriks, vektor, `list` lainnya, dan sebagainya.

*** =instructions
Buatlah sebuah `list` bernama `my_`list`` berisi variabel `my_vector`, `my_matrix`, dan` my_df` sebagai komponennya.

*** =hint
Gunakan fungsi [``list`()`](http://www.rdocumentation.org/packages/base/functions/`list`)  dengan `my_vector`, `my_matrix`, dan `my_df` sebagai argumen-argumen yang dipisahkan dengan koma.

*** =pre_exercise_code
```{r}
# no pec
```

*** =sample_code
```{r}
# Vector with numerics from 1 up to 10
my_vector <- 1:10 

# Matrix with numerics from 1 up to 9
my_matrix <- matrix(1:9, ncol = 3)

# First 10 elements of the built-in data frame mtcars
my_df <- mtcars[1:10,]

# Construct `list` with these different elements:
my_`list` <- 
```

*** =solution
```{r}
# Vector with numerics from 1 up to 10
my_vector <- 1:10 

# Matrix with numerics from 1 up to 9
my_matrix <- matrix(1:9, ncol = 3)

# First 10 elements of the built-in data frame mtcars
my_df <- mtcars[1:10,]

# Construct `list` with these different elements:
my_`list` <- `list`(my_vector, my_matrix, my_df)
```

*** =sct
```{r}
msg = "Jangan menghapus atau mengganti definisi variabel `my_vector`, `my_matrix`, atau `my_df`!"
test_object("my_vector", undefined_msg = msg, incorrect_msg = msg)
test_object("my_matrix", undefined_msg = msg, incorrect_msg = msg)
test_object("my_df", undefined_msg = msg, incorrect_msg = msg)
test_object("my_`list`",
            incorrect_msg = "Sepertinya `my_`list`` tidak berisi elemen-elemen yang benar. Pastikan Anda memasukkan variabel `my_vector`, `my_matrix`, dan `my_df` ke dalam fungsi ``list`()` secara berurutan, dipisah tanda koma.")
success_msg("Hebat! Pergilah ke latihan berikutnya.")
```


--- type:NormalExercise xp:100 skills:1 key:89dd0126568b1ff5a84033c571907a8a282245e4
## Membuat `list` bernama

Ayo, Anda pasti bisa!

Sama seperti daftar tugas, Anda tak ingin ada komponen yang tidak diketahui atau tidak dikenal pada `list`. Itulah sebabnya Anda harus menamai setiap komponen:

```
my_`list` <- `list`(name1 = your_comp1, 
                name2 = your_comp2)
``` 

Kode ini menciptakan sebuah `list` berisi komponen bernama `name1`, `name2`, dan sebagainya. Jika Anda ingin menamai `list` setelah Anda membuatnya, gunakan fungsi `names()` seperti yang Anda lakukan dengan vektor. Perintah berikut ini sepenuhnya setara dengan tugas di atas:

```
my_`list` <- `list`(your_comp1, your_comp2)
names(my_`list`) <- c("name1", "name2")
```

*** =instructions
- Ganti kode latihan sebelumnya (lihat editor) dengan menambahkan nama-nama pada komponen. Namai `my_vector` dengan `vec`, `my_matrix` dengan `mat`, dan `my_df` dengan `df`.
- Cetak `my_`list`` supaya Anda dapat memeriksa hasilnya.

*** =hint
Cara pertama untuk menamai komponen di dalam `list` adalah yang termudah. Dimulai seperti ini:
```
my_`list` <- `list`(vec = my_vector)
```
Tambahkan dua komponen lainnya dengan cara serupa.

*** =pre_exercise_code
```{r}
# no pec
```

*** =sample_code
```{r}
# Vector with numerics from 1 up to 10
my_vector <- 1:10 

# Matrix with numerics from 1 up to 9
my_matrix <- matrix(1:9, ncol = 3)

# First 10 elements of the built-in data frame mtcars
my_df <- mtcars[1:10,]

# Adapt `list`() call to give the components names
my_`list` <- `list`(my_vector, my_matrix, my_df)

# Print out my_`list`

```

*** =solution
```{r}
# Vector with numerics from 1 up to 10
my_vector <- 1:10 

# Matrix with numerics from 1 up to 9
my_matrix <- matrix(1:9, ncol = 3)

# First 10 elements of the built-in data frame mtcars
my_df <- mtcars[1:10,]

# Adapt `list`() call to give the components names
my_`list` <- `list`(vec = my_vector, mat = my_matrix, df = my_df)

# Print out my_`list`
my_`list`
```

*** =sct
```{r}
msg = "Jangan menghapus atau mengganti definisi variabel `my_vector`, `my_matrix`, atau `my_df`!"
test_object("my_vector", undefined_msg = msg, incorrect_msg = msg)
test_object("my_matrix", undefined_msg = msg, incorrect_msg = msg)
test_object("my_df", undefined_msg = msg, incorrect_msg = msg)
test_object("my_`list`",
            incorrect_msg = "Sepertinya `my_`list`` tidak berisi elemen-elemen yang benar.")
test_object("my_`list`", eq_condition = "equal",
            incorrect_msg = "Sepertinya `my_`list`` tidak berisi penamaan komponen yang benar. Pastikan Anda menggunakan nama `vec`, `mat`, dan `df` secara berurutan. Lihat petunjuknya jika Anda kesulitan.");
test_output_contains("my_`list`", incorrect_msg = "Jangan lupa untuk mencetak `my_`list`` ke konsol! Cukup tambahkan `my_`list`` pada baris baru di editor.")
success_msg("Hebat! Anda bukan hanya paham cara membangun sebuah `list`, tetapi juga menamainya. Ini keahlian yang akan terbukti paling bermanfaat dalam latihan. Lanjutkan ke latihan berikutnya.")
```


--- type:NormalExercise xp:100 skills:1 key:19fd17cc792ef870c1558b3a9bae08c1d1e3acae
## Membuat `list` nama (2)

Sebagai penggemar berat film (ingat tugas Anda kemarin di LucasFilms), Anda memutuskan untuk mulai menyimpan informasi film-film bagus dengan bantuan `list`.

Awali dengan membuat `list` untuk film "The Shining". Kami telah membuat variabel `mov`, `act`, dan` rev` di ruang kerja R. Silakan melihatnya di konsol.

*** =instructions
Lengkapi kode di sebelah kanan untuk membuat `shining_`list``; ada tiga elemen di dalamnya:

- moviename: string karakter berisi judul film (disimpan dalam `mov`)
- actors: vektor berisi nama para aktor utama (disimpan dalam `act`)
- reviews: frame data yang berisi sejumlah ulasan (disimpan dalam `rev`)

Jangan lupa untuk menamai setiap komponen `list` dengan benar (yaitu moviename, actors, dan reviews).

*** =hint
`shining_`list` <- `list`(moviename = mov)` adalah sebagian jawabannya; tugas Anda yaitu menambahkan `act` dan` rev` ke dalam `list` dengan nama yang sesuai.

*** =pre_exercise_code
```{r}
mov <- "The Shining"
act      <- c("Jack Nicholson","Shelley Duvall","Danny Lloyd","Scatman Crothers","Barry Nelson")
sources     <- c("IMDb1","IMDb2","IMDb3")
comments    <- c("Best Horror Film I Have Ever Seen","A truly brilliant and scary film from Stanley Kubrick","A masterpiece of psychological horror")
scores      <- c(4.5,4,5)
rev     <- data.frame(scores, sources, comments)
rm(scores, sources, comments)
```

*** =sample_code
```{r}
# The variables mov, act and rev are available

# Finish the code to build shining_`list`
shining_`list` <- `list`(moviename = mov)
```

*** =solution
```{r}
# The variables mov, act and rev are available

# Finish the code to build shining_`list`
shining_`list` <- `list`(moviename = mov, actors = act, reviews = rev)
```

*** =sct
```{r}
msg = "Jangan menghapus atau mengganti definisi variabel yang telah ditentukan sebelumnya!"
lapply(c("mov", "rev", "act"), test_object, undefined_msg = msg, incorrect_msg = msg)
test_object("shining_`list`",
            incorrect_msg = "Sepertinya `shining_`list`` tidak berisi elemen yang benar. Elemen pertama yaitu `mov`, kedua adalah `act`, dan ketiga yaitu `rev`.")
test_object("shining_`list`", eq_condition = "equal",
            incorrect_msg = "Sepertinya `shining_`list`` tidak berisi penamaan komponen yang benar. Namai elemen pertama `moviename`, elemen kedua `actors`, dan elemen ketiga `reviews`.");
success_msg("Hebat! Anda kini sudah tahu cara membangun dan menamai sebuah `list`. Sama seperti pada bab-bab sebelumnya, kita akan mencari tahu cara memilih elemen dari suatu `list`. Pergilah ke latihan berikutnya")
```


--- type:NormalExercise xp:100 skills:1 key:1ef3278944562caef64b9927dd2ddb6ee52334cd
## Memilih elemen dari `list`

Sebuah `list` biasanya dibangun dari banyak elemen dan komponen. Oleh sebab itu, memperoleh satu elemen, banyak elemen, atau satu komponen dari sebuah `list` tidak selalu mudah.

Salah satu cara untuk memilih sebuah komponen adalah menggunakan posisi bernomor komponen tersebut. Sebagai contoh, untuk "meraih" komponen pertama dari `shining_`list``, tuliskan:

```
shining_`list`[[1]]
```

Cara cepat untuk memeriksa kode ini adalah dengan mengetiknya di konsol. Penting untuk diingat bahwa untuk memilih elemen suatu vektor, gunakan kurung siku tunggal: `[ ]`. Jangan sampai terbalik, ya!

Anda juga bisa mengacu ke nama-nama komponen menggunakan `[[ ]]` atau tanda `$`. Keduanya sama-sama memilih frame data yang mewakili ulasan:

```
shining_`list`[["reviews"]]
shining_`list`$reviews
``` 

Selain memilih komponen, Anda biasanya harus memilih elemen tertentu dari komponen-komponen ini. Sebagai contoh, `shining_`list`[[2]][1]` artinya memilih dari komponen kedua, `actors` (`shining_`list`[[2]]`), elemen pertama (`[1]`). Saat Anda mengetik ini di konsol, jawaban Jack Nicholson akan muncul.

*** =instructions
- Pilih dari `shining_`list`` vektor yang mewakili para aktor. Cetak vektor ini.
- Pilih dari `shining_`list`` elemen kedua di dalam vektor yang mewakili para aktor. Cetak seperti sebelumnya.

*** =hint
- Anda dapat menggunakan `$actors` untuk memilih vektor yang mewakili para aktor.
- Anda menggunakan `shining_`list`$actors[3]` untuk memilih elemen ketiga dalam vektor yang mewakili para aktor. Apa yang harus diganti untuk memilih elemen kedua?

*** =pre_exercise_code
```{r}
load(url("http://s3.amazonaws.com/assets.datacamp.com/course/intro_to_r/shining_`list`.RData"))
```

*** =sample_code
```{r}
# shining_`list` is already pre-loaded in the workspace

# Print out the vector representing the actors


# Print the second element of the vector representing the actors

```

*** =solution
```{r}
# shining_`list` is already pre-loaded in the workspace

# Print out the vector representing the actors
shining_`list`$actors

# Print the second element of the vector representing the actors
shining_`list`$actors[2]
```

*** =sct
```{r}
msg <- "Jangan menghapus atau mengganti definisi `shining_`list`` yang sudah dimuat di ruang kerja!"
test_object("shining_`list`", undefined_msg = msg, incorrect_msg = msg)
test_output_contains("shining_`list`$actors", incorrect_msg = "Sudahkah Anda memilih dan mencetak vektor dengan benar yang mewakili para aktor? Anda bisa menggunakan `shining_`list`$actors`, misalnya.")
test_output_contains("shining_`list`$actors[2]", incorrect_msg = "Untuk memilih aktor kedua dari vektor yang mewakili para aktor, rangkai seleksi Anda: `shining_`list`$actors` mewakili para aktor sehingga Anda dapat menambahkan `[2]`untuk memilih elemen kedua.")
success_msg("Hebat! Memilih elemen dari `list` kelihatannya agak mudah, kan? Lanjutkan ke latihan berikutnya.")
```


--- type:NormalExercise xp:100 skills:1 key:ca3f7b71504ff93940cf65889d406a58c5b0019c
## Menambahkan lebih banyak informasi film ke `list`

`list` perdana ini sudah Anda serahkan kepada para anggota klub hobi film Anda. Namun, salah seorang anggota senior klub itu mengatakan bahwa Anda lupa menambahkan informasi tahun rilis film. Karena Anda ingin sekali menjadi presiden klub tahun depan, Anda memutuskan untuk menambahkan informasi ini ke dalam `list`.

Untuk menambahkan elemen ke suatu `list` secara mudah, gunakan fungsi [`c()`](http://www.rdocumentation.org/packages/base/functions/c) yang juga telah Anda gunakan untuk membangun vektor:

```
ext_`list` <- c(my_list , my_val)
``` 

Ini akan memperpanjang `list` mula-mula, `my_list`, dengan komponen `my_val`. Komponen baru ini ditambahkan ke ujung `list`.
Jika Anda ingin menamai item baru tersebut pada `list`, cukup tambahkan nama seperti sebelumnya:

```
ext_`list` <- c(my_`list`, my_name = my_val)
```

*** =instructions
- Lengkapi kode di bawah ini sehingga sebuah item bernama `year` ditambahkan ke `shining_`list`` dengan nilai 1980. Tetapkan hasilnya pada `shining_`list`_full`.
- Terakhir, lihat struktur `shining_list_full` dengan fungsi [`str()`](http://www.rdocumentation.org/packages/utils/functions/str).

*** =hint
Lihat contoh kode dalam tugas latihan. Kode berikut mungkin bisa memudahkan Anda:
```
shining_`list` <- c(shining_`list`, ...)
```
Anda masih harus melengkapi titik-titik pada kode di atas.

*** =pre_exercise_code
```{r, eval = FALSE}
load(url("http://s3.amazonaws.com/assets.datacamp.com/course/intro_to_r/shining_`list`.RData"))
```

*** =sample_code

```{r}
# shining_`list`, the `list` containing movie name, actors and reviews, is pre-loaded in the workspace

# We forgot something; add the year to shining_`list`
shining_`list`_full <- 

# Have a look at shining_`list`_full

```

*** =solution

```{r}
# shining_`list`, the `list` containing movie name, actors and reviews, is pre-loaded in the workspace

# Use c() to add a year to shining_`list`
shining_`list`_full <- c(shining_`list`, year = 1980)

# Have a look at shining_`list`_full
str(shining_`list`_full)
```

*** =sct
```{r}
msg = "Jangan menghapus atau mengganti definisi `shining_`list`` yang sudah dimuat di ruang kerja!"
test_object("shining_`list`", undefined_msg = msg, incorrect_msg = msg)
test_object("shining_`list`_full", eq_condition = "equal",
            incorrect_msg = paste("Sudahkah Anda memperpanjang 'shining_`list`` dengan elemen bernama `year`",
                                   "yang nilainya 1980? Anda bisa menggunakan `c(shining_`list`, year = 1980)`"))
test_function("str", "object", incorrect_msg = "Jangan lupa untuk menampilkan struktur `shining_`list`_full` dengan `str()`.")
success_msg("Luar biasa! Inilah latihan terakhir Anda pada `list`! Sekarang Anda sudah memiliki fondasi dalam bahasa pemrograman R. Masih ada banyak hal yang harus dipelajari. Lihat semua kursus lain di DataCamp dan jadilah pakar sains data sejati!")
```


