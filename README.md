# Sistem-Rekomendasi

# Laporan Proyek Machine Learning - Farhan Riyandi

## Project Overview

### Latar Belakang
Pasar industri perfilman, baik di tingkat internasional maupun domestik, terus mengalami pertumbuhan yang menjanjikan. Hal ini dapat dilihat dari peningkatan jumlah penonton bioskop setiap tahun. Pada tahun 2018, misalnya, jumlah penonton bioskop di Indonesia sendiri telah mencapai lebih dari 50 juta orang. Sementara itu, produksi film, termasuk baik dari luar negeri maupun dalam negeri, mencapai hampir 200 judul film yang telah tayang di seluruh Indonesia[1]. Rekomendasi film merupakan aplikasi yang paling banyak digunakan bersama dengan platform multimedia online, yang bertujuan membantu pelanggan untuk secara cerdas mengakses film pilihan mereka dari perpustakaan film yang sangat besar [2]. Contohnya diterapkan pada situs Netflix, IMDb, iqiyi.

Peningkatan jumlah penonton di bioskop sejalan dengan pertumbuhan produksi film yang semakin banyak. Ragam film dengan berbagai alur cerita dan genre baik dari dalam negeri maupun luar negeri, memeriahkan industri perfilman. Namun, melimpahnya produksi film membuat calon penonton kewalahan dan mengalami kesulitan dalam memilih film untuk ditonton. Proses pencarian film menjadi lebih memakan waktu, dan beberapa orang menggunakan fitur pencarian di situs-situs tertentu untuk membantu mereka dalam membuat keputusan. Karena setiap orang memiliki selera yang berbeda, mereka cenderung memilih film yang serupa dengan yang mereka sukai[3]. Karena itu, tujuan dari proyek *machine learning* ini adalah mengembangkan sebuah model machine learning yang dapat digunakan dalam sistem rekomendasi film. 

Sistem rekomendasi menjadi salah satu solusi yang sangat efektif dalam membantu penonton mendapatkan informasi yang relevan mengenai film. Dalam dunia yang dipenuhi dengan berbagai pilihan film dari berbagai genre dan jenis, mencari tahu film mana yang sesuai dengan preferensi pribadi bisa menjadi tugas yang menantang. Oleh karena itu, sistem rekomendasi hadir sebagai solusi cerdas yang mengubah cara kita mengeksplorasi dan menemukan konten yang sesuai.

Salah satu keunggulan utama sistem rekomendasi adalah kemampuannya untuk memahami dan mempelajari preferensi individu. Dengan menganalisis riwayat penonton, peringkat film sebelumnya, dan pola perilaku pengguna, sistem ini dapat memberikan rekomendasi yang disesuaikan dengan selera unik setiap individu. Ini tidak hanya memastikan bahwa penonton mendapatkan film yang sesuai dengan keinginan mereka, tetapi juga membuka pintu untuk mengeksplorasi genre atau direktor baru yang mungkin tidak pernah mereka pertimbangkan sebelumnya.

Keefektifan sistem rekomendasi juga terletak pada kemampuannya untuk memberikan saran yang tidak hanya didasarkan pada sejarah penonton, tetapi juga mempertimbangkan tren dan reaksi pengguna lainnya. Dengan memanfaatkan kecerdasan buatan dan algoritma pemrosesan data, sistem ini dapat memprediksi apa yang mungkin disukai oleh sekelompok penonton dengan preferensi serupa. Ini membantu menciptakan pengalaman menonton yang lebih memuaskan dan memperkaya portofolio film yang dinikmati oleh penonton.

# Business Understanding
Berdasarkan kondisi yang telah diuraikan sebelumnya, kemajuan teknologi di bidang machine learning memainkan peran krusial dalam memahami dan meramalkan tingkah laku pengguna. machine learning dapat memberikan sistem rekomendasi film kepada pengguna, membuka peluang untuk strategi bisnis yang lebih cerdas dengan mengembangkan sebuah sistem rekomendasi film.

