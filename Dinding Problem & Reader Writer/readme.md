## Dinding Problem :
#### Definisi :
#### Dinding Problem adalah situasi di mana beberapa proses atau thread harus mengakses sumber daya bersama dalam urutan tertentu untuk menghindari konflik seperti deadlock atau race condition.
#### Contoh :
#### Lima teman duduk di sekitar meja bundar. Di antara setiap dua teman ada satu cangkir. Untuk minum, seorang teman membutuhkan dua cangkir. Jika semua teman mengambil cangkir di sebelah kiri mereka secara bersamaan, tidak ada yang bisa minum karena masing-masing hanya memegang satu cangkir, menyebabkan deadlock.

## Reader Writer Problem :
#### Definisi :
#### Reader Writer Problem adalah masalah sinkronisasi di mana beberapa thread (pembaca) ingin membaca dari sumber daya bersama, dan beberapa thread (penulis) ingin menulis ke sumber daya tersebut. Tantangan utamanya adalah memastikan:Beberapa pembaca dapat membaca bersamaan.Penulis memiliki akses eksklusif saat menulis.
### Tipe Reader Writer Problem :
#### - First : Pembaca memiliki prioritas lebih tinggi, sehingga pembaca baru dapat terus membaca meskipun ada penulis yang menunggu.
#### - Second : Penulis memiliki prioritas lebih tinggi, sehingga pembaca baru tidak bisa mulai membaca jika ada penulis yang menunggu.
#### Contoh :
#### Bayangkan sebuah database yang bisa dibaca oleh banyak pengguna sekaligus (pembaca), tetapi saat satu pengguna (penulis) ingin mengupdate data, semua pembaca harus berhenti sampai update selesai.

## Kesimpulan :
#### Kedua masalah ini menggambarkan tantangan dalam pemrograman paralel mengenai akses sumber daya bersama dan sinkronisasi. Solusi yang baik harus menghindari deadlock, starvation, dan race conditions untuk memastikan efisiensi dan integritas data.
