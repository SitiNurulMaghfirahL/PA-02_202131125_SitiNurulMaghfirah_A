# Project Deteksi Marka Jalan

Siti Nurul Maghfirah
202131125
Pengolahan Citra A





## Teori mengenai Deteksi Marka Jalan

Markah jalan adalah suatu alat atau benda yang berada di permukaan jalan yang berfungsi untuk memberi suatu informasi tentang jalan. Markah jalan juga dapat diterapkan di fasilitas lain yang digunakan kendaraan untuk parkir maupun daerah khusus dengan kegunaan lainnya.

Markah jalan digunakan di permukaan jalan untuk mengarahkan dan memberi informasi kepada pengendara maupun pejalan kaki. Keseragaman bentuk markah merupakan faktor penting untuk meminimalkan kebingungan dan keraguan atas arti markah tersebut. Telah ada upaya antarnegara untuk melakukan standardisasi bentuk markah jalan.

Marka jalan membujur utuh adalah tanda lalu lintas berupa garis lurus yang tergambar di tengah-tengah permukaan jalan raya. Fungsinya, bila berada di tengah jalan ialah sebagai larangan bagi kendaraan untuk melintasi garis tersebut atau pun sebagai pembagi lajur kendaraan. 
Namun, bila letaknya di tepi jalan, maka fungsinya adalah sebagai tanda peringatan tepi jalur lalu lintas. Makna garis putih lurus adalah pengendara tidak diperbolehkan mendahului kendaraan lain dan tetap berada di jalur masing-masing.

## Menjelaskan tahapan cara menyelesaikan projek

Pada project ini mendeteksi marka jalan menggunakan OpenCV. Berikut adalah tahapan dan cara menyelesaikan projek tersebut:

1. Import Library: Langkah pertama adalah mengimpor library yang dibutuhkan, yaitu OpenCV (`import cv2`) dan NumPy (`import numpy as np`).

2. Membaca Gambar: Menggunakan `cv2.imread('path_to_image.jpg')` untuk membaca gambar jalan dari file yang ditentukan. Pastikan Anda mengganti `'path_to_image.jpg'` dengan path yang benar ke gambar jalan yang ingin Anda deteksi markanya.

3. Konversi ke Skala Abu-abu: Menggunakan `cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)` untuk mengubah gambar menjadi skala abu-abu. Ini dilakukan agar proses deteksi tepi lebih mudah dilakukan.

4. Filter Gaussian: Menggunakan `cv2.GaussianBlur(gray, (5, 5), 0)` untuk menerapkan filter Gaussian pada gambar skala abu-abu. Hal ini membantu mengurangi noise pada gambar.

5. Deteksi Tepi: Menggunakan `cv2.Canny(blur, 50, 150)` untuk mendeteksi tepi pada gambar hasil filter Gaussian. Metode Canny digunakan untuk menemukan tepi dengan intensitas yang signifikan dalam gambar.

6. Transformasi Hough: Menggunakan `cv2.HoughLinesP(edges, 1, np.pi/180, threshold=100, minLineLength=100, maxLineGap=10)` untuk menerapkan transformasi Hough Probabilistic pada gambar tepi. Metode ini digunakan untuk mendeteksi garis-garis marka jalan dalam gambar.

7. Menggambar Garis: Jika garis-garis marka jalan terdeteksi (`lines is not None`), maka digunakan loop `for` untuk menggambar garis-garis tersebut pada gambar asli menggunakan `cv2.line()`.

8. Menampilkan Gambar: Terakhir, menggunakan `cv2.imshow()` untuk menampilkan gambar hasil deteksi marka jalan. Kemudian, `cv2.waitKey(0)` menunggu hingga tombol keyboard ditekan sebelum menutup jendela gambar, dan `cv2.destroyAllWindows()` untuk menutup jendela gambar setelah selesai.

Dengan menjalankan kode di atas, Anda dapat melihat hasil deteksi marka jalan pada gambar yang Anda berikan dan memodifikasi parameter-parameter seperti threshold, panjang garis minimum, dan jarak maksimum antara garis-garis yang terhubung untuk mendapatkan hasil yang optimal.

Pada baris pertama, fig, axs = plt.subplots(1, 2, figsize=(15,5)) menginisialisasi sebuah objek Figure (fig) dan array dari objek Axes (axs) yang memiliki 1 baris dan 2 kolom. figsize=(15,5) menentukan ukuran figure yang akan ditampilkan dengan lebar 15 inci dan tinggi 5 inci.

Pada baris kedua, axs[0].imshow(img) menggunakan imshow() untuk menampilkan gambar img pada sumbu pertama (axs[0]).

Pada baris ketiga, axs[1].plot(color='green') menggunakan plot() untuk membuat sebuah plot kosong pada sumbu kedua (axs[1]). Parameter color='green' digunakan untuk memberikan warna garis plot menjadi hijau.

Terakhir, plt.show() digunakan untuk menampilkan plot yang telah dibuat. Namun, perlu diperhatikan bahwa ada kesalahan penulisan pada kode terakhir. Seharusnya, plt.show() ditulis sebagai plt.show()() untuk memanggil fungsi tersebut dan menampilkan plotnya.