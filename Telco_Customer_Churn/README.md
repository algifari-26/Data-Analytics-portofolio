# Prediksi & Analisis Retensi Pelanggan (Telco Customer Churn) 📊

**Tautan Dashboard Interaktif:** [Lihat Dashboard Tableau Public Di Sini](Masukkan_Link_Tableau_Anda_Di_Sini)

## 📌 Latar Belakang Masalah
Perusahaan telekomunikasi saat ini menghadapi rasio kehilangan pelanggan (*churn rate*) yang cukup tinggi, yakni sebesar **26.54%**. Mempertahankan pelanggan lama jauh lebih hemat biaya dibandingkan mengakuisisi pelanggan baru. Oleh karena itu, perusahaan membutuhkan pendekatan berbasis data untuk mengidentifikasi pelanggan mana yang berisiko tinggi untuk berhenti berlangganan di masa depan.

## 🎯 Tujuan Proyek
1. Mengidentifikasi faktor-faktor utama yang mendorong pelanggan untuk melakukan *churn*.
2. Membangun model *Machine Learning* untuk memprediksi probabilitas risiko *churn* pada setiap pelanggan (skor 0% - 100%).
3. Menyajikan wawasan (*insights*) ke dalam *Executive Dashboard* yang interaktif sebagai pendukung keputusan (*Decision Support System*) bagi tim Marketing dalam merancang strategi retensi.

## 🛠️ Teknologi & Tools yang Digunakan
* **Bahasa Pemrograman:** Python
* **Library Data & ML:** Pandas, NumPy, Scikit-Learn, Matplotlib, Seaborn
* **Pemodelan:** Random Forest Classifier
* **Visualisasi & BI:** Tableau Public
* **Environment:** Google Colab

## 🚀 Metodologi & Alur Kerja
1. **Pembersihan Data (Data Cleaning):** Menangani anomali data tipe *string* spasi kosong pada kolom `TotalCharges` dengan konversi numerik dan imputasi menggunakan nilai median.
2. **Exploratory Data Analysis (EDA):** Menganalisis distribusi data untuk menemukan pola awal, seperti korelasi antara tingginya *churn* pada 10 bulan pertama masa berlangganan.
3. **Data Preprocessing:** Menerapkan *One-Hot Encoding* untuk mengubah variabel kategorikal menjadi numerik dan melakukan pembagian data (*Stratified Train-Test Split* 80:20).
4. **Machine Learning:** Melatih algoritma *Random Forest* dengan 100 *estimators* untuk memprediksi klasifikasi pelanggan.
5. **Ekstraksi Risiko:** Menghitung `Predict_Proba` untuk mendapatkan persentase tingkat risiko tiap pelanggan, lalu mengekspor hasilnya menjadi dataset baru (`Telco_Churn_Predicted.csv`) untuk *dashboarding*.

## 💡 Insight & Rekomendasi Bisnis
Berdasarkan hasil pemodelan dan visualisasi Tableau, ditemukan beberapa wawasan utama:
* **Kerentanan Jenis Kontrak:** Pelanggan dengan sistem pembayaran Bulanan (*Month-to-month*) menyumbang angka *churn* tertinggi. Risiko menurun drastis ketika pelanggan beralih ke kontrak 1 atau 2 tahun.
* **Sensitivitas Harga:** Tagihan bulanan yang tinggi (rentang $70 - $110) berkorelasi kuat dengan keputusan pelanggan untuk berhenti, terutama jika mereka tidak terikat kontrak jangka panjang.
* **Rekomendasi Tindakan:** Tim Marketing direkomendasikan untuk menargetkan 1.385 pelanggan yang terdeteksi berada di kategori *High-Risk* (Probabilitas > 70%) dengan penawaran diskon khusus atau pemutakhiran gratis (*free upgrade*) dengan syarat mengunci kontrak menjadi 1 tahun.
