# Laporan Proyek Machine Learning - Icha Aulia Putri Ambarwati

# System Recommendation

### **Project Overview: Sistem Rekomendasi Buku**

Di era digital saat ini, minat membaca buku secara perlahan mengalami penurunan. Salah satu alasan utama adalah banyak orang merasa kesulitan menemukan buku yang sesuai dengan minat dan preferensi mereka. Ketika seseorang membaca buku yang tidak sesuai dengan selera atau kebutuhan mereka, pengalaman membaca menjadi kurang menyenangkan. Hal ini menyebabkan munculnya persepsi bahwa membaca buku adalah kegiatan yang membosankan.

Selain itu, setelah menyelesaikan satu buku, sebagian pembaca sering merasa kebingungan dalam menentukan buku berikutnya yang ingin mereka baca. Kurangnya referensi yang personal atau rekomendasi yang tepat membuat pembaca kehilangan arah dan akhirnya tidak melanjutkan kebiasaan membaca.

Untuk mengatasi permasalahan tersebut, sistem rekomendasi buku menjadi solusi yang relevan dan efektif. Sistem ini dapat memberikan saran buku berdasarkan preferensi pengguna, histori bacaan, serta kemiripan konten dengan buku-buku yang pernah disukai. Dengan demikian, pengguna dapat menemukan buku yang lebih sesuai dengan minat mereka dan membangun kebiasaan membaca yang lebih konsisten dan menyenangkan.

---

### **Referensi Pendukung**

Berikut ini beberapa referensi yang dapat digunakan sebagai landasan untuk laporan dan sitasi:

1. **Putra, R. A. (2022).** *Rekomendasi Buku Menggunakan Collaborative Filtering.* Jurnal Teknologi Informasi dan Komputer, 10(2), 45-52.
    
    > [IEEE Format]: R. A. Putra, "Rekomendasi Buku Menggunakan Collaborative Filtering," Jurnal Teknologi Informasi dan Komputer, vol. 10, no. 2, pp. 45–52, 2022.
    > 
2. **Setiawan, D. (2021).** *Minat Baca Generasi Muda dan Solusi Digitalisasi Literasi.* Prosiding Seminar Nasional Literasi Digital, 2021.
    
    > [IEEE Format]: D. Setiawan, "Minat Baca Generasi Muda dan Solusi Digitalisasi Literasi," in Prosiding Seminar Nasional Literasi Digital, 2021.
    > 

## **Business Understanding**

Membaca merupakan kegiatan penting yang mendukung pembelajaran dan pengembangan diri. Namun, minat baca masyarakat, khususnya generasi muda, menunjukkan tren penurunan. Banyak orang merasa bahwa membaca adalah kegiatan yang membosankan atau sulit untuk dilanjutkan. Salah satu penyebab utama adalah ketidaksesuaian antara buku yang dibaca dengan preferensi pribadi pembaca. Di samping itu, ketiadaan sistem yang dapat merekomendasikan bacaan yang relevan juga menghambat kebiasaan membaca. Oleh karena itu, diperlukan pemahaman yang mendalam terhadap masalah ini dan solusi teknologi yang dapat meningkatkan pengalaman membaca.

### **Problem Statements**

1. **Banyak orang menganggap membaca buku adalah kegiatan yang membosankan.**
    
    Hal ini terjadi karena mereka tidak menemukan buku yang sesuai dengan minat, preferensi, atau kebutuhan mereka.
    
2. **Pembaca kesulitan menemukan buku selanjutnya setelah menyelesaikan sebuah bacaan.**
    
    Kurangnya panduan atau referensi personal membuat pembaca ragu dalam memilih buku berikutnya, yang akhirnya menghentikan kebiasaan membaca.
    
3. **Tidak adanya sistem rekomendasi buku yang personal dan mudah diakses.**
    
    Sebagian besar sistem rekomendasi bersifat umum, dan tidak mempertimbangkan selera spesifik dari masing-masing pengguna.
    

