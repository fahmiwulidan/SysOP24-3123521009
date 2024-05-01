## •	Forking :
   - Forking adalah proses di mana sebuah program menghasilkan salinan dari dirinya sendiri, menciptakan dua proses baru yang identik secara program.
   - Proses yang memanggil `fork()` akan membagi dirinya menjadi dua proses: proses induk dan anak.
   - Proses induk dan anak berjalan secara independen, memiliki salinan dari ruang alamat yang sama pada awalnya, tetapi kemudian memiliki salinan yang terpisah saat perubahan dilakukan.

## •	Orphan :
   - Sebuah proses anak disebut "anak yatim piatu" ketika proses induknya keluar atau selesai sebelum proses anaknya selesai.
   - Sistem operasi akan mengadopsi proses anak tersebut dan menjadikannya anak dari proses init (dengan ID proses 1).
   - Proses init bertanggung jawab untuk mengurus anak-anak yatim piatu dan membersihkan sumber daya mereka setelah selesai.

## •	Zombie :
   - Zombie adalah proses yang telah menyelesaikan eksekusinya tetapi masih memiliki entri dalam tabel proses.
   - Biasanya terjadi ketika proses induk belum membaca status keluaran dari proses anak yang selesai.
   - Proses zombie tidak lagi berjalan tetapi masih memakan sumber daya sistem.
   - Untuk menghapus proses zombie, proses induk harus melakukan panggilan sistem seperti wait() untuk membaca status keluaran proses anak dan membersihkan entri zombie dari tabel proses.

### Dengan pemahaman ini, pengelolaan proses dalam sistem operasi menjadi lebih baik dan dapat mencegah masalah yang timbul karena proses anak yang tidak terkelola dengan baik.
##
## Akses & Clonning Repo :
![image](https://github.com/fahmiwulidan/SysOP24-3123521009/assets/160559491/e251eeca-4b2e-4bae-82c4-f809d4179790)
#### Disini Debian saya tidak bisa mengcloning repo tsb, Jadi langsung saya masukkan code tsb kedalam nano.
##
![image](https://github.com/fahmiwulidan/SysOP24-3123521009/assets/160559491/41de27e9-3cf7-4a7b-bf37-3617bfe0b4fe)
#### Untuk menampilkan code tsb saya menginstal gcc g++ terlebih dahulu.
##
### 	Froking
#### Sourcode : 
![image](https://github.com/fahmiwulidan/SysOP24-3123521009/assets/160559491/5f4bf5ef-9d7d-460e-aae5-082a2c976d28)
#### Output :
![image](https://github.com/fahmiwulidan/SysOP24-3123521009/assets/160559491/81ff89b7-6b5f-429d-92c4-011b24c84148)
![image](https://github.com/fahmiwulidan/SysOP24-3123521009/assets/160559491/e79b2781-006f-40a7-8b34-9d4fe11d2795)
#### Keterangan : Code tersebut merupakan contoh sederhana penggunaan fungsi fork() dalam bahasa pemrograman C untuk membuat proses anak. Proses anak yang dibuat akan menjalankan perintah ls menggunakan fungsi execlp(), sedangkan proses induk akan menunggu proses anak selesai dengan menggunakan fungsi wait(). Setelah proses anak selesai, proses induk akan mencetak pesan "Child Complete" sebelum program berakhir.
##
### 	Orphan
#### Sourcode : 
![image](https://github.com/fahmiwulidan/SysOP24-3123521009/assets/160559491/fc02b6f1-a99b-486a-9a0c-5f65f134773a)
![image](https://github.com/fahmiwulidan/SysOP24-3123521009/assets/160559491/5169dc91-d69d-40f2-b0ed-d73b2d0b84e2)
#### Output :
![image](https://github.com/fahmiwulidan/SysOP24-3123521009/assets/160559491/8630fd85-8a7e-4510-894b-835ebff63a6b)
![image](https://github.com/fahmiwulidan/SysOP24-3123521009/assets/160559491/aa2e45d3-f045-45c3-ac4f-746940ac6a60)
#### Keterangan : Code tersebut menciptakan proses anak dan proses induk. Proses induk mencetak informasi tentang dirinya, sedangkan proses anak menunggu selama 10 detik sebelum mencetak informasi tentang dirinya sendiri.
##
### 	Zombie
#### Sourcode :
![image](https://github.com/fahmiwulidan/SysOP24-3123521009/assets/160559491/4f167e2a-4a28-498c-b747-386d05a45a91)
#### Output :
![image](https://github.com/fahmiwulidan/SysOP24-3123521009/assets/160559491/c4dadeef-d19d-42bc-8742-9ee81763f70a)
![image](https://github.com/fahmiwulidan/SysOP24-3123521009/assets/160559491/285b5eb3-9b8e-4903-9ed0-98f0b13e2db4)
#### Keterangan : Kode tersebut membuat proses anak dan proses induk. Proses induk tidur selama 60 detik, sementara proses anak keluar segera setelah dibuat.
##
