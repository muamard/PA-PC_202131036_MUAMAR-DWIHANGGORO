# PA-PC_202131036_MUAMAR-DWIHANGGORO

# Word Segmentation 

Word segmentation adalah proses membagi teks yang tidak beraturan seperti kalimat atau paragraf menjadi unit-unit kata yang terpisah. Dalam bahasa Inggris, kata-kata biasanya dipisahkan oleh spasi, tetapi dalam beberapa bahasa atau teks khusus seperti tulisan tangan, pemisahan kata tidak selalu jelas. Oleh karena itu, word segmentation menjadi penting dalam banyak aplikasi pemrosesan bahasa alami dan pengenalan karakter optik.

Pada kodingan yang diberikan, terdapat implementasi dari fungsi detect_letters yang mendeteksi huruf-huruf pada sebuah gambar. Berikut adalah tahapan-tahapan dalam menyelesaikan proyek tersebut secara rinci:

1) Impor library dan modul yang diperlukan:
    matplotlib.pyplot untuk membuat plot dan menampilkan gambar.
    skimage.io untuk membaca gambar.
    skimage.color untuk mengonversi gambar menjadi skala abu-abu.
    skimage.measure untuk mengukur properti pada gambar.

2) Tentukan fungsi detect_letters(image_path) untuk mendeteksi huruf-huruf dalam gambar:
    a. Baca gambar menggunakan io.imread(image_path) dan konversi ke skala abu-abu menggunakan color.rgb2gray(image).
    b. Terapkan thresholding pada gambar menggunakan gray < 0.5, yang menghasilkan citra biner.
    c. Bersihkan citra biner menggunakan measure.label(threshold) untuk menghapus objek-objek kecil yang tidak relevan.
    d. Temukan kontur pada citra bersih menggunakan measure.find_contours(clean_image, 0.8).
    e. Lakukan iterasi untuk setiap kontur yang ditemukan:
        Dapatkan koordinat x dan y dari kontur.
        Hitung nilai minimal dan maksimal dari x dan y untuk menentukan batas kotak yang mengelilingi huruf.
        Hitung lebar, tinggi, luas, dan rasio aspek huruf.
        Jika luas huruf lebih besar dari 100 dan rasio aspek lebih besar dari 0.2, tambahkan huruf tersebut ke dalam daftar detected_letters.
    f. Kembalikan daftar huruf yang terdeteksi.
   
3) Tentukan path gambar yang akan digunakan dengan image_path = 'nama.jpg'.

4) Baca gambar menggunakan io.imread(image_path) dan simpan dalam variabel image.

5) Tampilkan gambar awal menggunakan plt.imshow(image) dan atur parameter plot lainnya seperti sumbu, judul, dan sebagainya.

6) Tampilkan gambar menggunakan plt.show() untuk melihat gambar awal.

7) Panggil fungsi detect_letters(image_path) untuk mendapatkan daftar huruf yang terdeteksi dalam gambar.

8) Tampilkan gambar awal dengan kontur huruf menggunakan plt.imshow(image) dan atur parameter plot lainnya seperti sumbu, judul, dan sebagainya.

9) Gunakan plt.Rectangle untuk menggambar kotak dengan koordinat dan dimensi yang sesuai dengan setiap huruf yang terdeteksi.

10) Tambahkan kotak ke plot menggunakan plt.gca().add_patch(rect).

11) Tampilkan gambar dengan kotak huruf yang telah ditambahkan menggunakan plt.show().

Dengan mengikuti langkah-langkah di atas, kodingan akan menampilkan gambar awal dan gambar yang telah dideteksi hurufnya dengan kotak-kotak yang mengelilingi huruf-huruf tersebut.
