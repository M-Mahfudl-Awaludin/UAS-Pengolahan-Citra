# UAS-Pengolahan-Citra

Nama : M Mahfudl Awaludin<br>
Nim : 210401010058

SOAL UJIAN
1. Buatlah program python dengan memanfaatkan imageio, numpy dan matplotlib untuk
mengimplementasikan konsep deteksi tepi dengan menggunakan model Robert, kemudian
bandingkan hasilnya dengan operator Sobel, lakukan analisa. Kumpulkan link github
untuk kode program beserta analisanya
2. Jelaskan apa yang dimaksud dengan segmentasi citra berbasis clustering?
Implementasikan kedalam kode program menggunakan K-Means

Jawaban

1). **Hasil & Analisa**<br>
1. Gambar Asli (Kiri)
Gambar pertama menunjukkan gambar asli dalam skala grayscale. Ini adalah gambar seekor kucing dengan latar belakang yang agak blur. Objek utama yang memiliki detail tinggi adalah bagian mata, kumis, dan batas kepala kucing.

2. Hasil Deteksi Tepi dengan Operator Roberts (Tengah)
- Karakteristik:<br>
Gambar hasil deteksi tepi menggunakan Roberts Operator terlihat memiliki banyak titik bintik atau noise, terutama di area yang seharusnya memiliki perubahan intensitas kecil.
Deteksi tepi terlihat cukup tajam pada bagian yang memiliki perubahan kontras tinggi, seperti kumis kucing, mata, dan batas kepala.
Namun, hasilnya cenderung lebih kasar dan lebih terpengaruh oleh noise dibandingkan dengan metode Sobel.
- Interpretasi:<br>
Operator Roberts menggunakan kernel 2×2, sehingga deteksi tepinya bekerja dengan sangat lokal dan sensitif terhadap perubahan kecil.
Metode ini kurang mampu menangkap detail pada gambar yang memiliki gradasi halus, yang menyebabkan banyak noise muncul pada bagian wajah kucing.
Kurang optimal untuk gambar dengan detail kompleks, tetapi cukup baik untuk pendeteksian tepi cepat pada gambar sederhana.
3. Hasil Deteksi Tepi dengan Operator Sobel (Kanan)
- Karakteristik:<br>
Gambar hasil deteksi tepi menggunakan Sobel Operator terlihat memiliki deteksi yang lebih halus dibandingkan dengan Roberts.
Tepi yang terdeteksi lebih luas, terutama pada kumis, batas kepala, dan mata kucing.
Namun, tampak bahwa gambar masih cukup berisik dengan banyak noise di bagian yang tidak seharusnya terdeteksi sebagai tepi.
- Interpretasi:<br>
Operator Sobel menggunakan kernel 3×3, sehingga hasilnya lebih stabil dibandingkan Roberts dalam menangkap tepi.
Meskipun lebih akurat dalam menangkap tepi yang lebih besar, hasil deteksi masih mengandung noise dalam jumlah yang signifikan.
Sobel lebih baik dibandingkan Roberts dalam menangani detail kompleks, tetapi masih memerlukan filter tambahan untuk mengurangi noise.

**Perbandingan**<br>

| Kriteria                  | Roberts Operator         | Sobel Operator           |
|---------------------------|-------------------------|--------------------------|
| **Ketajaman Tepi**        | Cukup tajam, tetapi kasar | Lebih halus dan lebih jelas |
| **Sensitivitas terhadap Noise** | Sangat tinggi (banyak bintik) | Sedang, tetapi masih cukup tinggi |
| **Ketepatan Deteksi**     | Deteksi kurang stabil   | Lebih baik dalam menangkap detail |
| **Efisiensi Komputasi**   | Cepat (Kernel 2×2)      | Lebih lambat (Kernel 3×3) |
| **Cocok untuk Gambar**    | Gambar sederhana, high contrast | Gambar dengan detail lebih kompleks |

2). **Analisis Hasil Segmentasi Citra dengan K-Means (K=3)**

1. Deskripsi Gambar

- Gambar menunjukkan hasil segmentasi citra menggunakan K-Means Clustering dengan K=3.

- Terdapat dua bagian utama dalam gambar:

  - Bagian kiri: Gambar asli dalam skala abu-abu beserta hasil deteksi tepi menggunakan operator Roberts dan Sobel.

  - Bagian kanan: Hasil segmentasi citra setelah diterapkan K-Means Clustering (K=3) pada gambar asli dan hasil deteksi tepi.

2. Analisis Perbandingan Sebelum dan Sesudah Segmentasi

a. Gambar Asli vs. Hasil Segmentasi

- Pada gambar asli, terdapat berbagai tingkatan intensitas abu-abu yang menunjukkan variasi warna dan tekstur dalam citra.

- Setelah dilakukan segmentasi dengan K=3, gambar terbagi menjadi tiga kelompok intensitas berbeda, menghasilkan efek penyederhanaan warna (quantization).

- Piksel yang memiliki kemiripan dalam intensitas diklasifikasikan ke dalam 3 cluster, yang menghasilkan tampilan gambar dengan batas-batas objek yang lebih jelas.

b. Deteksi Tepi (Roberts & Sobel) Sebelum dan Sesudah Segmentasi

- Sebelum segmentasi:

  - Deteksi tepi dengan Roberts dan Sobel menyoroti fitur utama dalam gambar, seperti kontur bulu kucing dan detail lainnya.

  - Metode Roberts menghasilkan garis yang lebih tipis, sedangkan Sobel menghasilkan garis tepi yang lebih tebal dan lebih jelas.

- Setelah segmentasi dengan K-Means (K=3):

  - Tepi yang terdeteksi dari metode Roberts dan Sobel tetap terlihat tetapi menjadi lebih terklasifikasi ke dalam tiga kelompok warna.

  - Segmentasi ini membuat fitur tepi lebih terorganisir dan membantu dalam pemisahan objek dari latar belakang.

3. Interpretasi Hasil Segmentasi

- Keuntungan Segmentasi dengan K-Means (K=3):

  - Mengurangi kompleksitas gambar dengan hanya menggunakan 3 warna dominan, memudahkan analisis objek.

  - Membantu mengisolasi bagian utama gambar dari latar belakang.

  - Memperjelas fitur penting dalam gambar dengan mengelompokkan piksel yang mirip.

- Kekurangan Segmentasi dengan K=3:

  - Informasi tekstur dan detail halus hilang, karena K-Means hanya mempertimbangkan warna piksel tanpa mempertimbangkan hubungan spasial antar piksel.

  - Bagian latar belakang dan beberapa detail mungkin terkelompok ke dalam cluster yang sama, sehingga beberapa informasi dalam gambar dapat tersamarkan.