---

### **Goals**

1. **Meningkatkan pengalaman membaca dengan menyediakan rekomendasi buku yang sesuai dengan minat pengguna.**
    
    Dengan ini, pengguna dapat menikmati membaca dan melihat buku sebagai sumber hiburan maupun pengetahuan yang menyenangkan.
    
2. **Membantu pengguna dalam menentukan bacaan selanjutnya berdasarkan histori bacaan dan preferensi mereka.**
    
    Sistem akan menyarankan buku yang berkaitan atau mirip dengan buku yang pernah dibaca dan disukai oleh pengguna.
    
3. **Mengembangkan sistem rekomendasi buku berbasis preferensi pengguna yang mudah digunakan dan dapat diakses secara luas.**
    
    Sistem ini akan menjadi alat bantu yang mendukung kebiasaan membaca dan dapat diintegrasikan dalam berbagai platform digital.
    

---

### **Solution Statements**

Untuk mencapai tujuan yang telah ditetapkan, berikut ini adalah pendekatan solusi yang dapat digunakan dalam pengembangan sistem rekomendasi buku:


1. **Collaborative Filtering**
    
    Pendekatan ini memberikan rekomendasi berdasarkan preferensi pengguna lain yang memiliki kebiasaan membaca serupa. Jika pengguna A dan B memiliki kesamaan dalam membaca beberapa buku, maka sistem akan menyarankan buku yang dibaca B namun belum dibaca A, dan sebaliknya.
   
2. **Content-Based Filtering**
    
    Pendekatan ini merekomendasikan buku berdasarkan kemiripan atribut konten (Judul, Penulis, Penerbit) dari buku-buku yang pernah disukai atau dibaca oleh pengguna. Misalnya, jika seorang pengguna menyukai buku fiksi ilmiah dengan tema futuristik, sistem akan merekomendasikan buku lain dengan karakteristik yang serupa.
    
## **Data Understanding**

