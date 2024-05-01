# TUGAS PENDAHULUAN :
Jawablah pertanyaan-pertanyaan di bawah ini :
1. Apa yang dimaksud redirection?
2. Apa yang dimaksud pipeline?
3. Apa yang dimaksud perintah di bawah ini :
echo, cat, more, sort, grep, wc, cut, uniq

Jawaban!!
1.	Redirection adalah proses mengarahkan pengguna dari satu URL ke URL lainnya. Ini berguna untuk mengatur pemetaan URL, menangani error, atau melacak perilaku pengguna. Dua jenis redirect umum adalah 301 (permanen) dan 302 (sementara).
2.	Pipeline adalah serangkaian langkah atau tahapan yang diatur secara berurutan untuk menyelesaikan tugas atau proses tertentu secara otomatis. Ini umumnya digunakan dalam konteks pemrograman dan pengembangan perangkat lunak untuk mengotomatiskan alur kerja, seperti dalam aliran data atau pemrosesan informasi.
3.	perintah dasar dalam sistem operasi Unix/Linux:
•	echo : Menampilkan teks yang diberikan ke output standar.
•	cat : Membaca, menggabungkan, dan menampilkan isi file.
•	more : Membantu menampilkan isi file atau output secara bertahap di layar.
•	sort : Mengurutkan baris teks dari input.
•	grep : Mencocokkan pola teks dalam file atau output.
•	wc : Menghitung jumlah baris, kata, dan karakter dalam file atau output.
•	cut : Menampilkan kolom tertentu dari file atau output.
•	uniq : Membuang baris duplikat dari input yang diurutkan.
Perintah-perintah ini sering digunakan untuk mengelola dan memanipulasi teks dan file dalam lingkungan Unix/Linux.

# PERCOBAAN :
1.	Login sebagai user.
2.	Bukalah Console Terminal dan lakukan percobaan-percobaan di bawah ini. Perhatikan hasil setiap percobaan.
3.	Selesaikan soal-soal latihan.


