# Soal!!
1.	Buatlah presentasi langkah demi langkah tentang siklus CPU (fetch,decode,execute) utk mengeksekusi sebuah program. Jelaskan juga peran dari Bahasa pemrograman dan compiler, begitu juga dengan peran dari Sistem Operaso. Gunakan referensi : Video referensi 1 dan Video referensi 2
2.	Baca dan pahami rangkuman materi OS : Materi Intro to OS-01
3.	Jalankan VM Debian anda, lalu lakukan clone https://github.com/ferryastika/flops-iops. Compile dan eksekusi sesuai petunjuk. Sesuiakan jumlah thread dengan jumlah CPU yang ada di VM Debianmu. Catat hasilnya dan jelaskan arti dari hasil ekskusi. Lakukan sebanyak 5 kali. Bandingkan hasilnya anatar temanmu. Buat Plot perbandinnga hasil untuk masing-masing PC di tiap kelompokmu. Analisa hasil percobaan tadi dan beri kesimpulan tentang IOPS dan FLOPS.
4.	Apabila Debian VM mu masih belum terdapat packeage gcc, make dan git, lakukan instalasi dan catat setiap langkahnya!
#
# Jawaban!!
### 1.
![Picture1](https://github.com/fahmiwulidan/SysOP24-3123521009/assets/160559491/2c5cc989-a5dd-471f-8135-3f0cff3aec6f)	
 
#### •	Tiga register tersebut yang dimiliki oleh CPU adalah.
-	Program Counter : Register ini menyimpan alamat memori instruksi berikutnya yang akan dieksekusi oleh CPU.
-	Instruction Register : Register ini menyimpan instruksi yang sedang dieksekusi oleh CPU. Setelah instruksi diambil dari memori, ia disimpan dalam IR untuk diproses lebih lanjut.
-	Accumulator : Register ini digunakan untuk menyimpan hasil operasi aritmatika atau logika yang sedang berlangsung. Ini adalah register tempat penyimpanan utama untuk hasil perhitungan CPU.
-	Komponen terakhir yang diperlukan dalam sebuah komputer sederhana adalah media penyimpanan untuk menyimpan instruksi dan nilai-nilai yang dihitung. Media penyimpanan ini dikenal sebagai RAM.
 
#### •	Siklus Fetch, Execute & Decode.
Proses dasar di mana CPU mengambil, memecahkan, dan menjalankan instruksi. Setiap siklus dimulai dengan CPU mengambil instruksi dari memori dan menempatkannya ke dalam register instruksi.
-	Fetch (Pengambilan) :
Tahap ini dimulai dengan CPU mengambil instruksi dari memori utama (RAM) berdasarkan alamat instruksi yang disimpan di dalam register instruksi (Instruction Pointer atau Program Counter). Instruksi yang diambil kemudian ditempatkan dalam register instruksi CPU untuk diproses lebih lanjut.
-	Execute (Eksekusi) :
Pada tahap ini, CPU menjalankan instruksi yang telah didekode. bisa berupa operasi aritmatika, operasi logika, transfer data antara register, atau operasi lainnya sesuai dengan jenis instruksi yang diambil. Setelah eksekusi selesai, siklus dimulai lagi dengan langkah pengambilan instruksi berikutnya.
-	Decode (Dekode) :
Setelah instruksi diambil, tahap dekode menerjemahkan instruksi tersebut menjadi serangkaian sinyal kontrol yang diperlukan oleh CPU. Proses ini melibatkan memahami instruksi yang diambil dan menyiapkan sinyal kontrol yang sesuai untuk mengatur operasi-operasi yang akan dilakukan pada tahap eksekusi.

#### •	Peran dari Bahasa Pemrograman, Compiler, & Sistem Operasi :
-	Bahasa Pemrograman :
Bahasa pemrograman adalah aturan sintaks dan semantik yang digunakan untuk menulis program komputer. 
Peran utamanya adalah sebagai alat untuk menyusun instruksi-instruksi yang diperlukan untuk mengeksekusi tugas-tugas tertentu. 
Bahasa pemrograman memungkinkan programmer untuk berkomunikasi dengan komputer dan menentukan perilaku program yang diinginkan.

-	Compiler :
Compiler adalah program komputer yang menerjemahkan kode yang ditulis dalam bahasa pemrograman ke dalam bahasa mesin atau kode yang dapat dipahami oleh komputer.
Peran utamanya adalah untuk mengubah kode sumber yang ditulis oleh programmer ke dalam bentuk yang dapat dieksekusi oleh komputer. 
Compiler melakukan proses ini dalam satu tahap, menghasilkan file biner atau kode objek yang dapat dijalankan tanpa memerlukan interpretasi tambahan.
    
-	Sistem Operasi :
Sistem operasi adalah perangkat lunak yang bertanggung jawab atas manajemen sumber daya perangkat keras dan menyediakan antarmuka antara perangkat keras komputer dan aplikasi perangkat lunak.
Peran utamanya adalah untuk menyediakan lingkungan tempat aplikasi dapat dijalankan dengan efisien dan koordinasi antara perangkat keras dan perangkat lunak.
Sistem operasi menyediakan layanan seperti manajemen memori, manajemen file, penjadwalan proses, serta antarmuka pengguna untuk berinteraksi dengan komputer.

### 2.	GitHub - ferryastika/OS-01: Operating System (OS) Tutorial

### 3.	Perintah git clone akan melakukan cloning flops-iops dari GitHub ke direktori  saat ini. Lalu cd flops-iops perinitah tersebut akan masuk ke directory flops-iops.
![Picture2](https://github.com/fahmiwulidan/SysOP24-3123521009/assets/160559491/cf37862e-9fd2-4462-b2db-51ea3810ff7b)

##### $ make
##### $ make clean
##### $ sudo make install
##### $ iops64 $(nproc)
##### $ flops64 $(nproc)
![Picture3](https://github.com/fahmiwulidan/SysOP24-3123521009/assets/160559491/9080df91-bd31-4656-9f88-1dbf2da34118)

#### •	$ iops64 $(nproc)
![Picture4](https://github.com/fahmiwulidan/SysOP24-3123521009/assets/160559491/34dc74d2-8b57-4d1e-9adb-21669b181427)

#### •	$ flops64 $(nproc)
![Picture5](https://github.com/fahmiwulidan/SysOP24-3123521009/assets/160559491/8bd92613-b89a-4bdb-8313-6b68ed690b52)

Kesimpulan :
- FLOPS dan IOPS adalah metrik penting untuk mengukur kinerja komputasi dan sistem penyimpanan/input-output.
- Kedua metrik ini menggambarkan kemampuan sistem dalam menangani operasi tertentu dalam jumlah yang besar dalam satu unit waktu.
- Penyediaan infrastruktur komputasi yang optimal memerlukan pemahaman tentang keduanya agar aplikasi dapat dijalankan dengan efisien.
- Meskipun keduanya penting, perlu dipahami bahwa FLOPS dan IOPS mengukur kinerja dalam domain yang berbeda dan tidak selalu berkorelasi satu sama lain. Sebagai contoh, kenaikan nilai FLOPS pada komputer tidak selalu berarti peningkatan IOPS pada penyimpanan, dan sebaliknya.
- Penting untuk mempertimbangkan keduanya secara bersamaan untuk mendapatkan gambaran yang lengkap tentang kinerja sistem komputasi.

### 4.	$ su -l
##### $ apt install make
##### $ apt install git
##### $ apt install gcc
##### $ git clone https://github.com/ferryastika/flops-iops
##### $ cd flops-iops
