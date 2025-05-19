# Laporan Akhir Machine Learning :  Netflix Movie Recommendation System Based on Content-Based and Collaborative Filtering - Eva Yuliana
## Proyek Overview
![dataset-cover](https://github.com/Eva-Yuliana/Sistem-Rekomendasi/blob/main/dataset-cover.jpg?raw=true)

Seiring dengan meningkatnya popularitas layanan streaming seperti Netflix, jumlah konten yang tersedia pun mengalami lonjakan drastis. Ribuan film dan acara TV tersedia dalam berbagai genre, negara asal, dan tahun rilis, membuat pengguna kesulitan untuk menemukan tontonan yang sesuai dengan selera mereka. Dalam situasi ini, sistem rekomendasi berperan penting sebagai alat bantu yang menyarankan konten yang relevan dan personal bagi pengguna [[1]](https://dl.acm.org/doi/10.1145/1864708.1864721).

Netflix, sebagai salah satu platform streaming terbesar di dunia, telah mengumpulkan data besar tentang film dan acara TV yang tersedia di platform-nya. Salah satu dataset publik yang merepresentasikan informasi tersebut tersedia di Kaggle [[2]](https://www.kaggle.com/datasets/shivamb/netflix-shows). Dataset ini memuat informasi penting seperti judul, genre, sutradara, aktor, negara asal, tanggal rilis, dan deskripsi singkat.

Rekomendasi yang akurat dapat membantu meningkatkan pengalaman pengguna serta waktu tonton (watch time), yang berdampak langsung pada loyalitas pengguna dan pendapatan perusahaan [[3]](https://ieeexplore.ieee.org/document/7552548). Oleh karena itu, dalam proyek ini dikembangkan sistem rekomendasi film menggunakan dua pendekatan utama:

1. **Content-Based Filtering**: merekomendasikan film berdasarkan kemiripan atribut konten, seperti genre, sutradara, dan deskripsi film.
2. **Collaborative Filtering**: menyarankan film berdasarkan perilaku pengguna lain yang memiliki pola preferensi serupa.

Tujuan dari proyek ini adalah untuk:
- Menjelajahi distribusi dan karakteristik konten Netflix berdasarkan genre, negara, dan tahun rilis.
- Mengembangkan sistem rekomendasi film yang efektif dan personal.
- Memberikan rekomendasi yang relevan bagi pengguna untuk meningkatkan efisiensi eksplorasi dan kepuasan pengguna dalam menemukan film di platform Netflix.

Melalui analisis data eksploratif dan penerapan dua pendekatan rekomendasi yang berbeda, proyek ini diharapkan dapat menghasilkan solusi yang dapat diimplementasikan dalam sistem informasi nyata, seperti yang digunakan oleh layanan streaming kontemporer.

## Referensi

[1] B. Sarwar, G. Karypis, J. Konstan, and J. Riedl, "Item-based collaborative filtering recommendation algorithms," in *Proceedings of the 10th international conference on World Wide Web*, 2001, pp. 285–295.

[2] S. Sharma, "Netflix Movies and TV Shows Dataset," Kaggle. [Online]. Available: https://www.kaggle.com/datasets/shivamb/netflix-shows

[3] G. Linden, B. Smith, and J. York, "Amazon.com recommendations: Item-to-item collaborative filtering," *IEEE Internet Computing*, vol. 7, no. 1, pp. 76–80, 2003.


## Business Understanding
### Problem Statements
1. Bagaimana distribusi film berdasarkan jenis, negara, dan tahun rilis pada dataset Netflix?
2. Bagaimana performa film berdasarkan genre dan negara asal?
3. Bagaimana cara mengetahui film yang relevan atau mirip dengan preferensi pengguna tertentu?
4. Bagaimana membangun sistem rekomendasi film yang efektif dan dapat diimplementasikan?

### Goals
1. Mengetahui distribusi film berdasarkan genre, negara, dan tahun rilis dari data Netflix.
2. Mengidentifikasi genre dan negara yang paling banyak diminati berdasarkan jumlah film yang tersedia.
3. Menghasilkan visualisasi yang menarik dan informatif mengenai karakteristik konten Netflix.
4. Mengembangkan sistem rekomendasi film menggunakan pendekatan content-based filtering dan collaborative filtering untuk menyarankan film yang relevan bagi pengguna.

### Solution Approach
1. Melakukan Exploratory Data Analysis (EDA) untuk memahami struktur dan pola dari data film Netflix.
2. Mengimplementasikan pendekatan content-based filtering dengan menggunakan kemiripan konten berdasarkan genre, sutradara, dan deskripsi.
3. Mengimplementasikan pendekatan collaborative-based filtering menggunakan algoritma cosine similarity atau deep learning berdasarkan data perilaku pengguna (jika tersedia).
4. Mengevaluasi performa sistem rekomendasi untuk memastikan akurasi dan relevansi rekomendasi yang dihasilkan.


## Data Understanding

Dataset yang digunakan dalam proyek ini merupakan data dari platform Netflix, yang berisi informasi terkait film dan acara TV yang tersedia pada layanan tersebut. Dataset ini umum digunakan dalam berbagai proyek analitik dan sistem rekomendasi, dan dapat diakses secara publik melalui platform Kaggle pada [tautan ini](https://www.kaggle.com/datasets/shivamb/netflix-shows).

### Keterangan Variabel

Dataset ini memiliki 12 variabel dengan keterangan sebagai berikut:

| Variabel      | Keterangan                                                               |
| ------------- | ------------------------------------------------------------------------ |
| show\_id      | ID unik dari setiap tayangan                                             |
| type          | Jenis tayangan: "Movie" atau "TV Show"                                   |
| title         | Judul tayangan                                                           |
| director      | Nama sutradara                                                           |
| cast          | Daftar pemeran dalam tayangan                                            |
| country       | Negara asal produksi tayangan                                            |
| date\_added   | Tanggal tayangan ditambahkan ke Netflix                                  |
| release\_year | Tahun rilis tayangan                                                     |
| rating        | Kategori rating usia penonton (seperti PG-13, TV-MA, dll.)               |
| duration      | Durasi tayangan: dalam menit untuk film, atau jumlah musim untuk TV Show |
| listed\_in    | Genre atau kategori tayangan                                             |
| description   | Deskripsi singkat mengenai tayangan                                      |

### Struktur Data

Berikut adalah informasi tipe data dan jumlah data yang tidak kosong (non-null) pada setiap kolom:

| No | Column        | Non-Null Count | Dtype  |
| -- | ------------- | -------------- | ------ |
| 0  | show\_id      | 8807 non-null  | object |
| 1  | type          | 8807 non-null  | object |
| 2  | title         | 8807 non-null  | object |
| 3  | director      | 6173 non-null  | object |
| 4  | cast          | 7982 non-null  | object |
| 5  | country       | 7976 non-null  | object |
| 6  | date\_added   | 8797 non-null  | object |
| 7  | release\_year | 8807 non-null  | int64  |
| 8  | rating        | 8803 non-null  | object |
| 9  | duration      | 8804 non-null  | object |
| 10 | listed\_in    | 8807 non-null  | object |
| 11 | description   | 8807 non-null  | object |

### Ringkasan

Dari tabel di atas, diperoleh informasi sebagai berikut:

* Terdapat **12 fitur** dalam dataset ini.
* **6 fitur** memiliki nilai null, yaitu: `director`, `cast`, `country`, `date_added`, `rating`, dan `duration`.
* Mayoritas fitur bertipe **object** atau kategori, sedangkan hanya `release_year` yang merupakan numerik bertipe **int64**.
* Fitur `duration` memiliki format berbeda tergantung jenis tayangan:

  * Untuk *Movie*: durasi dalam menit (misal: `90 min`)
  * Untuk *TV Show*: jumlah musim (misal: `2 Seasons`)


## Exploratory Data Analysis (EDA)

### 1. Distribusi Konten: Didominasi oleh Movie
![output](https://github.com/Eva-Yuliana/Sistem-Rekomendasi/blob/main/output.png?raw=true)

Berdasarkan hasil distribusi konten, konten terbagi menjadi dua jenis utama: **Movie** dan **TV Show**.
Hasil eksplorasi menunjukkan bahwa mayoritas konten merupakan **Movie**, yang menandakan bahwa Netflix lebih banyak menyediakan film dibandingkan dengan serial televisi.

### 2. Negara dengan Jumlah Konten Terbanyak
![output1](https://github.com/Eva-Yuliana/Sistem-Rekomendasi/blob/main/output1.png?raw=true)

Analisis 'Distribusi Konten Berdasarkan Negara (Top 10)' menunjukkan bahwa negara dengan jumlah konten terbanyak di Netflix adalah:

* **United States (AS)** — negara dengan industri hiburan terbesar di dunia.
* **India** — dikenal dengan industri Bollywood yang sangat produktif.
* **United Kingdom (UK)** — memiliki reputasi tinggi dalam produksi konten internasional.

Ketiga negara ini secara konsisten mendominasi produksi konten di platform Netflix.

### 3. Tren Konten Berdasarkan Tahun Rilis
![output2](https://github.com/Eva-Yuliana/Sistem-Rekomendasi/blob/main/output2.png?raw=true)

Berdasarkan analisis 'Tren Jumlah Rilis Tiap Tahun', ditemukan bahwa:

* Jumlah kontenGenre (Listed In) Terpopuler mengalami peningkatan tajam sejak awal **tahun 2000-an**.
* Puncaknya terjadi pada tahun **2018 hingga 2019**, yang bertepatan dengan fase ekspansi global Netflix secara agresif.

Tren ini menunjukkan pertumbuhan signifikan dalam industri hiburan berbasis streaming.

### 4. Genre Paling Populer
![output3](https://github.com/Eva-Yuliana/Sistem-Rekomendasi/blob/main/output3.png?raw=true)

Analisis 'Genre (Listed In) Terpopuler' menunjukkan bahwa genre yang paling sering muncul di Netflix antara lain:

* **International Movies**
* **Dramas**
* **Comedies**

Genre-genre ini menunjukkan preferensi global dari penonton Netflix, dan dapat digunakan sebagai fitur penting dalam sistem rekomendasi berbasis konten.

### 5. Sutradara Paling Produktif
![output4](https://github.com/Eva-Yuliana/Sistem-Rekomendasi/blob/main/output4.png?raw=true)

Dari analisis 'Direktur Terpopuler', beberapa sutradara yang paling produktif dalam katalog Netflix adalah:

* **Rajiv Chilaka** — dikenal luas sebagai kreator animasi anak-anak dari India, seperti serial *Chhota Bheem*.
* **Raul Campos** dan **Jan Suter** — aktif memproduksi dokumenter dan konten non-fiksi.

Informasi ini berguna untuk sistem rekomendasi berbasis sutradara atau gaya penyutradaraan.

### 6. Distribusi Durasi Film dan Serial
![output5](https://github.com/Eva-Yuliana/Sistem-Rekomendasi/blob/main/output5.png?raw=true)

Analisis terhadap 'Distribusi Durasi' menunjukkan:

* Film umumnya berdurasi antara **80 hingga 100 menit**, yang merupakan durasi ideal bagi banyak penonton.
* Untuk TV Show, jumlah musim yang paling umum adalah **1 hingga 3 season**, mencerminkan minat terhadap serial dengan durasi yang tidak terlalu panjang.

Hal ini penting dalam menyusun rekomendasi berdasarkan preferensi durasi tayangan.

### 7. Rating Terbanyak
![output6](https://github.com/Eva-Yuliana/Sistem-Rekomendasi/blob/main/output6.png?raw=true)

Analisis 'Jumlah Konten Berdasarkan Rating' menggambarkan klasifikasi usia penonton. Tiga label rating terbanyak adalah:

* **TV-MA** (konten untuk dewasa)
* **TV-14** (konten untuk usia 14 tahun ke atas)
* **TV-PG** (bimbingan orang tua disarankan)

Sebagian besar konten ditujukan untuk penonton remaja dan dewasa, yang menjadi acuan penting dalam sistem rekomendasi yang mempertimbangkan usia pengguna.


## Data Preparation

### Data Preprocessing

#### 1. Pemeriksaan Missing Values
Langkah awal dalam preprocessing adalah memeriksa keberadaan nilai kosong (missing values) di seluruh kolom dataset. Tujuannya untuk mengidentifikasi kolom mana yang membutuhkan pembersihan atau pengisian nilai.

#### 2. Penghapusan Baris dengan Nilai Kosong pada Kolom Penting
Baris yang memiliki nilai kosong pada kolom-kolom penting seperti `title`, `type`, dan `listed_in` dihapus karena ketiga kolom ini merupakan atribut utama untuk sistem rekomendasi dan analisis lebih lanjut.

#### 3. Pengisian Nilai Kosong dengan Placeholder 'Unknown'
Untuk kolom-kolom yang kurang kritikal namun tetap penting, seperti `director`, `cast`, `country`, `date_added`, `rating`, dan `duration`, nilai kosong diisi dengan string placeholder `'Unknown'`. Hal ini menjaga konsistensi data tanpa kehilangan baris.

#### 4. Normalisasi Teks
Kolom teks seperti `title`, `listed_in`, dan `description` dinormalisasi dengan:
- Menghapus spasi berlebih di awal dan akhir teks.
- Mengubah seluruh teks menjadi huruf kecil (lowercase).
Normalisasi ini penting untuk memastikan keseragaman data teks saat dilakukan pemrosesan lebih lanjut.

#### 5. Konversi Tipe Data `release_year`
Kolom `release_year` dikonversi ke tipe numerik (integer) agar dapat digunakan untuk analisis temporal dan perhitungan statistik dengan benar.

#### 6. Filter Data Berdasarkan Tipe 'Movie'
Dataset difokuskan hanya pada tipe data `Movie` karena sistem rekomendasi yang dikembangkan hanya untuk film, sehingga baris dengan tipe lain seperti `TV Show` dihilangkan.

#### 7. Konversi Kolom `duration`
Kolom `duration` yang awalnya berupa string dengan format seperti `'90 min'` diubah menjadi angka bertipe float yang hanya berisi durasi dalam menit. Hal ini memudahkan analisis numerik terkait durasi film.

#### 8. Pembuatan Kolom Fitur Gabungan
Kolom baru dibuat dengan menggabungkan konten dari `listed_in`, `director`, dan `description`. Kolom ini akan digunakan sebagai input utama untuk model content-based filtering dalam sistem rekomendasi.

#### 9. Reset Index DataFrame
Setelah semua proses filtering dan transformasi selesai, indeks DataFrame di-reset untuk menjaga konsistensi indeks dan memudahkan pemrosesan data selanjutnya.

Tahapan ini penting untuk memastikan bahwa data bersih, konsisten, dan siap digunakan dalam pembuatan model rekomendasi yang andal dan akurat.


# Modeling

Tahapan ini membahas mengenai dua pendekatan sistem rekomendasi yang dikembangkan untuk menyelesaikan permasalahan rekomendasi film pada platform Netflix.

## Tujuan

Membangun sistem **top-N recommendation**, yaitu menyajikan daftar film yang direkomendasikan berdasarkan:

1. Kemiripan konten film (**Content-Based Filtering**)
2. Kemiripan perilaku pengguna (**Collaborative Filtering**)

## 1. Content-Based Filtering

### Pendekatan

Pendekatan **content-based filtering** menggunakan informasi konten dari film, seperti genre, sutradara, dan deskripsi. Langkah-langkah utamanya:

1. Menggabungkan fitur teks (`listed_in`, `director`, `description`) menjadi satu kolom (`combined_features`)
2. Melakukan vektorisasi teks menggunakan `TfidfVectorizer`
3. Menghitung **cosine similarity** antar film
4. Membuat fungsi rekomendasi berdasarkan film input

### Contoh Output

Pengguna memasukkan judul film: **"The Irishman"**

| No | Judul Film                                                  | Skor Kemiripan |
| -- | ----------------------------------------------------------- | -------------- |
| 1  | Rolling Thunder Revue: A Bob Dylan Story By Martin Scorsese | 0.351664       |
| 2  | Goodfellas                                                  | 0.233481       |
| 3  | Gangs Of New York                                           | 0.218461       |
| 4  | Who's That Knocking At My Door?                             | 0.212751       |
| 5  | No Direction Home: Bob Dylan                                | 0.208175       |
| 6  | Shutter Island                                              | 0.206053       |
| 7  | Hugo                                                        | 0.197920       |
| 8  | The Departed                                                | 0.197083       |
| 9  | Raging Bull                                                 | 0.190008       |
| 10 | Mean Streets                                                | 0.190139       |

### Analisis

* Film-film yang direkomendasikan memiliki **sutradara yang sama (Martin Scorsese)** dan **genre sejenis**.
* Sistem berhasil menangkap kemiripan berdasarkan **gaya penyutradaraan**, **tema cerita**, dan **genre**.
* Cocok digunakan untuk pengguna yang ingin menonton film dengan "vibe" yang mirip dari film favorit mereka.

### Kelebihan:

* **Personalized**: Rekomendasi sangat relevan dengan item yang disukai pengguna karena didasarkan pada karakteristik kontennya.
* **Tidak membutuhkan data pengguna lain**: Cocok untuk sistem dengan sedikit pengguna (cold start user).
* **Mudah dikontrol dan dipahami**: Karena kita tahu fitur apa yang digunakan (genre, deskripsi, sutradara, dll), sistem transparan dan mudah dijelaskan.

### Kekurangan:

* **Terbatas pada informasi konten**: Hanya dapat merekomendasikan item yang **mirip** dengan apa yang pernah dilihat, tidak akan menyarankan hal baru yang sangat berbeda.
* **Over-specialization**: Bisa menyebabkan rekomendasi yang terlalu sempit atau berulang.
* **Butuh data konten yang lengkap dan bersih**: Jika deskripsi atau fitur kurang informatif, hasil rekomendasi jadi tidak akurat.

## 2. Collaborative Filtering

### Pendekatan

Pendekatan **user-based collaborative filtering** menggunakan data interaksi pengguna dengan film (rating). Karena data asli tidak tersedia, digunakan data **simulasi** dengan 100 pengguna dan 100 judul film secara acak.

Langkah-langkah:

1. Menyusun matriks user-item
2. Menghitung kemiripan antar pengguna menggunakan **cosine similarity**
3. Memperkirakan rating untuk film yang belum ditonton oleh pengguna target
4. Menyajikan **top-N** rekomendasi berdasarkan skor prediksi tertinggi

### Contoh Output

Rekomendasi untuk **user\_10**:

| No | Judul Film                      | Predicted Rating |
| -- | ------------------------------- | ---------------- |
| 1  | Shirkers                        | 4.851716         |
| 2  | A Go! Go! Cory Carson Halloween | 4.737564         |
| 3  | Under The Shadow                | 4.536955         |
| 4  | De Palma                        | 4.347762         |
| 5  | Tig Notaro Happy To Be Here     | 4.145264         |

### Analisis

* Film yang direkomendasikan adalah **film yang belum ditonton oleh user\_10**, namun disukai oleh pengguna lain yang memiliki pola penilaian serupa.
* Semakin tinggi prediksi rating, semakin besar kemungkinan pengguna akan menyukai film tersebut.
* Cocok untuk situasi di mana pengguna baru tidak tahu film mana yang ingin ditonton, tapi sistem mengenali pengguna dengan pola kesukaan yang mirip.

### Kelebihan:

* **Menangkap preferensi yang lebih kompleks**: Tidak hanya berdasarkan konten, tapi juga pola perilaku pengguna lain.
* **Bisa merekomendasikan item berbeda**: Termasuk item yang secara konten tidak terlalu mirip, tapi disukai oleh pengguna dengan selera serupa.
* **Tidak butuh informasi konten**: Hanya butuh data interaksi (misalnya rating atau like).

### Kekurangan:

* **Cold Start Problem**: Tidak efektif untuk pengguna baru (tanpa data interaksi) atau item baru (belum ada rating).
* **Skalabilitas**: Jika dataset sangat besar, perhitungan kemiripan antar pengguna bisa menjadi mahal secara komputasi.
* **Sparsity**: Jika matriks user-item sangat kosong, hasil prediksi bisa kurang akurat.

## Perbandingan Pendekatan

| Aspek       | Content-Based Filtering                                                                                        | Collaborative Filtering                                                                                         |
| ----------- | -------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------- |
| Sumber Data | Metadata film                                                                                                  | Interaksi pengguna (rating)                                                                                     |
| Kelebihan   | - Tidak butuh data pengguna lain  <br> - Bisa menjelaskan kenapa film direkomendasikan                         | - Menemukan pola tersembunyi antar pengguna <br> - Dapat menyarankan film dari genre yang belum pernah ditonton |
| Kekurangan  | - Tidak bisa merekomendasikan film dari genre yang belum pernah ditonton <br> - Cenderung sempit dan repetitif | - Membutuhkan cukup banyak data rating <br> - Masalah cold-start untuk pengguna/film baru                       |
| Cocok untuk | Pengguna yang sudah tahu selera film mereka                                                                    | Platform dengan banyak data interaksi pengguna                                                                  |

## Kesimpulan

Dua model sistem rekomendasi berhasil dikembangkan:

* **Content-Based Filtering** cocok untuk memberikan rekomendasi berdasarkan kemiripan film.
* **Collaborative Filtering** memberikan rekomendasi yang lebih personal berbasis pola perilaku pengguna.

Dengan menggabungkan keduanya (hybrid), sistem rekomendasi bisa menjadi lebih kuat, adaptif, dan akurat dalam memprediksi film yang relevan untuk ditonton pengguna.


## Evaluation

### **Metrik Evaluasi yang Digunakan**

Untuk mengevaluasi performa sistem rekomendasi **user-based collaborative filtering**, digunakan metrik berikut:

1. **Mean Squared Error (MSE)**
   Formula:

   $$
   \text{MSE} = \frac{1}{n} \sum_{i=1}^{n} (y_i - \hat{y}_i)^2
   $$

   * Mengukur rata-rata kuadrat selisih antara rating sebenarnya (`yᵢ`) dan rating yang diprediksi (`ŷᵢ`).
   * Nilai lebih kecil menandakan performa prediksi yang lebih baik.

2. **Root Mean Squared Error (RMSE)**
   Formula:

   $$
   \text{RMSE} = \sqrt{\text{MSE}}
   $$

   * RMSE menyajikan satuan kesalahan dalam skala yang sama dengan rating asli, sehingga lebih mudah untuk diinterpretasikan.
   * RMSE yang lebih rendah menunjukkan akurasi prediksi yang lebih tinggi.


### **Hasil Evaluasi**

Sistem rekomendasi dievaluasi hanya pada posisi rating asli yang tersedia dalam matriks interaksi pengguna-item.

| Metrik                              | Nilai  |
| ----------------------------------- | ------ |
| **Mean Squared Error (MSE)**        | 5.7502 |
| **Root Mean Squared Error (RMSE)**  | 2.398  |
| **Jumlah Sampel Rating Dievaluasi** | 1000   |


### **Interpretasi Hasil**

Nilai RMSE sebesar **2.398** pada skala rating 1–5 menunjukkan bahwa **prediksi sistem menyimpang rata-rata ±2.4 poin dari rating asli pengguna**. Hal ini tergolong cukup besar dan menunjukkan bahwa **akurasi sistem masih dapat ditingkatkan lebih lanjut**.

Beberapa kemungkinan penyebab nilai RMSE yang tinggi:

* Data user-item sparse (jarang diisi) → menyebabkan prediksi kurang akurat.
* Similarity antar pengguna tidak cukup mencerminkan selera yang sebenarnya.
* Jumlah data interaksi dan pengguna masih terbatas.

### **Saran Peningkatan Performa Sistem**

Untuk mengurangi nilai error dan meningkatkan kualitas rekomendasi, berikut beberapa pendekatan yang dapat dipertimbangkan:

1. **Menggunakan pendekatan lain**:

   * **Item-based Collaborative Filtering**, yang biasanya lebih stabil dalam sistem dengan jumlah pengguna besar.
   * **Matrix Factorization** seperti SVD atau NMF, yang mampu menangkap pola laten dalam data.
   * **Hybrid Recommendation System**: menggabungkan Collaborative dan Content-Based Filtering untuk menyeimbangkan kelebihan dan kekurangan masing-masing metode.

2. **Peningkatan data**:

   * Menambah jumlah pengguna, item, dan interaksi dalam dataset.
   * Membersihkan dan menyeimbangkan data agar representatif.

3. **Eksperimen parameter similarity**:

   * Mencoba berbagai metrik kemiripan pengguna, seperti **cosine similarity**, **Pearson correlation**, atau **Jaccard similarity**.
   * Melakukan thresholding pada similarity agar hanya mempertimbangkan tetangga yang benar-benar mirip.



