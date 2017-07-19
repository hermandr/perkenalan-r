--- 
title_meta  : Bab 2
title       : Vektor
description : "Pada kursus R gratis ini, kita akan berjalan-jalan ke Vegas. Anda akan belajar cara menganalisis hasil taruhan menggunakan vektor di R! Setelah menyelesaikan bab ini, Anda bisa membuat vektor di R, menamai vektor, memilih elemen-elemen vektor, serta membandingkan beberapa vektor."

--- type:NormalExercise xp:100 skills:1 key:d9b453dbdd
## Membuat vektor

Apakah Anda merasa beruntung? Sebaiknya begitu... karena bab ini akan membawa Anda jalan-jalan ke Kota Dosa, yang juga dikenal sebagai *Surga Statistik*!

Berkat R dan kemampuan baru Anda dalam menganalisis data, Anda akan paham cara meningkatkan kinerja permainan dan melejitkan karier Anda sebagai penjudi pro. Bab ini akan menunjukkan cara untuk mudah melacak perkembangan taruhan dan cara melakukan sejumlah analisis sederhana mengenai tindakan masa lalu. Perhentian berikutnya, Vegas Baby... VEGAS!!

*** =instructions
- Masih ingat yang sudah Anda pelajari di bab pertama? Tetapkan nilai `"Go!"` pada variabel `vegas`. Ingat: R itu peka huruf!

*** =hint
Cukup tulis baris berikut di editor:
```
vegas <- "Go!"
```

*** =pre_exercise_code
```{r}
# no pec
```

*** =sample_code
```{r}
# Define the variable vegas
vegas <- 
```

*** =solution
```{r}
# Define the variable vegas
vegas <- "Go!"
```

*** =sct
```{r}
test_object("vegas", incorrect_msg = "Pastikan Anda menetapkan nilai yang benar pada `vegas`. Jangan lupa kalau R itu peka huruf!")
success_msg("Bagus! Lanjutkan ke latihan berikutnya.")
```


--- type:NormalExercise xp:100 skills:1 key:fd427db76f
## Membuat vektor (2)

Mari kita awali dengan fokus! 

Di perjalanan dari miskin menjadi kaya-raya ini, kita akan memanfaatkan vektor secara luas. Vektor adalah larik (array) satu dimensi yang bisa menyimpan data numerik, karakter, atau logis. Dengan kata lain, vektor adalah alat sederhana untuk menyimpan data. Sebagai contoh, Anda bisa menyimpan kemenangan dan kekalahan setiap hari Anda menggunakan larik.

