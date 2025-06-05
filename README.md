# Proyek Machine Learning: Segmentasi Pelanggan dan Klasifikasi

## 👤 Informasi Pengembang

- **Nama:** Muhammad Husain Fadhlillah
- **ID Dicoding:** MC006D5Y2343

## 🚀 Ikhtisar Proyek

Proyek ini merupakan implementasi komprehensif dari teknik _Unsupervised Learning_ dan _Supervised Learning_ dalam konteks analisis data pelanggan. Tahap pertama melibatkan segmentasi pelanggan menggunakan algoritma clustering untuk mengidentifikasi kelompok-kelompok pelanggan yang berbeda berdasarkan karakteristik dan perilaku mereka. Label hasil clustering ini kemudian digunakan sebagai target pada tahap kedua, yaitu membangun model klasifikasi untuk memprediksi segmen pelanggan.

Tujuan utama proyek ini adalah untuk:

1.  Menerapkan teknik _Unsupervised Learning_ (Clustering) untuk menghasilkan label kelas pada dataset pelanggan.
2.  Mengintegrasikan hasil clustering dengan dataset asli.
3.  Menerapkan metode _Supervised Learning_ (Klasifikasi) untuk mengembangkan model yang mampu memprediksi kelas pelanggan berdasarkan fitur yang ada.

## 📊 Dataset

- **Nama Dataset:** Dataset Perilaku Pelanggan (Customer Behavior Dataset)
- **Deskripsi:** Dataset ini berisi berbagai atribut pelanggan seperti demografi (`Age`, `Gender`, `MaritalStatus`), finansial (`Income`, `Balance`), riwayat transaksi (`TransactionAmount`, `TransactionFrequency`, `PurchaseCategory`), metode pembayaran (`PaymentMethod`), lokasi (`Location`), dan interaksi dengan layanan (`CustomerSupportInteractions`, `SatisfactionScore`).
- **Sumber:** Disediakan untuk Proyek Akhir kelas "Belajar Machine Learning untuk Pemula" oleh Dicoding.

## ⚙️ Struktur Proyek & Alur Kerja

Proyek ini dibagi menjadi dua notebook utama yang mencerminkan dua fase analisis:

1.  **Notebook Clustering (`[Clustering]_Submission_Akhir_BMLP_Muhammad_Husain_Fadhlillah_MC006D5Y2343.ipynb`):**

    - **Pemuatan Data dan Exploratory Data Analysis (EDA):** Memahami struktur data, distribusi fitur, dan hubungan antar fitur.
    - **Pembersihan dan Pra-pemrosesan Data:** Menangani nilai yang hilang, data duplikat, outlier, serta melakukan scaling dan encoding fitur.
    - **Penentuan Jumlah Cluster Optimal:** Menggunakan metode Elbow dengan KElbowVisualizer.
    - **Pembangunan Model Clustering:** Mengimplementasikan K-Means Clustering.
    - **Analisis dengan PCA:** Membangun model clustering alternatif menggunakan Principal Component Analysis (PCA) sebagai perbandingan dan untuk visualisasi.
    - **Interpretasi Hasil Clustering:** Menganalisis karakteristik setiap cluster yang terbentuk.
    - **Inverse Transform:** Mengembalikan data ke skala aslinya untuk interpretasi yang lebih intuitif.
    - **Ekspor Hasil:** Menyimpan data dengan label cluster (`data_clustering.csv`) dan data yang telah di-inverse transform (`data_clustering_inverse.csv`).

2.  **Notebook Klasifikasi (`[Klasifikasi]_Submission_Akhir_BMLP_Muhammad_Husain_Fadhlillah_MC006D5Y2343.ipynb`):**
    - **Pemuatan Data Hasil Clustering:** Menggunakan data yang telah diberi label dari tahap clustering (`data_clustering_inverse.csv`).
    - **Pembagian Dataset:** Membagi data menjadi set pelatihan dan pengujian.
    - **Pembangunan Model Klasifikasi:**
      - Model dasar: Decision Tree.
      - Eksplorasi model lain: K-Nearest Neighbors (KNN), Random Forest, dan Logistic Regression.
    - **Evaluasi Model:** Mengevaluasi performa model menggunakan metrik seperti Akurasi, Presisi, Recall, dan F1-Score.
    - **Hyperparameter Tuning:** Mengoptimalkan parameter pada model menggunakan GridSearchCV.
    - **Ekspor Model:** Menyimpan model-model yang telah dilatih.

## 🛠️ Teknologi dan Pustaka yang Digunakan

- **Python**
- **Jupyter Notebook**
- **Core Libraries:**
  - `Pandas`: Untuk manipulasi dan analisis data.
  - `NumPy`: Untuk operasi numerik.
  - `Scikit-learn`: Untuk implementasi model machine learning (KMeans, PCA, DecisionTreeClassifier, KNeighborsClassifier, RandomForestClassifier, XGBClassifier, StandardScaler, LabelEncoder, train_test_split, metrics, GridSearchCV).
- **Visualization Libraries:**
  - `Matplotlib`: Untuk pembuatan plot dasar.
  - `Seaborn`: Untuk visualisasi data statistik yang lebih menarik.
  - `Yellowbrick`: Untuk visualisasi model machine learning (KElbowVisualizer).
- **Model Persistence:**
  - `Joblib`: Untuk menyimpan dan memuat model terlatih.

## 📁 Berkas dalam Repositori

```
├───[Clustering]_Submission_Akhir_BMLP_Muhammad_Husain_Fadhlillah_MC006D5Y2343.ipynb
├───[Klasifikasi]_Submission_Akhir_BMLP_Muhammad_Husain_Fadhlillah_MC006D5Y2343.ipynb
├───data_clustering.csv
├───data_clustering_inverse.csv
├───model_clustering.h5
├───PCA_model_clustering.h5
├───decision_tree_model.h5
├───explore_Logistic Regression_classification.h5
└───tuning_classification.h5
```

## ✨ Ringkasan Hasil Utama

### Tahap Clustering

- Algoritma K-Means berhasil mengidentifikasi **3 cluster pelanggan** yang berbeda.
- Metode Elbow menunjukkan bahwa 3 adalah jumlah cluster yang optimal.
- **Silhouette Score** untuk model K-Means utama adalah sekitar **0.573**, menunjukkan pemisahan cluster yang cukup baik.
- Setiap cluster dianalisis secara mendalam untuk memahami karakteristik uniknya berdasarkan data demografi, finansial, dan perilaku transaksi setelah dilakukan _inverse transform_.

### Tahap Klasifikasi

- Dataset hasil clustering (`data_clustering_inverse.csv`) digunakan sebagai input untuk model klasifikasi.
- Beberapa algoritma klasifikasi dieksplorasi: Decision Tree, KNN, Random Forest, dan Logistic Regression.
- **Model Random Forest menunjukkan performa terbaik** pada data uji di antara model yang dieksplorasi, dengan metrik sebagai berikut:
  - Akurasi: ~0.993
  - Presisi: ~0.993
  - Recall: ~0.993
  - F1-Score: ~0.993
- Hyperparameter tuning dilakukan pada model KNN karena model tersebut terendah daripada model yang lain, namun setelah dituning tetap menghasilkan performa yang rendah dibandingkan model yang lain.
