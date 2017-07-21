--- 
title_meta  : Bab 5
title       : Frame data
description : Sebagian besar set data yang Anda tangani akan disimpan sebagai frame data. Pada akhir bab ini yang berfokus pada dasar-dasar R, Anda akan bisa membuat frame data, memilih bagian yang menarik dari frame data, dan mengurutkan frame data menurut variabel tertentu.

--- type:NormalExercise xp:100 skills:1 key:7f95849020a2563168920409022ce7bed20835b5
## Apa itu frame data?

Ingatkah Anda tentang bab matriks yang menyatakan bahwa semua elemen yang dimasukkan ke dalam matriks jenisnya harus sama? Set data Star Wars saat itu hanya berisi elemen numerik.

Saat Anda menjalankan survei riset pasar, muncul banyak pertanyaan, seperti:

- 'Apakah Anda menikah?' atau pertanyaan 'ya/tidak' (`logis`)
- 'Berapa usia Anda?' (`numerik`)
- 'Apa pendapat Anda tentang produk ini?' Atau pertanyaan 'terbuka' lainnya (`karakter`)
- dan lain-lain

Jawaban responden terhadap pertanyaan di atas merupakan set data yang terdiri dari banyak tipe data. Anda akan sering bekerja dengan set data yang berisi berbagai tipe data alih-alih hanya satu.

Frame data memiliki variabel set data sebagai kolom dan observasi sebagai baris. Ini akan menjadi konsep yang akrab bagi Anda sudah terbiasa memakai aplikasi statistik, seperti SAS atau SPSS.

