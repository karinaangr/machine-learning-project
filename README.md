# machine-learning-project
# Komputasi Machine Learning: Analisis Harapan Hidup (Life Expectancy)

---

## Deskripsi Proyek
Proyek ini merupakan studi penerapan metode *machine learning* untuk menganalisis berbagai faktor yang memengaruhi harapan hidup (*life expectancy*) dari suatu negara. Analisis dilakukan menggunakan indikator kesehatan, sosial, dan ekonomi, seperti tingkat pendidikan, angka kematian, status perkembangan negara (*developed* atau *developing*), konsumsi alkohol, tingkat imunisasi, serta BMI. 

Penyelesaian masalah dalam proyek ini dimodelkan melalui dua pendekatan utama:
*   **Klasifikasi:** Mengidentifikasi status suatu negara ke dalam kategori *Developed* atau *Developing*.
*   **Regresi:** Memprediksi nilai harapan hidup (*life expectancy*) berdasarkan variabel-variabel independen yang tersedia di dalam dataset.

---

## Tujuan Proyek
Studi ini memiliki beberapa sasaran utama, yaitu:
*   Melakukan klasifikasi terhadap status perkembangan negara.
*   Membangun model prediksi nilai *life expectancy* dengan menggunakan metode regresi.
*   Mengevaluasi dan membandingkan performa tiga algoritma *machine learning*: Support Vector Machine (SVM), k-Nearest Neighbor (k-NN), dan Random Forest.
*   Menentukan model terbaik yang dievaluasi berdasarkan performa prediksi serta efisiensi komputasi.

---

## Informasi Dataset
Data yang digunakan bersumber dari dataset **Life Expectancy (WHO)** yang mencakup 193 negara dalam rentang pengamatan tahun 2000 hingga 2015. 
*   Dataset ini memiliki dimensi awal sebanyak 2.938 baris dan 22 kolom.
*   Distribusi status pada data menunjukkan ketidakseimbangan kelas (*imbalanced*), dengan 2.426 observasi berstatus *Developing* dan 512 berstatus *Developed*.
*   Berdasarkan analisis korelasi, fitur yang memiliki pengaruh (korelasi) terbesar terhadap angka harapan hidup adalah lamanya sekolah (*schooling*), angka kematian dewasa (*adult mortality*), dan persentase komposisi pendapatan (*income composition*).

---

## Alur Prapemrosesan Data
Sebelum memasuki tahap pemodelan, dataset melalui proses persiapan yang komprehensif untuk memastikan kualitas hasil prediksi:
*   **Pembersihan Kolom:** Menyeragamkan format nama kolom menjadi huruf kecil, mengganti spasi dengan *underscore*, dan menghapus karakter non-alfanumerik.
*   **Penanganan Nilai Kosong (*Missing Values*):** Melakukan imputasi pada kolom numerik yang kosong dengan nilai median yang dikelompokkan berdasarkan nama negara.
*   **Enkoding Kategori:** Mengubah teks status negara menjadi data numerik, di mana *Developing* = 0 dan *Developed* = 1.
*   **Penanganan Nilai Ekstrem (*Outliers*):** Menerapkan metode *Winsorizing* pada persentil 1 hingga 99 untuk membatasi nilai yang terdistribusi miring (*skewed*), seperti pada kolom GDP, populasi, tingkat penyebaran HIV/AIDS, dan kematian dewasa.
*   **Penyeimbangan Data:** Menggunakan teknik SMOTE untuk menangani kelas target yang tidak seimbang pada tahap klasifikasi.
*   **Penskalaan:** Melakukan normalisasi atau standardisasi data beserta pembagian data latih (*train*) dan uji (*test*).

---

## Model Machine Learning
Proyek ini mengimplementasikan dan membandingkan tiga algoritma pembelajaran mesin untuk pemodelan klasifikasi dan regresi:
*   **Support Vector Machine (SVM)**
*   **k-Nearest Neighbor (k-NN)**
*   **Random Forest**
