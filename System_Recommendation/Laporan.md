# Laporan Proyek Machine Learning - Nama Anda

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

1. **Content-Based Filtering**
    
    Pendekatan ini merekomendasikan buku berdasarkan kemiripan atribut konten (genre, penulis, kata kunci deskripsi) dari buku-buku yang pernah disukai atau dibaca oleh pengguna. Misalnya, jika seorang pengguna menyukai buku fiksi ilmiah dengan tema futuristik, sistem akan merekomendasikan buku lain dengan karakteristik yang serupa.
    
2. **Collaborative Filtering**
    
    Pendekatan ini memberikan rekomendasi berdasarkan preferensi pengguna lain yang memiliki kebiasaan membaca serupa. Jika pengguna A dan B memiliki kesamaan dalam membaca beberapa buku, maka sistem akan menyarankan buku yang dibaca B namun belum dibaca A, dan sebaliknya.
    
3. **Hybrid Approach**
    
    Kombinasi dari content-based dan collaborative filtering untuk menghasilkan rekomendasi yang lebih akurat dan personal. Hybrid approach mengatasi kelemahan masing-masing metode jika digunakan secara tunggal, seperti masalah cold-start atau sparseness.
    

## **Data Understanding**

Dataset yang digunakan dalam proyek sistem rekomendasi buku ini diambil dari [Kaggle - Book Recommendation Dataset oleh Arash Nic](https://www.kaggle.com/datasets/arashnic/book-recommendation-dataset). Dataset ini terdiri dari tiga file utama yaitu `Books.csv`, `Users.csv`, dan `Ratings.csv`, yang masing-masing berisi informasi buku, pengguna, dan interaksi berupa rating. Total jumlah data dari ketiga file mencapai lebih dari 1 juta entri, sehingga dataset ini cukup kaya dan cocok digunakan untuk membangun sistem rekomendasi berbasis content-based filtering, collaborative filtering, maupun pendekatan hybrid.

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
- Heatmap
  - **Insight** : 
![image](https://github.com/user-attachments/assets/b9be3d5d-cf74-4a73-9e56-cb46a15f1fc5)


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

  Tujuan: Supaya data lebih siap dipakai dalam model Collaborative Filtering dan lebih mudah digunakan dalam coding.
- **Feature Selection & Data Cleaning untuk Content-Based Filtering**
  Penjelasan:

  Membuat salinan books dan ratings untuk menjaga data asli tetap utuh.

  Rename kolom books agar mudah dibaca.

  Hapus baris buku yang tidak memiliki informasi penting seperti judul, penulis, atau penerbit.

  Tujuan: Menjamin data yang digunakan lengkap dan relevan untuk membuat profil konten buku (title, author, publisher).
- **Filtering pada data**
  Penjelasan:

  Rename kolom ratings.

  Ambil hanya data rating eksplisit (bukan nol).

  Pilih hanya buku yang memiliki setidaknya satu rating eksplisit.

  Tujuan: Memastikan model hanya menggunakan buku yang benar-benar pernah dinilai oleh pengguna, sehingga bisa diasumsikan memiliki kualitas tertentu.
- **Normalisasi pada data**
  Penjelasan:

  Fungsi clean_text() untuk normalisasi teks (huruf kecil dan hapus spasi tak perlu).

  Menggabungkan title, author, dan publisher menjadi satu string fitur.

  Tujuan: Membuat representasi konten buku dalam satu kolom, yang akan digunakan sebagai input ke model TF-IDF untuk mencari kemiripan antar buku.
  
## Modeling
Untuk menyelesaikan permasalahan pencarian buku yang relevan bagi pengguna, saya mengembangkan **dua model sistem rekomendasi berbeda** dan juga satu **pendekatan hybrid**. Masing-masing pendekatan memiliki kelebihan dan keterbatasan, yang dijelaskan di bawah.

---

### 1. Collaborative Filtering (Model: SVD - Singular Value Decomposition)

**Langkah-langkah:**
- Data diubah menjadi format `Surprise` untuk pemodelan.
- Model **SVD** dilatih dengan data rating pengguna.
- Evaluasi menggunakan RMSE menunjukkan kinerja prediktif model.
- Sistem menghasilkan *Top-5 Recommendation* untuk pengguna teraktif berdasarkan prediksi rating tertinggi terhadap buku yang belum pernah dibaca.

**Contoh Output:**
Top-5 Recommended Books for User 11676:

1. American Gods by Neil Gaiman - Predicted Rating: 10.00

2. Jesus Freaks by DC Talk - Predicted Rating: 10.00

3. The Fellowship of the Ring by J.R.R. Tolkien - Predicted Rating: 9.84

4. Angels & Demons by Dan Brown - Predicted Rating: 9.76

5. Rising Tides by Nora Roberts - Predicted Rating: 9.73


**Kelebihan:**
- Bisa menemukan hubungan *latent* antar pengguna dan buku.
- Tidak perlu metadata buku (judul, penulis, dll).
- Cocok untuk menangkap pola preferensi kompleks.

**Kekurangan:**
- Butuh banyak data interaksi (rating).
- Tidak bisa memberi rekomendasi untuk user atau item baru (cold start problem).
- Rentan terhadap data sparse.

---

### 2. Content-Based Filtering (Model: TF-IDF + Nearest Neighbors)

**Langkah-langkah:**
- Data konten buku (judul, penulis, penerbit) diproses menggunakan **TF-IDF**.
- Model pencarian menggunakan **cosine similarity** dengan algoritma Nearest Neighbors.
- Fungsi rekomendasi mencari buku yang paling mirip dengan buku input.

**Contoh Output untuk: "See Jane Run":**

| Judul              | Penulis      | Penerbit       | Skor Similaritas |
|--------------------|--------------|----------------|------------------|
| See Jane Run       | Joy Fielding | Harpercollins  | 0.8891           |
| Don't Cry Now      | Joy Fielding | Avon           | 0.6956           |
| Tell Me No Secrets | Joy Fielding | Avon           | 0.6064           |
| The First Time     | Joy Fielding | Atria          | 0.5430           |
| The Other Woman    | Joy Fielding | Signet Book    | 0.5389           |

**Kelebihan:**
- Tidak membutuhkan interaksi pengguna.
- Cocok untuk kasus **cold start item** (buku baru).
- Bisa menjelaskan alasan rekomendasi ("mirip dengan buku X").

**Kekurangan:**
- Terbatas pada konten yang tersedia (tidak bisa menangkap selera pengguna).
- Tidak memanfaatkan hubungan antar pengguna.
- Rekomendasi bisa terlalu "serupa" dan tidak variatif.

---

### 3. Hybrid Recommendation System (Content + Collaborative)

**Langkah-langkah:**
- Menggabungkan skor similarity dari model content-based dengan prediksi rating dari model SVD.
- Nilai akhir dihitung dengan rumus:  
  `hybrid_score = α * similarity + (1 - α) * predicted_rating`
- Hasil disortir berdasarkan skor hybrid untuk mendapatkan Top-N.

**Contoh Output untuk: "Harry Potter and the Goblet of Fire" (user_id = 11676):**

| Judul                                              | Similarity | Predicted Rating | Hybrid Score |
|----------------------------------------------------|------------|------------------|--------------|
| Harry Potter and the Goblet of Fire                | 0.7884     | 9.43             | 6.83         |
| Harry Potter and the Sorcerer's Stone              | 0.4836     | 9.21             | 6.59         |
| Harry Potter and the Prisoner of Azkaban           | 0.4983     | 8.69             | 6.23         |
| Fantastic Beasts and Where to Find Them            | 0.4987     | 7.63             | 5.49         |
| Harry Potter and the Chamber of Secrets            | 0.4919     | 7.62             | 5.48         |

**Kelebihan:**
- Mengatasi kekurangan masing-masing pendekatan.
- Lebih personal karena mempertimbangkan profil user dan konten buku.
- Fleksibel: bisa disesuaikan dengan mengubah nilai `alpha`.

**Kekurangan:**
- Lebih kompleks secara implementasi.
- Perlu kedua sumber data: konten buku dan interaksi user.
- Parameter `alpha` sensitif, harus di-*tune*.

---

## Kesimpulan

- **Collaborative Filtering** bekerja baik saat data interaksi melimpah.
- **Content-Based Filtering** berguna saat data interaksi minim, atau untuk menangani item baru.
- **Hybrid** menjadi solusi terbaik untuk rekomendasi yang akurat dan fleksibel.


## Evaluation
## 📊 Evaluasi Model

Evaluasi dilakukan untuk menilai seberapa baik model merekomendasikan buku yang sesuai dengan preferensi pengguna. Metrik evaluasi dipilih berdasarkan jenis model yang digunakan dan karakteristik data.

---

### Collaborative Filtering (SVD)

**Metrik yang digunakan: RMSE (Root Mean Squared Error)**

**Formula:**

![image](https://github.com/user-attachments/assets/2c0fb420-1179-48b4-a39b-15ecb251f02b)

**Penjelasan:**
RMSE mengukur seberapa jauh prediksi model dari rating aktual yang diberikan pengguna. Semakin kecil nilai RMSE, semakin baik performa model karena prediksi lebih mendekati nilai aktual.

**Hasil:**
RMSE:1.6228
Interpretasi:
Nilai RMSE sebesar 1.6 menunjukkan bahwa rata-rata kesalahan prediksi model berada di bawah 1 poin dalam skala rating 1–10. Hal ini mengindikasikan bahwa model SVD cukup baik dalam memahami preferensi pengguna.

### Content-Based Filtering  
**Metrik yang digunakan: Cosine Similarity**

**Formula:**
![Screenshot 2025-05-03 190215](https://github.com/user-attachments/assets/0bae4f56-3d9f-4ec9-8d95-64232b8e4585)

**Penjelasan:**  
Cosine similarity mengukur kesamaan antara dua vektor berdasarkan sudut di antara mereka. Nilainya berkisar dari 0 (tidak mirip sama sekali) hingga 1 (sangat mirip).  
Metrik ini sangat cocok digunakan untuk data berbasis teks seperti deskripsi buku karena tidak dipengaruhi oleh panjang dokumen.

**Hasil (Contoh):**  
Rekomendasi untuk buku *"See Jane Run"* memiliki skor similarity tertinggi sebesar **0.8891**, yang berarti sistem berhasil menemukan buku dengan konten yang sangat mirip.

---

### Hybrid Recommendation  
**Metrik yang digunakan: Hybrid Score**

**Formula:**
![Screenshot 2025-05-03 190231](https://github.com/user-attachments/assets/40829db6-f255-4b9e-b29c-00eef1746f2e)

**Penjelasan:**  
Metrik ini menggabungkan kekuatan prediksi rating dari collaborative filtering (SVD) dengan kesamaan konten dari content-based filtering.  
Dengan mengombinasikan keduanya, hybrid score memberikan skor akhir yang lebih seimbang — memperhitungkan baik preferensi pengguna maupun kemiripan antar buku.

**Hasil (Contoh):**  
Buku *Harry Potter and the Goblet of Fire* memperoleh skor hybrid sebesar **6.83**, hasil dari kombinasi similarity **0.7884** dan predicted rating **9.43**.