*** =instructions
Klik 'Kirim Jawaban'. Data contoh frame data [`mtcars`] (http://www.rdocumentation.org/packages/datasets/functions/mtcars) akan dicetak ke konsol.

*** =hint
Cukup klik 'Kirim Jawaban' dan lihat keajaiban yang terjadi!

*** =pre_exercise_code
```{r}
# no pec
```

*** =sample_code
```{r}
# Print out built-in R data frame
mtcars 
```

*** =solution
```{r}
# Print out built-in R data frame
mtcars 
```

*** =sct
```{r}
test_output_contains("mtcars", incorrect_msg = "Jangan ganti apa pun pada kode ini. Pastikan hasilnya `mtcars`.")
success_msg("Bagus! Lanjutkan ke latihan berikutnya..")
```


--- type:NormalExercise xp:100 skills:1 key:3d0e64ecf5f69521ee538ecc713caa02b8b0ec46
## Cepat, lihat set data Anda

Wow, banyak sekali mobilnya!

Bekerja dengan set data yang besar lazim terjadi di dalam analisis data. Jika Anda bekerja dengan set data dan frame data yang ukurannya (sangat) besar, tugas pertama Anda sebagai analis data adalah mengembangkan pemahaman yang jelas akan struktur dan elemen utamanya. Oleh sebab itu, menampilkan sebagian kecil dari seluruh set data saja sudah bermanfaat.

Jadi, bagaimana cara melakukan ini di R? Fungsi [`head()`](http://www.rdocumentation.org/packages/utils/functions/head) bermanfaat untuk menunjukkan observasi pertama suatu frame data. Demikian pula, fungsi [`tail()`](http://www.rdocumentation.org/packages/utils/functions/head) akan mencetak observasi terakhir set data Anda.

Baik [`head()`](http://www.rdocumentation.org/packages/utils/functions/head) dan [`tail()`](http://www.rdocumentation.org/packages/utils/functions/head) mencetak sebuah baris paling atas, disebut 'header'. Baris ini berisi nama-nama variabel berbeda dalam set data.

*** =instructions
Panggil [`head()`](http://www.rdocumentation.org/packages/utils/functions/head) pada set data [`mtcars`](http://www.rdocumentation.org/packages/datasets/functions/mtcars) untuk melihat header dan observasi pertama.

*** =hint
`head(mtcars)` akan menunjukkan observasi pertama frame data `mtcars`.

*** =pre_exercise_code
```{r}
# no pec
```

*** =sample_code
```{r}
# Call head() on mtcars

```

*** =solution
```{r}
# Call head() on mtcars
head(mtcars)
```

*** =sct
```{r}
test_function("head", "x", incorrect_msg = "Sudahkah Anda memasukkan `mtcars` dengan benar ke dalam fungsi `head()`?")
test_output_contains("head(mtcars)", incorrect_msg = "Cukup cetak hasil dari pemanggilan `head()`. Anda tidak perlu menetapkannya pada variabel baru.")
success_msg("Hebat! Jadi, apa yang Anda miliki pada set data ini? Sebagai contoh, `hp` mewakili tenaga kuda mobil; Datsun memiliki daya kuda terendah dari 6 jenis mobil yang ada. Untuk melihat gambaran lengkap mengenai arti setiap variabel, tulis `?mtcars` di konsol dan baca halaman bantuan yang muncul. Lanjutkan ke latihan berikutnya!");
```


--- type:NormalExercise xp:100 skills:1 key:f4d5b1a2c4aef31645fc7e3505e699fb6e48f3e6
## Melihat struktur data

Metode lain yang sering dipakai untuk memperoleh gambaran kilat suatu data adalah fungsi [`str()`](http://www.rdocumentation.org/packages/utils/functions/str). Fungsi [`str()`](http://www.rdocumentation.org/packages/utils/functions/str) menunjukkan struktur set data. Informasi yang diberikan oleh frame data yaitu:

- Total observasi (mis. 32 jenis mobil)
- Total variabel (mis. 11 fitur mobil)
- Daftar lengkap nama variabel (mis. `mpg`,` cyl`, dsb.)
- Tipe data setiap variabel (mis. `num`)
- Observasi pertama

Menerapkan fungsi [`str()`](http://www.rdocumentation.org/packages/utils/functions/str) umumnya menjadi hal pertama yang Anda lakukan saat menerima set data atau frame data baru. Ini cara yang baik untuk memperoleh lebih banyak wawasan set data sebelum terjun ke analisis sebenarnya.

*** =instructions
Selidiki struktur [`mtcars`](http://www.rdocumentation.org/packages/datasets/functions/mtcars). Pastikan Anda melihat angka, variabel, dan tipe data sama seperti yang disebutkan di atas.

*** =hint
Gunakan fungsi [`str()`](http://www.rdocumentation.org/packages/utils/functions/str) pada [`mtcars`](http://www.rdocumentation.org/packages/datasets/functions/mtcars).

*** =pre_exercise_code
```{r}
# no pec
```

*** =sample_code
```{r}
# Investigate the structure of mtcars
```

*** =solution
```{r}
# Investigate the structure of mtcars
str(mtcars)
```

*** =sct
```{r}
test_output_contains("str(mtcars)", incorrect_msg = "Sudahkah Anda memanggil `str()` pada `mtcars` dengan benar?")
success_msg("Bagus! Bisakah Anda menemukan semua informasi yang tercantum pada tugas latihan? Lanjutkan ke latihan berikutnya.")
```


--- type:NormalExercise xp:100 skills:1 key:df0b89706d90526b3c0bbe15e400b74cbd900704
## Membuat frame data

Memakai set data bawaan tidaklah seseru membuat set data sendiri. Itu sebabnya, pada bagian ini Anda akan mengembangkan set data secara pribadi. Siapkan jet pack Anda karena ini waktunya menjelajah ruang angkasa!

Sebagai tujuan pertama, Anda akan membuat frame data yang menggambarkan karakteristik utama delapan planet pada tata surya. Menurut sahabat Anda, Buzz, sifat-sifat utama sebuah planet adalah:

- Jenisnya (Terestrial atau Raksasa Gas).
- Diameternya relatif terhadap diameter Bumi.
- Rotasinya terhadap matahari relatif terhadap Bumi.
- Apakah planet tersebut memiliki cincin atau tidak (TRUE atau FALSE).

Setelah melakukan riset berkualitas tinggi di [Wikipedia](http://en.wikipedia.org/wiki/Planet), Anda cukup percaya diri untuk membuat semua vektor yang diperlukan: nama (name), tipe (type), diameter, rotasi (rotation), dan cincin (rings); Semua vektor ini telah dikodekan di sebelah kanan. Elemen pertama masing-masing vektor ini sesuai dengan observasi pertama.

Anda membuat frame data dengan fungsi [`data.frame()`](http://www.rdocumentation.org/packages/base/functions/data.frame). Sebagai argumen, Anda memasukkan vektor-vektor dari sebelumnya; semua vektor akan menjadi kolom-kolom frame data. Karena setiap kolom memiliki panjang serupa, panjang vektor yang dimasukkan juga harus sama. Namun, jangan lupa bahwa beberapa vektor (kemungkinan) memiliki berbagai jenis data.

*** =instructions
Gunakan fungsi [`data.frame()`](http://www.rdocumentation.org/packages/base/functions/data.frame) untuk membuat frame data. Masukkan vektor `name`,` type`, `diameter`,` rotation`, dan `rings` sebagai argumen ke dalam `data.frame()`, secara berurutan. Panggil frame data yang dihasilkan ini sebagai `planets_df`.

*** =hint
Pemanggilan `data.frame()` dimulai sebagai berikut:
```
data.frame(planets, type, diameter)
```
Bisakah Anda menyelesaikannya?

*** =pre_exercise_code
```{r}
# no pec
```

*** =sample_code
```{r}
# Definition of vectors
name <- c("Mercury", "Venus", "Earth", "Mars", "Jupiter", "Saturn", "Uranus", "Neptune")
type <- c("Terrestrial planet", "Terrestrial planet", "Terrestrial planet", 
          "Terrestrial planet", "Gas giant", "Gas giant", "Gas giant", "Gas giant")
diameter <- c(0.382, 0.949, 1, 0.532, 11.209, 9.449, 4.007, 3.883)
rotation <- c(58.64, -243.02, 1, 1.03, 0.41, 0.43, -0.72, 0.67)
rings <- c(FALSE, FALSE, FALSE, FALSE, TRUE, TRUE, TRUE, TRUE)

# Create a data frame from the vectors
planets_df <-

```

*** =solution
```{r}
# Definition of vectors
name <- c("Mercury", "Venus", "Earth", "Mars", "Jupiter", "Saturn", "Uranus", "Neptune")
type <- c("Terrestrial planet", "Terrestrial planet", "Terrestrial planet", 
          "Terrestrial planet", "Gas giant", "Gas giant", "Gas giant", "Gas giant")
diameter <- c(0.382, 0.949, 1, 0.532, 11.209, 9.449, 4.007, 3.883)
rotation <- c(58.64, -243.02, 1, 1.03, 0.41, 0.43, -0.72, 0.67)
rings <- c(FALSE, FALSE, FALSE, FALSE, TRUE, TRUE, TRUE, TRUE)

# Create a data frame from the vectors
planets_df <- data.frame(name, type, diameter, rotation, rings)
```

*** =sct
```{r}
msg = "Jangan mengganti apa pun tentang definisi vektor. Cukup panggil `data.frame()` untuk membuat `planets_df`."
test_object("name", undefined_msg = msg, incorrect_msg = msg)
test_object("type", undefined_msg = msg, incorrect_msg = msg)
test_object("diameter", undefined_msg = msg, incorrect_msg = msg)
test_object("rotation", undefined_msg = msg, incorrect_msg = msg)
test_object("rings", undefined_msg = msg, incorrect_msg = msg)

test_object("planets_df",
            incorrect_msg = "Sudahkah `data.frame()` untuk membuat `planets_df` dipanggil dengan benar? Di dalam `data.frame()`, pastikan semua vektor dimasukkan sesuai urutan: `name`, `type`, `diameter`, `rotation`, `rings`.")

success_msg("Bagus! Seperti yang Anda ketahui, langkah logis selanjutnya yaitu memeriksa frame data yang baru saja dibuat. Lanjutkan ke latihan berikutnya.");
```


--- type:NormalExercise xp:100 skills:1 key:c13ea421dd078030a225f49e53a8927ce8fefbe0
## Membuat frame data (2)

Basis data `planets_df` harus memiliki 8 observasi dan 5 variabel. Semua ini sudah tersedia di ruang kerja sehingga Anda bisa langsung memakainya.

*** =instructions
Gunakan [`str()`](http://www.rdocumentation.org/packages/utils/functions/str) untuk melihat struktur variabel `planets_df` yang baru.

*** =hint
`planets_df` sudah tersedia di ruang kerja. Perintah `str(planets_df)` saja sudah cukup.

*** =pre_exercise_code
```{r}
load(url("http://s3.amazonaws.com/assets.datacamp.com/course/intro_to_r/planets.RData"))
```

*** =sample_code
```{r}
# Check the structure of planets_df
```

*** =solution
```{r}
# Check the structure of planets_df
str(planets_df)
```

*** =sct
```{r}
msg = "Jangan menghapus atau menimpa frame data `planets_df` yang ada di ruang kerja!"
test_object("planets_df", undefined_msg = msg, incorrect_msg = msg)
test_output_contains("str(planets_df)", incorrect_msg = "Sudahkah Anda menampilkan struktur 'planets_df` dengan benar? Gunakan `str()` untuk melakukannya!")
success_msg("Luar biasa! Setelah Anda memahami dengan benar set data 'planets_df`, kini saatnya mengetahui cara memilih elemen tertentu. Pelajari semuanya di latihan berikutnya!")
```


--- type:NormalExercise xp:100 skills:1 key:8c664726b8a173cda730cbb20a52ac1795d9a0e9
## Seleksi elemen frame data

Mirip dengan vektor dan matriks, Anda memilih elemen tertentu dari suatu frame data dengan bantuan kurung siku `[]`. Dengan koma, Anda bisa menunjukkan yang harus dipilih dari setiap baris dan kolom. Sebagai contoh:

- `my_df[1,2]` memilih nilai pada baris pertama dan memilih elemen di `my_df`.
- `my_df[1:3,2:4]` memilih baris 1, 2, 3 dan kolom 2, 3, 4 di `my_df`.

Adakalanya Anda ingin memilih semua elemen dari sebuah baris atau kolom. Sebagai contoh, `my_df[1, ]` memilih seluruh elemen pada baris pertama. Ayo gunakan teknik ini pada `planets_df`!

*** =instructions
- Dari `planets_df`, pilih diameter Merkurius. Ini adalah nilai pada baris pertama dan kolom ketiga. Cukup cetak hasilnya.
- Dari `planets_df`, pilih semua data di Mars (baris keempat). Cukup cetak hasilnya.

*** =hint
Cara untuk memilih diameter Venus (baris kedua) adalah: `planets_df[2,3]`. Bagaimana cara memilih diameter Merkurius?

*** =pre_exercise_code
```{r}
load(url("http://s3.amazonaws.com/assets.datacamp.com/course/intro_to_r/planets.RData"))
```

*** =sample_code
```{r}
# The planets_df data frame from the previous exercise is pre-loaded

# Print out diameter of Mercury (row 1, column 3)


# Print out data for Mars (entire fourth row)

```

*** =solution
```{r}
# The planets_df data frame from the previous exercise is pre-loaded

# Print out diameter of Mercury (row 1, column 3)
planets_df[1,3]

# Print out data for Mars (entire fourth row)
planets_df[4, ]
```

*** =sct
```{r}
msg = "Jangan menghapus atau menimpa frame data `planets_df`!"
test_object("planets_df", undefined_msg = msg, incorrect_msg = msg)
test_output_contains("planets_df[1,3]", incorrect_msg = "Sudahkah Anda memilih dan mencetak diameter Merkurius dengan benar? Anda bisa memakai `[1,3]`.")
test_output_contains("planets_df[4, ]", incorrect_msg = "Sudahkah Anda memilih dan mencetak seluruh data Mars dengan benar? Anda bisa memakai `[4,]`.")
success_msg("Hebat! Selain memakai indeks, Anda juga bisa memakai nama kolom untuk memilih elemen frame data. Lanjutkan ke latihan berikutnya untuk mengetahui caranya, .")
```


--- type:NormalExercise xp:100 skills:1 key:faf104fb0c605fd89f048648a4a588200bc89c76
## Seleksi elemen frame data (2)

Alih-alih memakai numerik untuk memilih elemen frame data, Anda bisa memakai nama variabel untuk memilih kolom suatu frame data.

Anggaplah Anda ingin memilih tiga elemen pertama dari kolom `type`. Salah satu cara untuk melakukannya yaitu:

```
planets_df[1:3,1]
```

Kekurangan pendekatan ini yaitu Anda harus mengetahui (atau mencari) jumlah kolom `type`, yang bisa menyulitkan jika jumlah variabel yang ada cukup banyak. Akan lebih mudah jika Anda memakai nama variabel:

```
planets_df[1:3,"type"]
```

*** =instructions
Pilih dan cetak 5 nilai pertama kolom `"diameter"` dari `planets_df`.

*** =hint
Lima nilai pertama bisa dipilih dengan cara `planets_df[1:5, ...]`. Bisakah Anda mengganti `...` supaya hanya memilih kolom `"diameter"`?

*** =pre_exercise_code
```{r}
load(url("http://s3.amazonaws.com/assets.datacamp.com/course/intro_to_r/planets.RData"))
```

*** =sample_code
```{r}
# The planets_df data frame from the previous exercise is pre-loaded

# Select first 5 values of diameter column

```

*** =solution
```{r}
# The planets_df data frame from the previous exercise is pre-loaded

# Select first 5 values of diameter column
planets_df[1:5, "diameter"]
```

*** =sct
```{r}
msg = "Jangan menghapus atau menimpa frame data `planets_df`!"
test_object("planets_df", undefined_msg = msg, incorrect_msg = msg)
test_output_contains("planets_df[1:5, \"diameter\"]", incorrect_msg = "Sudahkah Anda memilih lima nilai pertama kolom diameter lalu mencetaknya? Anda bisa menggunakan `[1:5, \"diameter\"]`.")
success_msg("Bagus! Lanjutkan ke latihan berikutnya!")
```


--- type:NormalExercise xp:100 skills:1 key:e550ecb6ec45b856e6160ddfbb3d7875998e8365
## Hanya planet yang memiliki cincin

Anda akan sering memilih keseluruhan kolom, yaitu satu variabel tertentu dari suatu frame data. Jika Anda ingin memilih seluruh elemen dari variabel `diameter` misalnya, kedua perintah ini sama-sama bisa dipakai:

```
planets_df[,3]
planets_df[,"diameter"]
```

Namun, ada jalan pintas. Jika kolom Anda memiliki nama, Anda bisa memakai tanda `$`:

```
planets_df$diameter
```

*** =instructions
- Gunakan tanda `$` untuk memilih variabel `rings` dari` planets_df`. Simpan vektor yang dihasilkan sebagai `rings_vector`.
- Cetak `rings_vector` untuk melihat apakah cara Anda sudah benar.

*** =hint
`planets_df$diameter` dipakai untuk memilih kolom `diameter` dari `planets_df`; Bagaimana jika ingin memilih kolom `rings`?

*** =pre_exercise_code
```{r}
load(url("http://s3.amazonaws.com/assets.datacamp.com/course/intro_to_r/planets.RData"))
```

*** =sample_code
```{r}
# planets_df is pre-loaded in your workspace

# Select the rings variable from planets_df
rings_vector <- 
  
# Print out rings_vector
```

*** =solution
```{r}
# planets_df is pre-loaded in your workspace

# Select the rings variable from planets_df
rings_vector <- planets_df$rings

# Print out rings_vector
rings_vector
```

*** =sct
```{r}
msg = "Jangan menghapus atau menimpa frame data `planets_df`!"
test_object("planets_df", undefined_msg = msg, incorrect_msg = msg)
test_object("rings_vector",
            incorrect_msg = "Sudahkah Anda memilih variabel `rings` dari` planets_df`? Gunakan `$rings`. Simpan hasilnya sebagai `rings_vector`.")
test_output_contains("rings_vector", incorrect_msg = "Jangan lupa untuk mencetak `rings_vector` setelah dibuat!")
success_msg("Hebat! Lanjutkan ke latihan berikutnya dan temukan cara lain untuk menjabarkan data!")
```


--- type:NormalExercise xp:100 skills:1 key:1581bf4667477f274188f4f637ec7fdc73659651
## Hanya planet yang memiliki cincin (2)

Anda mungkin masih ingat pelajaran waktu SMA bahwa ada beberapa planet di tata surya yang memiliki cincin, dan ada yang tidak. Namun, saat itu Anda tidak terlalu memperhatikan sehingga tak lagi mengingat nama-nama planet ini, apalagi kecepatan rotasinya, dan lain-lain.

Bisakah R membantu Anda?

Jika Anda mengetikkan `rings_vector` di konsol, hasilnya adalah:

```
[1] FALSE FALSE FALSE FALSE  TRUE  TRUE  TRUE  TRUE
```

Artinya, empat observasi (atau planet) pertama tidak memiliki cincin (`FALSE`), sedangkan empat planet lainnya memiliki cincin (`TRUE`). Namun, Anda tidak mendapatkan gambaran yang baik tentang namanya, diameternya, dan sebagainya. Mari kita gunakan `rings_vector` untuk memilih data keempat planet dengan cincin.

*** =instructions
Kode di sebelah kanan memilih kolom `name` dari semua planet yang memiliki cincin. Sesuaikan kodenya sehingga yang terpilih bukan hanya kolom `name` melainkan _semua_ kolom untuk planet yang memiliki cincin.

*** =hint
Ingat, untuk memilih _semua_ kolom, cukup kosongkan kolom di dalam `[ ]`! Artinya, Anda hanya perlu `[rings_vector,]`.

*** =pre_exercise_code
```{r}
load(url("http://s3.amazonaws.com/assets.datacamp.com/course/intro_to_r/planets.RData"))
rings_vector <- planets_df$rings
```

*** =sample_code
```{r}
# planets_df and rings_vector are pre-loaded in your workspace

# Adapt the code to select all columns for planets with rings
planets_df[rings_vector, "name"]
```

*** =solution
```{r}
# planets_df and rings_vector are pre-loaded in your workspace

# Adapt the code to select all columns for planets with rings
planets_df[rings_vector, ]
```

*** =sct
```{r}
msg <- "Jangan menghapus atau menimpa `planets_df` atau`rings_vector`!"
test_object("planets_df", undefined_msg = msg, incorrect_msg = msg)
test_object("rings_vector", undefined_msg = msg, incorrect_msg = msg)
test_output_contains('planets_df[rings_vector, ]', incorrect_msg = "Sudahkah Anda menyesuaikan kode dengan benar untuk memilih _semua_ kolom untuk planet dengan cincin? Anda bisa memakai `planets_df[rings_vector, ]`. Jangan sampai lupa menambahkan koma!")
success_msg("Hebat! Mungkin solusi ini agak membosankan. Latihan berikutnya akan memberi tahu cara yang lebih ringkas.")
```


--- type:NormalExercise xp:100 skills:1 key:a4a8b72a74097196eb2f8a28b056987aae834565
## Hanya planet yang memiliki cincin tetapi lebih ringkas

Jadi, apa sebenarnya yang telah Anda pelajari pada latihan sebelumnya? Anda memilih subset dari frame data (`planets_df`) berdasarkan syarat tertentu, benar atau salah (cincin atau tanpa cincin), dan Anda berhasil menampilkan semua data yang relevan. Itu sudah cukup keren. NASA sekarang mungkin sudah melirik CV Anda ;-).

Sekarang, kita naik satu tingkat dan memakai fungsi [`subset()`](http://www.rdocumentation.org/packages/base/functions/subset). Anggap fungsi [`subset()`](http://www.rdocumentation.org/packages/base/functions/subset) sebagai jalan pintas untuk melakukan hal yang sama persis dengan yang Anda lakukan pada latihan sebelumnya.

```
subset(my_df, subset = some_condition)
``` 

Argumen pertama [`subset()`](http://www.rdocumentation.org/packages/base/functions/subset) menentukan set data yang Anda inginkan subsetnya. Dengan menambahkan argumen kedua, Anda memberi informasi dan kondisi yang diperlukan kepada R untuk memilih subset yang benar.

Kode berikut ini memberikan hasil yang sama persis dengan latihan sebelumnya. Bedanya, kali ini Anda tidak memerlukan `rings_vector`!

```
subset(planets_df, subset = rings)
``` 

*** =instructions
Gunakan `subset ()` pada `planets_df` untuk memilih planet-planet yang memiliki diameter lebih kecil daripada Bumi. Karena variabel `diameter` merupakan ukuran relatif diameternya yang mengacu pada planet Bumi, syarat Anda yaitu `diameter < 1`.

*** =hint
`subset(planets_df, subset = ...)` sedikit lagi selesai; Bisakah Anda melengkapi `...`?

*** =pre_exercise_code
```{r}
load(url("http://s3.amazonaws.com/assets.datacamp.com/course/intro_to_r/planets.RData"))
```

*** =sample_code
```{r}
# planets_df is pre-loaded in your workspace

# Select planets with diameter < 1

```

*** =solution
```{r}
# planets_df is pre-loaded in your workspace

# Select planets with diameter < 1
subset(planets_df, subset = diameter < 1)
```

*** =sct
```{r}
msg = "Jangan menghapus atau menimpa frame data `planets_df`!"
test_object("planets_df", undefined_msg = msg, incorrect_msg = msg)
test_correct({
  test_output_contains("subset(planets_df, subset = diameter < 1)", incorrect_msg = "Sudahkah Anda melengkapi `subset = ...` di dalam `subset()`? Syarat soal ini yaitu `diameter < 1`. Cukup cetak hasilnya.")  
}, {
  test_function("subset", args = "x", 
                not_called_msg = "Pastikan Anda memakai fungsi `subset()` untuk melakukan seleksi! ",
                 incorrect_msg = "Argumen pertama yang Anda masukkan ke `subset()` harus `planets_df`.")
})
success_msg("Hebat! Selain lebih ringkas, fungsi `subset ()` juga lebih mudah dipahami oleh orang yang membaca kode Anda. Lanjutkan ke latihan berikutnya.");
```


--- type:NormalExercise xp:100 skills:1 key:6a6fe74d3917c37380f7ac616ce084aa7814fb8a
## Menyortir data

Menciptakan peringkat adalah salah satu hal yang kita sukai. Ada banyak peringkat yang bermanfaat (seperti "10 universitas terbaik di dunia"), menghibur (mis. "7 aktor film paling berpengaruh"), atau sia-sia (cth. "5 selebritas paling mirip James Bond").

Dalam analisis data, Anda bisa menyortir data menurut variabel tertentu dalam suatu set data. Dalam R, fungsi [`order()`](http://www.rdocumentation.org/packages/base/functions/order) dipakai untuk menyortir data.   

[`order()`](http://www.rdocumentation.org/packages/base/functions/order) adalah fungsi yang memberi posisi peringkat tiap-tiap elemen saat diterapkan pada variabel, misalnya pada sebuah vektor:

```
> a <- c(100, 10, 1000)
> order(a)
[1] 2 1 3
```

Elemen kedua pada `a`, yaitu 10, merupakan elemen terkecil. Jadi, 2 tampil lebih dahulu pada hasil perintah `order (a)`. Elemen pertama pada `a`, yaitu 100, merupakan elemen terkecil kedua. Jadi, 1 berada di posisi kedua.

Artinya, Anda bisa menggunakan perintah `order(a)` untuk menyortir ulang `a`:
    
```
> a[order(a)]
[1]   10  100 1000
``` 

*** =instructions
Lakukan eksperimen fungsi [`order()`](http://www.rdocumentation.org/packages/base/functions/order) di konsol. Klik 'Kirim Jawaban' jika Anda siap melanjutkan.

*** =hint
Cukup utak-atik fungsi [`order()`](http://www.rdocumentation.org/packages/base/functions/order) di konsol!

*** =pre_exercise_code
```{r}
# no pec
```

*** =sample_code
```{r}
# Play around with the order function in the console
```

*** =solution
```{r}
# Play around with the order function in the console
```

*** =sct
```{r}
success_msg("Hebat! Sekarang gunakan fungsi `order()` untuk menyortir frame data Anda!")
```


--- type:NormalExercise xp:100 skills:1 key:fa88b58bf2cf62e0c181dfdcbdd2e1ddeac66807
## Menyortir frame data

Setelah Anda memahami fungsi [`order()`](http://www.rdocumentation.org/packages/base/functions/order), kita akan lakukan sesuatu yang bermanfaat. Anda akan mengatur ulang frame data Anda sehingga dimulai dari planet terkecil dan diakhir dengan planet terbesar. Sortirlah pada kolom `diameter`.

*** =instructions
- Panggil `order()` pada `planets_df$diameter` (kolom `diameter` pada `planets_df`). Simpan hasilnya sebagai `positions`.
- Sekarang, sortir ulang `planets_df` dengan vektor `positions` sebagai indeks baris di dalam kurung siku. Simpan seluruh kolom. Cetak hasilnya.

*** =hint
- Gunakan `order(planets_df$diameter)` untuk menciptakan `positions`.
- Kini Anda bisa memakai `positions` di dalam kurung siku: `planets_df[...]`; bisakah Anda melengkapi `...`?

*** =pre_exercise_code
```{r}
load(url("http://s3.amazonaws.com/assets.datacamp.com/course/intro_to_r/planets.RData"))
```

*** =sample_code
```{r}
# planets_df is pre-loaded in your workspace

# Use order() to create positions
positions <-  

# Use positions to sort planets_df

```

*** =solution
```{r}
# planets_df is pre-loaded in your workspace

# Use order() to create positions
positions <- order(planets_df$diameter)

# Use positions to sort planets_df
planets_df[positions, ]
```

*** =sct
```{r}
msg = "Jangan menghapus atau menimpa frame data `planets_df`!"
test_object("planets_df", undefined_msg = msg, incorrect_msg = msg)
test_object("positions",
            incorrect_msg = "Sudahkah Anda menghitung variabel `positions` dengan benar? Anda bisa menggunakan `order(planets_df$diameter)`.")
test_output_contains("planets_df[positions,]",
                     incorrect_msg = "Gunakan `planets_df[positions, ]` untuk menyortir `planets_df`; tanda koma di dalam kurung siku itu sangat penting!")
success_msg("Hebat! Latihan ini menyimpulkan bab mengenai frame data. Ingat, frame data sangat penting dalam R dan Anda akan sering membutuhkannya. Struktur data lain yang juga sangat sering dipakai yaitu daftar... dan ini akan menjadi pembahasan kita pada bab berikutnya!")
```


