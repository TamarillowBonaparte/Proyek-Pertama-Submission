## Proyek Prediksi Harga Ethereum Menggunakan Machine Learning - MOCH. DANI SUGIARTO
# Domain Proyek: Keuangan / FinTech (Financial Technology)
Proyek ini berada dalam ranah Financial Technology dengan fokus pada analisis pasar aset kripto, khususnya prediksi harga Ethereum sebagai bagian dari aplikasi prediktif analytics untuk mendukung pengambilan keputusan investasi

Penugasan Studi Kasus Pertama: Predictive Analytics

# Business Understanding
Perkembangan teknologi blockchain telah membawa perubahan signifikan dalam sistem keuangan global, khususnya dalam hal aset digital seperti cryptocurrency. Salah satu aset kripto yang paling populer dan memiliki kapitalisasi pasar terbesar kedua setelah Bitcoin adalah Ethereum (ETH). Ethereum tidak hanya digunakan sebagai alat tukar digital, tetapi juga sebagai platform untuk membangun aplikasi terdesentralisasi (DApps) dan kontrak pintar (smart contracts), yang membuatnya memiliki nilai lebih dibandingkan dengan aset kripto lainnya.

Namun, seperti halnya dengan aset digital lainnya, harga Ethereum sangat fluktuatif dan dipengaruhi oleh berbagai faktor, baik dari aspek teknis maupun sentimen pasar. Fluktuasi harga ini dapat menjadi tantangan bagi investor dan trader dalam mengambil keputusan investasi. Oleh karena itu, dibutuhkan suatu pendekatan yang dapat membantu memprediksi pergerakan harga Ethereum secara lebih akurat untuk mendukung pengambilan keputusan investasi yang lebih tepat.

Dalam konteks ini, penerapan teknik machine learning dapat menjadi solusi yang menjanjikan. Dengan memanfaatkan data historis harga Ethereum dan teknik pembelajaran mesin seperti K-Nearest Neighbor (KNN), Random Forest, dan AdaBoost, prediksi harga dapat dilakukan secara lebih sistematis dan berdasarkan pola data yang ada.

Proyek ini bertujuan untuk membangun model prediksi harga Ethereum dalam jangka pendek, yaitu selama 30 hari ke depan, menggunakan algoritma-algoritma tersebut. Model ini diharapkan dapat memberikan gambaran estimasi harga yang lebih akurat sehingga dapat digunakan sebagai acuan dalam strategi investasi aset kripto, khususnya Ethereum.
– [Nama Anda]
📂 Domain Proyek: Prediksi Harga Ethereum dengan Machine Learning
📌 Latar Belakang
Dalam beberapa tahun terakhir, cryptocurrency seperti Ethereum telah menjadi aset investasi yang sangat diminati. Volatilitas harganya yang tinggi membuat banyak investor dan trader mencoba memanfaatkan analisis data historis untuk melakukan prediksi harga di masa depan. Oleh karena itu, pendekatan berbasis machine learning sangat potensial untuk membantu memberikan insight dan prediksi harga secara lebih akurat.

Prediksi harga Ethereum menjadi tantangan menarik karena dipengaruhi oleh banyak faktor seperti permintaan pasar, volume transaksi, dan tren historis. Berdasarkan laporan dari Investopedia, Ethereum merupakan aset kedua terbesar setelah Bitcoin dengan volume perdagangan yang tinggi, sehingga akurasi prediksi harga dapat memberikan dampak signifikan pada pengambilan keputusan investasi.

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
Dataset yang digunakan adalah coin_Ethereum.csv yang memuat informasi harian harga Ethereum, seperti:

| Kolom       | Deskripsi                   |
| ----------- | --------------------------- |
| `Date`      | Tanggal data harga Ethereum |
| `Open`      | Harga pembukaan             |
| `High`      | Harga tertinggi             |
| `Low`       | Harga terendah              |
| `Close`     | Harga penutupan             |
| `Volume`    | Volume transaksi            |
| `Marketcap` | Kapitalisasi pasar          |


> Beberapa kolom seperti SNo, Name, Symbol, Volume, dan Marketcap dihapus karena tidak relevan untuk prediksi harga.

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

3. Eksplorasi Data
Visualisasi data dengan histogram.

Korelasi antar fitur menggunakan heatmap.
Split Dataset:

Pembagian 80% data latih dan 20% data uji

Alasan: Tahapan ini dilakukan untuk memastikan bahwa data yang digunakan untuk pelatihan model bersih, relevan, dan terstandardisasi agar model dapat belajar secara optimal.

# Modeling
Algoritma yang Digunakan:
Linear Regression

Model baseline dengan asumsi linearitas

K-Nearest Neighbors Regressor

- Model berbasis jarak, cocok untuk dataset yang tidak linear

Random Forest Regressor

- Model ensemble berbasis pohon, kuat terhadap overfitting

Gradient Boosting (XGBoost)

- Model boosting yang kuat dalam menangkap pola kompleks

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
