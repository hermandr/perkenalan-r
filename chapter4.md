---
title_meta  : Bab 4
title       : Faktor
description : Secara umum, data digolongkan ke dalam kategori terbatas. Sebagai contoh, manusia adalah pria atau wanita. Dalam R, data kategoris disimpan dalam faktor. Mengingat pentingnya faktor dalam menganalisis data, Anda harus menguasai cara membuat, menggabungkan, dan membandingkannya!

--- type:NormalExercise xp:100 skills:1 key:05273321916d99bb9c0deadf75c6834d25a47244
## Apa itu faktor dan mengapa Anda menggunakannya?

Di bab ini, Anda akan memasuki dunia **faktor** yang luar biasa.

Istilah faktor mengacu pada tipe data statistik yang dipakai untuk menyimpan variabel-variabel kategoris. Perbedaan antara variabel kategoris dan variabel kontinu adalah variabel kategoris bisa termasuk dalam **kategori terbatas**. Di sisi lain, variabel kontinu bisa berhubungan dengan jumlah nilai tak terbatas.

R harus mengetahui apakah akan menangani variabel kontinu ataukah kategoris. Hal ini karena model statistik yang akan dikembangkan nantinya memperlakukan kedua jenis variabel ini dengan cara yang berbeda (Anda akan paham alasannya nanti.).

Contoh yang baik dari variabel kategoris adalah variabel 'Gender'. Manusia bisa digolongkan menjadi pria (Male) atau wanita (Female), memisahkannya menurut jenis kelamin. Jadi, dalam arti sederhana, "Male" dan "Female" adalah dua nilai variabel kategori "Gender", dan setiap observasi bisa ditetapkan pada nilai "Male" dari "Female".

*** =instructions
Tetapkan nilai `"factors for categorical variables"` pada `theory`.

*** =hint
Cukup tetapkan variabel (`<-`); pastikan Anda menggunakan huruf besar dengan benar.

*** =pre_exercise_code
```{r}
# no pec
```

*** =sample_code
```{r}
# Assign to the variable theory what this bab is about!
```

*** =solution
```{r}
# Assign to the variable theory what this bab is about!
theory <- "factors for categorical variables"
```

*** =sct
```{r}
# MC-note: ideally, we could check for commonly mistyped variable names
#test_or({
#    bad_names <- c('Theory', "teory", "thoery", "theroy", "theiory", 'gender', 'value')
#    lapply(bad_names, test_object, eval=FALSE)
#    })

msg_undef <- "Sepertinya Anda belum mendefinisikan variabel `theory`."
msg_incor <- "Nilai `theory` kelihatannya salah. Pastikan Anda menetapkan karakter string `\"factors for categorical variables\"`. Ingat: R itu peka huruf.
msg_err <- "Pastikan Anda mendefinisikan `theory` dengan benar memakai `<-`."

# If get error and theory is undefined, point out the error
test_or(test_error(msg_err), test_object("theory", eval = FALSE))

test_object("theory", undefined_msg = msg_undef, incorrect_msg = msg_incor)
success_msg("Bagus! Lanjutkan ke latihan berikutnya!")
```


--- type:NormalExercise xp:100 skills:1 key:6cc21c842b075347926bb1b244782213df32e370
## Apa itu faktor dan mengapa Anda menggunakannya? (2)

Untuk membuat faktor pada R, Anda memanfaatkan fungsi [`factor()`](http://www.rdocumentation.org/packages/base/functions/factor). Pertama-tama, Anda membuat sebuah vektor berisi seluruh observasi yang tergolong ke dalam kategori terbatas. Sebagai contoh, `gender_vector` berisi jenis kelamin 5 individu yang berbeda:

```
gender_vector <- c("Male","Female","Female","Male","Male")
```

Jelas bahwa ada dua kategori, atau dalam **'level faktor'** R yang tengah dikerjakan: "Male" dan "Female".

Fungsi [`factor()`](http://www.rdocumentation.org/packages/base/functions/factor) akan mengodekan vektor sebagai faktor:

```
factor_gender_vector <- factor(gender_vector)
```

*** =instructions
- Ubah vektor karakter `gender_vector` menjadi faktor berisi `factor()`, lalu tetapkan hasilnya pada `factor_gender_vector`
- Cetak `factor_gender_vector` dan nyatakan bahwa R mencetak level faktor di bawah nilai sebenarnya.

*** =hint
Cukup gunakan fungsi [`factor()`](http://www.rdocumentation.org/packages/base/functions/factor)  pada `gender_vector`. Coba lihat tugasnya, jawabannya sudah ada di situ...

*** =pre_exercise_code
```{r}
# no pec
```

*** =sample_code
```{r}
# Gender vector
gender_vector <- c("Male", "Female", "Female", "Male", "Male")

