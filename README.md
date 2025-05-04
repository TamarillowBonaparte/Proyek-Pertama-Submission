# Proyek-Pertama-Submission
Penugasan Studi Kasus Pertama: Predictive Analytics
# Business Understanding
Perkembangan teknologi blockchain telah membawa perubahan signifikan dalam sistem keuangan global, khususnya dalam hal aset digital seperti cryptocurrency. Salah satu aset kripto yang paling populer dan memiliki kapitalisasi pasar terbesar kedua setelah Bitcoin adalah Ethereum (ETH). Ethereum tidak hanya digunakan sebagai alat tukar digital, tetapi juga sebagai platform untuk membangun aplikasi terdesentralisasi (DApps) dan kontrak pintar (smart contracts), yang membuatnya memiliki nilai lebih dibandingkan dengan aset kripto lainnya.

Namun, seperti halnya dengan aset digital lainnya, harga Ethereum sangat fluktuatif dan dipengaruhi oleh berbagai faktor, baik dari aspek teknis maupun sentimen pasar. Fluktuasi harga ini dapat menjadi tantangan bagi investor dan trader dalam mengambil keputusan investasi. Oleh karena itu, dibutuhkan suatu pendekatan yang dapat membantu memprediksi pergerakan harga Ethereum secara lebih akurat untuk mendukung pengambilan keputusan investasi yang lebih tepat.

Dalam konteks ini, penerapan teknik machine learning dapat menjadi solusi yang menjanjikan. Dengan memanfaatkan data historis harga Ethereum dan teknik pembelajaran mesin seperti K-Nearest Neighbor (KNN), Random Forest, dan AdaBoost, prediksi harga dapat dilakukan secara lebih sistematis dan berdasarkan pola data yang ada.

Proyek ini bertujuan untuk membangun model prediksi harga Ethereum dalam jangka pendek, yaitu selama 30 hari ke depan, menggunakan algoritma-algoritma tersebut. Model ini diharapkan dapat memberikan gambaran estimasi harga yang lebih akurat sehingga dapat digunakan sebagai acuan dalam strategi investasi aset kripto, khususnya Ethereum.
# Tujuan Proyek Data
Laporan ini bertujuan untuk membangun model machine learning yang dapat memprediksi harga Ethereum untuk 30 hari ke depan berdasarkan data historis. Dengan model ini, pengguna diharapkan dapat:

Memahami tren harga Ethereum berdasarkan data masa lalu

Menggunakan hasil prediksi untuk menyusun strategi investasi

Mengidentifikasi pola fluktuasi harga jangka pendek

# Sumber dan Karakteristik Data
Data yang digunakan bersumber dari Kaggle dengan nama file coin_Ethereum.csv. Dataset ini memuat informasi harian tentang Ethereum yang mencakup:

Open: Harga saat pasar dibuka

High: Harga tertinggi harian

Low: Harga terendah harian

Close: Harga penutupan

Volume dan Marketcap (tidak digunakan dalam model utama)

Date: Waktu pengambilan data

# Permasalahan yang Dihadapi
Adanya fluktuasi harga yang tajam (outlier)

Data volume dan marketcap yang tidak selalu konsisten

Dibutuhkannya teknik prediksi yang cukup akurat dalam jangka waktu pendek (30 hari)

# Solusi dan Metodologi
Dalam laporan ini, dilakukan beberapa tahapan untuk mencapai prediksi harga:

Preprocessing dan Feature Engineering

Menggabungkan fitur open-high-low-close (OHLC)

Membuat fitur target: Close price 30 hari ke depan

Outlier Detection

Menggunakan metode IQR untuk membersihkan data ekstrem

Modeling

Menggunakan 3 algoritma:

KNN Regressor

Random Forest Regressor

AdaBoost Regressor

Pemilihan dilakukan dengan membandingkan metrik MSE dan R² score

Prediksi

Menggunakan model terbaik (KNN) untuk memprediksi harga 30 hari ke depan

