TEORI DAN PENJELASAN PROGRAM

Materi Deteksi Daun
>Pengenalan
    Deteksi daun adalah proses mengenali dan memisahkan daun dari objek lain dalam gambar. Ini biasanya dilakukan dalam penelitian botani, pertanian, dan lingkungan untuk tujuan analisis, pemantauan kesehatan tanaman, dan klasifikasi jenis tanaman.

>Langkah-Langkah Deteksi Daun

1. Pra-Pemrosesan Gambar
- Konversi Warna: Gambar dikonversi dari format RGB/BGR ke HSV. Format HSV memisahkan informasi warna dari intensitas, sehingga lebih mudah untuk mendeteksi warna tertentu.
- Pengurangan Noise: Penggunaan filter seperti Gaussian blur untuk mengurangi noise dalam gambar.

2. Thresholding
    Thresholding adalah teknik untuk memisahkan objek dari latar belakang berdasarkan nilai piksel. Dalam deteksi daun, thresholding dilakukan berdasarkan rentang warna hijau daun.

3. Masking
   Masking adalah proses membuat gambar biner (hitam-putih) di mana piksel dalam rentang warna daun ditandai sebagai putih (1), dan lainnya sebagai hitam (0). Mask ini kemudian digunakan untuk mengekstraksi daun dari gambar asli.

4. Segmentasi
   Segmentasi adalah proses memisahkan daun dari latar belakang atau objek lain dalam gambar. Segmentasi dilakukan dengan operasi bitwise-AND antara gambar asli dan mask.

5. Kontur dan Fitur
   Setelah segmentasi, kontur daun dapat diidentifikasi. Fitur-fitur seperti bentuk, ukuran, dan tekstur daun dapat diekstraksi untuk analisis lebih lanjut.

> Implementasi
Implementasi deteksi daun dalam kode di atas melibatkan langkah-langkah berikut:
- Mengkonversi gambar ke format HSV.
- Mendefinisikan rentang warna untuk deteksi daun.
- Melakukan thresholding untuk membuat mask daun.
- Menggunakan mask untuk mengekstrak dan menampilkan segmentasi daun.

> Aplikasi
- Pemantauan Kesehatan Tanaman: Deteksi penyakit, nutrisi, dan kelembaban daun.
- Klasifikasi Tanaman: Identifikasi spesies tanaman berdasarkan bentuk dan ukuran daun.
- Pertanian Presisi: Pemantauan tanaman untuk meningkatkan hasil dan efisiensi.

Deteksi daun adalah alat penting dalam botani dan pertanian modern, memungkinkan analisis dan pemantauan yang lebih efisien dan akurat.


Penjelasan Program:
    Program ini bertujuan untuk mendeteksi dan melakukan segmentasi objek belimbing dan daun dalam gambar menggunakan pemrosesan citra dengan OpenCV dan visualisasi hasilnya menggunakan Matplotlib.

>Langkah-langkah Program
1. Import Library
   Program ini menggunakan library cv2 untuk pemrosesan citra, numpy untuk operasi numerik, dan matplotlib.pyplot untuk visualisasi gambar.

2. Fungsi plot_images
   Fungsi ini digunakan untuk menampilkan beberapa gambar dalam subplot. Gambar ditampilkan dalam grid 2x2 dengan judul masing-masing gambar. Jika ada parameter cmap, gambar akan ditampilkan dengan colormap yang sesuai; jika tidak, gambar dikonversi ke format RGB untuk visualisasi.

3. Baca Gambar
   Gambar dibaca dari path yang diberikan dan disimpan dalam variabel image.

4. Konversi ke Format HSV
   Gambar BGR dikonversi ke format HSV untuk memudahkan deteksi warna tertentu. Format HSV memisahkan informasi warna (Hue) dari intensitas (Value), sehingga lebih mudah untuk mendeteksi warna spesifik seperti belimbing dan daun.

5. Definisikan Rentang Warna
   Rentang warna dalam format HSV didefinisikan untuk mendeteksi belimbing (warna kuning) dan daun (warna hijau).

6. Thresholding
   Melakukan thresholding pada gambar HSV untuk mendapatkan mask belimbing dan daun. Mask adalah gambar biner di mana piksel dalam rentang warna yang ditentukan ditandai sebagai putih (1) dan piksel di luar rentang warna ditandai sebagai hitam (0).

7. Segmentasi dengan Bitwise-AND
   Melakukan segmentasi belimbing dan daun dengan operasi bitwise-AND antara gambar asli dan mask yang telah dibuat. Ini menghasilkan gambar yang hanya menampilkan area belimbing atau daun.

8. Menampilkan Gambar
   Gambar asli, mask belimbing, hasil segmentasi belimbing, dan hasil segmentasi daun ditampilkan menggunakan fungsi plot_images. Gambar ditampilkan dalam subplot dengan judul masing-masing untuk memudahkan interpretasi.

Program ini menyediakan cara untuk mendeteksi dan menampilkan objek spesifik (belimbing dan daun) dalam gambar menggunakan teknik pemrosesan citra dasar dengan OpenCV.