# Convert gender_vector to a factor
factor_gender_vector <-

# Print out factor_gender_vector

```

*** =solution
```{r}
# Gender vector
gender_vector <- c("Male", "Female", "Female", "Male", "Male")

# Convert gender_vector to a factor
factor_gender_vector <- factor(gender_vector)

# Print out factor_gender_vector
factor_gender_vector
```

*** =sct
```{r}
test_object ("factor_gender_vector",
           incorrect_msg = "Apakah Anda menetapkan faktor `gender_vector` ke `factor_gender_vector`?")
test_output_contains ("factor_gender_vector", incorrect_msg = "Jangan lupa mencetak `factor_gender_vector`! ")
success_msg ("Hebat! Jika Anda ingin tahu lebih lanjut tentang fungsi `factor()`, tuliskan `?factor` di konsol dan halaman bantuan akan terbuka. Lanjutkan ke latihan berikutnya.") ;
```


--- type:NormalExercise xp:100 skills:1 key:5bd4f50afc2c2dbc881e16b8ca94ca56960dff42
## Apa itu faktor dan mengapa Anda menggunakannya? (3)

Ada dua jenis variabel kategoris: **variabel kategoris nominal** dan variabel kategoris ordinal**.

Variabel nominal adalah variabel kategoris tanpa perintah tersirat. Artinya, tidak mungkin untuk menyatakan bahwa 'kategori A bernilai lebih daripada kategori B'. Sebagai contoh, ada variabel kategoris `animals_vector` berisi kategori gajah, (Elephant), jerapah (Giraffe), keledai (Donkey), dan kuda (Horse). Anda di sini tidak mungkin menyatakan bahwa gajah bernilai lebih dibanding kuda (walaupun beberapa dari Anda mungkin tidak setuju ;-)).

Sebaliknya, variabel ordinal memiliki urutan alami. Misalkan variabel kategoris `temperature_vector` memiliki kategori rendah (Low), sedang (Medium), dan tinggi (High). Di sini, jelas bahwa `"Medium"` berada di atas `"Low"`, dan `"High"` berada di atas `"Medium"`.

*** =instructions
Klik 'Kirim Jawaban' untuk mencari tahu cara R menyusun dan mencetak variabel nominal dan ordinal. Jangan khawatir jika Anda belum paham semua kode tadi. Nanti akan kita bahas lebih lanjut.

*** =hint
Cukup klik tombol 'Kirim Jawaban' lalu lihat di konsol. Perhatikan cara R menunjukkan urutan level faktor untuk variabel kategoris ordinal.

*** =pre_exercise_code
```{r}
# no pec
```

*** =sample_code
```{r}
# Animals
animals_vector <- c("Elephant", "Giraffe", "Donkey", "Horse")
factor_animals_vector <- factor(animals_vector)
factor_animals_vector

# Temperature
temperature_vector <- c("High", "Low", "High","Low", "Medium")
factor_temperature_vector <- factor(temperature_vector, order = TRUE, levels = c("Low", "Medium", "High"))
factor_temperature_vector
```

*** =solution
```{r}
# Animals
animals_vector <- c("Elephant", "Giraffe", "Donkey", "Horse")
factor_animals_vector <- factor(animals_vector)
factor_animals_vector

