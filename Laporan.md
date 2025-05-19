# Laporan Akhir Machine Learning :  Netflix Movie Recommendation System Based on Content-Based and Collaborative Filtering - Eva Yuliana
## Proyek Overview
![dataset-cover](https://github.com/Eva-Yuliana/Sistem-Rekomendasi/blob/main/dataset-cover.jpg?raw=true)

Seiring berkembangnya layanan streaming seperti Netflix, pengguna dihadapkan pada ribuan pilihan film dan serial. Banyaknya pilihan ini dapat membuat pengguna kesulitan menemukan tontonan yang sesuai dengan selera mereka. Oleh karena itu, sistem rekomendasi menjadi solusi penting untuk menyajikan film yang relevan dan menarik bagi pengguna. Dalam proyek ini, akan dikembangkan sistem rekomendasi film menggunakan dua pendekatan utama: Content-Based Filtering, yang merekomendasikan film berdasarkan kemiripan konten seperti genre atau sutradara; dan Collaborative Filtering, yang menyarankan film berdasarkan preferensi pengguna lain yang memiliki selera serupa. Tujuan dari proyek ini adalah memberikan rekomendasi film yang lebih akurat dan personal, sekaligus meningkatkan kepuasan pengguna serta efisiensi eksplorasi konten di platform streaming.



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