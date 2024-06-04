## Dinding Problem :
#### Definisi :
#### Dinding Problem adalah situasi di mana beberapa proses atau thread harus mengakses sumber daya bersama dalam urutan tertentu untuk menghindari konflik seperti deadlock atau race condition.
#### Contoh :
#### Lima teman duduk di sekitar meja bundar. Di antara setiap dua teman ada satu piring. Untuk makan, seorang teman membutuhkan dua piring. Jika semua teman mengambil piring di sebelah kiri mereka secara bersamaan, tidak ada yang bisa makan karena masing-masing hanya memegang satu piring, menyebabkan deadlock.
#### Ilustrasi : 
![image](https://github.com/fahmiwulidan/SysOP24-3123521009/assets/160559491/b9965a77-cd32-4958-805c-6d3c64d17b72)
##
## Reader Writer Problem :
#### Definisi :
#### Reader Writer Problem adalah masalah sinkronisasi di mana beberapa thread (pembaca) ingin membaca dari sumber daya bersama, dan beberapa thread (penulis) ingin menulis ke sumber daya tersebut. Tantangan utamanya adalah memastikan:Beberapa pembaca dapat membaca bersamaan.Penulis memiliki akses eksklusif saat menulis.
### Tipe Reader Writer Problem :
#### - First : Pembaca memiliki prioritas lebih tinggi, sehingga pembaca baru dapat terus membaca meskipun ada penulis yang menunggu.
#### - Second : Penulis memiliki prioritas lebih tinggi, sehingga pembaca baru tidak bisa mulai membaca jika ada penulis yang menunggu.
#### Contoh :
#### Bayangkan sebuah database yang bisa dibaca oleh banyak pengguna sekaligus (pembaca), tetapi saat satu pengguna (penulis) ingin mengupdate data, semua pembaca harus berhenti sampai update selesai.
#### Ilustrasi :
![1678856087244-1-01 (17)](https://github.com/fahmiwulidan/SysOP24-3123521009/assets/160559491/d69f57aa-8e0d-4849-95db-99432af63c86)
##
## Kesimpulan :
#### Kedua masalah ini menggambarkan tantangan dalam pemrograman paralel mengenai akses sumber daya bersama dan sinkronisasi. Solusi yang baik harus menghindari deadlock, starvation, dan race conditions untuk memastikan efisiensi dan integritas data.
