# Sistem-Rekomendasi

# Laporan Proyek Machine Learning - Farhan Riyandi

## Project Overview

### Latar Belakang
Peningkatan jumlah penonton di bioskop sejalan dengan pertumbuhan produksi film yang semakin banyak. Ragam film dengan berbagai alur cerita dan genre baik dari dalam negeri maupun luar negeri, memeriahkan industri perfilman. Namun, melimpahnya produksi film membuat calon penonton kewalahan dan mengalami kesulitan dalam memilih film untuk ditonton. Proses pencarian film menjadi lebih memakan waktu, dan beberapa orang menggunakan fitur pencarian di situs-situs tertentu untuk membantu mereka dalam membuat keputusan. Karena setiap orang memiliki selera yang berbeda, mereka cenderung memilih film yang serupa dengan yang mereka sukai. Salah satu solusi untuk mendapatkan informasi yang relevan mengenai film adalah melalui penggunaan sistem rekomendasi [1].

# Business Understanding

## Problem Statement

* Bagaimana cara membuat rekomendasi film yang akurat agar pengguna tidak memakan waktu banyak dalam mencari film?


## Goals
* Membuat sistem rekomendasi film yang akurat agar pengguna tidak memakan waktu banyak dalam mencari film

## Solution Statement
Solusi yang dibuat dapat menggunakan 2 algoritma yaitu:
* Content Based Filtering: Merekomendasikan item yang mirip dengan item yang disukai pengguna di masa lalu.
* Collaborative Filtering: Bergantung pada pendapat komunitas pengguna. Collaborative Filtering tidak membutuhkan atribut khusus untuk setiap item, berbeda dengan sistem yang berbasis konten.

# Data Understanding
Dataset yang digunakan dalam proyek ini adalah dataset **Movie Recommender System Dataset** yang didapat dari situs kaggle. Berikut adalah link dataset:
[Movie Recommender System](https://www.kaggle.com/datasets/gargmanas/movierecommenderdataset).
variabel-variabel pada movie-recommendation-data adalah sebagai berikut:
* Dataset memiliki format CSV (Comma-Seperated Values).
* Memiliki 2 file csv yaitu: movies.csv, ratings.csv
  
  Pada movies.csv:
    * Terdapat 9742 sampel dan 3 fitur
    * movies.csv memiliki 2 fitur bertipe object dan 1 fitur bertipe int64.
    * Tidak ada *missing value*

  Pada ratings.csv:
    * Terdapat 100836 sampel dan 4 fitur
    * ratings.csv memiliki 1 fitur bertipe float64 dan 3 fitur bertipe int64
    * Tidak ada *missing value*

## Deskripsi Variabel
**Variabel-variabel pada dataset movies.csv:**
* movieId: Merupakan identifikasi unik untuk setiap film dalam dataset.
* title: Merupakan judul dari film yang tercantum dalam dataset. Kolom ini berisi informasi mengenai nama atau judul dari masing-masing film.
* genres: Menunjukkan genre atau kategori film.

**Variabel-variabel pada dataset ratings.csv:**
* userId: Merupakan identifikasi unik untuk setiap pengguna atau pemirsa dalam dataset.
* movieId: Merupakan identifikasi unik untuk setiap film dalam dataset, yang berkorelasi dengan kolom movieId pada dataset movies.csv.
* timestamp: Menunjukkan waktu atau penanda waktu ketika pengguna memberikan rating atau interaksi terhadap suatu film.

# Data Preparation
*  Mengurutkan movie berdasarkan movieID kemudian memasukkannya ke dalam variabel fix_movie
*  Membuat variabel preparation yang berisi dataframe fix_movie kemudian mengurutkan berdasarkan movieId
*  Membuang data duplikat pada variabel preparation
*  Mengonversi data series ‘movieId’ menjadi dalam bentuk list
*  Mengonversi data series ‘movieId’ menjadi dalam bentuk list
*  Mengonversi data series ‘title’ menjadi dalam bentuk list
*  Mengonversi data series ‘genres’ menjadi dalam bentuk list
*  Membuat dictionary untuk data ‘movie_id’, ‘title’, dan ‘genres’ pada variabel movie_new

# Modeling and Result
Proses modeling pada proyek ini menggunakan 2 algoritma yaitu *Content Based Filtering* dan *Collaborative Filtering*. Untuk *Content Based Filtering* merekomendasikan item yang mirip dengan item yang disukai pengguna di masa lalu dan *Collaborative Filtering* dengan memanfaatkan pada tingkat rating dari movie tersebut. 

### Hasil dari *Content Based Filtering*:
Berikut adalah movie yang disukai pengguna dimasa lalu:

![image](https://github.com/farhanriyandi/Sistem-Rekomendasi/assets/67671418/3f2c35ec-33c6-4f6a-912d-f4302f2f0711)

Dari gambar diatas pengguna menyukai film Lover Come Back (1961)	dari genre Comedy|Romance. Maka berikut hasil 10 rekomendasi movie kepada pengguna tersebut menggunakan *Content Based Filtering*
![image](https://github.com/farhanriyandi/Sistem-Rekomendasi/assets/67671418/29bfb3e6-eae7-47ea-abf1-0b8c7bd8a89f)

dari hasil di atas dapat dilihat bahwa movie yang bergenre antar Comedy, Romance direkomendasikan oleh sistem karena berdasarkan kesukaan pengguna dimasa lalu.

### Hasil dari *Collaborative Filtering*:
Berikut adalah rekomendasi movie berdasarkan rating:

![image](https://github.com/farhanriyandi/Sistem-Rekomendasi/assets/67671418/f7d3cbf8-d1d9-4933-99bd-d221b7f501f8)

Diatas adalah hasil dari top 10 rekomendasi movies dimana genre Mystery|Thriller, Drama, Comedy, Adventure|Fantasy menjadi rekomendasi movie kepada pengguna tersebut.

# Evaluation
### Hasil Evaluasi untuk *Content Based Filtering*
Dapat dilihat bahwa rekomendasi movie yang mirip dari Lover Come Back (1961)

![image](https://github.com/farhanriyandi/Sistem-Rekomendasi/assets/67671418/29bded09-8c33-4c6d-b9ba-0a7595dc62dc)

sistem merekomendasikan Top 10 movies yaitu:

![image](https://github.com/farhanriyandi/Sistem-Rekomendasi/assets/67671418/2bf2ef6f-770c-4bcf-af90-3281021ca4d9)

Dari hasil rekomendasi di atas, diketahui bahwa Lover Come Back (1961) termasuk ke dalam genre Comedy|Romance. Dari 10 item yang direkomendasikan, 10 item memiliki genre Comedy|Romance. Artinya, precision dari sistem tersebut adalah 10/10 atau 100%.
Teknik evaluasi model tersebut menggunakan *precision* adapun rumus *presicion* adalah sebagai berikut:

![image](https://github.com/farhanriyandi/Sistem-Rekomendasi/assets/67671418/9ef69612-f037-45d9-8d33-0f29e74587e0)

### Hasil Evaluasi untuk *Collaborative Filtering*






# Referensi
[1] Fajriansyah, M., Adikara, P. P., & Widodo, A. W. (2021). "Sistem Rekomendasi Film Menggunakan Content Based Filtering." Jurnal Pengembangan Teknologi Informasi dan Ilmu Komputer, 5(6), 2188-2199.
