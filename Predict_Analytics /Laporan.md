## Domain Project

Harga emas telah lama dikenal sebagai salah satu instrumen investasi yang stabil dan memiliki kecenderungan meningkat dalam jangka panjang. Di tengah kondisi ekonomi global yang penuh ketidakpastian, seperti krisis geopolitik, pandemi, atau tingginya inflasi, emas sering dijadikan sebagai aset *safe haven* dan instrumen lindung nilai (*hedging asset*). Hal ini didukung oleh laporan dari **World Gold Council (2023)(https://www.gold.org)** yang menunjukkan bahwa emas memiliki korelasi negatif terhadap inflasi dan mampu mempertahankan daya beli dalam jangka panjang.

Namun demikian, masih banyak masyarakat yang belum memahami sepenuhnya potensi investasi emas. Minimnya akses terhadap sistem prediksi harga emas yang akurat dan mudah dipahami menjadi salah satu penyebab utama kurangnya literasi investasi di kalangan masyarakat umum. Padahal, dengan adanya sistem prediksi berbasis teknologi, investor individu dapat mengambil keputusan investasi yang lebih tepat, terutama dalam jangka pendek.

Sebagai respons terhadap permasalahan tersebut, proyek ini bertujuan untuk:

- **Memprediksi harga emas harian** di masa depan dengan akurasi tinggi menggunakan metode *deep learning*, khususnya LSTM dan GRU.
- **Menyediakan insight dan literasi** kepada masyarakat terkait pentingnya memahami pergerakan harga emas sebagai dasar pengambilan keputusan investasi.
- **Menghadirkan solusi data-driven** yang berbasis pada dataset historis yang kredibel, seperti data dari Goldhub – World Gold Council dan [Kaggle - Gold Price Historical Data (2004–2024)](https://www.kaggle.com/datasets/novandraanugrah/xauusd-gold-price-historical-data-2004-2024).

Dengan adanya sistem prediksi berbasis *machine learning*, diharapkan masyarakat dapat memperoleh manfaat dalam mengatur portofolio keuangan mereka secara lebih terinformasi dan adaptif terhadap dinamika pasar global.

## Business Understanding

### Problem Statements

1. **Kurangnya literasi masyarakat terkait pentingnya investasi emas sebagai bentuk perlindungan terhadap inflasi.**
    
    Meskipun emas dikenal sebagai aset lindung nilai, banyak masyarakat belum memahami potensi dan mekanisme investasi emas dalam konteks ekonomi modern, terutama saat inflasi tinggi.
    
2. **Tidak tersedia sistem prediksi harga emas yang mudah diakses dan akurat.**
    
    Sebagian besar prediksi harga emas masih bersifat teknikal atau berbasis indikator kompleks yang sulit dimengerti oleh investor pemula. Hal ini menyulitkan masyarakat dalam mengambil keputusan investasi yang tepat waktu.
    
3. **Kurangnya pemanfaatan teknologi modern untuk memodelkan pergerakan harga emas.**
    
    Banyak pendekatan konvensional seperti rata-rata bergerak atau model statistik sederhana yang belum mampu menangkap kompleksitas pola harga emas jangka pendek.
    

### Goals

1. **Meningkatkan literasi investasi emas di kalangan masyarakat.**
    
    Dengan menyajikan visualisasi tren harga emas dari waktu ke waktu, masyarakat dapat lebih memahami perilaku pasar dan urgensi investasi emas dalam mengelola risiko inflasi.
    
2. **Mengembangkan sistem prediksi harga emas harian yang akurat.**
    
    Sistem ini ditargetkan dapat memprediksi harga 1–2 hari ke depan, sehingga dapat dimanfaatkan oleh investor dalam pengambilan keputusan jangka pendek.
    
3. **Mengintegrasikan teknologi deep learning untuk meningkatkan akurasi prediksi.**
    
    Penggunaan algoritma seperti LSTM dan GRU memungkinkan pemodelan yang lebih baik terhadap data sekuensial seperti harga emas historis.
    

### Solution Statements

1. **Mengimplementasikan model LSTM (Long Short-Term Memory)** untuk memprediksi harga emas jangka pendek berdasarkan pola historis harga. LSTM dipilih karena kemampuannya dalam mengingat urutan data dalam jangka panjang, cocok untuk data time series.
2. **Menerapkan model GRU (Gated Recurrent Unit)** sebagai pembanding LSTM. GRU memiliki arsitektur yang lebih ringan dan dapat memberikan performa serupa atau lebih baik pada data time series, tergantung pada kompleksitasnya.
3. **Mengevaluasi performa kedua model menggunakan metrik yang terukur**, seperti:
    - **MAE (Mean Absolute Error)** untuk mengetahui kesalahan rata-rata absolut.
    - **RMSE (Root Mean Squared Error)** untuk mengukur penyimpangan prediksi secara kuadrat.
    - **R² (Coefficient of Determination)** sebagai indikator kualitas prediksi.
4. **Membandingkan hasil kedua model untuk memilih pendekatan terbaik**, sekaligus membuka ruang untuk perbaikan lebih lanjut melalui hyperparameter tuning, optimalisasi arsitektur model, atau penambahan fitur.

## Data Understanding

Dataset yang digunakan dalam proyek ini adalah **Gold Price Historical Data**, yang diperoleh dari Kaggle:

📎 [Kaggle - Gold Price Historical Data (2004–2024)](https://www.kaggle.com/datasets/novandraanugrah/xauusd-gold-price-historical-data-2004-2024).

Dataset ini berisi informasi historis harga emas dalam USD per troy ounce dari tahun 2004 hingga awal 2024. Data dikumpulkan dari sumber-sumber pasar terpercaya dan telah digunakan secara luas dalam berbagai analisis ekonomi dan keuangan.

### Variabel dalam Dataset

Berikut adalah penjelasan dari setiap fitur atau kolom dalam dataset:

- **Date**: Tanggal pencatatan harga emas. Formatnya YYYY-MM-DD.
- **Open**: Harga emas pada saat pasar dibuka (USD/oz).
- **High**: Harga tertinggi emas yang tercatat dalam satu hari perdagangan (USD/oz).
- **Low**: Harga terendah emas yang tercatat dalam satu hari perdagangan (USD/oz).
- **Close**: Harga emas saat pasar ditutup (USD/oz). Kolom ini menjadi target utama dalam prediksi harga.
- **Volume**: Volume transaksi perdagangan emas pada hari tersebut. Kolom ini bersifat opsional dan tidak selalu tersedia atau akurat.

### Exploratory Data Analysis (EDA) & Visualisasi

Untuk memahami pola dan struktur data, dilakukan beberapa tahap analisis eksploratif, antara lain:

- **Time Series Plot**![Screenshot 2025-04-29 155147](https://github.com/user-attachments/assets/b2bcf45f-03e8-4412-82fe-dd9f1f2fc7b6)
: Untuk melihat tren harga emas dari waktu ke waktu, termasuk identifikasi adanya seasonality dan tren jangka panjang.
- **Moving Average Plot**:![Screenshot 2025-04-29 155202](https://github.com/user-attachments/assets/fa040df6-eca9-445d-ad3a-2cc4af08bbd5)
 Untuk menghaluskan fluktuasi harga dan menyoroti arah tren umum (misalnya MA 7-hari atau 30-hari).
- **Heatmap Korelasi**:![Screenshot 2025-04-29 155212](https://github.com/user-attachments/assets/509b10df-fd90-43fc-826e-c0b853280b1d)
 Untuk mengevaluasi korelasi antar fitur seperti Open, High, Low, dan Close.
- **Distribusi Harga Harian dan Perubahannya**![Screenshot 2025-04-29 155219](https://github.com/user-attachments/assets/62db5974-b3c5-4b33-8af3-f2a2f65e38b9)
: Untuk melihat sebaran harga dan volatilitas harian yang mungkin memengaruhi model prediksi.
- **Candlestick Chart**: ![Screenshot 2025-04-29 155228](https://github.com/user-attachments/assets/635bf0aa-f58c-4e39-8f2e-76fc5a6a93d7)
Untuk menampilkan dinamika harga harian secara detail, termasuk Open, High, Low, dan Close.

Visualisasi tersebut membantu dalam mengidentifikasi pola-pola penting yang bisa dimanfaatkan oleh model prediktif, serta memastikan tidak ada outlier ekstrem atau missing value yang dapat mengganggu proses modeling.

## Data Preparation

Proses persiapan data sangat penting dalam proyek time series forecasting karena kualitas input akan sangat mempengaruhi hasil prediksi. Berikut adalah tahapan data preparation yang dilakukan secara berurutan:

1. **Konversi Kolom `Date` ke Format Datetime**
    
    Kolom `Date` dikonversi ke format datetime (`pd.to_datetime`) untuk memastikan data dapat diolah secara kronologis dan memungkinkan pemanfaatan fungsi-fungsi time series Pandas.
    
    *Alasan:* Format datetime diperlukan agar data dapat disortir dan digunakan dalam analisis berbasis waktu.
    
2. **Pengurutan Data Secara Kronologis**
    
    Setelah konversi, data diurutkan berdasarkan tanggal secara menaik (ascending).
    
    *Alasan:* Data time series harus dalam urutan waktu yang benar agar windowing dan pembelajaran temporal model RNN/LSTM/GRU berjalan sesuai konteks waktu yang akurat.
    
3. **Pemilihan Fitur yang Digunakan**
    
    Fitur yang digunakan dalam modeling adalah: `Open`, `High`, `Low`, dan `Close`. Fitur `Volume` diabaikan karena nilainya banyak yang kosong dan tidak konsisten.
    
    *Alasan:* Fitur yang dipilih memiliki korelasi kuat terhadap harga penutupan dan relevan dalam analisis teknikal.
    
4. **Normalisasi Data (MinMaxScaler)**
    
    Semua fitur diskalakan ke rentang [0, 1] menggunakan `MinMaxScaler` dari scikit-learn.
    
    *Alasan:* Model deep learning sensitif terhadap skala data. Normalisasi mempercepat konvergensi dan mencegah dominasi fitur tertentu.
    
5. **Pembuatan Dataset Time Series (Windowing)**
    
    Data disusun ulang menjadi window time series dengan panjang 60 hari (time_step = 60). Setiap 60 data sebelumnya digunakan untuk memprediksi 1 harga `Close` berikutnya.
    
    *Alasan:* Windowing memungkinkan model untuk belajar dari pola historis, misalnya tren 2 bulan terakhir untuk prediksi harga esok hari.
    
6. **Split Data: Train, Validation, dan Test**
    
    Data dibagi menjadi:
    
    - 70% untuk training model,
    - 20% untuk validasi selama proses training (tuning dan early stopping),
    - 10% untuk pengujian akhir model.
        
        *Alasan:* Pembagian data ini membantu menghindari overfitting dan mengukur performa model secara obyektif pada data yang belum pernah dilihat sebelumnya.
        

## Modeling

Untuk menyelesaikan permasalahan prediksi harga emas harian, digunakan dua jenis arsitektur deep learning: **LSTM (Long Short-Term Memory)** dan **GRU (Gated Recurrent Unit)**. Keduanya merupakan varian dari Recurrent Neural Network (RNN) yang efektif dalam memproses data sekuensial seperti data time series.

---

### Model 1: LSTM (Long Short-Term Memory)

**Arsitektur Model:**

- Layer 1: LSTM dengan 64 unit, `return_sequences=True`, `activation='relu'`
- Dropout: 0.2 (untuk mengurangi overfitting)
- Layer 2: LSTM dengan 32 unit, `activation='relu'`
- Dropout: 0.2
- Output Layer: Dense(1)
- Optimizer: Adam
- Loss Function: Mean Squared Error (MSE)
- Epochs: 50
- Batch Size: 32
- Fitur yang digunakan: `Open`, `High`, `Low`, `Close` (total 4 fitur)
- Callbacks: EarlyStopping untuk menghentikan pelatihan jika validasi loss tidak membaik

```python
model = Sequential([
    LSTM(64, return_sequences=True, activation='relu', input_shape=(time_step, 4)),
    Dropout(0.2),
    LSTM(32, activation='relu'),
    Dropout(0.2),
    Dense(1)
])
model.compile(optimizer='adam', loss='mse')
history = model.fit(
    X_train, y_train,
    epochs=50,
    validation_data=(X_val, y_val),
    batch_size=32,
    verbose=1,
    callbacks=[early_stop]
)

```

**Kelebihan:**

- Mampu menangkap informasi dari banyak fitur sekaligus.
- Potensial untuk memahami dinamika kompleks antar fitur teknikal harga emas.

**Kekurangan:**

- Waktu pelatihan lebih lama karena kompleksitas arsitektur.
- Performa prediksi pada data aktual masih memiliki gap kecil terhadap nilai sebenarnya (sedikit underfit atau overfit tergantung kondisi).

---

### Model 2: GRU (Gated Recurrent Unit)

**Arsitektur Model:**

- Layer 1: GRU dengan 50 unit, `return_sequences=True`
- Layer 2: GRU dengan 50 unit
- Output Layer: Dense(1)
- Optimizer: Adam
- Loss Function: MSE
- Epochs: 50
- Batch Size: 32
- Fitur yang digunakan: hanya `Close` (1 fitur)
- Callbacks: EarlyStopping

```python
model = Sequential()
model.add(GRU(50, return_sequences=True, input_shape=(time_step, 1)))
model.add(GRU(50))
model.add(Dense(1))
model.compile(optimizer='adam', loss='mean_squared_error')
history = model.fit(
    X_train, y_train,
    validation_data=(X_val, y_val),
    epochs=50,
    batch_size=32,
    verbose=1,
    callbacks=[early_stop]
)

```

**Kelebihan:**

- Lebih ringan dan cepat saat training dibanding LSTM.
- Performa prediksi lebih baik dibanding LSTM dalam eksperimen ini, meskipun hanya menggunakan 1 fitur.

**Kekurangan:**

- Hanya menggunakan 1 fitur membuat informasi yang digunakan model lebih terbatas.
- Kurang informatif jika ingin menjelaskan penyebab naik turunnya harga berdasarkan fitur lain.

---

### Eksperimen Tambahan: GRU dengan 4 Fitur

- Layer GRU: 2 lapisan
- Dense Layer: 1 output neuron
- Optimizer: Adam
- Loss Function: MSE
- Epochs: 50
- Fitur yang digunakan: `Open`, `High`, `Low`, `Close` (4 fitur)

Eksperimen ini menunjukkan bahwa penggunaan 4 fitur pada GRU meningkatkan informasi yang tersedia untuk model, namun waktu pelatihan menjadi sedikit lebih lama dibanding GRU 1 fitur. Hasil prediksi tetap akurat dan mendekati hasil dari model LSTM.

### Model Terbaik: **GRU dengan 1 Fitur (Close)**

Berdasarkan hasil evaluasi menggunakan metrik **MAE**, **RMSE**, dan **R²**, model **GRU dengan satu fitur `Close`** dipilih sebagai model terbaik. Meskipun hanya menggunakan satu fitur, model ini menunjukkan **hasil prediksi yang lebih akurat dan konsisten** dibandingkan model lainnya, dengan waktu pelatihan yang lebih efisien.

**Alasan pemilihan model ini:**

- **Performa prediksi lebih baik dari model LSTM**, dengan nilai error (MAE dan RMSE) yang lebih rendah.
- **Waktu pelatihan lebih singkat**, sehingga cocok untuk digunakan dalam sistem real-time atau update berkala.
- Meskipun hanya menggunakan satu fitur, **akurasi prediksi tetap tinggi** dan cukup representatif untuk harga emas harian.
- Sederhana namun efektif, sehingga **mudah di-deploy dan di-maintain** dalam sistem prediksi berbasis web atau IoT.

Model GRU 1 fitur ini menjadi solusi utama dalam proyek ini karena memberikan **kombinasi terbaik antara kecepatan, kesederhanaan, dan akurasi prediksi**. Cocok untuk digunakan oleh masyarakat atau investor pemula yang membutuhkan estimasi harga emas harian dengan cepat dan praktis.

Semua model dilengkapi dengan **EarlyStopping**, dengan parameter:

```python
early_stop = EarlyStopping(monitor='val_loss', patience=5, restore_best_weights=True)
```

Hal ini dilakukan untuk **mencegah overfitting** dan memastikan model berhenti pada epoch terbaik saat validasi loss tidak membaik lagi.

## Evaluation

### Metrik Evaluasi

Dalam proyek ini, karena permasalahan yang diangkat adalah regresi (prediksi harga emas sebagai data numerik berkelanjutan), maka digunakan tiga metrik evaluasi utama:

1. **MAE (Mean Absolute Error)**MAE=n1i=1∑n∣yi−y^i∣
    
    MAE mengukur rata-rata selisih absolut antara nilai aktual dan nilai prediksi.
    
    $$
    \text{MAE} = \frac{1}{n} \sum_{i=1}^{n} \left| y_i - \hat{y}_i \right|
    $$

    
    Metrik ini mudah diinterpretasikan karena memiliki satuan yang sama dengan target (dalam hal ini USD). Nilai yang lebih rendah menunjukkan performa model yang lebih baik.
    
2. **RMSE (Root Mean Squared Error)**RMSE=n1i=1∑n(yi−y^i)2
    
    RMSE mengukur akar kuadrat dari rata-rata kesalahan kuadrat antara nilai prediksi dan aktual.
    
    $$
    \text{RMSE} = \sqrt{ \frac{1}{n} \sum_{i=1}^{n} (y_i - \hat{y}_i)^2 }
    $$

    
    RMSE memberi penalti lebih besar terhadap kesalahan besar. Nilai lebih rendah menunjukkan prediksi yang lebih akurat dan stabil.
    
3. **R² Score (Coefficient of Determination)**R2=1−∑(yi−yˉ)2∑(yi−y^i)2
    
    R² mengukur seberapa besar variasi dari data target yang bisa dijelaskan oleh model.
    
    $$
    R^2 = 1 - \frac{\sum_{i=1}^{n} (y_i - \hat{y}_i)^2}{\sum_{i=1}^{n} (y_i - \bar{y})^2}
    $$

    
    Nilai R² berada di antara 0 hingga 1. Nilai mendekati 1 menunjukkan bahwa model mampu menjelaskan sebagian besar variasi pada data.
    

---

### Hasil Evaluasi Model

Berikut adalah hasil evaluasi untuk masing-masing model:

### 1. **Model GRU dengan 1 Fitur (`Close`)**

- **MAE**: 16.74 USD
- **RMSE**: 22.23 USD
- **R² Score**: 0.9942

Model ini memberikan hasil terbaik dengan MAE dan RMSE paling rendah serta R² tertinggi. Ini menunjukkan bahwa prediksi mendekati nilai aktual dan model sangat mampu menjelaskan variasi harga emas.

### 2. **Model GRU dengan 4 Fitur (`Open`, `High`, `Low`, `Close`)**

- **MAE**: 22.56 USD
- **RMSE**: 29.85 USD
- **R² Score**: 0.9896

Model ini memberikan hasil yang juga baik, namun sedikit di bawah performa model GRU 1 fitur. Model ini bisa menjadi alternatif apabila dibutuhkan pemodelan yang mempertimbangkan lebih banyak fitur.

### 3. **Model LSTM dengan 4 Fitur**

- **MAE**: 41.18 USD
- **RMSE**: 55.47 USD
- **R² Score**: 0.9640

Meskipun LSTM adalah arsitektur populer untuk data time series, model ini memiliki performa paling rendah dalam eksperimen ini. Hal ini menunjukkan bahwa dalam kasus ini, GRU lebih cocok karena lebih ringan dan konvergen lebih cepat.

## Evaluation

### Metrik Evaluasi

Dalam proyek ini, karena permasalahan yang diangkat adalah regresi (prediksi harga emas sebagai data numerik berkelanjutan), maka digunakan tiga metrik evaluasi utama:

1. **MAE (Mean Absolute Error)**MAE=n1i=1∑n∣yi−y^i∣
    
    MAE mengukur rata-rata selisih absolut antara nilai aktual dan nilai prediksi.
    
    MAE=1n∑i=1n∣yi−y^i∣\text{MAE} = \frac{1}{n} \sum_{i=1}^{n} | y_i - \hat{y}_i |
    
    Metrik ini mudah diinterpretasikan karena memiliki satuan yang sama dengan target (dalam hal ini USD). Nilai yang lebih rendah menunjukkan performa model yang lebih baik.
    
2. **RMSE (Root Mean Squared Error)**RMSE=n1i=1∑n(yi−y^i)2
    
    RMSE mengukur akar kuadrat dari rata-rata kesalahan kuadrat antara nilai prediksi dan aktual.
    
    RMSE=1n∑i=1n(yi−y^i)2\text{RMSE} = \sqrt{\frac{1}{n} \sum_{i=1}^{n} (y_i - \hat{y}_i)^2}
    
    RMSE memberi penalti lebih besar terhadap kesalahan besar. Nilai lebih rendah menunjukkan prediksi yang lebih akurat dan stabil.
    
3. **R² Score (Coefficient of Determination)**R2=1−∑(yi−yˉ)2∑(yi−y^i)2
    
    R² mengukur seberapa besar variasi dari data target yang bisa dijelaskan oleh model.
    
    R2=1−∑(yi−y^i)2∑(yi−yˉ)2R^2 = 1 - \frac{\sum (y_i - \hat{y}_i)^2}{\sum (y_i - \bar{y})^2}
    
    Nilai R² berada di antara 0 hingga 1. Nilai mendekati 1 menunjukkan bahwa model mampu menjelaskan sebagian besar variasi pada data.
    

---

### Hasil Evaluasi Model

Berikut adalah hasil evaluasi untuk masing-masing model:

### 1. **Model GRU dengan 1 Fitur (`Close`)**

- **MAE**: 19.08 USD
- **RMSE**: 25.19 USD
- **R² Score**: 0.9926

Model ini memberikan hasil terbaik dengan MAE dan RMSE paling rendah serta R² tertinggi. Ini menunjukkan bahwa prediksi mendekati nilai aktual dan model sangat mampu menjelaskan variasi harga emas.

### 2. **Model GRU dengan 4 Fitur (`Open`, `High`, `Low`, `Close`)**

- **MAE**: 22.56 USD
- **RMSE**: 29.85 USD
- **R² Score**: 0.9896

Model ini memberikan hasil yang juga baik, namun sedikit di bawah performa model GRU 1 fitur. Model ini bisa menjadi alternatif apabila dibutuhkan pemodelan yang mempertimbangkan lebih banyak fitur.

### 3. **Model LSTM dengan 4 Fitur**

- **MAE**: 35.27 USD
- **RMSE**: 47.63 USD
- **R² Score**: 0.9734

Meskipun LSTM adalah arsitektur populer untuk data time series, model ini memiliki performa paling rendah dalam eksperimen ini. Hal ini menunjukkan bahwa dalam kasus ini, GRU lebih cocok karena lebih ringan dan konvergen lebih cepat.

---

### Visualisasi

- **Plot Prediksi vs Aktual**: ![Screenshot 2025-04-29 155415](https://github.com/user-attachments/assets/b6cb68f4-4232-4bc8-b5ad-395296e934ee)
Digunakan untuk memverifikasi bagaimana model mengikuti tren harga emas harian.
- **Plot Loss Function**:![Screenshot 2025-04-29 155421](https://github.com/user-attachments/assets/69f84183-52ec-4e16-bc80-58a428da819b)
 Dilakukan monitoring pada training dan validation loss untuk setiap model guna mendeteksi overfitting. Semua model menggunakan **EarlyStopping** untuk menghentikan pelatihan saat performa validasi tidak meningkat lagi dalam 5 epoch berturut-turut.