Dataset yang digunakan dalam proyek sistem rekomendasi buku ini diambil dari [Kaggle - Book Recommendation Dataset oleh Arash Nic](https://www.kaggle.com/datasets/arashnic/book-recommendation-dataset). Dataset ini terdiri dari tiga file utama yaitu `Books.csv`, `Users.csv`, dan `Ratings.csv`, yang masing-masing berisi informasi buku, pengguna, dan interaksi berupa rating. Total jumlah data dari ketiga file mencapai lebih dari 1 juta entri, sehingga dataset ini cukup kaya dan cocok digunakan untuk membangun sistem rekomendasi berbasis content-based filtering dan collaborative filtering.

### **Ringkasan Dataset**

### 1. **Books.csv**

- Jumlah baris: 271.360
- Jumlah kolom: 8
- Kolom: `ISBN`, `Book-Title`, `Book-Author`, `Year-Of-Publication`, `Publisher`, `Image-URL-S`, `Image-URL-M`, `Image-URL-L`
- **Missing Value**:
    - `Book-Author`: 2
    - `Publisher`: 2
    - `Image-URL-L`: 3
- **Outlier** : 
    - Number of low outliers: 9078
    - Number of high outliers: 17
    - Total number of outliers: 9095

   ![image](https://github.com/user-attachments/assets/98ff9c05-6ae7-4fb1-8891-1b0ceec77963)

- **Duplikat**: 0

### 2. **Users.csv**

- Jumlah baris: 278.838
- Jumlah kolom: 3
- Kolom: `User-ID`, `Location`, `Age`
- **Missing Value**:
    - `Age`: 110.762 (banyak pengguna tidak mengisi usia)
- **Outlier Usia**: 1.084 (usia ekstrem, misalnya < 5 atau > 100)

  ![image](https://github.com/user-attachments/assets/422ef4a5-2ef6-4aa7-a18e-f1a066dd5137)
- **Duplikat**: 0

### 3. **Ratings.csv**

- Jumlah baris: 1.149.780
- Jumlah kolom: 3
- Kolom: `User-ID`, `ISBN`, `Book-Rating`
- **Missing Value**: 0
- **Duplikat**: Tidak ditemukan
- **Distribusi Rating**:
    - Rating 0 mendominasi hampir separuh data
    - Rating eksplisit (1–10) paling banyak adalah rating 8
- **User Teraktif**: User-ID `11676` (memberikan rating terbanyak)

---

### **Deskripsi Variabel dalam Dataset**

### **Books.csv**

- `ISBN`: Nomor unik untuk mengidentifikasi setiap buku.
- `Book-Title`: Judul buku.
- `Book-Author`: Nama penulis buku.
- `Year-Of-Publication`: Tahun terbit buku.
- `Publisher`: Nama penerbit buku.
- `Image-URL-S`: URL gambar sampul berukuran kecil.
- `Image-URL-M`: URL gambar sampul berukuran sedang.
- `Image-URL-L`: URL gambar sampul berukuran besar.

### **Users.csv**

- `User-ID`: ID unik untuk setiap pengguna.
- `Location`: Lokasi pengguna dalam format “kota, negara bagian, negara”.
- `Age`: Usia pengguna.

### **Ratings.csv**

- `User-ID`: ID pengguna yang memberikan rating.
- `ISBN`: Nomor buku yang diberi rating.
- `Book-Rating`: Nilai rating yang diberikan pengguna terhadap buku (rentang 0–10, di mana 0 bisa berarti implicit rating atau belum dibaca).

### **Exploratory Data Analysis (EDA) & Visualisasi**
- Distribusi Rating Buku
  - **Insight** : Mayoritas rating bernilai 0 (lebih dari 700.000), yang kemungkinan besar menunjukkan rating tidak diberikan atau kosong. Rating yang benar-benar diberikan lebih banyak di angka 8, diikuti 7, 10, dan 9. Artinya, ketika pengguna memberi rating, mereka cenderung memberikan penilaian yang positif.

![image](https://github.com/user-attachments/assets/e2901b77-03c2-4dd5-afcf-5cc428d6bb39)
- Top 5 Buku yang memiliki Rating terbanyak :
    - Wild Animus   :     2502.0
    - The Lovely Bones: A Novel    :    1295.0
    - The Da Vinci Code      :   883.0
    - Divine Secrets of the Ya-Ya Sisterhood: A Novel    :     732.0
    - The Red Tent (Bestselling Backlist)     :    723.0
- Top active user dengan ID : 11676
- Top 10 Negara dengan Jumlah User Terbanyak
  - **Insight** : USA mendominasi jumlah pengguna dengan selisih yang sangat jauh dibanding negara lainnya. Negara seperti Kanada, UK, dan Jerman juga memiliki cukup banyak pengguna, namun jauh di bawah USA.
  - **Implikasi** : Implikasi: Data sangat didominasi oleh pengguna dari USA, sehingga preferensi buku dan perilaku rating bisa sangat bias terhadap budaya atau tren di USA.

![image](https://github.com/user-attachments/assets/382bf172-305b-4cef-b363-9bf7032f88d5)
- Distribusi Usia Pengguna
  - **Insight** : Mayoritas pengguna berada di rentang usia 20–40 tahun, dengan puncak sekitar usia 25 tahun. Terlihat distribusi miring ke kanan (right-skewed), artinya ada lebih banyak pengguna muda dibanding pengguna yang lebih tua.
  - **Implikasi** : Sistem rekomendasi mungkin lebih relevan untuk kelompok usia muda karena mereka adalah mayoritas pengguna.

![image](https://github.com/user-attachments/assets/25ac21d9-02d7-4af0-8d3e-e532811a090e)
- Distribusi Pengguna Berdasarkan Kelompok Usia
  - **Insight** : Kelompok usia 21–30 tahun adalah yang paling dominan, disusul oleh 31–40 tahun dan 41–50 tahun. Kelompok usia anak-anak (0–10 tahun) dan lansia (71+) jumlahnya sangat kecil.
  - **Implikasi** : Rekomendasi buku yang bersifat dewasa atau young-adult lebih relevan untuk ditonjolkan dibanding buku anak-anak atau lansia.

![image](https://github.com/user-attachments/assets/c2a59a8c-f394-4526-8375-4b9f585bc4f3)

## Data Preparation
- **Mengubah Tipe Data pada kolom Year-Of-Publisher**

  Penjelasan: Kolom Year-Of-Publication diubah menjadi tipe numerik. Jika terdapat data tidak valid (seperti string atau simbol), akan dikonversi menjadi NaN.

  Tujuan: Supaya bisa dianalisis atau difilter sebagai angka, bukan string.Supaya tahun bisa dianalisis dan difilter secara numerik.
- **Menghapus Outlier pada Year-Of-Publication**
  Penjelasan: Menghapus data buku dengan tahun publikasi yang tidak wajar (di luar 1980–2024).

  Tujuan: Menghindari data outlier yang bisa mengganggu analisis atau rekomendasi (misalnya tahun 0 atau 9999).
- **Menghapus Nilai Kosong pada Kolom Penting**
  
  Penjelasan: Baris yang memiliki NaN di kolom Book-Author, Publisher, atau Image-URL-L dihapus..

  Tujuan: Kolom ini penting untuk filtering konten dan tampilan aplikasi, jadi harus lengkap.
- **Menghapus Outlier pada Kolom Umur**
  Penjelasan: Menghapus data pengguna dengan umur yang tidak wajar berdasarkan batas bawah dan atas yang telah ditentukan.

  Tujuan: Umur ekstrem atau tidak masuk akal bisa bias terhadap analisis demografi pengguna.
- **Menggabungkan Tabel Rating, User, dan Buku**
  Penjelasan: Menggabungkan tabel rating dengan user dan buku untuk mendapatkan data lengkap dalam satu tabel.

  Tujuan: Collaborative Filtering membutuhkan informasi pengguna, buku, dan rating dalam satu struktur data.
- **Menghapus Rating dengan Nilai Nol**
  Penjelasan: Hanya rating eksplisit (1–10) yang dipertahankan. Rating 0 dihapus karena tidak mewakili interaksi nyata.
  
  Tujuan: Collaborative Filtering membutuhkan informasi pengguna, buku, dan rating dalam satu struktur data.
- **Menyaring data user dan buku**
  Penjelasan: Menyaring hanya user dan buku yang muncul lebih dari satu kali.

  Tujuan: Untuk meningkatkan kualitas data, karena interaksi tunggal sulit digunakan dalam Collaborative Filtering.
- **Membersihkan dan Menangani Kolom Umur**
  Penjelasan: Membersihkan nilai usia ekstrem dan mengganti nilai kosong dengan -1 sebagai penanda "tidak diketahui".

  Tujuan: Menghindari error saat analisis, dan tetap bisa mengenali pengguna yang tidak mengisi umur.
- **Feature Selection untuk Collaborative Filtering**
  Penjelasan: Mengambil hanya kolom penting untuk modeling dan mengganti nama kolom agar lebih ringkas.
- **Data Preparation untuk Collaborative Filtering**
  - Format data sesuai Surprise
    - Penjelasan: Library Surprise membutuhkan data dalam format khusus. Kode Reader(rating_scale=(1, 10)) digunakan untuk menentukan skala rating yang digunakan dalam dataset (antara 1 hingga 10). Kemudian Dataset.load_from_df(...) mengubah DataFrame menjadi format yang bisa diproses oleh Surprise.

  - Train-Test Split
    - Penjelasan: Membagi data menjadi set pelatihan dan pengujian menggunakan train_test_split untuk evaluasi model. Parameter test_size=0.2 berarti 20% data digunakan untuk pengujian, sedangkan random_state=42 menjamin reprodusibilitas.
  Tujuan: Supaya data lebih siap dipakai dalam model Collaborative Filtering dan lebih mudah digunakan dalam coding.
- **Data Preparation untuk Content-Based Filtering**
  - Duplikasi Data

    - Penjelasan: Menyalin DataFrame df_book dan df_Ratings ke variabel lokal books dan ratings untuk menghindari modifikasi data asli.

  - Rename dan Seleksi Kolom Buku

    - Penjelasan: Mengubah nama kolom pada dataset buku agar lebih deskriptif dan memilih hanya kolom yang relevan: ISBN, judul, penulis, penerbit, dan link gambar besar (img_l).

  - Menghapus Data Kosong

    - Penjelasan: Membersihkan data dengan menghapus entri buku yang memiliki informasi penting (judul, penulis, penerbit, gambar) yang kosong. Ini penting agar sistem rekomendasi tidak menghasilkan output yang tidak lengkap.

  - Gabungkan Fitur Buku

    - Penjelasan: Membuat fitur gabungan (combined_features) dari judul, penulis, dan penerbit untuk mewakili konten buku sebagai satu string. Ini akan digunakan untuk ekstraksi fitur TF-IDF.

  - Threshold Relevansi

    - Penjelasan: Menentukan ambang batas nilai rating (RELEVANT_THRESHOLD = 7) untuk menilai apakah suatu buku dianggap relevan dalam evaluasi precision dan recall.

  - Filter dan Persiapan Rating

    - Penjelasan:

      - Menghapus entri rating yang mengandung nilai kosong.

      - Menyaring rating berdasarkan ISBN buku yang masih tersedia.

      - Menambahkan kolom user_id sebagai identifikasi pengguna. Ini mempersiapkan data untuk evaluasi dan sistem rekomendasi.

  - Ekstraksi Fitur TF-IDF

    - Penjelasan: Mengubah teks combined_features menjadi vektor numerik menggunakan TF-IDF Vectorizer. Konfigurasi stop_words='english', max_features=5000, dan lainnya dibuat untuk mengoptimalkan akurasi dan efisiensi memori.

  - Cleaning dan Index Judul

    - Penjelasan: Menambahkan kolom clean_title dengan judul yang sudah dibersihkan (huruf kecil dan tanpa simbol khusus) agar pencarian judul lebih konsisten dan efisien. Kolom ini dijadikan indeks pencarian cepat dengan title_to_index.
  
## Modeling
Untuk menyelesaikan permasalahan pencarian buku yang relevan bagi pengguna, saya mengembangkan **dua model sistem rekomendasi berbeda**. Masing-masing pendekatan memiliki kelebihan dan keterbatasan, yang dijelaskan di bawah.

---

## Model 1: Collaborative Filtering menggunakan SVD (Singular Value Decomposition)
### Arsitektur Model:
- model_svd = SVD()
    Menggunakan algoritma SVD dari library Surprise untuk mempelajari pola preferensi pengguna berdasarkan data rating historis.

- model_svd.fit(trainset)
    Melatih model pada data pelatihan (trainset) untuk mempelajari hubungan antara pengguna dan buku berdasarkan rating.

- model_svd.test(testset)
    Menguji performa model pada data uji untuk mengevaluasi akurasi prediksi.

- accuracy.rmse(predictions)
    Mengukur Root Mean Square Error (RMSE) sebagai metrik evaluasi. Semakin rendah RMSE, semakin baik performa prediksi model.

- Rekomendasi untuk User Tertentu:

    - User teraktif diambil berdasarkan frekuensi rating terbanyak (user_id = df_model['user_id'].value_counts().index[0])

    - Buku yang belum pernah dibaca oleh user tersebut difilter (books_to_predict)

    - Prediksi rating dilakukan pada buku-buku tersebut (model_svd.predict)

    - Buku dengan estimasi rating tertinggi diurutkan dan diambil 5 teratas untuk direkomendasikan.

### Hasil Top 5 :
    
![image](https://github.com/user-attachments/assets/1182bb77-e05e-4776-b03a-066fff3f35c9)

### Kelebihan:
- Tidak membutuhkan informasi tentang konten buku (hanya rating).

- Mampu menangkap pola laten antara user dan item secara efisien.

### Kekurangan:
- Tidak bisa merekomendasikan item ke user baru atau item baru (cold start problem).

- Butuh data rating yang cukup banyak dan merata agar hasilnya akurat.

---

## 2. Model 2: Content-Based Filtering menggunakan TF-IDF + Nearest Neighbors
### Arsitektur Model:
- TfidfVectorizer(...)
    Mengubah teks gabungan dari judul, penulis, dan penerbit (combined_features) menjadi representasi numerik berdasarkan frekuensi kata (TF-IDF).
Konfigurasi:

    - stop_words='english': Menghapus kata umum yang tidak informatif.

    - max_features=5000: Membatasi jumlah kata agar hemat memori.

    - strip_accents='unicode', lowercase=True: Membersihkan teks untuk konsistensi.

- NearestNeighbors(metric='cosine', algorithm='brute')
    Model pembanding yang mengukur kemiripan antar buku berdasarkan vektor TF-IDF menggunakan cosine similarity.

- nn_model.fit(tfidf_matrix)
    Melatih model Nearest Neighbors dengan representasi vektor semua buku.

- Fungsi get_recommendations()

    - Menerima input judul buku.

    - Mencari indeks buku di books.

    - Mengambil vektor TF-IDF buku tersebut.

    - Menghitung kemiripan dengan semua buku lain.

    - Mengembalikan daftar buku paling mirip (selain buku input itu sendiri).

- recommended_books[['title', 'author', 'publisher', 'img_l']]
Menampilkan hasil rekomendasi dalam format yang informatif.

### Hasil Top 10 :
![image](https://github.com/user-attachments/assets/55192171-885b-49df-b5c1-9f5ce0cc5787)

### Kelebihan:
- Tidak tergantung pada data rating, bisa bekerja walau data rating sedikit.

- Bisa direkomendasikan ke user baru (selama mereka memilih buku favorit).

### Kekurangan:
- Rekomendasi terbatas pada item yang memiliki konten mirip (kurang variasi).

- Sulit menangkap preferensi pengguna secara kompleks (tidak ada data interaksi user).

---

## Kesimpulan

- **Collaborative Filtering** bekerja baik saat data interaksi melimpah.
- **Content-Based Filtering** berguna saat data interaksi minim, atau untuk menangani item baru.
  
---

## Evaluation

Evaluasi dilakukan untuk menilai seberapa baik model merekomendasikan buku yang sesuai dengan preferensi pengguna. Metrik evaluasi dipilih berdasarkan jenis model yang digunakan dan karakteristik data.

---

## Metrik Evaluasi
Dalam proyek sistem rekomendasi, evaluasi model dilakukan menggunakan dua metrik utama yang umum digunakan dalam Information Retrieval, yaitu:

### 1. Precision@K

**Precision@K** mengukur proporsi item relevan di antara K item teratas yang direkomendasikan oleh sistem.

![image](https://github.com/user-attachments/assets/5793e8fb-1811-4743-889f-7022b72b61fd)

​
Precision@K memberikan informasi seberapa akurat rekomendasi model. Nilai precision yang tinggi menunjukkan bahwa sebagian besar item yang direkomendasikan adalah relevan bagi pengguna. Metrik ini cocok digunakan ketika kita ingin memaksimalkan kualitas rekomendasi dalam jumlah terbatas.

### 2. Recall@K

**Recall@K** mengukur proporsi item relevan yang berhasil direkomendasikan oleh sistem dari keseluruhan item relevan yang tersedia untuk pengguna.

![image](https://github.com/user-attachments/assets/9d531217-e05b-4eaa-93ea-c2b2e31e7ca3)

Recall@K menunjukkan seberapa baik sistem dalam menangkap seluruh item yang seharusnya direkomendasikan. Nilai yang lebih tinggi menunjukkan sistem mampu mengidentifikasi lebih banyak item yang benar-benar disukai oleh pengguna.

#### Catatan:

- Nilai Precision@K dan Recall@K berada pada rentang 0 hingga 1.

- Precision@K fokus pada kualitas dari top-K rekomendasi, sedangkan Recall@K fokus pada cakupan (coverage) dari seluruh item relevan.

- Keduanya saling melengkapi dan sering digunakan bersamaan untuk mengevaluasi kinerja sistem rekomendasi.

---

## Hasil Evaluasi Model

Berikut adalah hasil evaluasi dua pendekatan sistem rekomendasi yang dibangun, menggunakan metrik Precision@5 dan Recall@5, yang merepresentasikan seberapa relevan rekomendasi terhadap preferensi pengguna.

### 1. Model Collaborative Filtering (SVD)
- Precision@5: 0.3860

- Recall@5: 0.9366

    Model ini menunjukkan performa terbaik dengan nilai precision dan recall yang tinggi. Precision@5 sebesar 0.3860 berarti sekitar 38,6% dari buku yang direkomendasikan termasuk dalam buku relevan (rating tinggi). Sementara Recall@5 sebesar 0.9366 menunjukkan bahwa hampir semua buku relevan berhasil direkomendasikan kepada pengguna. Hal ini mencerminkan bahwa pendekatan collaborative filtering berhasil menangkap pola preferensi pengguna dengan baik.

### 2. Model Content-Based Filtering (TF-IDF + Nearest Neighbors)
- Precision@5: 0.0020

- Recall@5: 0.0019

    Model content-based menunjukkan performa yang sangat rendah pada metrik evaluasi. Hanya sekitar 0,2% dari rekomendasi yang benar-benar relevan, dan hanya sekitar 0,19% dari semua buku relevan berhasil direkomendasikan. Hal ini disebabkan oleh keterbatasan fitur konten buku dalam dataset, yang hanya terdiri dari atribut seperti judul, penulis, penerbit, dan tahun publikasi, tanpa deskripsi atau genre yang lebih mendalam.

### Kesimpulan :
#### Model collaborative filtering (SVD) secara efektif menjawab ketiga masalah utama:

- Membuat membaca jadi lebih menarik: Dengan merekomendasikan buku yang relevan secara personal, pengguna lebih mungkin tertarik untuk membaca.

- Membantu menemukan bacaan selanjutnya: Sistem menyarankan buku berdasarkan pola pengguna lain yang serupa, mengurangi kebingungan dalam memilih buku berikutnya.

- Menyediakan sistem rekomendasi yang personal: Model berbasis SVD mampu menyesuaikan rekomendasi berdasarkan interaksi pengguna.

#### Sebaliknya, model content-based belum berhasil menjawab masalah tersebut secara optimal karena keterbatasan fitur dalam dataset.
Sebagian besar goals berhasil dicapai melalui model collaborative filtering:

- Pengalaman membaca meningkat melalui rekomendasi yang sesuai minat.

- Rekomendasi bacaan selanjutnya dihasilkan berdasarkan histori pengguna.

- Sistem bersifat personal dan bisa dikembangkan ke platform digital.

Namun, goal dari pendekatan content-based masih belum tercapai karena kurangnya fitur konten deskriptif pada buku.

---

Solusi menggunakan Collaborative Filtering terbukti berdampak signifikan, sesuai dengan performa evaluasi dan kemampuannya menjawab permasalahan utama. Solusi Content-Based Filtering memberikan insight bahwa untuk meningkatkan efektivitasnya, dibutuhkan dataset yang lebih kaya, seperti sinopsis buku, genre, atau tag yang lebih spesifik.
