# UTS_ML_2301010413_Lusia-Ricindi-Mumun-Jelahut
# UTS Machine Learning — Clustering Destinasi Wisata Indonesia (CRISP-DM)

## Identitas Mahasiswa
* **Nama**: [Lusia Ricindi Mumun Jelahut]
* **NIM**: [2301010413]
* **Kelas**: [XX]
* **Mata Kuliah**: Machine Learning (UTS — Jalur C: Clustering)

## Pernyataan Penggunaan AI
* **Alat yang dipakai**: Gemini (asisten AI percakapan & penyusunan dokumentasi/kode).
* **Untuk bagian apa**: Membantu menyusun kerangka tahapan CRISP-DM (Tahap 1–6), merapikan penjelasan narasi/blok *Keputusan saya*, menyusun draf `README.md`, serta membantu memahami langkah penggunaan Google Colab dan GitHub.
* **Bagaimana hasilnya diperiksa**: Seluruh kode dijalankan secara berurutan dari awal hingga akhir di Google Colab menggunakan `Runtime -> Run all` untuk memastikan bebas *error* dan seluruh *output* (statistik, grafik Elbow & Silhouette, plot PCA 2D, serta ringkasan cluster) tampil dengan benar. Angka metrik, ukuran cluster, dan kesimpulan dicocokkan langsung dengan hasil eksekusi kode serta disesuaikan dengan ketentuan soal.

## Ringkasan Proyek & Dataset
* **Dataset**: *Indonesia Tourism Destination* (`tourism_with_id.csv`, 437 baris).
* **Sumber & Akses Dataset**: Kaggle — *Indonesia Tourism Destination* oleh A. Prabowo (`https://www.kaggle.com/datasets/aprabowo/indonesia-tourism-destination`), diakses pada 25 November 2026.
* **Cara mengunduh dataset**: Buka tautan dataset di Kaggle, unduh berkas `tourism_with_id.csv`, lalu letakkan di folder `data/tourism_with_id.csv` atau unggah saat menjalankan notebook di Google Colab.
* **Metode & Parameter**: **K-Means Clustering** dengan `SEED = 413`, `StandardScaler`, dan jumlah cluster terpilih **$k = 4$** (Silhouette Score `0,3619`).

## Ringkasan Alur CRISP-DM (Tahap 1–6)
1. **Pemahaman Masalah dan Data**: Menetapkan tujuan pengelompokan destinasi wisata berbasis fitur numerik (`Price`, `Rating`, `Time_Minutes`, `Lat`, `Long`) untuk membantu penyusunan paket wisata, promosi, dan pengelolaan destinasi[cite: 2].
2. **Eksplorasi dan Visualisasi Data**: Menganalisis distribusi fitur, korelasi antarvariabel numerik, serta deteksi *outlier* menggunakan histogram, *heatmap* korelasi, dan *boxplot*[cite: 2].
3. **Pra-pemrosesan Data**: Menangani nilai kosong (termasuk imputasi median pada `Time_Minutes`), menghapus kolom/duplikasi yang tidak relevan, dan melakukan standarisasi fitur numerik dengan `StandardScaler`[cite: 2].
4. **Pemodelan**: Melatih model **K-Means** (`SEED = 413`) serta membandingkan jumlah cluster menggunakan metode Elbow dan Silhouette Score untuk memilih **$k = 4$**[cite: 2].
5. **Evaluasi**: Mengevaluasi kualitas pemisahan cluster dan memvisualisasikan sebaran cluster menggunakan **PCA** serta profil karakteristik tiap cluster[cite: 2].
6. **Kesimpulan**: Merangkum karakter keempat cluster, rekomendasi tindakan, keterbatasan dataset (437 data di 5 kota besar di Pulau Jawa serta imputasi median durasi), dan rencana pengembangan lanjutan[cite: 2].

## Ringkasan Hasil Clustering ($k = 4$)
* **Cluster 0 (29 destinasi)**: Rata-rata tiket Rp 88.275,86, rating 4,46, durasi 180,00 menit (didominasi destinasi berdurasi kunjungan panjang)[cite: 2].
* **Cluster 1 (184 destinasi)**: Rata-rata tiket Rp 21.589,67, rating 4,43, durasi 72,96 menit (destinasi terjangkau di wilayah barat)[cite: 2].
* **Cluster 2 (2 destinasi)**: Rata-rata tiket Rp 700.000,00, rating 4,70, durasi 120,00 menit (destinasi bertarif tinggi/eksklusif)[cite: 2].
* **Cluster 3 (222 destinasi)**: Rata-rata tiket Rp 14.394,14, rating 4,44, durasi 70,34 menit (segmen terbesar dengan tarif paling ekonomis di wilayah tengah/timur)[cite: 2].

## Struktur Repository
```text
UTS-ML-NIM-Nama/
├── README.md
├── notebook/
│   └── UTS_ML_NIM_Nama.ipynb
├── data/
│   └── tourism_with_id.csv
└── reports/
    └── [grafik utama / slide presentasi jika ada]