Di R, Anda membuat vektor dengan fungsi gabungan [`c()`](http://www.rdocumentation.org/packages/base/functions/c). Elemen-elemen vektor dipisahkan oleh koma di dalam tanda kurung. Sebagai contoh:

```
numeric_vector <- c(1, 2, 3)
character_vector <- c("a", "b", "c")
```

Setelah vektor-vektor ini dibuat di R, Anda bisa memakainya untuk melakukan perhitungan.

*** =instructions 
Lengkapi kode ini sehingga `boolean_vector` berisi tiga macam elemen: `TRUE`, `FALSE`, dan `TRUE` (secara berurutan).

*** =hint 
Tetapkan `c(TRUE, FALSE, TRUE)` pada variabel `boolean_vector` dengan operator `<-`.

*** =pre_exercise_code
```{r}
# no pec
```

*** =sample_code
```{r}
numeric_vector <- c(1, 10, 49)
character_vector <- c("a", "b", "c")

# Complete the code for boolean_vector
boolean_vector <-
```

*** =solution
```{r}
numeric_vector <- c(1, 10, 49)
character_vector <- c("a", "b", "c")

# Complete the code for boolean_vector
boolean_vector <- c(TRUE, FALSE, TRUE)
```

*** =sct
```{r}
msg <- "Jangan ganti kode yang mendefinisikan `numeric_vector` dan `character_vector`!"
test_object("numeric_vector", undefined_msg = msg, incorrect_msg = msg)
test_object("character_vector", undefined_msg = msg, incorrect_msg = msg)
test_object("boolean_vector",
            incorrect_msg = "Pastikan Anda menetapkan nilai yang benar pada `boolean_vector`. Gunakan `c(TRUE, FALSE, TRUE)`. Jangan gunakan tanda kutip untuk mengapit `TRUE` dan` FALSE`! Pastikan juga Anda menggunakan urutan yang sama seperti instruksi.")
success_msg("Sempurna! Perhatikan bahwa penambahan spasi di belakang koma dalam fungsi `c()` memudahkan kode Anda dibaca. Ayo latihan lagi dengan membuat vektor berikutnya.")
```


--- type:NormalExercise xp:100 skills:1 key:9f41229dbc
## Membuat vektor (3)

Anda sudah satu pekan berada di Las Vegas tetapi belum ada satu pun mobil Ferrari yang Anda peroleh. Anda memutuskan untuk mulai menggunakan kekuatan super analisis data.

Sebelum melakukan analisis pertama, kumpulkan semua kemenangan dan kekalahan pekan lalu:

Untuk `poker_vector`:

- Pada hari Senin, Anda menang $140
- Selasa Anda kalah $50
- Rabu Anda menang $20
- Kamis Anda kalah $120
- Jumat Anda menang $240

Untuk `roulette_vector`:

- Pada hari Senin, Anda kalah $24
- Selasa Anda kalah $50
- Rabu Anda menang $100
- Kamis Anda kalah $350
- Jumat Anda menang $10

Anda hanya bermain poker dan rolet karena ada wakil perantara di meja taruhan. Agar bisa menggunakan data ini di R, Anda memutuskan untuk membuat variabel `poker_vector` dan `roulette_vector`.

*** =instructions
Tetapkan kemenangan dan kekalahan rolet ke variabel `roulette_vector`.

*** =hint
Untuk memudahkan Anda pada langkah ini, editor sudah berisi kode untuk membuat `poker_vector`. Tetapkan nilai yang benar pada `roulette_vector` berdasarkan angka-angka dalam tugas. Ingat: kekalahan adalah angka negatif.

*** =sample_code
```{r}
# Poker winnings from Monday to Friday
poker_vector <- c(140, -50, 20, -120, 240)

# Roulette winnings from Monday to Friday
roulette_vector <-  
```

*** =solution
```{r}
# Poker winnings from Monday to Friday
poker_vector <- c(140, -50, 20, -120, 240)

# Roulette winnings from Monday to Friday
roulette_vector <- c(-24, -50, 100, -350, 10)
```

*** =sct
```{r}
test_object("poker_vector",
            incorrect_msg = "Pastikan Anda menetapkan nilai yang benar pada `poker_vector`.")
test_object("roulette_vector",
            incorrect_msg = "Pastikan Anda menetapkan nilai yang benar pada`roulette_vector`. Pastikan urutannya sudah benar!")
success_msg("Bagus sekali! Untuk memeriksa konten vektor, Anda dapat mengetikkan variabel itu di konsol lalu tekan Enter. Lanjutkan ke latihan berikutnya!")
```


--- type:NormalExercise xp:100 skills:1 key:3b0b80b192
## Memberi nama vektor

Sebagai analis data, Anda harus memiliki pandangan yang jelas tentang data yang sedang Anda gunakan. Penting bagi Anda untuk memahami apa yang diacu oleh setiap elemen.

Dalam latihan sebelumnya, Anda telah membuat vektor untuk menyimpan data kemenangan selama sepekan. Setiap elemen vektor mengacu pada hari dalam sepekan, tetapi sulit untuk mengetahui elemen mana untuk hari apa. Alangkah baiknya jika Anda bisa menunjukkan hal itu di dalam vektor itu sendiri.

Anda bisa menamai elemen-elemen vektor dengan fungsi `names ()`. Lihat contoh berikut ini:

```
some_vector <- c("John Doe", "poker player")
names(some_vector) <- c("Name", "Profession")
```

Kode di atas pertama-tama membuat vektor `some_vector`. Lalu, kedua elemen di dalamnya diberi nama. Elemen pertama diberi nama `Name`, elemen kedua diberi nama` Profession`. Jika konten dicetak ke konsol, hasilnya sebagai berikut:

```
          Name     Profession 
    "John Doe" "poker player" 
```

*** =instructions
- Kode di kanan adalah untuk menamai elemen-elemen `poker_vector` dengan nama-nama hari dalam sepekan. Tambahkan kode untuk melakukan hal serupa untuk `roulette_vector`.

*** =hint
Anda bisa memakai `names(roulette_vector)` untuk menamai variabel `roulette_vector`. Pastikan pada vektor yang sama Anda menggunakan nama hari-hari dalam sepekan sebagai nama. Ingat: R itu peka huruf!

*** =sample_code
```{r}
# Poker winnings from Monday to Friday
poker_vector <- c(140, -50, 20, -120, 240)

# Roulette winnings from Monday to Friday
roulette_vector <- c(-24, -50, 100, -350, 10)

# Assign days as names of poker_vector
names(poker_vector) <- c("Monday", "Tuesday", "Wednesday", "Thursday", "Friday")

# Assign days as names of roulette_vectors
```

*** =solution
```{r}
# Poker winnings from Monday to Friday
poker_vector <- c(140, -50, 20, -120, 240)

# Roulette winnings from Monday to Friday
roulette_vector <- c(-24, -50, 100, -350, 10)

# Assign days as names of poker_vector
names(poker_vector) <- c("Monday", "Tuesday", "Wednesday", "Thursday", "Friday")

# Assign days as names of roulette_vectors
names(roulette_vector) <- c("Monday", "Tuesday", "Wednesday", "Thursday", "Friday")
```

*** =sct
```{r}
test_object("poker_vector",
            incorrect_msg = "Jangan ganti nilai-nilai di dalam `poker_vector` karena sudah dikodekan untuk Anda.")
test_object("roulette_vector",
            incorrect_msg = "Jangan ganti nilai-nilai di dalam `roulette_vector` karena sudah dikodekan untuk Anda.")
test_object("poker_vector",
            eq_condition = "equal",
            incorrect_msg = "Jangan ganti kode yang menamai elemennya pada `poker_vector`; fokuskan pada `roulette_vector`!")
test_object("roulette_vector",
            eq_condition = "equal",
            incorrect_msg = "Pastikan Anda menetapkan nama vektor yang benar pada `roulette_vector`. Gunakan vektor yang sama persis dengan yang digunakan untuk menamai `poker_vector`.")
success_msg("Selamat! Lanjutkan ke latihan berikutnya.")
```


--- type:NormalExercise xp:100 skills:1 key:6858c65a4a
## Memberi nama vektor (2)

Anda harus menjadi pemalas jika ingin menjadi ahli statistik yang baik (...jika Anda dari sananya sudah pemalas, mungkin Anda seorang ahli statistik natural dengan talenta yang luar biasa).

Dalam latihan sebelumnya, Anda mungkin merasa bosan dan frustrasi harus mengetik hari-hari dalam sepekan berulang-ulang. Namun, ada cara yang lebih efisien, yaitu dengan menetapkan vektor hari-hari dalam sepekan pada sebuah **variabel**!

Sama seperti yang Anda lakukan dengan pengembalian poker dan rolet, Anda juga bisa membuat variabel baru berisi hari-hari dalam sepekan. Dengan demikian, Anda bisa menggunakannya berulang-ulang.

*** =instructions
- Variabel `days_vector` berisi nama-nama hari dalam sepekan telah dibuat untuk Anda.
- Gunakan `days_vector` untuk menetapkan nama `poker_vector` dan `roulette_vector`.

*** =hint
Anda bisa menggunakan `names(poker_vector) <- days_vector` untuk menetapkan nama-nama elemen` poker_vector`. Lakukan hal yang sama untuk `roulette_vector`.

*** =pre_exercise_code
```{r}
# no pec
```

*** =sample_code
```{r}
# Poker winnings from Monday to Friday
poker_vector <- c(140, -50, 20, -120, 240)

# Roulette winnings from Monday to Friday
roulette_vector <- c(-24, -50, 100, -350, 10)

# The variable days_vector
days_vector <- c("Monday", "Tuesday", "Wednesday", "Thursday", "Friday")
 
# Assign the names of the day to roulette_vector and poker_vector
names(poker_vector) <-   
names(roulette_vector) <-
```

*** =solution
```{r}
# Poker winnings from Monday to Friday
poker_vector <- c(140, -50, 20, -120, 240)

# Roulette winnings from Monday to Friday
roulette_vector <- c(-24, -50, 100, -350, 10)

# The variable days_vector
days_vector <- c("Monday", "Tuesday", "Wednesday", "Thursday", "Friday")

# Assign the names of the day to roulette_vector and poker_vector
names(poker_vector) <- days_vector
names(roulette_vector) <- days_vector
```

*** =sct
```{r}
msg <- "Jangan ganti variabel yang telah ditentukan ini: `poker_vector`, `roulette_vector`, dan `days_vector`."
test_object("poker_vector", undefined_msg = msg, incorrect_msg = msg)
test_object("roulette_vector", undefined_msg = msg, incorrect_msg = msg)
test_object("days_vector", undefined_msg = msg, incorrect_msg = msg)

test_object("poker_vector",
            eq_condition = "equal",
            incorrect_msg = "Pastikan Anda menetapkan `days_vector` pada nama-nama `poker_vector`.")
test_object("roulette_vector",
            eq_condition = "equal",
            incorrect_msg = "Pastikan Anda menetapkan `days_vector` pada nama-nama `roulette_vector`.")
success_msg("Bagus sekali! Saran untuk Anda: cobalah menghindari duplikasi kode. Lanjutkan latihan berikutnya dan pelajari cara melakukan aritmetika dengan vektor!")
```


--- type:NormalExercise xp:100 skills:1 key:da995f099f
## Menghitung total kemenangan

Kemenangan poker dan rolet kini sudah disimpan sebagai vektor bernama. Anda bisa mulai melancarkan sihir analisis data.

Anda ingin mengetahui semua informasi berikut ini:

- Berapa banyak kemenangan atau kekalahan keseluruhan Anda per hari dalam sepekan?
- Adakah Anda kehilangan uang sepanjang pekan ini?
- Apakah Anda menang/kalah uang di poker ataukah di rolet?

Lakukan perhitungan aritmetika pada vektor untuk memperoleh jawabannya.

Penting untuk diketahui bahwa jika Anda menjumlahkan dua buah vektor di R, Anda harus mencocokkan elemen-elemennya. Sebagai contoh, tiga pernyataan berikut ini adalah ekivalen:

```
c(1, 2, 3) + c(4, 5, 6)
c(1 + 4, 2 + 5, 3 + 6)
c(5, 7, 9)
```

Anda juga bisa melakukan perhitungan dengan variabel-variabel yang mewakili vektor:

```
a <- c(1, 2, 3) 
b <- c(4, 5, 6)
c <- a + b
```

*** =instructions
- Jumlahkan variabel `A_vector` dan` B_vector`, lalu tetapkan pada `total_vector`.
- Periksa hasilnya dengan mencetak `total_vector`.

*** =hint
Gunakan operator `+` untuk menjumlahkan `A_vector` dan` B_vector`. Pakai `<-` untuk menetapkan hasilnya pada `total_vector`.

*** =pre_exercise_code
```{r}
# no pec
```

*** =sample_code
```{r}
A_vector <- c(1, 2, 3)
B_vector <- c(4, 5, 6)

# Take the sum of A_vector and B_vector
total_vector <- 
  
# Print out total_vector

```

*** =solution
```{r}
A_vector <- c(1, 2, 3)
B_vector <- c(4, 5, 6)

# Take the sum of A_vector and B_vector
total_vector <- A_vector + B_vector

# Print out total_vector
total_vector
```

*** =sct
```{r}
msg <- "Jangan ganti konten `A_vector` atau `B_vector`!"
test_object("A_vector", undefined_msg = msg, incorrect_msg = msg)
test_object("B_vector", undefined_msg = msg, incorrect_msg = msg)
test_object("total_vector", incorrect_msg = "Pastikan `total_vector` berisi hasil penjumlahan` A_vector` dan `B_vector`.")
test_output_contains("total_vector", incorrect_msg = "Jangan lupa untuk mencetak `total_vector`! Cukup tulis `total_vector` pada baris baru.")
success_msg("Bagus!  Lanjutkan ke latihan berikutnya.")
```


--- type:NormalExercise xp:100 skills:1 key:2969d8ed65
## Menghitung total kemenangan (2)

Sekarang Anda sudah paham cara R menjalankan aritmetika dengan vektor. Saatnya mendapatkan Ferrari baru! Pertama-tama, Anda harus memahami berapa kemenangan atau kekalahan keseluruhan Anda per hari dalam sepekan. Total profit harian adalah jumlah kemenangan/kekalahan poker per hari dan kemenangan/kekalahan pada rolet per hari.

Di R, total ini bisa diketahui dengan menjumlahkan `roulette_vector` dan` poker_vector`.

*** =instructions
Tetapkan total kemenangan atau kekalahan Anda setiap hari (gabungan antara poker dan rolet) pada variabel `total_daily`.

*** =hint
Sama seperti latihan sebelumnya, tetapkan hasil penjumlahan kedua vektor pada variabel baru: `total_daily`.

*** =pre_exercise_code
```{r}
# no pec
```

*** =sample_code
```{r}
# Poker and rolet winnings from Monday to Friday:
poker_vector <- c(140, -50, 20, -120, 240)
roulette_vector <- c(-24, -50, 100, -350, 10)
days_vector <- c("Monday", "Tuesday", "Wednesday", "Thursday", "Friday")
names(poker_vector) <- days_vector
names(roulette_vector) <- days_vector

# Assign to total_daily how much you won/lost on each day
total_daily <- 
```

*** =solution
```{r}
# Poker and rolet winnings from Monday to Friday:
poker_vector <- c(140, -50, 20, -120, 240)
roulette_vector <- c(-24, -50, 100, -350, 10)
days_vector <- c("Monday", "Tuesday", "Wednesday", "Thursday", "Friday")
names(poker_vector) <- days_vector
names(roulette_vector) <- days_vector

# Assign to total_daily how much you won/lost on each day
total_daily <- poker_vector + roulette_vector
```

*** =sct
```{r}
msg = "Jangan ganti apa pun tentang definisi dan penamaan `poker_vector` dan `roulette_vector`."
test_object("days_vector", undefined_msg = msg, incorrect_msg = msg)
test_object("poker_vector", eq_condition = "equal", undefined_msg = msg, incorrect_msg = msg)
test_object("roulette_vector", eq_condition = "equal", undefined_msg = msg, incorrect_msg = msg)

test_object("total_daily", incorrect_msg = "Pastikan Anda menetapkan hasil penjumlahan `poker_vector` dan` roulette_vector` pada `total_daily`.")

success_msg("Bagus! Lanjutkan ke latihan berikutnya.")
```


--- type:NormalExercise xp:100 skills:1 key:e66a56b9f0
## Menghitung total kemenangan (3)

Berdasarkan analisis sebelumnya, Anda sepertinya mengalami perpaduan hari baik dan jelek. Ini bukanlah yang Anda harapkan, dan Anda penasaran apakah ada sedikit risiko bagi Anda kehilangan uang di sepanjang pekan ini?

Fungsi yang akan menjawab pertanyaan ini adalah [`sum()`](http://www.rdocumentation.org/packages/base/functions/sum). Fungsi ini menghitung jumlah semua elemen vektor. Jadi, untuk menghitung total uang kalah/menang pada permainan poker:

`` `
Total_poker <- sum (poker_vector)
`` `

*** =instructions
- Hitung total uang menang/kalah pada permainan rolet, lalu tetapkan pada variabel `total_roulette`.
- Setelah total rolet dan poker diketahui, Anda bisa mudah menghitung `total_week` (yang merupakan hasil penjumlahan dari semua kemenangan dan kekalahan dalam pekan ini).
- Cetak `total_week`.

*** =hint
Gunakan fungsi [`sum()`](http://www.rdocumentation.org/packages/base/functions/sum) untuk mendapatkan total roulette_vector`. `total_week` adalah hasil penjumlahan dari `roulette_vector` dan` poker_vector`.

*** =pre_exercise_code
```{r}
# no pec
```

*** =sample_code
```{r}
# Poker and rolet winnings from Monday to Friday:
poker_vector <- c(140, -50, 20, -120, 240)
roulette_vector <- c(-24, -50, 100, -350, 10)
days_vector <- c("Monday", "Tuesday", "Wednesday", "Thursday", "Friday")
names(poker_vector) <- days_vector
names(roulette_vector) <- days_vector

# Total winnings with poker
total_poker <- sum(poker_vector)

# Total winnings with rolet
total_roulette <-  

# Total winnings overall
total_week <- 

# Print out total_week
  
```

*** =solution
```{r}
# Poker and rolet winnings from Monday to Friday:
poker_vector <- c(140, -50, 20, -120, 240)
roulette_vector <- c(-24, -50, 100, -350, 10)
days_vector <- c("Monday", "Tuesday", "Wednesday", "Thursday", "Friday")
names(poker_vector) <- days_vector
names(roulette_vector) <- days_vector

# Total winnings with poker
total_poker <- sum(poker_vector)

# Total winnings with rolet
total_roulette <-  sum(roulette_vector)

# Total winnings overall
total_week <- total_roulette + total_poker

# Print out total_week
total_week
```

*** =sct
```{r}
msg = "Jangan ganti apa pun tentang definisi dan penamaan `poker_vector` dan `roulette_vector`."
test_object("days_vector", undefined_msg = msg, incorrect_msg = msg)
test_object("poker_vector", eq_condition = "equal", undefined_msg = msg, incorrect_msg = msg)
test_object("roulette_vector", eq_condition = "equal", undefined_msg = msg, incorrect_msg = msg)
test_object("total_poker", 
            incorrect_msg = "Pastikan Anda menetapkan penjumlahan `poker_vector` pada `total_poker`.")
test_object("total_roulette",
            incorrect_msg = "Pastikan Anda menetapkan penjumlahan `roulette_vector` pada `total_roulette`.")
test_object("total_week",
            incorrect_msg = "Pastikan Anda menetapkan total penjumlahan vektor `total_roulette` dan `total_poker` pada `total_week`.")

test_output_contains("total_week", incorrect_msg = "Jangan lupa untuk menulis `total_week` pada baris baru untuk mencetak variabel itu.")
success_msg("Selamat. Ini benar-benar kabar jelek...")
```


--- type:NormalExercise xp:100 skills:1 key:f532f5332d
## Membandingkan total kemenangan

Aduh, kelihatannya uang Anda hilang. Waktunya berpikir dan mengatur ulang strategi! Anda perlu analisis lebih mendalam...

Setelah berpikir ulang sejenak di jacuzzi hotel, Anda baru sadar bahwa keahlian Anda bermain rolet tidak begitu berkembang dibanding keahlian Anda bermain poker. Jadi, total kemenangan Anda di poker lebih tinggi (atau `>`) daripada di rolet.

*** =instructions
- Hitung `total_poker` dan` total_roulette` sama seperti latihan sebelumnya. Gunakan fungsi `sum()` dua kali.
- Menggunakan perbandingan, cari tahu apakah total kemenangan Anda di poker lebih tinggi daripada rolet . Caranya, cukup cetak hasil perbandingan ini. Apa kesimpulannya? Apakah Anda harus fokus pada rolet, ataukah poker?

*** =hint
- Anda sudah menghitung sebagian jawaban atas pertanyaan ini pada latihan sebelumnya!
- Untuk mencari tahu apakah 6 lebih besar daripada 5, tulis `6 > 5`. Ini mengembalikan nilai logis (`TRUE` atau` FALSE`).

*** =pre_exercise_code
```{r}
# no pec
```

*** =sample_code
```{r}
# Poker and rolet winnings from Monday to Friday:
poker_vector <- c(140, -50, 20, -120, 240)
roulette_vector <- c(-24, -50, 100, -350, 10)
days_vector <- c("Monday", "Tuesday", "Wednesday", "Thursday", "Friday")
names(poker_vector) <- days_vector
names(roulette_vector) <- days_vector

# Calculate total gains for poker and rolet
total_poker <-
total_roulette <-

# Check if you realized higher total gains in poker than in rolet 

```

*** =solution
```{r}
# Poker and rolet winnings from Monday to Friday:
poker_vector <- c(140, -50, 20, -120, 240)
roulette_vector <- c(-24, -50, 100, -350, 10)
days_vector <- c("Monday", "Tuesday", "Wednesday", "Thursday", "Friday")
names(poker_vector) <- days_vector
names(roulette_vector) <- days_vector

# Calculate total gains for poker and rolet
total_poker <- sum(poker_vector)
total_roulette <- sum(roulette_vector)

# Check if you realized higher total gains in poker than in rolet
total_poker > total_roulette
```

*** =sct
```{r}
msg = "Jangan ganti apa pun tentang definisi dan penamaan `poker_vector` dan `roulette_vector`."
test_object("days_vector", undefined_msg = msg, incorrect_msg = msg)
test_object("poker_vector", eq_condition = "equal", undefined_msg = msg, incorrect_msg = msg)
test_object("roulette_vector", eq_condition = "equal", undefined_msg = msg, incorrect_msg = msg)

test_object("total_poker", 
            incorrect_msg = "Pastikan Anda menetapkan penjumlahan `poker_vector` pada `total_poker`. Gunakan `sum()`.")
test_object("total_roulette",
            incorrect_msg = "Pastikan Anda menetapkan penjumlahan `roulette_vector` pada `total_roulette`. Gunakan `sum()`.")
test_output_contains("total_poker > total_roulette",
                     incorrect_msg = "Sudahkah Anda melakukan perbandingan dengan benar? Untuk mencari tahu jika `total_poker` lebih besar daripada `total_roulette`, Anda dapat menggunakan `total_poker > total_roulette`.")
success_msg("Bagus! Lanjutkan ke latihan berikutnya.")
```


--- type:NormalExercise xp:100 skills:1 key:8d78be44e9
## Seleksi vektor: waktu yang baik

Firasat Anda sepertinya benar. Permainan poker kelihatannya lebih menguntungkan Anda daripada rolet.

Hal lain yang harus dicari tahu yaitu performa Anda di awal pekan dibandingkan akhir pekan. Anda ingat bahwa Anda cukup bersenang-senang saat akhir pekan...

Untuk menjawab pertanyaan ini, fokuskan pada seleksi `total_vector`. Dengan kata lain, tujuan Anda adalah memilih elemen-elemen tertentu pada vektor. Untuk memilih elemen sebuah vektor (dan matriks berikutnya, bingkai data, dsb.), gunakan kurung siku. Di dalam kurung siku, tunjukkan elemen-elemen yang akan dipilih. Sebagai contoh, untuk memilih elemen pertama vektor, tulis `poker_vector[1]`. Untuk memilih elemen kedua vektor, tulis `poker_vector[2]`, dan seterusnya. Perhatikan: elemen pertama vektor memiliki indeks 1, bukan 0 seperti pada banyak bahasa pemrograman lainnya.

*** =instructions
Tetapkan hasil poker hari Rabu pada variabel `poker_wednesday`.

*** =hint
Rabu adalah elemen ketiga dari `poker_vector` sehingga bisa dipilih dengan `poker_vector[3]`.

*** =pre_exercise_code
```{r}
# no pec
```

*** =sample_code
```{r}
# Poker and rolet winnings from Monday to Friday:
poker_vector <- c(140, -50, 20, -120, 240)
roulette_vector <- c(-24, -50, 100, -350, 10)
days_vector <- c("Monday", "Tuesday", "Wednesday", "Thursday", "Friday")
names(poker_vector) <- days_vector
names(roulette_vector) <- days_vector

# Define a new variable based on a selection
poker_wednesday <- 
```

*** =solution
```{r}
# Poker and rolet winnings from Monday to Friday:
poker_vector <- c(140, -50, 20, -120, 240)
roulette_vector <- c(-24, -50, 100, -350, 10)
days_vector <- c("Monday", "Tuesday", "Wednesday", "Thursday", "Friday")
names(poker_vector) <- days_vector
names(roulette_vector) <- days_vector

# Define a new variable based on a selection
poker_wednesday <- poker_vector[3]
```

*** =sct
```{r}
msg = "Jangan ganti apa pun tentang definisi dan penamaan `poker_vector` dan `roulette_vector`."
test_object("days_vector", undefined_msg = msg, incorrect_msg = msg)
test_object("poker_vector", eq_condition = "equal", undefined_msg = msg, incorrect_msg = msg)
test_object("roulette_vector", eq_condition = "equal", undefined_msg = msg, incorrect_msg = msg)
test_object("poker_wednesday", 
            undefined_msg = "Pastikan Anda mendefinisikan variabel `poker_wednesday`.",
            incorrect_msg = "Sepertinya `poker_wednesday` tidak berisi nilai yang benar dari `poker_vector`.")
success_msg("Bagus! R juga memungkinkan Anda memilih banyak elemen sekaligus dari vektor. Pelajari caranya di latihan berikutnya!")
```


--- type:NormalExercise xp:100 skills:1 key:1351521670
## Seleksi vektor: waktu yang baik (2)

Bagaimana menganalisis hasil tengah pekan?

Untuk memilih banyak elemen vektor, tambahkan kurung siku di bagian akhir. Tunjukkan elemen-elemen yang harus dipilih di dalam kurung. Misalkan Anda ingin memilih hari ke-1 dan ke-5 dalam sepekan: gunakan vektor `c (1, 5)` di dalam kurung siku. Sebagai contoh, kode di bawah ini akan memilih elemen ke-1 dan ke-5 dari `poker_vector`:

```
poker_vector[c(1, 5)]
```

*** =instructions
Tetapkan hasil poker pada hari Selasa, Rabu, dan Kamis pada variabel `poker_midweek`.

*** =hint
Gunakan vektor `c (2, 3, 4)` di dalam kurung siku untuk memilih elemen-elemen yang sesuai dari `poker_vector`.

*** =pre_exercise_code
```{r}
# no pec
``` 

*** =sample_code
```{r}
# Poker and rolet winnings from Monday to Friday:
poker_vector <- c(140, -50, 20, -120, 240)
roulette_vector <- c(-24, -50, 100, -350, 10)
days_vector <- c("Monday", "Tuesday", "Wednesday", "Thursday", "Friday")
names(poker_vector) <- days_vector
names(roulette_vector) <- days_vector

# Define a new variable based on a selection
poker_midweek <- 
```

*** =solution
```{r}
# Poker and rolet winnings from Monday to Friday:
poker_vector <- c(140, -50, 20, -120, 240)
roulette_vector <- c(-24, -50, 100, -350, 10)
days_vector <- c("Monday", "Tuesday", "Wednesday", "Thursday", "Friday")
names(poker_vector) <- days_vector
names(roulette_vector) <- days_vector

# Define a new variable based on a selection
poker_midweek <- poker_vector[c(2, 3, 4)]
```

*** =sct
```{r}
msg = "Jangan ganti apa pun tentang definisi dan penamaan `poker_vector` dan `roulette_vector`."
test_object("days_vector", undefined_msg = msg, incorrect_msg = msg)
test_object("poker_vector", eq_condition = "equal", undefined_msg = msg, incorrect_msg = msg)
test_object("roulette_vector", eq_condition = "equal", undefined_msg = msg, incorrect_msg = msg)
test_object("poker_midweek", 
            incorrect_msg = "Sepertinya `poker_midweek` tidak berisi nilai yang benar dari `poker_vector`. Anda dapat menggunakan vector `c(2, 3, 4)` dalam kurung siku.")
success_msg("Selamat! Lanjutkan ke latihan berikutnya agar Anda lebih mahir dalam seleksi vektor!");
```


--- type:NormalExercise xp:100 skills:1 key:27976b79f4
## Seleksi vektor: waktu yang baik (3)

Memilih banyak elemen `poker_vector` dengan `c (2, 3, 4)` rasanya tidak terlalu nyaman. Banyak ahli statistik yang dari sananya sudah pemalas. Untuk itu, mereka menciptakan cara yang lebih mudah untuk ini. Vektor `c (2, 3, 4)` bisa dipersingkat menjadi `2:4`, yang menghasilkan sebuah vektor dengan semua bilangan natural dari 2 sampai 4.

Jadi, cara lain untuk menemukan hasil tengah pekan yaitu `poker_vector[2:4]`. Perhatikan cara penempatan vektor `2:4` di dalam kurung siku untuk memilih elemen 2-4.

*** =instructions
Tetapkan hasil rolet dari hari Selasa sampai Jumat pada `roulette_selection_vector`; gunakan `:` jika Anda rasa lebih mudah.

*** =hint
Tetapkan seleksi `roulette_vector` pada` roulette_selection_vector` dengan meletakkan `2:5` di dalam kurung siku.

*** =sample_code
```{r}
# Poker and rolet winnings from Monday to Friday:
poker_vector <- c(140, -50, 20, -120, 240)
roulette_vector <- c(-24, -50, 100, -350, 10)
days_vector <- c("Monday", "Tuesday", "Wednesday", "Thursday", "Friday")
names(poker_vector) <- days_vector
names(roulette_vector) <- days_vector

# Define a new variable based on a selection
roulette_selection_vector <- 
```

*** =solution
```{r}
# Poker and rolet winnings from Monday to Friday:
poker_vector <- c(140, -50, 20, -120, 240)
roulette_vector <- c(-24, -50, 100, -350, 10)
days_vector <- c("Monday", "Tuesday", "Wednesday", "Thursday", "Friday")
names(poker_vector) <- days_vector
names(roulette_vector) <- days_vector

# Define a new variable based on a selection
roulette_selection_vector <- roulette_vector[2:5]
```

*** =sct

```{r}
msg = "Jangan ganti apa pun tentang definisi dan penamaan `poker_vector` dan `roulette_vector`."
test_object("days_vector", undefined_msg = msg, incorrect_msg = msg)
test_object("poker_vector", eq_condition = "equal", undefined_msg = msg, incorrect_msg = msg)
test_object("roulette_vector", eq_condition = "equal", undefined_msg = msg, incorrect_msg = msg)
test_object("roulette_selection_vector", 
            undefined_msg = "Pastikan Anda mendefinisikan variabel `roulette_selection_vector`.",
            incorrect_msg = "Sepertinya `roulette_selection_vector` tidak berisi seleksi yang benar dari `roulette_vector`. Pastikan indeks yang Anda pakai sudah tepat.")
success_msg("Luar biasa! Operator titik dua sangat bermanfaat dan sangat sering dipakai dalam pemrograman R. Jadi, ingat baik-baik, ya. Lanjutkan ke latihan berikutnya.")
```


--- type:NormalExercise xp:100 skills:1 key:e6c263ddee
## Seleksi vektor: waktu yang baik (4)

Cara lain untuk menyelesaikan latihan sebelumnya adalah dengan menggunakan nama elemen vektor (Senin, Selasa, dst.) alih-alih posisi numeriknya. Sebagai contoh,

```
poker_vector["Monday"]
```

akan memilih elemen pertama `poker_vector` karena `"Monday"` adalah nama elemen pertama tersebut.

Sama seperti yang Anda lakukan pada latihan sebelumnya dengan angka, Anda juga bisa menggunakan nama elemen untuk memilih banyak elemen, misalnya:

```
poker_vector[c("Monday","Tuesday")]
```

*** =instructions
- Pilih tiga elemen pertama dalam `poker_vector` menggunakan namanya: `"Monday"`, `"Tuesday"`, dan `"Wednesday"`. Tetapkan hasil seleksi ini pada `poker_start`.
- Hitung rata-rata nilai pada `poker_start` dengan fungsi [`mean()`](http://www.rdocumentation.org/packages/base/functions/mean). Cukup cetak hasilnya agar Anda bisa memeriksanya.

*** =hint
- Anda bisa menggunakan `c(" Monday "," Tuesday "," Wednesday ")` dalam kurung siku ke subset `poker_vector` secara tepat.
- Anda bisa menggunakan `mean(poker_start)` untuk mendapatkan rata elemen dalam `poker_start`. Alih-alih rata semua elemen poker, Anda hanya memerlukan tiga hari pertama.

*** =pre_exercise_code
```{r}
# no pec
```

*** =sample_code
```{r}
# Poker and rolet winnings from Monday to Friday:
poker_vector <- c(140, -50, 20, -120, 240)
roulette_vector <- c(-24, -50, 100, -350, 10)
days_vector <- c("Monday", "Tuesday", "Wednesday", "Thursday", "Friday")
names(poker_vector) <- days_vector
names(roulette_vector) <- days_vector

# Select poker results for Monday, Tuesday and Wednesday
poker_start <- 
  
# Calculate the average of the elements in poker_start

```

*** =solution
```{r}
# Poker and rolet winnings from Monday to Friday:
poker_vector <- c(140, -50, 20, -120, 240)
roulette_vector <- c(-24, -50, 100, -350, 10)
days_vector <- c("Monday", "Tuesday", "Wednesday", "Thursday", "Friday")
names(poker_vector) <- days_vector
names(roulette_vector) <- days_vector

# Select poker results for Monday, Tuesday and Wednesday
poker_start <- poker_vector[c("Monday", "Tuesday", "Wednesday")]
  
# Calculate the average of the elements in poker_start
mean(poker_start)
```

*** =sct
```{r}
msg = "Jangan ganti apa pun tentang definisi dan penamaan `poker_vector` dan `roulette_vector`."
test_object("days_vector", undefined_msg = msg, incorrect_msg = msg)
test_object("poker_vector", eq_condition = "equal", undefined_msg = msg, incorrect_msg = msg)
test_object("roulette_vector", eq_condition = "equal", undefined_msg = msg, incorrect_msg = msg)
test_object("poker_start", 
            incorrect_msg = "Sepertinya `poker_start` tidak berisi tiga nilai pertama dari `poker_vector`. Anda dapat memakai `c(\"Monday\", \"Tuesday\", \"Wednesday\")` dalam kurung siku untuk hal ini.")
test_output_contains("mean(poker_start)", incorrect_msg = "Sudahkah Anda menghitung rata-rata nilai dalam `poker_start` dengan benar dan mencetaknya? Gunakan `mean(poker_start)`. ")
Success_msg ("Bagus! Selain menjabarkan vektor menurut indeks atau nama, Anda juga bisa membuat subset vektor dengan perbandingan. Latihan selanjutnya akan memberi tahu caranya!");
```


--- type:NormalExercise xp:100 skills:1 key:f0f619c901
## Seleksi dengan perbandingan - Langkah 1

Menggunakan operator perbandingan, kita bisa menjawab pertanyaan sebelumnya dengan cara yang lebih proaktif.

Operator perbandingan (logis) yang dipahami oleh R antara lain:

- `<` untuk kurang dari
- `>` untuk lebih dari
- `<=` untuk kurang dari atau sama dengan
- `>=` untuk lebih dari atau sama dengan
- `==` untuk setara satu sama lain
- `!=` tidak setara satu sama lain

Seperti yang bisa Anda lihat pada bab sebelumnya, `6 > 5` mengembalikan `TRUE`. Hal yang baik tentang R yaitu Anda bisa memakai operator perbandingan ini juga pada vektor. Sebagai contoh:

```
> c(4, 5, 6) > 5
[1] FALSE FALSE TRUE
```

Perintah ini menguji setiap elemen vektor jika kondisi yang dinyatakan oleh operator pembandingnya adalah `TRUE` atau `FALSE`.

*** =instructions
- Periksa elemen di `poker_vector` yang nilainya positif (yaitu > 0), lalu tetapkan pada `selection_vector`.
- Cetak `selection_vector` sehingga Anda bisa memeriksanya. Hasil cetakan akan memberi tahu jika Anda menang (`TRUE`) atau kalah (` FALSE`) uang untuk setiap hari.

*** =hint
Untuk mengetahui hari-hari kemenangan poker yang nilainya positif, R harus memeriksa setiap elemen `poker_vector` yang nilainya lebih besar daripada nol. `some_vector > 0` adalah cara untuk memberi tahu R yang ingin Anda ketahui.

*** =pre_exercise_code
```{r}
# no pec
```

*** =sample_code
```{r}
# Poker and rolet winnings from Monday to Friday:
poker_vector <- c(140, -50, 20, -120, 240)
roulette_vector <- c(-24, -50, 100, -350, 10)
days_vector <- c("Monday", "Tuesday", "Wednesday", "Thursday", "Friday")
names(poker_vector) <- days_vector
names(roulette_vector) <- days_vector

# Which days did you make money on poker?
selection_vector <- 
  
# Print out selection_vector

```

*** =solution
```{r}
# Poker and rolet winnings from Monday to Friday:
poker_vector <- c(140, -50, 20, -120, 240)
roulette_vector <- c(-24, -50, 100, -350, 10)
days_vector <- c("Monday", "Tuesday", "Wednesday", "Thursday", "Friday")
names(poker_vector) <- days_vector
names(roulette_vector) <- days_vector

# Which days did you make money on poker?
selection_vector <- poker_vector > 0
  
# Print out selection_vector
selection_vector
```

*** =sct
```{r}
msg <- "Jangan ganti apa pun tentang definisi dan penamaan `poker_vector` dan `roulette_vector`."
test_object("days_vector", undefined_msg = msg, incorrect_msg = msg)
test_object("poker_vector", eq_condition = "equal", undefined_msg = msg, incorrect_msg = msg)
test_object("roulette_vector", eq_condition = "equal", undefined_msg = msg, incorrect_msg = msg)

test_object("selection_vector", incorrect_msg = "Sepertinya `selection_vector` tidak berisi hasil yang benar. Ingat: R menggunakan operasi elemen untuk vektor.")
test_output_contains("selection_vector", incorrect_msg = "Jangan lupa untuk mencetak `selection_vector` dengan menuliskan nama variabel itu pada baris baru.")
success_msg("Hebat!")
```


--- type:NormalExercise xp:100 skills:1 key:2754fc5cd4
## Seleksi dengan perbandingan - Langkah 2

Bekerja dengan perbandingan memudahkan tugas analisis data. Alih-alih memilih subset hari untuk menyelidiki diri sendiri (seperti sebelumnya), minta R untuk memunculkan hari-hari yang Anda sadari terdapat pengembalian positif untuk poker.

Dalam latihan sebelumnya, Anda memakai `selection_vector <- poker_vector > 0` untuk menemukan hari-hari yang terdapat pengembalian positif untuk poker. Sekarang, selain hari-hari Anda menang, Anda juga ingin tahu jumlah uang yang Anda menangkan ketika itu.

Anda bisa memilih elemen yang diinginkan dengan meletakkan `selection_vector` dalam kurung siku setelah `poker_vector`:

`` `
Poker_vector [selection_vector]
`` `

R tahu apa yang harus dilakukan ketika Anda memasukkan vektor logis dalam kurung siku, yaitu hanya memilih elemen-elemen yang nilainya`TRUE` di` selection_vector`.

*** =instructions
Gunakan `selection_vector` dalam kurung siku untuk menetapkan jumlah uang yang Anda menangkan pada hari-hari menguntungkan pada variabel` poker_winning_days`.

*** =hint
Gunakan `poker_vector [selection_vector]` untuk memilih elemen-elemen yang diinginkan dari `poker_vector`, lalu tetapkan hasilnya pada `poker_winning_days`.

*** =pre_exercise_code
```{r}
# no pec
```

*** =sample_code
```{r}
# Poker and rolet winnings from Monday to Friday:
poker_vector <- c(140, -50, 20, -120, 240)
roulette_vector <- c(-24, -50, 100, -350, 10)
days_vector <- c("Monday", "Tuesday", "Wednesday", "Thursday", "Friday")
names(poker_vector) <- days_vector
names(roulette_vector) <- days_vector

# Which days did you make money on poker?
selection_vector <- poker_vector > 0

# Select from poker_vector these days
poker_winning_days <- 
```

*** =solution
```{r}
# Poker and rolet winnings from Monday to Friday:
poker_vector <- c(140, -50, 20, -120, 240)
roulette_vector <- c(-24, -50, 100, -350, 10)
days_vector <- c("Monday", "Tuesday", "Wednesday", "Thursday", "Friday")
names(poker_vector) <- days_vector
names(roulette_vector) <- days_vector

# Which days did you make money on poker?
selection_vector <- poker_vector > 0

# Select from poker_vector these days
poker_winning_days <- poker_vector[selection_vector]
```

*** =sct
```{r}
msg = "Jangan ganti apa pun tentang definisi dan penamaan `poker_vector` dan `roulette_vector`."
test_object("days_vector", undefined_msg = msg, incorrect_msg = msg)
test_object("poker_vector", eq_condition = "equal", undefined_msg = msg, incorrect_msg = msg)
test_object("roulette_vector", eq_condition = "equal", undefined_msg = msg, incorrect_msg = msg)
test_object("selection_vector", incorrect_msg = "Jangan mengganti cara perhitungan `selection_vector`.")
test_object("poker_winning_days",
            incorrect_msg =  "Sepertinya `poker_winning_days` tidak berisi hasil yang benar. Gunakan `poker_vector[selection_vector]`.")
success_msg("Bagus! Lanjutkan ke latihan berikutnya.")
```


--- type:NormalExercise xp:100 skills:1 key:59e8dcbbd5
## Seleksi tingkat lanjut

Sama seperti yang Anda lakukan untuk poker, Anda juga ingin tahu hari-hari Anda menyadari pengembalian positif untuk rolet.

*** =instructions
- Buat variabel `selection_vector` untuk mengetahui jika Anda menghasilkan profit pada rolet untuk hari-hari yang berbeda.
- Tetapkan jumlah yang Anda buat pada hari-hari yang berakhir positif untuk rolet pada variabel `roulette_winning_days`. Vektor ini berisi kemenangan positif dari `roulette_vector`.

*** =hint
Setelah `selection_vector` dihitung dengan benar, Anda bisa memakai `roulette_vector[selection_vector]` untuk memilih hasil positif dari `roulette_vector`.

*** =pre_exercise_code
```{r}
# no pec
```

*** =sample_code
```{r}
# Poker and rolet winnings from Monday to Friday:
poker_vector <- c(140, -50, 20, -120, 240)
roulette_vector <- c(-24, -50, 100, -350, 10)
days_vector <- c("Monday", "Tuesday", "Wednesday", "Thursday", "Friday")
names(poker_vector) <- days_vector
names(roulette_vector) <- days_vector

# Which days did you make money on rolet?
selection_vector <-

# Select from roulette_vector these days
roulette_winning_days <- 
```

*** =solution
```{r}
# Poker and rolet winnings from Monday to Friday:
poker_vector <- c(140, -50, 20, -120, 240)
roulette_vector <- c(-24, -50, 100, -350, 10)
days_vector <- c("Monday", "Tuesday", "Wednesday", "Thursday", "Friday")
names(poker_vector) <- days_vector
names(roulette_vector) <- days_vector

# Which days did you make money on rolet?
selection_vector <- roulette_vector > 0

# Select from roulette_vector these days
roulette_winning_days <- roulette_vector[selection_vector]
```

*** =sct
```{r}
msg = "Jangan ganti apa pun tentang definisi dan penamaan `poker_vector` dan `roulette_vector`."
test_object("days_vector", undefined_msg = msg, incorrect_msg = msg)
test_object("poker_vector", eq_condition = "equal", undefined_msg = msg, incorrect_msg = msg)
test_object("roulette_vector", eq_condition = "equal", undefined_msg = msg, incorrect_msg = msg)
test_object("selection_vector", 
            incorrect_msg = "Sepertinya `selection_vector` tidak berisi hasil yang benar. Gunakan `roulette_vector > 0`.")
test_object("roulette_winning_days",
            incorrect_msg = "Sepertinya `roulette_winning_days` tidak berisi hasil yang benar. Gunakan `roulette_vector[selection_vector]`.")

success_msg("Hebat! Latihan ini menyimpulkan bab mengenai vektor. Bab berikutnya akan memperkenalkan Anda pada vektor dua dimensi, atau dikenal dengan matriks.")
```