# Temperature
temperature_vector <- c("High", "Low", "High","Low", "Medium")
factor_temperature_vector <- factor(temperature_vector, order = TRUE, levels = c("Low", "Medium", "High"))
factor_temperature_vector
```

*** =sct
```{r}
msg <- "Jangan ganti apa pun tentang kode contoh. Cukup tekan tombol Kirim Jawaban dan lihat jawabannya!"
test_object("animals_vector", undefined_msg = msg, incorrect_msg = msg)
test_object("temperature_vector", undefined_msg = msg, incorrect_msg = msg)
test_object("factor_animals_vector", undefined_msg = msg, incorrect_msg = msg)
test_output_contains("factor_animals_vector", incorrect_msg = msg)
test_object("factor_temperature_vector", undefined_msg = msg, incorrect_msg = msg)
test_output_contains("factor_temperature_vector", incorrect_msg = msg)
Success_msg ("Sudahkah Anda paham yang terjadi dalam latihan ini? Bagus! Lanjutkan ke latihan berikutnya untuk melihat level faktor lebih terperinci.")
```


--- type:NormalExercise xp:100 skills:1 key:1aa698978d32d1a0befa4700d7da85a648e1d69e
## Level faktor

Saat kali pertama Anda mendapatkan set data, Anda akan sering melihat bahwa set data itu berisi banyak faktor dengan level spesifik. Jika Anda ingin mengubah nama level ini supaya lebih mudah diingat atau pun alasan lainnya, lakukan dengan fungsi [`levels()`](http://www.rdocumentation.org/packages/base/functions/levels):

```
levels(factor_vector) <- c("name1", "name2",...)
```

Sebagai contoh, Anda menerima data mentah kuesioner. Pertanyaan standar untuk setiap kuesioner adalah gender responden. Anda ingat dari pertanyaan sebelumnya bahwa ini merupakan faktor dan ketika kuesioner dijalankan, gender sering dikodekan sebagai `"M"` dan `"F"`.

```
survey_vector <- c("M", "F", "F", "M", "M")
```

Selanjutnya, ketika ingin memulai analisis data, Anda ingin tetap mengingat semua variabel itu beserta artinya. Sampai sini, Anda biasanya mengganti level faktor menjadi `"Male"` dan `"Female"` daripada `"M"` dan `"F"` untuk memudahkan Anda.

**Hati-hati:** Urutan penetapan level itu penting. Ketika Anda mengetikkan `levels(factor_survey_vector)`, Anda akan melihat bahwa hasilnya adalah `[1] "F" "M"`. Jika Anda tidak menentukan level faktor saat membuat vektor, `R` otomatis akan menetapkannya menurut abjad. Untuk memetakan `"F"` ke `"Female"` dan `"M"` ke `"Male"` dengan benar, levelnya harus diganti menjadi `c("Female","Male")`.

*** =instructions
- Lihat kode yang membangun vektor faktor dari `survey_vector`. Anda harus menggunakan `factor_survey_vector` pada instruksi berikutnya.
- Ganti level faktor `factor_survey_vector` menjadi `c("Female", "Male")`. Perhatikan urutan elemen vektor di sini.

*** =hint
Perhatikan urutan ketika mengetikkan level faktor. Petunjuk: lihat urutan cetak level saat mengetikkan `levels(factor_survey_vector)`.

*** =pre_exercise_code
```{r}
# no pec
survey_vector <- c("M", "F", "F", "M", "M")
factor_survey_vector <- factor(survey_vector)
```

*** =sample_code
```{r}
# Code to build factor_survey_vector
survey_vector <- c("M", "F", "F", "M", "M")
factor_survey_vector <- factor(survey_vector)

# Specify the levels of factor_survey_vector
levels(factor_survey_vector) <-

factor_survey_vector
```

*** =solution
```{r}
# Code to build factor_survey_vector
survey_vector <- c("M", "F", "F", "M", "M")
factor_survey_vector <- factor(survey_vector)

