# Laporan Proyek Machine Learning - Kevin Chandra

## Domain Proyek
Menurut tautan [Gender and Crime](https://law.jrank.org/pages/1250/Gender-Crime-Differences-between-male-female-offending-patterns.html), Di dunia kiriminal perempuan memiliki peluang lebih kecil dalam hampir semua kategori kriminal kecuali prostitusi. Hal ini berlaku untuk semua negara, ras, etnis, dan periode sejarah. Pelaku perempuan lebih sering melakukan tindakan kriminal sendiri, bukan dalam kelompok. Laki-laki sangat dominan dalam kejahatan yang lebih terorganisir.

Dataset jenis ini memberikan gambaran umum tentang ciri - ciri perempuan dan laki - laki di semua kelompok umur. Tujuan dari proyek ini adalah untuk mengklasifikasikan manusia menurut perbedaan rambut dan ukuran bentuk wajah.

Terdapat kriminalitas di wilayah tertentu dimana polisi butuh mengetahui gender dari pelaku kriminal berdasarkan informasi yang didapat dari data yang ada. Dengan menggunakan model machine learning ini, polisi dapat dengan mudah mengetahui jenis kelamin pelaku dengan data - data yang telah mereka kumpulkan. Tidak terbatas pada polisi, detektif pun juga bisa menggunakan model ini untuk melakukan investigasi pelaku kriminal.

## Business Understanding
Setiap manusia memiliki perbedaan ciri - ciri fisik seperti warna kulit, warna dan bentuk rambut, bentuk muka, ukuran badan, bentuk badan, bentuk dan warna mata serta ciri fisik yang lainnya. Di dalam dataset ini, perbedaan ciri - ciri mencakup ukuran bentuk wajah dan rambut, sehingga masalah yang akan saya angkat di proyek ini adalah mengklasifikasikan jenis kelamin manusia berdasarkan ukuran bentuk wajah dan panjang rambut.

### Problem Statements
Bagaimana cara membedakan karakteristik pelaku antara laki-laki dan perempuan menggunakan machine learning?

### Goals
Dapat memprediksi jenis kelamin pelaku berdasarkan ciri - ciri ukuran bentuk wajah dan panjang rambut.

### Solution statements
1. Menggunakan Correlation Matrix untuk melihat korelasi antara ciri - ciri yang ada terhadap jenis kelamin pada dataset.
2. Menggunakan dua model machine learning untuk melakukan prediksi jenis kelamin. Kedua model yang akan digunakan adalah model untuk klasifikasi antara laki - laki atau perempuan. Model - model tersebut yaitu:
 - **XGBClassifier**.
    Gradient boosting adalah sebuah algoritma yang berusaha untuk memprediksi dengan akurat variabel target dengan menggabungkan perkiraan dari sebuah set yang lebih    sederhana.
    - Kelebihan:
      XGBClassifier bekerja dengan baik pada data sederhana, data dengan subkelompok, data besar, dan data yang rumit.
    - Kelemahan:
      XGBClassifier tidak berfungsi dengan baik dan dapat menimbulkan masalah pada *sparse* data dan data yang sangat tersebar.

 - **LogisticRegression**.
    LogisticRegression menggunakan sebuah persamaan sebagai representasi seperti regresi linier. Nilai input (x) akan dikombinasikan dengan linier menggunakan berat atau nilai koefisien (ditandai dengan huruf kapital Yunani Beta ) untuk memprediksi hasil nilai (y).
    - Kelebihan:
      LogisticRegression memilik akurasi yang baik untuk dataset sederhana dan memiliki kinerja baik ketika datase dipisahkan secara linier.
    - Kelemahan:
      Masalah *non-linier* tidak dapat diselesaikan dengan LogisticRegression karena memiliki *linear decision interface*. Data yang dapat dipisahkan secara linier jarang ditemukan dalam skenario dunia nyata.

## Data Understanding
Dataset yang saya gunakan adalah dataset klasifikasi jenis kelamin yang dapat didownload pada link berikut: [link](https://www.kaggle.com/elakiricoder/gender-classification-dataset). Dataset ini adalah dataset klasifikasi jenis kelamin, dataset ini berisikan data - data untuk membedakan antara perempuan atau laki - laki berdasarkan ciri - ciri yang ada. Dataset ini umumnya digunakan bagi para pemula yang berminat mempelajari Machine Learning. Selain itu, dataset ini juga terbilang sederhana karena kebanyakan nilai yang terdapat di dalamnya adalah benar(1) atau salah(0).

Pada dataset ini terdapat delapan kolom, yaitu:
- long_hair : mengindikasi apakah ia memiliki rambut panjang. Jika ya maka memiliki nilai 1, dan jika tidak maka memiliki nilai 0.
- forehead_width_cm : mengindikasi lebar dahi yang dimiliki orang tersebut dengan satuan sentimeter.
- forehead_height_cm : mengindikasi tinggi dahi yang dimiliki orang tersebut dengan satuan sentimeter.
- nose_wide : mengindikasi apakah orang tersebut memiliki hidung yang lebar. Jika ya maka memiliki nilai 1, dan jika tidak maka memiliki nilai 0.
- nose_long : mengindikasi apakah orang tersebut memiliki hidung yang panjang. Jika ya maka memiliki nilai 1, dan jika tidak maka memiliki nilai 0.
- lips_thin : mengindikasi apakah orang tersebut memiliki bibir yang tipis. Jika ya maka memiliki nilai 1, dan jika tidak maka memiliki nilai 0.
- distance_nose_to_lip_long : mengindikasi apakah orang tersebut memiliki jarang antara hidung ke bibir yang jauh. Jika ya maka memiliki nilai 1, dan jika tidak maka
 memiliki nilai 0.
- gender : mengindikasi apakah orang tersebut laki - laki atau perempian. Jika laki - laki maka memiliki nilai 1, dan jika perempuan makan memiliki nilai 0.

Visualisasi data yang saya gunakan pada dataset ini adalah visualisasi menggunakan Correlation Matrix dan Pie Chart. Berikut merupakan kumpulan gambar dari hasil visualisasi data yang saya buat adalah sebagai berikut:
- **Pie Chart**
  ![Gambar pertama](https://user-images.githubusercontent.com/92379646/137475184-f07883f1-d062-4582-bad5-d8aef1050743.png)
  ![Barplot kedua](https://user-images.githubusercontent.com/92379646/136966152-fc7d69d6-882d-4179-9e24-9ae677a626fa.png)
  ![Gambar ketiga](https://user-images.githubusercontent.com/92379646/136966169-920a4dfa-fcd3-481b-a26d-86bbfa94e2ec.png)
  ![Gambar keempat](https://user-images.githubusercontent.com/92379646/137474869-0f6a12b3-5ff1-4820-b08f-4cbc71fb2441.png)
  ![Gambar kelima](https://user-images.githubusercontent.com/92379646/137474881-e0f5af22-1094-45d9-928a-dc37e0fd9831.png)
  ![Gambar keenam](https://user-images.githubusercontent.com/92379646/136966184-f7c2ad5a-68bd-47fe-8959-37f53e0f4f82.png)
- **Correlation Matrix**
 ![Gambar Korelasi](https://user-images.githubusercontent.com/92379646/139410323-76a3f0d3-4379-4e24-95eb-5e612041a586.png)

Dari hasil map korelasi metrik saya melakukan drop pada kolom long_hair karena memiliki nilai yang lemah.

## Data Preparation
Teknik data preparation yang saya gunakan ada tiga, yaitu:
- **Train-test-splitting**
 Teknik ini digunakan untuk mengevaluasi performa dari algoritma machine learning. Saya menggunakan teknik ini untuk membagi data menjadi training dan testing set. Data yang lebih banyak akan digunakan untuk training set dan data yang lebih sedikit akan digunakan untuk testing set.
- **Standardization**
 Teknik ini digunakan untuk mengurangkan mean (nilai rata-rata) kemudian membaginya dengan standar deviasi untuk menggeser distribusi. Saya menggunakan teknik ini karena proses scaling dan standardisasi membantu untuk membuat fitur data menjadi bentuk yang lebih mudah diolah oleh algoritma.

- **Encoding**
 Teknik ini digunakan untuk mengubah variabel categorical ke nilai numerik, sehingga data tersebut bisa dengan mudah digunakan pada model machine learning. Saya menggunakan teknik ini karena machine learning tidak dapat menangani secara langsung kategori data dengan bentuk teks, sehingga harus diubah terlebih dahulu ke dalam bentuk numerik.

## Modeling
Model yang saya gunakan pada proyek ini adalah:
- **XGBClassifier**.
  Gradient boosting adalah sebuah algoritma yang berusaha untuk memprediksi dengan akurat variabel target dengan menggabungkan perkiraan dari sebuah set yang lebih sederhana. Gradien boost meminimalkan fungsi (L1 dan L2) yang menggabungkan *convex loss function*. Pelatihan berlangsung secara iteratif dengan menambahkan pohon baru yang memprediksi residual atau *error* pohon sebelumnya yang kemudian digabungkan dengan pohon sebelumnya untuk membuat prediksi akhir. Hal ini disebut gradient boosting karena menggunakan algoritma penurunan gradien untuk meminimalkan *loss* saat menambahkan model baru.
  Ilustrasi dari pernyataan tersebut dapat dilihat pada gambar berikut:
  ![Gambar ilustrasi 1](https://user-images.githubusercontent.com/92379646/138396922-2e68d378-ed99-4bc1-8502-17caf371c5a2.png)

- **LogisticRegression**.
  LogisticRegression menggunakan sebuah persamaan sebagai representasi seperti regresi linier. Nilai input (x) akan dikombinasikan dengan linier menggunakan berat atau nilai koefisien (ditandai dengan huruf kapital Yunani Beta ) untuk memprediksi hasil nilai (y). LogisticRegressien digunakan untuk memprediksi *odds* menjadi kasus berdasarkan nilai-nilai variabel independen (prediktor). *Odds* didefinisikan sebagai probabilitas yang hasilnya adalah kasus dibagi dengan probabilitas yang bukan *instance*. 
  Ilustrasi dari pernyataan di atas dapat dilihat pada gambar berikut:
  ![Gambar ilustrasi 2](https://user-images.githubusercontent.com/92379646/138398016-6a76495d-2b02-4c8a-b158-7ea1b9e20688.png)

Kedua model menggunakan tahap yang sama. Pertama akan dilakukan fit kepada model dari data yang telah disiapkan dan dibersihkan sebelumnya, dan kemudian data akan diprediksi oleh model.

Setelah mendapatkan hasil dari kedua model, saya membandingkan kedua model menggunakan tabel agar lebih mudah dilihat.
![Perbandingan](https://user-images.githubusercontent.com/92379646/137468894-65154d43-fd36-4933-afef-4ca21fda0e6f.png)

Dari tabel tersebut, bisa dilihat bahwa akurasi, presisi, dan F1 dari XGBClassifier lebih baik daripada model LogisticRegressor, maka saya dapat menyimpulkan model XGBClassifier merupakan model yang lebih baik.

## Evaluation
Agar kita dapat lebih memahami penjelasan tentang evaluasi metrik, ada beberapa hal yang perlu dilihat:
1. True Positive(TP)
 True positive adalah sebuah hasil dimana model dengan benar memprediksi kelas positive.
2. True Negative(TN)
 True negative adalah sebuah hasil dimana model dengan benar memprediksi kelas negatif.
3. False Positive(FP)
 False positive adalah sebuah hasil dimana model salah memprediksi kelas positive.
4. False Negative(FN)
 False negative adalah sebuah hasil dimana model salah memprediksi kelas negative.

Dalam proyek ini, saya membuat model dengan empat evaluasi metrik, yaitu:
- **Accuracy**
 Accuracy mewakili jumlah contoh data yang diklasifikasikan dengan benar di atas jumlah total contoh data.
 Rumus: (TP+TN)/(TP+TF+FP+FN)
- **Precision**
 Presisi adalah rasio TP dengan total TP dan FP
 Rumus: TP/(TP+FP)
- **Recall**
 Recall secara harfiah berarti berapa banyak TP yang ditemukan.
 Rumus: TP/(TP+FN)
- **F1 Score**
 F1 score adalah ukuran yang digunakan untuk menilai kualitas masalah klasifikasi biner serta masalah dengan beberapa label biner atau beberapa kelas.
 Rumus: 2(Precision*Recall)/(Precision+Recall) = TP/(TP+1/2(FP+FN))

Berikut adalah hasil evaluasi metrik kedua model dengan menggunakan tabel:
![Perbandingan](https://user-images.githubusercontent.com/92379646/137468894-65154d43-fd36-4933-afef-4ca21fda0e6f.png)

Kemudian saya akan memprediksi data yang saya siapkan sebelumnya dengan menggunakan model terbaik, yaitu XGBClassifier. Hasilnya adalah sebagai berikut:
![Hasil](https://user-images.githubusercontent.com/92379646/137054657-db8a8fb2-f9b7-4360-b0ca-a4d1ea3897d9.png)

Dari tabel hasil tersebut dapat kita lihat bahwa jenis kelamin yang memiliki nilai 1 (laki - laki) mempunyai ciri - ciri yang dominan memiliki nilai 1 (true) pada kolom - kolom fitur. Sehingga saya dapet menyimpulkan bahwa semakin banyak nilai true yang dimiliki pada fitur, semakin besar kemungkinan prediksi jenis kelaminnya sebagai laki - laki, begitu juga sebaliknya. 