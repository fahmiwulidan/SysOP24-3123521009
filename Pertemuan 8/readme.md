# Fork 01, 02, 03
## 1. Fork : Parent - Child Process
### •	Buat tulisan tentang konsep fork dan implementasinya dengan menggunakan bahasa pemrograman C! (minimal 2 paragraf disertai dengan gambar)
### •	Akses dan clonning repo : https://github.com/ferryastika/operatingsystem.git
### •	Deskripsikan dan visualisasikan pohon proses hasil eksekusi dari kode program fork01.c, fork02.c, fork03.c.
### •	Konsep fork merupakan salah satu istilah yang sering digunakan dalam konteks pengembangan perangkat lunak, terutama dalam pengelolaan proyek perangkat lunak berbasis kode sumber terbuka (open source). Istilah ini berasal dari dunia pengembangan perangkat lunak dan memiliki analogi dengan proses bercabang atau forking dalam dunia nyata.
### Secara sederhana, fork merujuk pada tindakan membuat salinan dari suatu proyek perangkat lunak, baik itu seluruhnya atau hanya sebagian, dengan tujuan untuk mengembangkan atau mengubahnya secara independen. Analoginya dapat dibayangkan seperti bercabangnya sebuah jalur dalam sebuah jalan, di mana jalur baru tersebut dapat mengambil arah yang berbeda sesuai dengan kebutuhan atau visi pengembangnya.
### •	Akses & Clonning Repo : 
![image](https://github.com/fahmiwulidan/SysOP24-3123521009/assets/160559491/0d3bc543-ca36-4d6c-a46d-bde7dbdba1a7)
#### Disini saya tidak dapat mengcloning repo, Digambar terdapat error untuk melihat isi fork01, fork02, fork03 saya isi code fork tsb kedalam nano.
##
![image](https://github.com/fahmiwulidan/SysOP24-3123521009/assets/160559491/a99b0912-8ba1-4a30-ad90-91c5d56ea000)
#### Lamjut menginstal gcc g++ untuk nanti menampilkan fork01, fork02, fork03 tsb.
##
## 	Fork 01
#### Sourcode : 
![image](https://github.com/fahmiwulidan/SysOP24-3123521009/assets/160559491/e100b779-b197-43f5-a170-1d354b2145dc)
#### Output :
![image](https://github.com/fahmiwulidan/SysOP24-3123521009/assets/160559491/af72446c-3549-4913-ac45-ec9dead6a609)
##
![image](https://github.com/fahmiwulidan/SysOP24-3123521009/assets/160559491/1ca163aa-5c4a-41eb-b495-49d47b9b0a39)
### Keterangan : Program ini akan mencetak PID, PPID, dan UID, lalu jeda selama tiga detik sebelum mencetak informasi lagi, dan akan diulangi sebanyak tiga kali.
##
## 	Fork 02
#### Sourcode : 
![image](https://github.com/fahmiwulidan/SysOP24-3123521009/assets/160559491/6c9cad83-32a6-44ed-9877-e151e2aa32c0)
#### Output :
![image](https://github.com/fahmiwulidan/SysOP24-3123521009/assets/160559491/77800731-9988-4eab-b9be-4adabb9545d1)
##
![image](https://github.com/fahmiwulidan/SysOP24-3123521009/assets/160559491/a6385de9-443d-47d2-bee0-3b4bcb5d5167)
### Keterangan : Program ini menampilkan PID sendiri dan nilai variabel x dalam loop tak terbatas. Menggunakan system call fork() untuk membuat child process.
##
## 	Fork 03
#### Sourcode :
![image](https://github.com/fahmiwulidan/SysOP24-3123521009/assets/160559491/3fda17e0-9b8b-4b63-abdc-c703b24d1c3e)
#### Output :
![image](https://github.com/fahmiwulidan/SysOP24-3123521009/assets/160559491/4be9f984-217c-4db3-ae42-df5e80e56016)
##
![image](https://github.com/fahmiwulidan/SysOP24-3123521009/assets/160559491/6fcf976c-00ea-4024-bea2-e7691949c087)
### Keterangan : Program ini melakukan forking berulang lima kali, membuat proses-proses baru dengan pesan yang mencatat PID masing-masing. PID yang berulang menandakan proses parent melakukan forking beberapa kali, menghasilkan child processes dengan PID yang sama.
##