## Problem Statement
* Bagaimana menghasilkan top rekomendasi film kepada pengguna?
* Berdasarkan film yang disukai pengguna di masa lalu, Bagaimana cara membuat daftar rekomendasi film dengan metode pendekatan *content based filtering*?
* Berdasarkan kesamaan antar pengguna, Bagaimana cara membuat daftar rekomendasi film dengan metode pendekatan *collaborative filtering*?
* Bagaimana kinerja dan evaluasi model dalam pengembangan sistem rekomendasi content based filtering menggunakan *precision* dan *collaborative filtering* menggunakan *root mean square error*?

## Goals
* Menampilkan top rekomendasi film kepada pengguna.
* Menghasilkan rekomendasi film berdasarkan film yang disukai pengguna menggunakan pendekatan *content based filtering*.
* Menghasilkan rekomendasi film berdasarkan film yang disukai pengguna menggunakan pendekatan *collaborative filtering*.
* Mengetahi kinerja dan evaluasi model dalam pengembangan sistem rekomendasi film *content based filtering* menggunakan *precision* dan *collaborative filtering* menggunakan *root mean square error*.

## Solution Statement
* Melakukan ekplorasi pada data, dan melakukan visualisasi data agar memahami data dan memberikan wawasan tentang data.
* Melakukan data *preparation* agar dapat digunakan dalam membangun model.
* Membangun model dengan *content based filtering* dan melakukan evaluasi menggunakan *precision* dan membangun model dengan *collaborative filtering* menggunakan *root mean square error*.

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

## Exploratory Data Analysis
### Univariate Exploratory Data Analysis
**Movie Variable**

