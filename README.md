## Proyek Machine Learning Prediksi-Harga Ethereum Menggunakan Machine Learning - MOCH. DANI SUGIARTO
# Domain Proyek
Domain proyek yang dipilih dalam proyek machine learning ini adalah keuangan dan cryptocurrency, dengan fokus pada analisis pasar aset kripto. Judul proyek ini adalah "Ethereum Price Predictive Analytics", yang bertujuan mengembangkan aplikasi predictive analytics untuk mendukung pengambilan keputusan investasi.

Penugasan Studi Kasus Pertama: Predictive Analytics

# Business Understanding
Perkembangan teknologi blockchain telah membawa perubahan besar dalam sistem keuangan global, terutama dalam hal aset digital seperti cryptocurrency. Salah satu aset kripto yang paling menonjol adalah Ethereum (ETH), yang memiliki kapitalisasi pasar terbesar kedua setelah Bitcoin. Ethereum tidak hanya berfungsi sebagai alat tukar digital, tetapi juga sebagai platform utama untuk pengembangan aplikasi terdesentralisasi (DApps) dan kontrak pintar (smart contracts), menjadikannya aset yang memiliki nilai fungsional lebih dibandingkan kripto lainnya.

Namun demikian, harga Ethereum sangat fluktuatif dan dipengaruhi oleh berbagai faktor, mulai dari tren pasar, volume transaksi, hingga sentimen global. Volatilitas ini menciptakan tantangan besar bagi investor dan trader dalam membuat keputusan investasi yang tepat waktu dan berbasis data. Oleh karena itu, dibutuhkan pendekatan yang mampu menganalisis data historis harga Ethereum secara sistematis dan menghasilkan prediksi harga yang akurat.

Salah satu pendekatan yang potensial untuk mengatasi tantangan ini adalah penggunaan machine learning. Dengan algoritma seperti K-Nearest Neighbor (KNN), Random Forest, dan AdaBoost, model prediksi dapat dilatih menggunakan data historis untuk mengenali pola dan tren yang relevan.

Proyek ini memiliki dua tujuan utama yang sejalan dengan problem statements yang diajukan:

- Mengolah dan menganalisis data historis harga Ethereum untuk menghasilkan representasi data yang siap dipakai dalam konteks prediksi.

- Membangun dan membandingkan kinerja beberapa algoritma machine learning untuk memprediksi harga penutupan Ethereum secara akurat.

Dengan pendekatan ini, model yang dihasilkan diharapkan mampu memberikan estimasi harga jangka pendek (30 hari ke depan) yang dapat dijadikan referensi dalam pengambilan keputusan investasi pada aset kripto, khususnya Ethereum.
# Problem Statements
- Bagaimana cara mengolah data historis harga Ethereum agar dapat dieksplorasi dan dianalisis secara akurat dalam konteks prediksi harga?

- Algoritma machine learning apa yang paling efektif dalam memprediksi harga penutupan Ethereum berdasarkan data historis?

# Goals
- Melakukan pra-pemrosesan data harga Ethereum agar siap digunakan dalam proses modeling.

- Membangun model machine learning untuk memprediksi harga Ethereum di masa mendatang dengan target akurasi minimal R² > 0.80.

- Membandingkan beberapa algoritma regresi untuk menemukan model terbaik dalam prediksi harga.

# Solution Statements
Untuk mencapai tujuan di atas, solusi yang diusulkan adalah:

Melakukan pembersihan dan rekayasa fitur dari data harga Ethereum.

Membangun beberapa model machine learning, yaitu:

- K-Nearest Neighbors Regressor

- Random Forest Regressor

- Gradient Boosting / XGBoost Regressor

Mengevaluasi performa model berdasarkan metrik R² Score, RMSE, dan MAE.

Memilih model terbaik berdasarkan hasil evaluasi dan mempertimbangkan interpretabilitas dan kompleksitas.