# Specify the levels of factor_survey_vector
levels(factor_survey_vector) <- c("Female", "Male")

factor_survey_vector
```

*** =sct
```{r}
msg = "Jangan ganti definisi `survey_vector`!"
test_object("survey_vector", undefined_msg = msg, salah_msg = msg)
msg = "Jangan ganti atau hapus kode untuk membuat vektor faktor."
test_function("factor", "x", not_called_msg = msg, incorrect_msg = msg)

# MC-note: ideally would want to test assign operator `<-`, and have it highlight whole line.

# MC-note: or negate this test_student_typed, to highlight where they type this incorrect phrase
# test_student_typed('c("Male", "Female")')

test_object("factor_survey_vector", eq_condition = "equal",
            incorrect_msg = paste("Apakah Anda menetapkan level faktor yang benar pada `factor_survey_vector`? Gunakan `levels(factor_survey_vector) <- c(\"Female\", \"Male")`. Ingat: R itu peka huruf!"))


success_msg("Luar biasa! Lanjutkan ke latihan berikutnya.")
```


--- type:NormalExercise xp:100 skills:1 key:a549f13c0644ccc89cd39a10aa48706754637ed0
## Membuat rangkuman faktor

Setelah menyelesaikan kursus ini, [`summary()`](http://www.rdocumentation.org/packages/base/functions/summary)  akan menjadi salah satu fungsi kesukaan Anda di R. Fungsi ini memberi gambaran kilat mengenai isi suatu variabel:

```
summary(my_var)
```

Kembali ke survei tadi... Anda ingin mengetahui jumlah respons "Male" serta respons "Female" dalam penelitian ini. Fungsi [`summary()`](http://www.rdocumentation.org/packages/base/functions/summary) memberikan jawaban untuk ini.

*** =instructions
Mintalah [`summary()`](http://www.rdocumentation.org/packages/base/functions/summary) dari `survey_vector` dan `factor_survey_vector`. Tafsirkan hasil kedua vektor. Apakah keduanya sama-sama bermanfaat dalam kasus ini?

*** =hint
Panggil fungsi [`summary()`](http://www.rdocumentation.org/packages/base/functions/summary) pada `survey_vector` dan `factor_survey_vector`. Itu saja, kok!

*** =pre_exercise_code
```{r}
# no pec
```

*** =sample_code
```{r}
# Build factor_survey_vector with clean levels
survey_vector <- c("M", "F", "F", "M", "M")
factor_survey_vector <- factor(survey_vector)
levels(factor_survey_vector) <- c("Female", "Male")
factor_survey_vector

# Generate summary for survey_vector


# Generate summary for factor_survey_vector

```

*** =solution
```{r}
# Build factor_survey_vector with clean levels
survey_vector <- c("M", "F", "F", "M", "M")
factor_survey_vector <- factor(survey_vector)
levels(factor_survey_vector) <- c("Female", "Male")
factor_survey_vector

# Generate summary for survey_vector
summary(survey_vector)

# Generate summary for factor_survey_vector
summary(factor_survey_vector)
```

*** =sct
```{r}
msg = "Jangan mengganti apa pun pada beberapa baris pertama yang mendefinisikan `survey_vector` dan `factor_survey_vector`."
test_object("survey_vector", undefined_msg = msg, incorrect_msg = msg)
test_object("factor_survey_vector", eq_condition = "equal", undefined_msg = msg, incorrect_msg = msg)
msg <- "Sudahkah anda menggunakan `summary()` untuk membuat rangkuman `%s`?"
test_output_contains("summary(survey_vector)", incorrect_msg = sprintf(msg, "survey_vector"))
test_output_contains("summary(factor_survey_vector)", incorrect_msg = sprintf(msg, "factor_survey_vector"))
success_msg("Bagus! Lihat hasilnya. Fakta bahwa Anda mengenali `\"Male\"` dan `\"Female\"` sebagai level faktor dalam `factor_survey_vector` memungkinkan R untuk menampilkan jumlah elemen setiap kategori.")
```


--- type:NormalExercise xp:100 skills:1 key:90ecc160d1ebf2f75bf53f9c3843fc1632bdd0a5
## Persaingan gender

Pada `factor_survey_vector`, ada sebuah faktor berisi dua level: Male and Female. Tetapi bagaimana R menilai ini secara relatif satu sama lain? Dengan kata lain, siapa yang dianggap R lebih baik, pria ataukah wanita?

*** =instructions
Baca kode di editor, lalu klik 'Kirim Jawaban' untuk melihat apakah pria lebih baik daripada wanita.

*** =hint
Cukup klik 'Kirim Jawaban' lalu lihat hasil yang dicetak ke konsol.

*** =pre_exercise_code
```{r}
# no pec
```

*** =sample_code
```{r}
# Build factor_survey_vector with clean levels
survey_vector <- c("M", "F", "F", "M", "M")
factor_survey_vector <- factor(survey_vector)
levels(factor_survey_vector) <- c("Female", "Male")

# Male
male <- factor_survey_vector[1]

# Female
female <- factor_survey_vector[2]

# Battle of the sexes: Male 'larger' than female?
male > female
```

*** =solution
```{r}
# Build factor_survey_vector with clean levels
survey_vector <- c("M", "F", "F", "M", "M")
factor_survey_vector <- factor(survey_vector)
levels(factor_survey_vector) <- c("Female", "Male")

# Male
male <- factor_survey_vector[1]

# Female
female <- factor_survey_vector[2]

# Battle of the sexes: Male 'larger' than female?
male > female
```

*** =sct
```{r}
msg = "Jangan ganti apa pun tentang kodenya, cukup tekan Kirim Jawaban lalu lihat hasilnya."
test_object("survey_vector", undefined_msg = msg, incorrect_msg = msg)
test_object("factor_survey_vector", eq_condition = "equal", undefined_msg = msg, incorrect_msg = msg)
test_object("male", undefined_msg = msg, incorrect_msg = msg)
test_object("female", undefined_msg = msg, incorrect_msg = msg)
test_output_contains("male > female", incorrect_msg = msg)
success_msg("Fiuh, kelihatannya R itu netral gender. Atau mungkin R mau cari aman saja ;-).")
```


--- type:NormalExercise xp:100 skills:1 key:9ab0928916bf84ab225713a9a1ce40d9e322c6a0
## Faktor yang diprioritaskan

Karena `"Male"` dan `"Female"` adalah level faktor tak berurutan (atau nominal), R mengembalikan pesan peringatan yang memberi tahu bahwa operator lebih besar tidak bermakna apa pun di sini. Seperti yang terlihat sebelumnya, R mengaitkan nilai setara pada level untuk faktor-faktor tersebut.

Tetapi ini tidak selalu terjadi! Terkadang, Anda juga harus menghadapi faktor-faktor yang memiliki urutan natural di antara kategori-kategorinya. Untuk itu, kita harus memastikan telah menyampaikan informasi ini ke R...

Mari kita katakan bahwa Anda memimpin sebuah tim riset beranggotakan lima analis data. Anda ingin mengevaluasi kinerja mereka. Untuk itu, Anda melacak kecepatan setiap analis dan menilainya sebagai lamban (slow), cepat (fast), dan gila (insane), lalu menyimpan hasilnya di `speed_vector`.

*** =instructions
Sebagai langkah awal, tetapkan pada `speed_vector` sebuah vektor yang berisi 5 macam entri; satu entri untuk setiap analis. Setiap entri harus berisi `"slow"`, `"fast"`, atau `"insane"`. Gunakan daftar berikut ini:

- Analis 1 cepat,
- Analis 2 lambat,
- Analis 3 lambat,
- Analis 4 cepat dan
- Analis 5 gila.

Anda belum perlu menentukan semua ini sebagai faktor.

*** =hint
Tetapkan pada `speed_vector` sebuah vektor yang berisi string-string karakter: `"fast"`, `"slow"`, dan seterusnya.

*** =pre_exercise_code
```{r}
# no pec
```

*** =sample_code
```{r}
# Create speed_vector
speed_vector <-
```

*** =solution
```{r}
# Create speed_vector
speed_vector <- c("fast", "slow", "slow", "fast", "insane")
```

*** =sct
```{r}
test_object("speed_vector",
            incorrect_msg = "`speed_vector` harus berupa vektor dengan 5 entri; satu entri untuk setiap nilai kecepatan analis. Jangan pakai huruf kapital; R itu peka huruf!")
success_msg("Bagus! Lanjutkan ke latihan berikutnya.")
```


--- type:NormalExercise xp:100 skills:1 key:279077d10248ce03d5f972939ef8576430a16683
## Faktor yang diprioritaskan (2)

`Speed_vector` harus diubah ke faktor ordinal karena kategorinya memiliki urutan natural. Secara default, fungsi [`factor()`](http://www.rdocumentation.org/packages/base/functions/factor) mengubah `speed_vector` menjadi faktor tak berurutan. Untuk membuat faktor berurutan, Anda harus menambahkan argumen `ordered` dan `levels`.

```
factor(some_vector,
       ordered = TRUE,
       levels = c("lev1", "lev2" ...))
```

Dengan menetapkan nilai `TRUE` pada argumen `ordered` dalam fungsi [`factor()`](http://www.rdocumentation.org/packages/base/functions/factor), Anda menunjukkan bahwa faktor tersebut berurutan. Dengan argumen `level`, Anda memberi urutan yang benar kepada nilai faktor.

*** =instructions
Dari `speed_vector`, buatlah sebuah vektor faktor berurutan: `factor_speed_vector`. Tetapkan`ordered` ke `TRUE`, dan tetapkan `levels` ke `c("slow", "fast", "insane")`.

*** =hint
Gunakan fungsi [`factor()`](http://www.rdocumentation.org/packages/base/functions/factor) untuk membuat `factor_speed_vector` berdasarkan `speed_character_vector`. Argumen `ordered` harus ditetapkan ke `TRUE` karena adanya urutan natural. Selain itu, tetapkan `levels = c("slow","fast","insane")`.

*** =pre_exercise_code
```{r}
# no pec
```

*** =sample_code
```{r}
# Create speed_vector
speed_vector <- c("fast", "slow", "slow", "fast", "insane")

# Convert speed_vector to ordered factor vector
factor_speed_vector <-

# Print factor_speed_vector
factor_speed_vector
summary(factor_speed_vector)
```

*** =solution
```{r}
# Create speed_vector
speed_vector <- c("fast", "slow", "slow", "fast", "insane")

# Add your code below
factor_speed_vector <- factor(speed_vector, ordered = TRUE, levels = c("slow", "fast", "insane"))

# Print factor_speed_vector
factor_speed_vector
summary(factor_speed_vector)
```

*** =sct
```{r}
msg = "Jangan ganti apa pun tentang perintah yang menentukan variabel `speed_vector`."
test_object("speed_vector", undefined_msg = msg, incorrect_msg = msg)
test_function("factor", args = c("x", "ordered", "levels"),
              incorrect_msg = c("Argumen pertama yang Anda masukkan pada `factor()` harus `speed_vector`.",
                                 "Pastikan Anda menetapkan `ordered = TRUE` di dalam panggilan `factor()`.",
                                 "Pastikan Anda menetapkan `levels = c(\"slow\", \"fast\", \"insane\")` di dalam panggilan `factor()`."))
test_object("factor_speed_vector", eq_condition = "equal",
            incorrect_msg = "Masih ada yang salah dengan `factor_speed_vector`; pastikan Anda hanya memasukkan `speed_vector`, `ordered = TRUE`, dan `levels = c(\"slow\", \"fast\", \"insane\")` di dalam panggilan `factor()`.")
success_msg("Hebat! Lihat konsolnya. Sekarang terpampang nyata di situ bahwa Level memang memiliki urutan terkait menggunakan tanda `<`. Lanjutkan ke latihan berikutnya.")
```


--- type:NormalExercise xp:100 skills:1 key:db16e69805625bcfde227743a8cbc985f8482a37
## Membandingkan faktor urutan

Karena faktor pekerjaan, 'analis data nomor dua' mendatangi ruangan kerja Anda dan mengeluh bahwa 'analis data nomor lima' memperlambat keseluruhan proyek. Karena Anda tahu bahwa 'analis data nomor dua' dikenal sebagai sok tahu, Anda ingin memeriksa kebenaran pernyataannya terlebih dahulu.

Fakta bahwa `factor_speed_vector` kini sudah diurutkan memungkinkan Anda untuk membandingkan berbagai elemen (dalam kasus ini analis data). Anda bisa melakukannya memakai operator yang telah dikenal.

*** =instructions
- Gunakan `[2]` dari `factor_speed_vector` untuk memilih nilai faktor analis data kedua. Simpan sebagai `da2`.
- Gunakan `[5]` dari `factor_speed_vector` untuk memilih nilai faktor analis data kelima. Simpan sebagai `da5`.
- Cari tahu apakah `da2` lebih besar daripada `da5`; cukup cetak hasilnya. Ingat: Anda bisa menggunakan operator `>` untuk memeriksa apakah satu elemen lebih besar daripada elemen lain.

*** =hint
- Untuk memilih nilai faktor untuk analis data ketiga, Anda memerlukan `factor_speed_vector[3]`.
- Untuk membandingkan kedua nilai, Anda bisa menggunakan `>`. Misalnya: `da3 > da4`.

*** =pre_exercise_code
```{r}
# no pec
```

*** =sample_code
```{r}
# Create factor_speed_vector
speed_vector <- c("fast", "slow", "slow", "fast", "insane")
factor_speed_vector <- factor(speed_vector, ordered = TRUE, levels = c("slow", "fast", "insane"))

# Factor value for second data analyst
da2 <-

# Factor value for fifth data analyst
da5 <-

# Is data analyst 2 faster than data analyst 5?

```

*** =solution
```{r}
# Create factor_speed_vector
speed_vector <- c("fast", "slow", "slow", "fast", "insane")
factor_speed_vector <- factor(speed_vector, ordered = TRUE, levels = c("slow", "fast", "insane"))

# Factor value for second data analyst
da2 <- factor_speed_vector[2]

# Factor value for fifth data analyst
da5 <- factor_speed_vector[5]

# Is data analyst 2 faster data analyst 5?
da2 > da5
```

*** =sct
```{r}
msg = "msg = "Jangan ganti apa pun tentang perintah yang menentukan `speed_vector` dan `factor_speed_vector`!"
test_object("speed_vector", undefined_msg = msg, incorrect_msg = msg)
test_object("factor_speed_vector", eq_condition = "equal", undefined_msg = msg, incorrect_msg = msg)

msg <- "Sudahkah Anda memilih nilai faktor untuk analis data %s? Anda bisa memakai `factor_speed_vector[%s]`."
test_object("da2", eq_condition = "equal", incorrect_msg = sprintf(msg, "second", "2"))
test_object("da5", eq_condition = "equal", incorrect_msg = sprintf(msg, "fifth", "5"))
test_output_contains("da2 > da5", incorrect_msg = "Sudahkah Anda membandingkan `da2` dan `da5` dengan benar ? Anda bisa menggunakan `>`. Cukup cetak hasilnya.")

success_msg("Hebat! Apa yang bisa Anda simpulkan dari hasil ini? Analis data nomor dua mengeluhkan analis data nomor lima padahal sebenarnya dia yang memperlambat semuanya! Inilah kesimpulan bab mengenai faktor ini. Dengan basis pengetahuan solid mengenai vektor, matriks, dan faktor, Anda siap terjun ke dunia frame data yang luar biasa, yaitu struktur data yang sangat penting dalam R!")
```