![image](https://github.com/farhanriyandi/Sistem-Rekomendasi/assets/67671418/d67163d7-c401-4379-9e53-fc8c9b4e9966)

Terdapat 9742 baris data dan tidak adanya *missing value*

![image](https://github.com/farhanriyandi/Sistem-Rekomendasi/assets/67671418/e43fa19e-696e-4be0-be38-47e32383a87b)

Banyak tipe genre adalah 951 

**Rating Variable**

![image](https://github.com/farhanriyandi/Sistem-Rekomendasi/assets/67671418/0a832de7-c033-4814-a756-66a7b750661b)

Terdapat 100836 baris data dan tidak adanya *missing value*

![image](https://github.com/farhanriyandi/Sistem-Rekomendasi/assets/67671418/04baf7fe-51ea-4e3d-bd39-dc76a44de8e5)

Dari output di atas, diketahui bahwa nilai maksimum rating adalah 5 dan nilai minimumnya adalah 0.5. Artinya, skala rating berkisar antara 0.5 hingga 5.

![image](https://github.com/farhanriyandi/Sistem-Rekomendasi/assets/67671418/57215e3a-682e-4e29-bfa9-c0fa8f482f93)

Pengguna yang memberikan rating 610, jumlah movie 9724, dan jumlah rating adalah 100836.

### Analisis distribusi data rating pada movie

![image](https://github.com/farhanriyandi/Sistem-Rekomendasi/assets/67671418/5cd97ea0-eff2-4e2a-ad3b-669283e9129a)

Dapat dilihat bahwa sebagian besar rata-rata peringkat movie tersebar dari rating 3 sampai 5.


## Data Preprocessing
### Menggabungkan data rating dan movie berdasarkan movieId

![image](https://github.com/farhanriyandi/Sistem-Rekomendasi/assets/67671418/35496334-d05b-49dd-bb52-c00b9d385e8e)

### Mengecek missing value pada data hasil gabungan antara rating dan movie berdasarkan movieId
| Fitur      | Jumlah Missing Value |
|------------|-----------------------|
| userId     | 0                     |
| movieId    | 0                     |
| rating     | 0                     |
| timestamp  | 0                     |
| title      | 0                     |
| genres     | 0                     |

Tidak ada *missing value* pada data hasil gabungan antara rating dan movie berdasarkan movieId

# Data Preparation
1. Mengurutkan movie berdasarkan movieID dari terkecil ke terbesar kemudian memasukkannya ke dalam variabel fix_movie
2. Sebelum melakukan data preparation lebih lanjut, ukuran dataset yaitu: Baris: 100836 dan kolom 6
3. Membuat variabel preparation yang berisi dataframe fix_movie kemudian membuang data duplikat pada variabel preparation berdasarkan movieId
     * Sebelum membuang data yang duplikat pada variabel preparation berdasarkan movieId ada 100836 baris dan 6 kolom
     * Setelah membuang data yang duplikat pada variabel preparation berdasarkan movieId ada 9724 baris dan 6 kolom
4. Mengonversi data series movieId ke variabel movie_id dalam bentuk list dan jumlah data 9724
5. Mengonversi data series title ke variabel title dalam bentuk list dan jumlah data 9274,
6. Mengonversi data series genres ke variabel genres dalam bentuk list dan jumlah data adalah 9724
7. Membuat dictionary untuk data ‘movie_id’, ‘title’, dan ‘genres’ pada variabel movie_new
8. Setelah melakukan data preparation terdapat pada variabel movie_new, ukuran dataset yaitu: Baris: 9724 dan kolom 3


# Modeling and Result
Proses modeling pada proyek ini menggunakan 2 algoritma yaitu *Content Based Filtering* dan *Collaborative Filtering*. Untuk *Content Based Filtering* merekomendasikan item yang mirip dengan item yang disukai pengguna di masa lalu dan *Collaborative Filtering* dengan memanfaatkan pada tingkat rating dari movie tersebut.

## *Content Based Filtering*
Content-Based Filtering adalah metode rekomendasi yang menggunakan karakteristik atau "konten" dari item untuk merekomendasikan item lain yang memiliki kesamaan karakteristik. Dalam konteks rekomendasi film, ini berarti merekomendasikan film berdasarkan fitur-fitur atau konten tertentu dari film tersebut, seperti genre, aktor, sutradara, atau topik.

![image](https://github.com/farhanriyandi/Sistem-Rekomendasi/assets/67671418/2a64862e-ce05-4a83-90cf-f93ef3cb3261)

**Kelebihan**
1. Personalisasi:
   * Menawarkan rekomendasi yang disesuaikan dengan preferensi individual pengguna berdasarkan karakteristik yang disukai oleh pengguna.

2. Transparansi:
   * Lebih mudah dipahami mengapa suatu item direkomendasikan karena menggunakan informasi tentang fitur-fitur atau konten item tersebut.

3. Tidak Memerlukan Data Eksternal:
   * Tidak terlalu tergantung pada data eksternal atau preferensi pengguna lainnya. Dapat bekerja dengan baik bahkan jika data riwayat pengguna terbatas

**Kelemahan**
1. Keterbatasan Diversitas:
   * Cenderung merekomendasikan item yang serupa dengan yang sudah disukai oleh pengguna, sehingga mungkin kurang efektif dalam mengenalkan pengguna pada item   baru atau berbeda.

2. Ketergantungan pada Representasi Konten:
   * Keberhasilan sistem sangat tergantung pada seberapa baik representasi konten dari item dapat diukur atau diidentifikasi.

3. Kesenjangan Informasi:
   * Dapat mengalami kesulitan jika terdapat sedikit informasi atau variasi dalam fitur-fitur yang digunakan untuk merepresentasikan item.

### Tahapan untuk melakukan pemodelan *Content Based Filtering*
1. Menyiapkan data yang sudah disiapkan pada data *preparation*
   
2. TF-IDF Vectorizer
   
   Teknik TF-IDF Vectorizer digunakan pada sistem rekomendasi pada proyek ini untuk menemukan representasi fitur penting dari setiap genre. mari kita lihat matriks tf-idf untuk beberapa   title dan kategori genre film.
   
   ![image](https://github.com/farhanriyandi/Sistem-Rekomendasi/assets/67671418/340ed156-e05b-43dd-9d1d-b1e0859bac01)

4. Perhitungan *Cosine Similarity*
   
   Dengan teknik *Cosine Similarity* menghitung derajat kesamaan (similarity degree) antar film. Kalkulasi similarity dilakukan dengan function [cosine_similarity](https://scikit-learn.org/stable/modules/generated/sklearn.metrics.pairwise.cosine_similarity.html) pada *library* sklearn. Cosine similarity mengukur kesamaan antara dua vektor dan menentukan apakah kedua vektor tersebut menunjuk ke arah yang sama. Ia menghitung sudut cosinus antara dua vektor. Semakin kecil sudut cosinus, semakin besar nilai *cosine similarity*. Hasil dari perhitungan cosine similarity akan menghasilkan matriks kesamaan yang dapat divisualisasikan melalui konversi ke bentuk dataframe seperti berikut:

| Title                                       | River, The (1984) | Hommage à Zgougou (et salut à Sabine Mamou) (2002) | Cocoanuts, The (1929) | Company Man (2000) | Inkwell, The (1994) |
|---------------------------------------------|-------------------|---------------------------------------------------|------------------------|---------------------|---------------------|
| Hellraiser III: Hell on Earth (1992)         | 0.000000          | 0.0                                               | 0.000000               | 0.000000            | 0.000000            |
| Man of Steel (2013)                         | 0.000000          | 0.0                                               | 0.000000               | 0.000000            | 0.000000            |
| Elizabethtown (2005)                        | 0.466539          | 0.0                                               | 0.205750               | 0.504636            | 0.687253            |
| Revenge of the Green Dragons (2014)         | 0.403822          | 0.0                                               | 0.000000               | 0.000000            | 0.274133            |
| Who Killed the Electric Car? (2006)         | 0.000000          | 1.0                                               | 0.000000               | 0.000000            | 0.000000            |
| Snow White and the Seven Dwarfs (1937)     | 0.228181          | 0.0                                               | 0.504719               | 0.000000            | 0.154900            |
| Rocker, The (2008)                          | 0.000000          | 0.0                                               | 0.407720               | 1.000000            | 0.734280            |
| Boyz N the Hood (1991)                      | 0.503700          | 0.0                                               | 0.000000               | 0.000000            | 0.341935            |
| Faust (1926)                                | 0.350226          | 0.0                                               | 0.000000               | 0.000000            | 0.237749            |
| Scent of a Woman (1992)                     | 1.000000          | 0.0                                               | 0.000000               | 0.000000            | 0.678847            |

4. Mendapatkan Rekomendasi dari model *Content Based Filtering*:
   
Berikut adalah movie yang disukai pengguna dimasa lalu:

| ID   | Title                          | Genres         |
|------|--------------------------------|----------------|
| 5169 | Lover Come Back (1961)         | Comedy,Romance |

Dari gambar diatas pengguna menyukai film Lover Come Back (1961)	dari genre Comedy|Romance. Maka berikut hasil 10 rekomendasi movie kepada pengguna tersebut menggunakan *Content Based Filtering*

| Title                                    | Genres         |
|------------------------------------------|----------------|
| Shall We Dance? (2004)                   | Comedy,Romance |
| The Importance of Being Earnest (1952)   | Comedy,Romance |
| Good Luck Chuck (2007)                   | Comedy,Romance |
| Mo' Money (1992)                         | Comedy,Romance |
| Mr. Deeds (2002)                         | Comedy,Romance |
| Kiss me Kismet (2006)                    | Comedy,Romance |
| When Harry Met Sally... (1989)           | Comedy,Romance |
| Better Off Dead... (1985)                | Comedy,Romance |
| Impromptu (1991)                         | Comedy,Romance |
| 27 Dresses (2008)                        | Comedy,Romance |

dari hasil di atas dapat dilihat bahwa movie yang bergenre antar Comedy, Romance direkomendasikan oleh sistem karena berdasarkan kesukaan pengguna dimasa lalu.

## *Collaborative Filtering*
Collaborative Filtering adalah metode rekomendasi yang menggunakan informasi dari pengguna lain (user) atau item yang serupa untuk merekomendasikan item kepada pengguna. Ide dasarnya adalah bahwa pengguna yang memiliki preferensi atau perilaku serupa dalam masa lalu cenderung memiliki preferensi serupa di masa depan. Dalam konteks rekomendasi film, Collaborative Filtering mengidentifikasi kemiripan antara pengguna atau item berdasarkan data historis pengguna.

**Kelebihan**
1. Personalisasi yang Tinggi:
   * Mampu memberikan rekomendasi yang sangat personal karena mempertimbangkan preferensi dan perilaku pengguna secara langsung.

2. Tidak Memerlukan Informasi Item:
   * Tidak perlu informasi rinci tentang item (film) karena hanya membutuhkan pola hubungan antar-pengguna atau antar-item.

3. Efektif untuk Data yang Besar:
   * Dapat menghasilkan rekomendasi yang baik bahkan pada dataset besar dengan banyak item

**Kelemahan**
1. *Cold Start Problem*:
   * Kesulitan memberikan rekomendasi untuk pengguna baru atau item baru yang belum memiliki data historis.

2. Ketergantungan pada Data Historis:
   * Bergantung pada data historis yang cukup untuk mengidentifikasi pola hubungan antar-pengguna atau antar-item.

3. Sparsity Problem:
   * Dalam dataset besar, mungkin ada banyak item atau pengguna yang tidak memiliki cukup data untuk membangun model yang akurat.

### Tahapan untuk melakukan pemodelan *Collaborative Filtering*
1. Data Understanding
   Pada tahap awal meng-*import library* yang dibutuhkan, kemudian membaca dataset rating yang telah digunakan sebelumnya.
   
2. Data Preparation
   Pada tahap ini, menyandikan (encode) fitur ‘userId’ dan ‘movieId’ ke dalam indeks integer. Berikutnya memetakan userId dan placeId ke dataframe yang berkaitan.

3. Dataset *Splitting*
   Data *train* digunakan untuk melatih model. Saat proses pelatihan, model belajar dari pola-pola dalam data *train* untuk memahami hubungan antara fitur 
   (variabel independen) dan variabel target (variabel dependen). data val digunakan untuk mengevaluasi kinerja model. Model diuji pada data yang tidak pernah 
   dilihat selama proses pelatihan untuk mengukur seberapa baik model tersebut mampu menggeneralisasi pada data baru. Dalam proyek ini data dibagi menjadi 80:20.
   Hasil dari pembagian data *train* dan data val dengan rasio 80:20 adakah sebagai berikut:
     * Total data keseluruhan 100836
     * Total data latih 80668
     * Total data uji 20168

Dikarenakan dataset sudah besar yakni 100836, pembagian rasio data latih dan data uji 80:20 pada data uji sudah memiliki cukup banyak data untuk menguji model memiliki kinerja yang baik atau tidak.

4. Proses *Training*
   Pelatihan model melibatkan penerapan teknik embedding untuk mengukur kesesuaian antara film dan pengguna. Pada tahap kompilasi, digunakan BinaryCrossentropy sebagai fungsi kerugian, Optimizer Adam (Adaptive Moment Estimation), dan Root Mean Squared Error (RMSE) sebagai evaluasi metrik. Proses pelatihan model berlangsung sebanyak 10 epochs dengan penggunaan *batch size* 64.

5. Mendapatkan rekomendasi dari model *Collaborative Filtering*:
Berikut adalah rekomendasi movie berdasarkan rating untuk *users* 42

Film dengan rating tinggi dari pengguna 42
| Title                     | Genre                    |
|---------------------------|--------------------------|
| A Time to Kill (1996)     | Drama,Thriller           |
| The Doors (1991)          | Drama                    |
| Top Gun (1986)            | Action,Romance           |
| On Golden Pond (1981)     | Drama                    |
| Saving Private Ryan (1998)| Action,Drama,War         |

Berikut ada 10 top rekomendasi Film
| Title                                            | Genre                                |
|--------------------------------------------------|--------------------------------------|
| Rear Window (1954)                               | Mystery,Thriller                     |
| Cinema Paradiso (Nuovo cinema Paradiso) (1989)   | Drama                                |
| Cool Hand Luke (1967)                            | Drama                                |
| This Is Spinal Tap (1984)                        | Comedy                               |
| Sweet Hereafter, The (1997)                      | Drama                                |
| Zero Effect (1998)                               | Comedy,Mystery,Thriller              |
| Boondock Saints, The (2000)                      | Action,Crime,Drama,Thriller          |
| Lord of the Rings: The Two Towers, The (2002)    | Adventure,Fantasy                    |
| Departed, The (2006)                             | Crime,Drama,Thriller                 |
| Dark Knight, The (2008)                          | Action|Crime|Drama|IMAX              |



Diatas adalah hasil dari top 10 rekomendasi movies dimana genre Mystery|Thriller, Drama, Comedy, Adventure|Fantasy menjadi rekomendasi movie kepada pengguna tersebut.

# Evaluation
### Hasil Evaluasi untuk *Content Based Filtering*
Evaluasi yang digunakan pada model *content based filtering* adalah precision. *Precision* adalah metrik evaluasi yang mengukur sejauh mana item yang diidentifikasi sebagai positif oleh model benar-benar relevan atau benar-benar positif. Presisi didefinisikan sebagai rasio antara jumlah item relevan yang diidentifikasi dengan benar dan total jumlah item yang diidentifikasi sebagai positif oleh model.

**Kegunaan Precision**:
Presisi memberikan wawasan tentang tingkat ketepatan model dalam mengidentifikasi item yang benar-benar relevan dari total item yang dianggap positif. Metrik ini berguna terutama dalam konteks tugas klasifikasi di mana model harus membedakan antara kelas positif dan kelas negatif.

**Intrepretasi Precision**:
* Tingkat presisi yang tinggi menunjukkan bahwa sebagian besar item yang diidentifikasi sebagai positif oleh model memang benar-benar positif.
* Tingkat presisi yang rendah dapat menandakan adanya masalah, di mana sejumlah besar item yang diidentifikasi sebagai positif mungkin tidak relevan atau tidak 
  benar-benar positif.

Adapun rumus *presicion* adalah sebagai berikut:

![image](https://github.com/farhanriyandi/Sistem-Rekomendasi/assets/67671418/9ef69612-f037-45d9-8d33-0f29e74587e0)

Dapat dilihat bahwa rekomendasi movie yang mirip dari Lover Come Back (1961)

| ID   | Title                          | Genres         |
|------|--------------------------------|----------------|
| 5169 | Lover Come Back (1961)         | Comedy,Romance |

sistem merekomendasikan Top 10 movies yaitu:

| Title                                    | Genres         |
|------------------------------------------|----------------|
| Shall We Dance? (2004)                   | Comedy,Romance |
| The Importance of Being Earnest (1952)   | Comedy,Romance |
| Good Luck Chuck (2007)                   | Comedy,Romance |
| Mo' Money (1992)                         | Comedy,Romance |
| Mr. Deeds (2002)                         | Comedy,Romance |
| Kiss me Kismet (2006)                    | Comedy,Romance |
| When Harry Met Sally... (1989)           | Comedy,Romance |
| Better Off Dead... (1985)                | Comedy,Romance |
| Impromptu (1991)                         | Comedy,Romance |
| 27 Dresses (2008)                        | Comedy,Romance |

Dari hasil rekomendasi di atas, diketahui bahwa Lover Come Back (1961) termasuk ke dalam genre Comedy|Romance. Dari 10 item yang direkomendasikan, 10 item memiliki genre Comedy|Romance. Artinya, precision dari sistem tersebut adalah 

Precision = 10/10

Precision = 1

Precision = 100%

Berdasarkan Top 10 rekomendasi film yang diberikan didapatkan pricision sebesar 100% dari model content-based filtering untuk sistem rekomendasi yang telah dikembangkan

### Hasil Evaluasi untuk *Collaborative Filtering*
Evaluasi metrik yang digunakan untuk mengukur kinerja model *Collaborative Filtering* adalah metrik RMSE (Root Mean Squared Error). RMSE adalah metode evaluasi yang mengukur perbedaan antara nilai prediksi sebuah model dengan nilai yang sebenarnya sebagai estimasi atas pengamatan yang dilakukan. RMSE diperoleh dengan mengakarkan hasil dari Mean Square Error. Tingkat keakuratan suatu metode estimasi kesalahan pengukuran dapat diidentifikasi melalui nilai RMSE yang kecil. Metode estimasi dengan RMSE yang lebih rendah dianggap lebih akurat dibandingkan dengan metode yang memiliki RMSE yang lebih besar.

**Kegunaan RMSE**

RMSE umumnya digunakan dalam konteks regresi untuk mengevaluasi seberapa baik model dapat menghasilkan prediksi yang mendekati nilai sebenarnya. Semakin kecil nilai RMSE, semakin baik model dapat memprediksi nilai aktual.

**Interpretasi RMSE**
* RMSE memberikan gambaran tentang tingkat kesalahan prediksi model dalam satuan yang sama dengan variabel yang diprediksi.
* Nilai RMSE yang rendah menunjukkan bahwa model cenderung memberikan prediksi yang dekat dengan nilai sebenarnya.
* Nilai RMSE yang tinggi menandakan bahwa terdapat ketidakcocokan yang signifikan antara nilai prediksi dan nilai sebenarnya.

Adapun formula dari metrik RMSE adalah sebagai berikut:
  
![image](https://github.com/farhanriyandi/Sistem-Rekomendasi/assets/67671418/a2c52689-e846-4544-a739-63425d35c38b)

Keterangan:
* At : Nilai Aktual.
* ft = Nilai hasil peramalan.
* N = banyaknya dataset

Berikut adalah visualisasi metrik dari evaluasi model *collaborative Filtering*:

![image](https://github.com/farhanriyandi/Sistem-Rekomendasi/assets/67671418/faa7748a-4d64-4833-8ae6-9df8dcf14987)

Berdasarkan visualisasi metrik diatas didapatkan RMSE: 0.1963 dan validasi RMSE: 0.2030, yang mana sistem telah dikembangkan sudah baik.

# Conclusion
Berdasarkan sistem rekomendasi yang telah dibuat pada proyek ini, pada model *content based filtering* mendapatkan *precision* 100%. Pada model *collaborative Filtering* mendapatkan root mean square error 0.1963 pada data latih dan 0.2030 pada data uji. Hasil dari evaluasi kedua model tersebut sudah baik diharapkan dapat merekomendasikan film sesuai dengan preferensi, minat atau perilaku pengguna. 

# Referensi
[1]"Tren Positif Film Indonesia," Indonesia.go.id. [Online]. Available: https://indonesia.go.id/ragam/seni/sosial/tren-positif-film-indonesia. [Accessed: 28-Aug-2020].
[2] Z. Wang, X. Yu, N. Feng, and Z. Wang, "An improved collaborative movie recommendation system using computational intelligence," Journal of Visual Languages & Computing, vol. 25, no. 6, pp. 667-675, 2014.
[3] Fajriansyah, M., Adikara, P. P., & Widodo, A. W. (2021). "Sistem Rekomendasi Film Menggunakan Content Based Filtering." Jurnal Pengembangan Teknologi Informasi dan Ilmu Komputer, 5(6), 2188-2199.
