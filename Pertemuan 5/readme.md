## Perbedaan Paging & Swapping
### Paging & Swapping adalah dua teknik yang digunakan dalam manajemen memori pada sistem komputer, terutama pada sistem operasi. Meskipun keduanya digunakan untuk mengatur bagaimana data disimpan dan diakses dalam memori, ada perbedaan penting antara keduanya :

## •	Paging :

-	Penggunaan Memori : Dalam paging, memori fisik dibagi menjadi blok-blok yang sama besar yang disebut dengan halaman (pages). Memori virtual juga dibagi menjadi blok-blok yang sama besar yang disebut dengan frame.

-	Alokasi Memori : Proses dipecah menjadi bagian-bagian yang sama besar, yang disebut dengan halaman. Halaman-halaman ini bisa tersebar di memori fisik secara tidak berurutan.

-	Kontinuitas : Tidak memerlukan alokasi kontigu (berurutan) dalam memori fisik.

-	Manajemen Memori : Tidak memerlukan memindahkan seluruh proses ke memori fisik saat proses dieksekusi, hanya halaman-halaman yang dibutuhkan.

-	Penyimpanan : Proses atau data hanya dimuat ke dalam memori fisik saat diperlukan. Halaman-halaman yang tidak diperlukan saat ini tetap berada di disk.

-	Implementasi : Implementasi paging biasanya dilakukan dalam perangkat keras (hardware) dengan dukungan dari sistem operasi.

## •	Swapping :

-	Penggunaan Memori : Swapping melibatkan pertukaran (swap) antara data atau proses yang berada di dalam memori fisik dengan data atau proses yang berada di dalam memori sekunder (biasanya hard disk).

-	Alokasi Memori : Memori fisik harus dialokasikan secara kontigu untuk proses yang di-swap. Ini berarti proses keseluruhan harus dipindahkan ke dalam memori sekunder secara utuh.

-	Kontinuitas : Memerlukan alokasi kontigu dalam memori fisik.

-	Manajemen Memori : Seluruh proses dipindahkan ke dalam memori sekunder saat tidak digunakan untuk memberikan ruang bagi proses lain yang membutuhkan memori fisik.

-	Penyimpanan : Proses atau data yang tidak aktif (tidak digunakan) dipindahkan secara keseluruhan ke dalam memori sekunder, sementara proses atau data yang aktif tetap berada di memori fisik.

-	Implementasi : Swapping dilakukan oleh sistem operasi.

#### Jadi, Perbedaan utama antara paging dan swapping adalah cara di mana data atau proses dipindahkan antara memori fisik dan memori sekunder. Paging membagi proses ke dalam halaman-halaman kecil, sementara swapping memindahkan proses secara utuh antara memori fisik dan memori sekunder.
