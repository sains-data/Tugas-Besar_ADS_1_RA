# Tugas Besar Analisis Data Statistika

# Kelompok 1 – Kelas RA – 2025

## 1. Cara Menjalankan Script
1. Pastikan struktur folder repository sudah benar: /data/ /code/ /output/ /poster/ README.md

2. Download dataset pada folder: data/Dataset_1_RA.csv

3. Download script R utama pada folder: code/CodeR_1_RA.R

4. Buka script di RStudio lalu install paket yang dibutuhkan:

5. install.packages(c("ggplot2","dplyr","car"))

6. Pada baris ke-6 di R yaitu "df <- read.csv("C:/Users/Dalsa/Downloads/Dataset (1).csv", stringsAsFactors = TRUE)", diganti file path nya dengan direktori masing-masing tempat disimpannya dataset csv

7. Jalankan script dengan menekan: "run all"

## 2. Paket R Yang Digunakan
1. ggplot2
Untuk visualisasi statistik, terutama: Boxplot sebaran nilai IPK, Penanda mean, Warna kategori, Kustomisasi tema
2. dplyr
Untuk manipulasi data: Pembersihan kolom, Grouping, Perhitungan statistik deskriptif
3. car
Digunakan untuk Levene Test, yaitu uji homogenitas varians, salah satu syarat penting ANOVA.

## 3. Penjelasan Singkat Dataset
Dataset yang digunakan merupakan hasil Survei Karakteristik Mahasiswa ITERA dengan total 458 responden. Dataset ini memuat berbagai informasi dasar mahasiswa, seperti program studi, jenis kelamin, domisili, status tempat tinggal, serta IPK terakhir. 

Dalam penelitian ini, fokus analisis diarahkan pada dua variabel utama, yaitu Tempat Tinggal sebagai variabel independen (X) dan IPK sebagai variabel dependen (Y). Variabel Tempat Tinggal terdiri atas beberapa kategori, seperti Asrama, Kontrakan (Bersama/Pribadi), Kos, dan Rumah Orang Tua. Variabel IPK bersifat numerik dan digunakan untuk melihat bagaimana perbedaan tempat tinggal berkaitan dengan variasi nilai IPK mahasiswa.

Kedua variabel ini dianalisis menggunakan statistik deskriptif, visualisasi boxplot, uji korelasi, dan regresi linear sederhana untuk mengevaluasi hubungan antara kondisi tempat tinggal dan prestasi akademik mahasiswa.

## 4. Struktur Repository
1. /data/ → dataset setelah dibersihkan
2. /code/ → script R (codeR_1_RA.R)
3. /output/ → tabel, hasil uji, dan grafik
4. /poster/ → poster A1 (PDF)
5. README.md → dokumentasi proyek
