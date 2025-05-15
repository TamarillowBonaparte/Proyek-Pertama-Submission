## Proyek Machine Learning Prediksi-Harga Ethereum Menggunakan Machine Learning - MOCH. DANI SUGIARTO

Penugasan Studi Kasus Pertama: Predictive Analytics
# Domain Proyek

Domain proyek yang dipilih dalam proyek machine learning ini adalah keuangan dan cryptocurrency , dengan fokus pada analisis prediktif harga Ethereum (ETH). Judul proyek ini adalah "Analisis dan Prediksi Harga Ethereum Menggunakan Machine Learning" . Tujuan utamanya adalah untuk mengembangkan model prediktif berbasis algoritma machine learning yang dapat membantu investor dan pengguna dalam membuat keputusan investasi berbasis data.

# Latar Belakang Masalah

Perkembangan teknologi blockchain telah membawa perubahan besar dalam sistem keuangan global, salah satunya melalui munculnya aset digital seperti Ethereum (ETH) . Ethereum merupakan platform terdesentralisasi yang mendukung kontrak pintar (smart contracts ) dan aplikasi terdesentralisasi (DApps ), menjadikannya lebih dari sekadar mata uang digital. Sebagai aset kripto dengan kapitalisasi pasar terbesar kedua setelah Bitcoin, Ethereum banyak digunakan dalam transaksi digital, DeFi, NFT, dan berbagai ekosistem Web3.

Namun, Ethereum memiliki sifat volatilitas tinggi , di mana harganya bisa berubah secara signifikan dalam waktu singkat karena berbagai faktor seperti:

- Pergerakan pasar crypto secara umum
- Volume perdagangan harian
- Regulasi pemerintah
- Sentimen media sosial dan berita
- Kondisi makroekonomi global
- Volatilitas ini memberikan peluang sekaligus risiko bagi investor. Oleh karena itu, dibutuhkan pendekatan prediktif yang akurat untuk memahami tren harga dan mengurangi ketidakpastian dalam pengambilan keputusan investasi.

Penugasan Studi Kasus: Predictive Analytics
Proyek ini menggunakan pendekatan predictive analytics berbasis machine learning untuk memprediksi harga penutupan Ethereum (Close Price) 30 hari ke depan berdasarkan data historis. Dengan memanfaatkan fitur-fitur seperti Open, High, Low, Close, Volume, dan Marketcap, proyek ini bertujuan untuk:

1. Memproses dan mempersiapkan dataset Ethereum untuk analisis prediktif.
2. Membangun dan membandingkan beberapa model regresi machine learning (KNN, Random Forest, AdaBoost, Gradient Boosting).
3. Menghasilkan prediksi harga Ethereum 30 hari ke depan yang dapat digunakan sebagai referensi investasi.

# Business Understanding
Perkembangan teknologi blockchain telah membawa perubahan besar dalam sistem keuangan global, terutama dalam hal aset digital seperti cryptocurrency. Salah satu aset kripto yang paling menonjol adalah Ethereum (ETH), yang memiliki kapitalisasi pasar terbesar kedua setelah Bitcoin. Ethereum tidak hanya berfungsi sebagai alat tukar digital, tetapi juga sebagai platform utama untuk pengembangan aplikasi terdesentralisasi (DApps) dan kontrak pintar (smart contracts), menjadikannya aset yang memiliki nilai fungsional lebih dibandingkan kripto lainnya.

Namun demikian, harga Ethereum sangat fluktuatif dan dipengaruhi oleh berbagai faktor, mulai dari tren pasar, volume transaksi, hingga sentimen global. Volatilitas ini menciptakan tantangan besar bagi investor dan trader dalam membuat keputusan investasi yang tepat waktu dan berbasis data. Oleh karena itu, dibutuhkan pendekatan yang mampu menganalisis data historis harga Ethereum secara sistematis dan menghasilkan prediksi harga yang akurat.

Salah satu pendekatan yang potensial untuk mengatasi tantangan ini adalah penggunaan machine learning. Dengan algoritma seperti K-Nearest Neighbor (KNN), Random Forest, dan AdaBoost, model prediksi dapat dilatih menggunakan data historis untuk mengenali pola dan tren yang relevan. Berdasarkan latar belakang di atas, masalah utama yang ingin diselesaikan dalam proyek ini adalah:

Untuk menjawab pertanyaan tersebut, proyek ini menetapkan tiga tujuan utama yang selaras dengan problem statement:

1. Memproses dan menganalisis data historis Ethereum untuk menghasilkan representasi data yang siap digunakan dalam konteks prediksi harga.
Termasuk normalisasi data, deteksi outlier, feature engineering (seperti OHLC rata-rata), dan pembentukan target prediksi (Price_After_Month).

2. Membangun dan melatih beberapa model regresi machine learning (KNN, Random Forest, AdaBoost, Gradient Boosting) menggunakan data yang telah diproses.
Setiap model dilatih dan dievaluasi menggunakan metrik seperti MSE dan R² Score untuk memastikan performa prediksi.

3. Melakukan prediksi harga Ethereum 30 hari ke depan berdasarkan model terbaik.
Hasil prediksi dapat digunakan sebagai referensi awal dalam pengambilan keputusan investasi atau trading.

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
dengan total 2160 baris dan 9 kolom fitur sebelum praproses seperti:

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

