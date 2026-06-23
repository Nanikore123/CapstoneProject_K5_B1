# CapstoneProject_K5_B1
"Pengembangan Prototipe Sistem Personalisasi Mobile Banking untuk Meningkatkan Engagement Nasabah Berbasis Analitik dan AI"

---

## Deskripsi Proyek

Proyek ini merupakan Capstone Project K5-B1 yang berfokus pada pengembangan sistem personalisasi pada aplikasi mobile banking berbasis analitik data dan Artificial Intelligence (AI).

Tujuan utama sistem adalah mengelompokkan nasabah berdasarkan perilaku penggunaan layanan mobile banking sehingga aplikasi dapat memberikan rekomendasi produk, promo, dan fitur yang lebih relevan bagi setiap pengguna.

Studi kasus menggunakan konsep personalisasi layanan pada aplikasi OCTO Mobile milik CIMB Niaga.

---

## Latar Belakang

Setiap nasabah memiliki pola penggunaan mobile banking yang berbeda-beda. Sebagian lebih sering melakukan transfer, sebagian aktif menggunakan QRIS dan top-up, sementara yang lain lebih tertarik pada produk investasi.

Pendekatan personalisasi memungkinkan aplikasi memberikan pengalaman yang lebih relevan kepada pengguna sehingga dapat meningkatkan:

* User Engagement
* User Experience
* Feature Adoption
* Cross-Selling Opportunity
* Customer Retention

---

## Teknologi AI/ML yang Digunakan

Project ini menggunakan pendekatan **Unsupervised Learning** dengan algoritma:

### K-Means Clustering

Digunakan untuk mengelompokkan nasabah berdasarkan kemiripan perilaku transaksi dan penggunaan fitur aplikasi.

### Alur Pemrosesan Data

```text
Raw Dataset
      ↓
Preprocessing
      ↓
Feature Scaling (StandardScaler)
      ↓
Dimensionality Reduction (PCA)
      ↓
K-Means Clustering
      ↓
Segment Labeling
      ↓
Personalized Recommendation
```

---

## Dataset

Dataset yang digunakan merupakan dataset dummy (simulasi) yang dibuat untuk merepresentasikan perilaku pengguna mobile banking.

**Jumlah Data:** 10.000 Nasabah

### Fitur Utama

* Age
* Monthly Income
* Average Balance
* Transaction Frequency
* Transfer Ratio
* Payment Ratio
* QRIS Ratio
* Top Up Ratio
* Investment Activity
* Loan Usage
* Credit Card Usage
* Cardless Usage
* Poin Xtra Active
* Login Frequency Weekly
* Average Session Duration
* Recent Transaction Days
* Dominant Activity
* Frequent Product
* Customer Type

---

## Preprocessing

### 1. Label Encoding

Mengubah fitur kategorikal menjadi numerik.

Contoh fitur:

* dominant_activity
* frequent_product
* customer_type

### 2. StandardScaler

Digunakan untuk menyamakan skala antar fitur sehingga tidak terjadi bias akibat perbedaan rentang nilai.

### 3. PCA (Principal Component Analysis)

Digunakan untuk mereduksi dimensi fitur sehingga proses clustering menjadi lebih efisien tanpa kehilangan informasi utama secara signifikan.

---

## Penentuan Jumlah Cluster

Jumlah cluster ditentukan menggunakan dua metode evaluasi:

### Elbow Method

Digunakan untuk melihat titik penurunan inertia yang mulai melandai.

### Silhouette Score

Digunakan untuk mengukur kualitas pemisahan antar cluster.

### Hasil

```text
Jumlah Cluster Optimal (k) = 6
```

---

## Hasil Segmentasi Nasabah

Hasil clustering kemudian diterjemahkan menjadi beberapa segmen bisnis yang lebih mudah dipahami.

### Digital Spender

**Karakteristik:**

* Aktif menggunakan QRIS
* Sering melakukan top-up
* Aktif menggunakan layanan digital

**Rekomendasi:**

```text
Promo Cashback QRIS Tap & Bills Top Up
```

---

### Bill Payer

**Karakteristik:**

* Sering membayar tagihan
* Aktif menggunakan fitur pembayaran

**Rekomendasi:**

```text
Promo Cashback Tagihan & Auto-Debit Bulanan
```

---

### Investor

**Karakteristik:**

* Aktivitas investasi tinggi
* Memiliki saldo relatif besar

**Rekomendasi:**

```text
Promo Reksa Dana & Savings Deposito OCTO
```

---

### Low Activity

**Karakteristik:**

* Aktivitas transaksi relatif rendah
* Penggunaan fitur masih terbatas

**Rekomendasi:**

```text
Gratis Biaya Transfer & Eksplorasi Fitur OCTO
```

---

## Privacy & Consent

Prototype menerapkan konsep **User Consent**.

Hanya pengguna yang memberikan persetujuan (consent) yang akan diproses untuk kebutuhan personalisasi.

Jika pengguna tidak memberikan consent:

```text
Tidak dilakukan segmentasi
Tidak diberikan rekomendasi personalisasi
```

Hal ini bertujuan menjaga privasi dan kepatuhan terhadap prinsip perlindungan data pengguna.

---

## Simulasi Integrasi Backend

Model yang telah dilatih dapat disimpan dalam format:

```text
scaler.pkl
pca_model.pkl
kmeans_model.pkl
segment_map.pkl
```

### Alur Inference

```text
Input Data User Baru
        ↓
StandardScaler
        ↓
PCA Transform
        ↓
K-Means Predict
        ↓
Cluster
        ↓
Segment
        ↓
Recommendation
```

---

## Dashboard Analitik

Dashboard prototype menampilkan:

* Distribusi Segmen Nasabah
* Proporsi Segmen Nasabah
* Distribusi Rekomendasi per Segmen
* Proporsi Dominant Activity per Segmen
* Top 5 Aktivitas Dominan Nasabah

---

## Tech Stack

### Data Processing & Machine Learning

* Python
* Pandas
* NumPy
* Scikit-Learn

### Visualization

* Matplotlib
* Seaborn

### Deployment (Prototype)

* Google Colab
* GitHub

### Frontend & Backend

* Flutter
* FLASK API*

---