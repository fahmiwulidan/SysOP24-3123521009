## Producer-Consumer Problem in C

Masalah Produsen-Konsumen atau masalah buffer adalah salah satu masalah klasik yang penting dalam sinkronisasi multi-proses dalam Sistem Operasi. Bagian terbaik tentang pemrograman komputer adalah bahwa semua masalah terkait dengan dunia nyata; tentu saja program komputer dan perangkat lunak adalah solusi untuk memenuhi kebutuhan sehari-hari kita dari pemesanan makanan online, belanja, media sosial, pemesanan tiket, dan banyak lagi!

Pada akhir blog tutorial ini, saya tidak hanya akan mempelajari masalah Produsen-Konsumen secara mendalam tetapi juga dapat mengodekannya seiring dengan pemrograman thread di C!

Jadi, mari kita mulai. Misalkan saya adalah pemilik sebuah toko roti bernama "Bakes and Bytes" Dan bisa membuat 50 kue maksimal karena saya belum memiliki oven yang besar. Sekarang, saya memiliki beberapa pelanggan yang ingin membelinya, tetapi mari kita pertimbangkan hanya satu pelanggan. Toko roti saya canggih dan memiliki sistem manajemen yang bagus seperti yang ditunjukkan dalam kode berikut :

![image](https://github.com/fahmiwulidan/SysOP24-3123521009/assets/160559491/2abd8598-2d66-4986-9c32-31d43e779d18)
![image](https://github.com/fahmiwulidan/SysOP24-3123521009/assets/160559491/f7ce3073-4dc3-4799-b1b0-7494eee9b333)

dari kode di atas, kita dapat memahami beberapa hal :

##### Jika toko roti tidak memiliki kue (kue == 0), tukang roti akan tidur dan tidak membuat kue lagi sampai ada pesan dari pelanggan untuk membuat kue.
##### Tukang roti terus membuat kue baru sampai oven penuh (kue != 50).
##### Ketika oven sudah penuh dengan kue (kue == 50), tukang roti akan tidur dan hanya akan terbangun kembali ketika pelanggan membeli kue sehingga oven tidak penuh lagi.
##### Jika hanya ada satu kue (kue == 1), pelanggan akan bangun dan mengambil kue tersebut.
##### Masalah utama adalah kurangnya sinkronisasi antara tukang roti dan pelanggan. Ini bisa menyebabkan kekacauan di toko roti.
##### Salah satu masalah konkret adalah bahwa pelanggan bisa tidur sebelum tukang roti membuat kue baru. Jika tukang roti kemudian membuat kue, panggilan untuk membangunkan pelanggan tidak akan berguna karena pelanggan sudah tidur.
##### Juga, karena tukang roti terus membuat kue bahkan ketika pelanggan tidak datang, pelanggan bisa tidur tak terbatas karena tidak ada kondisi di mana tukang roti berhenti membuat kue.

Solusi untuk masalah ini akan melibatkan sinkronisasi antara tukang roti dan pelanggan. Misalnya, penggunaan semafor atau variabel kondisi dapat digunakan untuk memastikan bahwa tukang roti hanya membuat kue saat pelanggan meminta, dan bahwa pelanggan hanya bangun ketika ada kue yang tersedia. Ini akan mengatasi masalah kekacauan dan kekurangan sinkronisasi yang terjadi dalam skenario tersebut.
