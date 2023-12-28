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
* Content Based Filtering
* Collaborative Filtering

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


# Modeling


# Evaluation



# Referensi
[1] Fajriansyah, M., Adikara, P. P., & Widodo, A. W. (2021). "Sistem Rekomendasi Film Menggunakan Content Based Filtering." Jurnal Pengembangan Teknologi Informasi dan Ilmu Komputer, 5(6), 2188-2199.