## Percobaan 1 : File descriptor
1.	Output ke layar (standar output), input dari system (kernel)
##### $ ps
![image](https://github.com/fahmiwulidan/SysOP24-3123521009/assets/160559491/144c4f6a-9a30-4653-99cc-4d7505974b2f)
##### Analisa : Perintah $ps digunakan untuk menampilkan proses yang sedang berjalan di linux.
##
2.	Output ke layar (standar output), input dari keyboard (standard input)
 $ cat
##### hallo, apa khabar
##### hallo, apa khabar
##### exit dengan ^d
##### exit dengan ^d
##### [Ctrl-d]
![image](https://github.com/fahmiwulidan/SysOP24-3123521009/assets/160559491/9147d190-6540-42f2-82be-ee1181252e12)
##### Analisa : $cat digunakan untuk menginputkan data dari keyboard dan di output kelayar.
##
3.	Input nama direktori, output tidak ada (membuat direktori baru), bila terjadi error maka tampilan error pada layar (standard error)
##### $ mkdir mydir
##### $ mkdir mydir **(Terdapat pesan error)**
![image](https://github.com/fahmiwulidan/SysOP24-3123521009/assets/160559491/0d5bf0e1-3c10-4cee-8d5c-684c3b4eb668)
##### Analisa : Pesan yang ditampilkan adalah pesan error standar
##### -Sebab error karena file mydir pernah dibuat sebelumnya.
##

## Percobaan 2 : Pembelokan (redirection)
1.	Pembelokan standar output
##### $ cat 1> myfile.txt
##### Ini adalah teks yang saya simpan ke file myfile.txt
![image](https://github.com/fahmiwulidan/SysOP24-3123521009/assets/160559491/4f7f1746-b174-47c8-b14c-b4cd42dc32c4)
##### Analisa : Dalam percobaan diatas, input dari keyboard pada layar akan dimasukkan atau diredirect pada file  myfile.txt. Apabila myfile.txt dibuka  maka akan muncul tulisan yang sudah dimasukkan tersebut.
##
2.	Pembelokan standar input, yaitu input dibelokkan dari keyboard menjadi dari file
##### $ cat 0< myfile.txt
##### $ cat myfile.txt
![image](https://github.com/fahmiwulidan/SysOP24-3123521009/assets/160559491/968a6c12-8d52-409d-9008-7fa0a1ef2eda)
##### Analisa : Percobaan diatas akan  menampilkan isi/teks yang terdapat pada file myfile.txt pada layar.
##
3.	Pembelokan standar error untuk disimpan di file.
##### $ mkdir mydir (Terdapat pesan error)
##### $ mkdir mydir 2> myerror.txt
##### $ cat myerror.txt
![image](https://github.com/fahmiwulidan/SysOP24-3123521009/assets/160559491/03325e73-3c44-4f6b-b2a3-ff4494ac37b4)
##### Analisa : Perintah $cat mkdirmydir 2> myerror.txt akan menyimpan peringatan error kedalam myerror.txt apabila ketika membuat folder (mkdir mydir) terjadi error, contohnya ketika folder dengan nama mydir telah ada sebelumnya.
##
4.	Notasi 2>&1 : pembelokan standar error (2>) adalah identik dengan file descriptor 1.
##### $ ls filebaru (Terdapat pesan error)
##### $ ls filebaru 2> out.txt
##### $ cat out.txt
##### $ ls filebaru 2> out.txt 2>&
##### $ cat out.txt
![image](https://github.com/fahmiwulidan/SysOP24-3123521009/assets/160559491/967fd195-9bdb-425e-bb1d-c2ba3ceb4fc1)
##### Analisa : Pesan error karena mencoba direktori filebaru yang sebenarnya tidak ada dibelokkan ke out.txt.
##
5.	Notasi 1>&2 (atau >&2) : pembelokan standar output adalah sama dengan file descriptor 2 yaitu standar error
##### $ echo “mencoba menulis file” 1> baru
##### $ cat filebaru 2> baru 1>&
##### $ cat baru
![image](https://github.com/fahmiwulidan/SysOP24-3123521009/assets/160559491/e6fad0a5-d90a-403c-972f-b1b062999ce4)
##### Analisa : Kalimat yang dioutputkan dengan perintah echo dibelokkan kedalam filebaru. Namun selanjunya filebaru tersebut isinya tertindih oleh pesan error hasil pembelokan dari perintah cat filebaru yang gagal dilaksanakan.
##
6.	Notasi >> (append)
##### $ echo “kata pertama” > surat
##### $ echo “kata kedua” >> surat
##### $ echo “kata ketiga” >> surat
##### $ cat surat
##### $ echo “kata keempat” > surat
##### $ cat surat
![image](https://github.com/fahmiwulidan/SysOP24-3123521009/assets/160559491/8f9e21eb-e9e7-482c-bf30-2a427098390f)
##### Analisa : Karakter > akan membelokkan output dari echo menjadi sebuah filebaru bernama surat, Karakter >> akan menyisipkan output dari echo di kelanjutan isi dari file tujuan.
##
7.	Notasi here document (<<++ .... ++) digunakan sebagai pembatas input dari keyboard. Perhatikan bahwa tanda pembatas dapat digantikan dengan tanda apa saja, namun harus sama dan tanda penutup harus diberikan pada awal baris
##### $ cat <<++
##### Hallo, apa kabar?
##### Baik-baik saja?
##### Ok!
##### ++
##### $ cat <<%%%
##### Hallo, apa kabar?
##### Baik-baik saja?
##### Ok!
##### %%%
![image](https://github.com/fahmiwulidan/SysOP24-3123521009/assets/160559491/201fe683-1b61-49f4-93a7-712444e6feec)
##### Analisa : Notasi (<<++....++) & (<<%%%....%%%) digunakan sebagai pembatas input dari keyboard.
##
8.	Notasi – (input keyboard) adalah representan input dari keyboard. Artinya menampilkan file 1, kemudian menampilkan input dari keyboard dan menampilkan file 2. Perhatikan bahwa notasi “-“ berarti menyelipkan input dari keyboard
##### $ cat myfile.txt – surat
![image](https://github.com/fahmiwulidan/SysOP24-3123521009/assets/160559491/0c227c75-065f-4264-b41a-549097c9e2c9)
##### Analisa : melihat isi dari myfile.txt dan surat.
##

## Percobaan 3 : Pipa (pipeline)
1.	Operator pipa (|) digunakan untuk membuat eksekusi proses dengan melewati data langsung ke data lainnya.
##### $ who
##### $ who | sort
##### $ who | sort –r
##### $ who > tmp
##### $ sort tmp
##### $ rm tmp
##### $ ls –l /etc | more
##### $ ls –l /etc | sort | more
![image](https://github.com/fahmiwulidan/SysOP24-3123521009/assets/160559491/a741286a-22f7-4b0a-a837-5668167b92d6)
![image](https://github.com/fahmiwulidan/SysOP24-3123521009/assets/160559491/b24bf47e-734f-401d-9275-065cf3fe1994)
##### Analisa : $ who : Menampilkan daftar pengguna yang sedang masuk ke sistem.| sort -r : Mengurutkan output dari perintah who secara terbalik (descending).> tmp : Mengalihkan output dari perintah sort ke dalam file sementara yang disebut tmp.&& cat tmp : Menampilkan isi dari file sementara tmp.&& rm tmp : Menghapus file sementara tmp setelah ditampilkan.Ini akan menampilkan daftar pengguna yang sedang masuk ke sistem dalam urutan terbalik dan kemudian menghapus file sementara setelah ditampilkan.
##
2.	Untuk membelokkan standart output ke file, digunakan operator ">"
##### $ echo hello
##### $ echo hello > output
##### $ cat output
![image](https://github.com/fahmiwulidan/SysOP24-3123521009/assets/160559491/6fcf2395-ec68-4d14-809d-d9c3a68a3f2a)
##### Analisa : Perintah $echo yaitu untuk memunculkan hello lalu  > untuk membeklokan standart output ke file outuput lalu perintah cat untuk melihat isi file output.
##
3.	Untuk menambahkan output ke file digunakan operator ">>"
##### $ echo bye >> output
##### $ cat output 
![image](https://github.com/fahmiwulidan/SysOP24-3123521009/assets/160559491/1c5632b2-ff06-464f-8dea-67d426325fe9)
##### Analisa : $ echo bye >> output digunakan untuk menambahkan text by ke file output.$ cat output perintah ini dikunakan untuk melihat isi file output.
##
4.	Untuk membelokkan standart input digunakan operator "<"
##### $ cat < output
![image](https://github.com/fahmiwulidan/SysOP24-3123521009/assets/160559491/d505fce9-e5b7-4f63-b782-f744bd528a92)
##### Analisa : Perintah tersebut digunakan untuk menampilkan isi file dari output.
##
5.	Pembelokan standart input dan standart output dapat dikombinasikan tetapi tidak boleh menggunakan nama file yang sama sebagai standart input dan output.
##### $ cat < output > out
##### $ cat out
##### $ cat < output >> out
##### $ cat out
##### $ cat < output > output
##### $ cat output
##### $ cat < out >> out (Proses tidak berhenti)
##### [Ctrl-c]
##### $ cat out
![image](https://github.com/fahmiwulidan/SysOP24-3123521009/assets/160559491/0f2d8272-86ef-4ea8-acc5-2030b2bc8014)
##### Analisa : $ cat < output > out : Perintah ini mengambil isi dari file output dan menuliskannya ke dalam file out.
##

## Percobaan 4 : Filter
1.	Pipa juga digunakan untuk mengkombinasikan utilitas sistem untuk membentuk fungsi yang lebih kompleks
##### $ w –h | grep <user>
##### $ grep <user> /etc/passwd
##### $ ls /etc | wc
##### $ ls /etc | wc –l
##### $ cat > kelas1.txt
##### Badu
##### Zulkifli
##### Yulizir
##### Yudi
##### Ade
##### [Ctrl-d]
##### $ cat > kelas2.txt
##### Budi
##### Gama
##### Asep
##### Muchlis
##### [Ctrl-d]
##### $ cat kelas1.txt kelas2.txt | sort
##### $ cat kelas1.txt kelas2.txt > kelas.txt
##### $ cat kelas.txt | sort | uniq
![image](https://github.com/fahmiwulidan/SysOP24-3123521009/assets/160559491/e5b579d0-eabc-4217-8a84-61f878e00712)
![image](https://github.com/fahmiwulidan/SysOP24-3123521009/assets/160559491/83e37154-47e6-4a17-a3a7-2c60e4e7ab53)
##### Analisa : $ cat > kelas1.txt : Perintah ini membuka editor untuk membuat atau mengedit file bernama kelas1.txt.
##

# LATIHAN :
1. Lihat daftar secara lengkap pada direktori aktif, belokkan tampilan standard output ke file baru.
2. Lihat daftar secara lengkap pada direktori /etc/passwd, belokkan tampilan standard output ke file baru tanpa menghapus file baru sebelumnya.
3. Urutkan file baru dengan cara membelokkan standard input.
4. Urutkan file baru dengan cara membelokkan standard input dan standard output ke file baru.urut.
5. Buatlah direktori latihan2 sebanyak 2 kali dan belokkan standard error ke file rmdirerror.txt.
6. Urutkan kalimat berikut :
Jakarta
Bandung
Surabaya
Padang
Palembang
Lampung
Dengan menggunakan notasi here document (<@@@ ...@@@
7. Hitung jumlah baris, kata dan karakter dari file baru. urut dengan menggunakan filter dan tambahkan data tersebut ke file baru.
8. Gunakan perintah di bawah ini dan perhatikan hasilnya.
$ cat > hello.txt
dog cat
cat duck
dog chicken
chicken duck
chicken cat
dog duck
[Ctrl-d]
$ cat hello.txt | sort | uniq
$ cat hello.txt |
grep "dog" |
grep -v "cat"

## Jawaban!!
### 1.	Output :
![image](https://github.com/fahmiwulidan/SysOP24-3123521009/assets/160559491/8bb88d46-df4b-4784-952a-2f3545f084b4)
##### Analisa : Perintah ls -l > file.txt digunakan untuk menyimpan daftar file dan direktori dalam sebuah direktori ke dalam file teks file.txt. Kemudian, cat file.txt digunakan untuk menampilkan isi dari file tersebut di terminal.

### 2.	Output :
![image](https://github.com/fahmiwulidan/SysOP24-3123521009/assets/160559491/f7d063b8-e78c-4753-8654-0c88377b68f9)
##### Analisa : Perintah cat /etc/passwd >> file.txt digunakan untuk menyalin isi file /etc/passwd ke dalam file teks file.txt. Operator >> digunakan untuk menambahkan konten ke akhir file tanpa menghapus konten yang sudah ada. Kemudian, perintah cat file.txt digunakan untuk menampilkan isi dari file file.txt di terminal.

### 3.	Output :
![image](https://github.com/fahmiwulidan/SysOP24-3123521009/assets/160559491/6162a7b5-09da-4428-b512-fc52c4b4c572)
##### Analisa : Perintah sort < file.txt digunakan untuk mengurutkan baris-baris teks yang ada dalam file file.txt dan menampilkannya di terminal. Perintah tersebut menggunakan operator < untuk mengarahkan input dari perintah sort ke file file.txt.

### 4.	Output : 
![image](https://github.com/fahmiwulidan/SysOP24-3123521009/assets/160559491/c81a072e-a114-4cc5-9864-ed5a711db2f3)
##### Analisa : Perintah cat file.txt > baru.urut digunakan untuk menyalin isi dari file file.txt ke dalam sebuah file baru yang bernama baru.urut. Operator > digunakan untuk mengarahkan output dari perintah cat ke dalam file baru.urut. Kemudian, perintah cat baru.urut digunakan untuk menampilkan isi dari file baru.urut di terminal.

### 5.	Output : 
![image](https://github.com/fahmiwulidan/SysOP24-3123521009/assets/160559491/bb45b443-edf2-45cc-b5e9-6005beb8c610)
##### Analisa : Perintah mkdir latihan2 membuat direktori baru bernama "latihan2". Perintah mkdir latihan2 2> rmdirerror.txt mencoba membuat lagi direktori "latihan2" tetapi mengalihkan pesan kesalahan ke file rmdirerror.txt. Perintah cat rmdirerror.txt menampilkan pesan kesalahan tersebut.

### 6.	Output : 
![image](https://github.com/fahmiwulidan/SysOP24-3123521009/assets/160559491/4bc5d9f1-1408-4b80-9c61-84925443b444)
##### Analisa : Perintah sort <<@@@ adalah perintah shell yang menggunakan here document untuk menyalin teks yang dimasukkan sampai baris yang berisi @@@ ke perintah sort sebagai inputnya. Dengan demikian, sort akan mengurutkan teks yang dimasukkan dan menampilkannya di terminal.

### 7.	Output : 
![image](https://github.com/fahmiwulidan/SysOP24-3123521009/assets/160559491/e0b90aef-b62c-4dee-a7a0-08b61a7f0ff7)
##### Analisa : Perintah cat baru.urut | wc menghitung baris, kata, & byte dalam file baru.urut. Perintah cat baru.urut | wc -l menghitung jumlah baris dalam file baru.urut. Perintah cat baru.urut | wc -c menghitung jumlah byte dalam file baru.urut.Perintah cat baru.urut | wc -w menghitung jumlah kata dalam file baru.urut.

### 8.	Output :
![image](https://github.com/fahmiwulidan/SysOP24-3123521009/assets/160559491/55d17120-faee-44fc-8b40-1a0032b9c7a9)
##### Analisa : Hasil dari perintah tersebut dalam terminal.
##