1. Missing Value (Nilai Kosong)
Tidak ada nilai kosong (null) di seluruh dataset.
Semua kolom memiliki data lengkap dari awal hingga akhir.

3. Duplikasi Data
Tidak ditemukan baris duplikat dalam dataset.
Setiap baris merepresentasikan data harian unik tanpa pengulangan.

5. Outlier
Terdapat outlier pada fitur numerik seperti High, Low, Open, dan Close.
Outlier dideteksi menggunakan metode IQR (Interquartile Range) .
Outlier telah dihapus untuk meningkatkan kualitas model prediksi.

7. Kolom Irrelevan
Beberapa kolom dianggap tidak relevan untuk prediksi harga Ethereum:

- SNo: Nomor urut baris (tidak informatif).
- Name: Semua nilai adalah "Ethereum".
- Symbol: Semua nilai adalah "ETH".
- Volume: Meskipun penting secara finansial, tidak digunakan dalam model ini.
- Marketcap: Dianggap redundan karena merupakan fungsi dari harga dan pasokan.

Kolom-kolom tersebut telah dihapus , sehingga hanya tersisa:

- Date
- High
- Low
- Open
- Close

5. Fitur Baru
Ditambahkan fitur baru:

OHLC_Average: Rata-rata dari Open, High, Low, dan Close sebagai representasi harga harian.

6. Target Prediksi
Dibuat kolom target: Price_After_Month → harga Close setelah 30 hari (shift(-30)).
Beberapa baris terakhir dihapus karena mengandung nilai NaN.

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

Untuk mengevaluasi performa model prediksi harga Ethereum, digunakan dua metrik utama:

R² Score: Mengukur proporsi variansi harga aktual yang bisa dijelaskan oleh model. Semakin mendekati 1, semakin baik performa model.

Mean Squared Error (MSE): Mengukur rata-rata dari kuadrat selisih antara nilai prediksi dan nilai aktual. Semakin kecil nilai MSE, semakin akurat model.
📊 Hasil Evaluasi:
| Model - MSE	|					Hasil R²						|
| ----------- | --------------------------- |
| KNN - MSE: 6100.06 | R² Score: 0.8259|
| Random Forest - MSE (Default): 7163.01 | R² Score: 0.7955|
| Random Forest - MSE (Tuned): 6782.00 | R² Score: 0.8064 |
| AdaBoost - MSE: 6203.98 |  R² Score: 0.8229 |

Penjelasan pada tabel :
- Model Random Forest pertama (Random Forest Default) menggunakan parameter bawaan scikit-learn seperti n_estimators=100 dan max_depth=None.
- Untuk meningkatkan performa, dilakukan tuning hyperparameter, menghasilkan model Random Forest kedua (Random Forest Tuned) dengan konfigurasi n_estimators=200, max_depth=10, dan random_state=42. Model ini menunjukkan peningkatan signifikan dalam akurasi prediksi.
- KNN tetap menjadi model dengan performa terbaik berdasarkan MSE terendah dan R² tertinggi.
- Namun, Random Forest yang ditune memberikan hasil yang sangat kompetitif dan bahkan sedikit lebih baik daripada KNN dalam hal R² Score.
Meskipun KNN memiliki nilai R² tertinggi dan MSE paling rendah, perbedaan performa antar model relatif kecil, menunjukkan bahwa semua model cukup mampu menangkap pola historis dalam data harga Ethereum.
---
Keterkaitan dengan Business Understanding dan Problem Statement
Model prediksi harga Ethereum ini dibangun untuk membantu investor dalam mengambil keputusan yang lebih informatif berdasarkan data historis (sesuai dengan tujuan dalam Business Understanding). Berdasarkan hasil evaluasi:

Problem Statement 1: "Bagaimana cara mengolah data historis harga Ethereum agar dapat dieksplorasi dan dianalisis secara akurat?"

✅ Sudah dijawab dengan tahapan preprocessing, penghapusan outlier, dan normalisasi fitur yang menghasilkan dataset bersih dan siap pakai untuk modeling.

Problem Statement 2: "Algoritma machine learning apa yang paling efektif dalam memprediksi harga penutupan Ethereum berdasarkan data historis?"

✅ Sudah dijawab melalui eksperimen dengan tiga algoritma (KNN, Random Forest, AdaBoost), dengan hasil bahwa KNN memberikan performa terbaik berdasarkan metrik evaluasi.

Pencapaian Goals
- Model berhasil dibangun untuk memprediksi harga Ethereum 30 hari ke depan dengan cukup baik.

- Model KNN sebagai model terbaik telah menunjukkan kemampuan menjelaskan 82% variansi harga Ethereum, yang dapat membantu investor memitigasi risiko dalam pengambilan keputusan.

- Evaluasi menunjukkan bahwa pendekatan berbasis machine learning memberikan prediksi yang lebih sistematis dan berbasis pola, sebagaimana direncanakan pada tahap awal proyek.

Dengan demikian, seluruh solusi yang dirancang telah berdampak langsung terhadap tujuan utama proyek: memberikan wawasan prediktif bagi pengambilan keputusan investasi dalam aset kripto, khususnya Ethereum.

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