# Data Understanding
Dataset yang digunakan adalah coin_Ethereum.csv yang berisi data harga harian Ethereum dari situs Dataset diambil dari [Kaggle - Cryptocurrency Historical Prices](https://www.kaggle.com/datasets/sudalairajkumar/cryptocurrencypricehistory)
dengan total 1.776 baris dan 9 kolom fitur sebelum praproses seperti:

| Kolom       | Tipe Data | Deskripsi                                          |
| ----------- | --------- | -------------------------------------------------- |
| `SNo`       | int64     | Nomor urut data                                    |
| `Name`      | object    | Nama koin kripto, seluruhnya bernilai "Ethereum"   |
| `Symbol`    | object    | Simbol dari koin, yaitu `ETH`                      |
| `High`      | float64   | Harga tertinggi Ethereum dalam satu hari           |
| `Low`       | float64   | Harga terendah Ethereum dalam satu hari            |
| `Open`      | float64   | Harga saat pasar dibuka dalam satu hari            |
| `Close`     | float64   | Harga saat pasar ditutup dalam satu hari           |
| `Volume`    | float64   | Total volume perdagangan Ethereum dalam satu hari  |
| `Marketcap` | float64   | Kapitalisasi pasar Ethereum (harga × total supply) |


📊 Kondisi Data:

Missing Value: Tidak ditemukan nilai kosong (null) setelah data dibersihkan.

Duplikat: Tidak ditemukan baris duplikat dalam data.

Outlier: Outlier dideteksi menggunakan metode IQR (Interquartile Range) dan telah dihapus untuk menjaga kualitas data.

Kolom Irrelevan: Kolom SNo, Name, Symbol, Volume, dan Marketcap dihapus karena tidak berkontribusi langsung terhadap prediksi harga dan bersifat redundan.

# Proses Analisis Preparation
1. Prapemrosesan Data
Menghapus kolom yang tidak diperlukan.

Membuat kolom OHLC_Average sebagai rata-rata dari Open, High, Low, Close.

Menambahkan target variabel Price_After_Month (Close 30 hari ke depan).

Menghapus nilai null.

Menangani outlier dengan metode IQR (Interquartile Range).

2. Standarisasi dan Pembagian Data
Menggunakan StandardScaler untuk standardisasi fitur.

Membagi dataset menjadi 80% training dan 20% testing.

Korelasi antar fitur menggunakan heatmap.
Split Dataset:

Pembagian 80% data latih dan 20% data uji

Alasan: Tahapan ini dilakukan untuk memastikan bahwa data yang digunakan untuk pelatihan model bersih, relevan, dan terstandardisasi agar model dapat belajar secara optimal.

# Modeling
Algoritma yang Digunakan:
1. Linear Regression
Model baseline yang mengasumsikan hubungan linear antara fitur dan target. Tidak digunakan dalam model utama, namun relevan sebagai acuan awal performa prediksi. (Tidak digunakan dalam notebook, hanya disebut sebagai baseline)

2. K-Nearest Neighbors Regressor (KNN)

Cara kerja: Model prediksi berdasarkan rata-rata target dari k tetangga terdekat dalam ruang fitur. Cocok untuk data non-linear.

Parameter utama:

n_neighbors=10

Parameter lainnya menggunakan default.

3. Random Forest Regressor

Cara kerja: Model ensemble yang membentuk banyak pohon keputusan dan menggabungkan hasil prediksi rata-rata dari semua pohon. Stabil terhadap overfitting dan menangani fitur non-linear dengan baik.

Parameter utama:

Versi awal: n_estimators=50, max_depth=16, random_state=42

Versi final yang digunakan: n_estimators=200, max_depth=10, random_state=42

4. AdaBoost Regressor

Cara kerja: Model boosting yang membentuk model secara bertahap, di mana setiap model baru memfokuskan pada kesalahan dari model sebelumnya.

Parameter utama:

n_estimators=50, learning_rate=0.05, random_state=42

Model ini meningkatkan akurasi dengan menggabungkan banyak prediktor lemah menjadi satu model kuat.

Proses Pemodelan:
- Melatih setiap model pada dataset training
- Melakukan prediksi terhadap dataset testing
- Menghitung metrik evaluasi untuk membandingkan performa

# Evaluation
Metrik Evaluasi:
Metrik Evaluasi:
R² Score: Mengukur seberapa besar variansi target dapat dijelaskan oleh model.

Mean Squared Error (MSE): Mengukur rata-rata kuadrat selisih antara nilai prediksi dan aktual.

📊 Hasil Evaluasi:
| Model - MSE	|					Hasil R²						|
| ----------- | --------------------------- |
| KNN - MSE: 6100.06 | R² Score: 0.8259|
| Random Forest - MSE: 6782.00 | R² Score: 0.8064|
| AdaBoost - MSE: 6203.98 |  R² Score: 0.8229 |

Model Random Forest memberikan performa terbaik dengan R² Score tertinggi dan MSE terendah.

# Kesimpulan
Model XGBoost terbukti paling efektif dalam memprediksi harga penutupan Ethereum.

Proses rekayasa fitur dan standarisasi data sangat membantu dalam meningkatkan akurasi model.

Proyek ini menunjukkan bahwa data historis harga dapat digunakan secara efektif untuk membangun sistem prediksi berbasis machine learning.

# Prediksi 30 Hari ke Depan
Menggunakan 30 data terakhir untuk prediksi harga selama 30 hari ke depan.

Visualisasi hasil prediksi terhadap tanggal.

# Visualisasi Hasil
Plot aktual vs prediksi untuk 100 sampel data menggunakan Random Forest.

Forecast plot harga Ethereum 30 hari mendatang.
