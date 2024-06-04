# Perbedaan Serial, Konkuren, Paralel, & Konkuren Paralel
## Serial (Serial Execution) :
#### Definisi : Tugas dikerjakan satu per satu secara berurutan.
#### Ilustrasi : Jadi ada tiga tugas A, B, dan C. Dalam eksekusi serial, tugas A harus selesai terlebih dahulu sebelum tugas B dimulai, dan tugas B harus selesai sebelum tugas C dimulai.
### Contoh : 
# A ----> B ----> C
## Konkuren (Concurrent Execution) :
#### Definisi : Tugas dapat dimulai pada waktu yang hampir bersamaan dan berjalan bersamaan, tetapi tidak harus selesai pada saat yang sama.
#### Ilustrasi : Jadi ada tiga tugas A, B, dan C. Dalam eksekusi konkuren, tugas A, B, dan C dapat dimulai hampir bersamaan, tetapi mereka bisa saling berhenti sejenak atau saling bergantian waktu proses.
### Contoh :
# A ----
# B ---------
# C ------
## Paralel (Parallel Execution) :
#### Definisi : Tugas dijalankan secara bersamaan pada waktu yang sama di berbagai prosesor atau thread.
#### Ilustrasi : Jadi ada tiga tugas A, B, dan C. Dalam eksekusi paralel, tugas A, B, dan C dijalankan secara bersamaan dan benar-benar berjalan secara paralel pada prosesor yang berbeda.
### Contoh :
# A -----
# B -----
# C -----
## Konkuren Paralel (Parallel Concurrent Execution) :
#### Definisi : Kombinasi dari eksekusi konkuren dan paralel. Beberapa set tugas dijalankan secara paralel, dan di dalam setiap set tugas-tugas tersebut bisa berjalan secara konkuren.
#### Ilustrasi : Bayangkan ada enam tugas A, B, C, D, E, dan F. Dalam eksekusi konkuren paralel, kita dapat membagi tugas menjadi dua kelompok (misalnya: A, B, C di satu kelompok dan D, E, F di kelompok lain). Kelompok pertama (A, B, C) dan kelompok kedua (D, E, F) dijalankan secara paralel, dan dalam setiap kelompok, tugas bisa berjalan secara konkuren.
### Contoh :
## - Kelompok 1
# A ----
# B ---------
# C -----
###
## - Kelompok 2
# D ----
# E ---------
# F -----
##
## Kesimpulan :
#### - Serial : Tugas diselesaikan satu per satu.
#### - Konkuren : Tugas dapat berjalan hampir bersamaan, tetapi tidak harus selesai pada saat yang sama.
#### - Paralel : Tugas dijalankan secara bersamaan pada waktu yang sama.
#### - Konkuren Paralel : Kombinasi di mana beberapa kelompok tugas berjalan secara paralel, dan di dalam setiap kelompok, tugas dapat berjalan secara konkuren.
