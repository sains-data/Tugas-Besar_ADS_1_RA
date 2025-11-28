# Tugas Besar Analisis Data Statistika

# Kelompok 1 – Kelas RA – 2025

## Paket R yang Digunakan
1. ggplot2
Untuk visualisasi statistik, terutama: Boxplot sebaran nilai IPK, Penanda mean, Warna kategori, Kustomisasi tema
2. dplyr
Untuk manipulasi data: Pembersihan kolom, Grouping, Perhitungan statistik deskriptif
3. car
Digunakan untuk Levene Test, yaitu uji homogenitas varians, salah satu syarat penting ANOVA.

Dataset berisi 326 baris (mahasiswa) dan 20 variabel, di antaranya:
IPK : Indeks Prestasi Kumulatif terakhir
Tempat_Tinggal : Kategori tempat tinggal mahasiswa (Kos, Kontrakan, Rumah orang tua, dll.)
Program Studi: Program studi mahasiswa
Jenis Kelamin: L/P
Tinggi & Berat Badan: Informasi fisik
Pekerjaan Orang Tua: Pekerjaan ayah & ibu
Pendapatan Orang Tua: Pendapatan per bulan
Jumlah Saudara / Anggota Keluarga: Data demografi

# Tahapan dan Alur Analisis
1. Import & Data Cleaning
- Membaca dataset CSV
- Menyamakan nama kolom: “IPK” dan “Tempat_Tinggal”
- Mengubah IPK menjadi numeric
- Menstandarkan nama label tempat tinggal agar konsisten
Tahapan ini memastikan analisis tidak terganggu oleh inkonsistensi data survei.

2. Statistik Deskriptif
-Menggunakan group_by() dan summarise() pada setiap kategori tempat tinggal:
- Jumlah responden (N)
- Rata-rata IPK
- Standar deviasi
- Nilai minimum & maksimum
Statistik deskriptif memberikan gambaran awal mengenai:
- Apakah ada kelompok yang tampak memiliki IPK lebih tinggi?
- Sebaran IPK antar kategori

3. Visualisasi Boxplot
Boxplot digunakan untuk:
- Melihat median dan persebaran IPK
- Mengidentifikasi outlier
-Mendeteksi pola perbedaan antara kategori
  Outlier diberi warna merah
  Mean ditampilkan sebagai titik putih
  Label kategori dirapikan agar lebih mudah dibaca
Visualisasi ini membantu meramalkan apakah ANOVA mungkin menemukan perbedaan nyata.

4. Uji Asumsi ANOVA
a. Uji Normalitas Residual (Shapiro–Wilk)
Dijalankan pada residual model ANOVA, bukan pada setiap kelompok. Karena ini mengikuti asumsi model linear.
Hasil interpretasi:
Jika p-value > 0.05 → residual dianggap berdistribusi normal
Jika p-value < 0.05 → asumsi normalitas dilanggar
Karena jumlah responden 326, maka sesuai dengan limit central theorem yang artinya tetap bisa dilanjutkan
b. Q-Q Plot
Digunakan sebagai verifikasi visual:
- Titik mengikuti garis: distribusi residual mendekati normal
- Kurva melengkung: potensi masalah normalitas
c. Uji Homogenitas Varians (Levene Test)
Syarat ANOVA lain adalah setiap kelompok harus memiliki varians yang mirip.
Interpretasi:
- p-value > 0.05 → varians homogen
- p-value < 0.05 → varians tidak homogen
Jika tidak homogen, alternatif yang bisa digunakan adalah Welch ANOVA.

5. One-Way ANOVA
Model yang digunakan:
IPK, Tempat_Tinggal
Output yang diperoleh:
- Df (Degrees of Freedom)
- Sum Sq (Jumlah Kuadrat)
- Mean Sq
- F-value (statistik uji)
- P-value (Pr > F)

# Interpretasi Hasil
- Jika p-value < 0.05: Terdapat perbedaan signifikan rata-rata IPKberdasarkan tempat tinggal. Dilanjutkan dengan uji lanjut seperti Tukey HSD.
- Jika p-value > 0.05: Tidak ada bukti perbedaan signifikan IPK antar kategori tempat tinggal.
Cara Menjalankan Script
1. Buka RStudio
2. Pastikan library terinstal
3. Buka file script:
4. Jalankan keseluruhan script
5. Hasil akan muncul di output
