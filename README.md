# Analisis Berita Banjir Indonesia — Kelompok 6

Repository ini berisi seluruh kode dan data untuk Project A mata kuliah Pengolahan Bahasa Alami (PBA) semester genap 2025/2026. Proyek ini berfokus pada analisis teks berita banjir di Indonesia, dengan membandingkan karakteristik pemberitaan banjir biasa dan banjir bandang menggunakan berbagai teknik NLP.

## Anggota Kelompok

| Nama | NRP | Pembagian
|---|---|
| Maria Adeline Maharani W. | 5026231048 | Data Cleaning , Preprocessing 
| Hafizhan Yusra Sulistyo | 5026231060 | Sentimen Analysis dan Frequency top 100 words
| Zeldano Shan Oeffie | 5026231118 | Data Preparation 
| Khalila Shafarayhani Atletiko | 5026231167 | TF-IDF dan Vector 
| Astrid Meilendra | 5026231183 | Tokenization dan Lemmatization
| Alisha Rafimalia | 5026231202 | POS Tag, N-grams 

## Deskripsi Proyek

Banjir merupakan salah satu bencana alam yang paling sering terjadi di Indonesia. Proyek ini menganalisis berita banjir dari berbagai portal berita nasional (Kompas, Detik, Tribun, Antara, CNN Indonesia) untuk memahami pola bahasa yang digunakan dalam pemberitaan banjir biasa dibandingkan banjir bandang.

Data dikumpulkan melalui web scraping dari ratusan artikel berita, kemudian diproses menggunakan pipeline NLP mulai dari preprocessing, POS tagging, NER, N-gram, TF-IDF, hingga klasifikasi sentimen.

## Struktur Repository

```
ProjectA_Kelompok6_BanjirArticles_PBA/
│
├── data/
│   ├── data_berita_banjir_scraped.csv
│   └── data_banjir_clean.csv
│
├── notebooks/
│   ├── 01_scraping_berita_banjir_final.ipynb
│   ├── 02_data_cleaning_banjir.ipynb
│   ├── 03_preprocessing.ipynb
│   ├── 04_analysis.ipynb
│   ├── 05_tfidf.ipynb
│   └── 06_sentiment_classification.ipynb
│
├── outputs/
│
├── paper/
│   └── Kelompok6_Paper_PBA.pdf
│
└── README.md
```

## Penjelasan Notebook

**01_scraping.ipynb**
Pengumpulan data berita banjir dari berbagai portal berita menggunakan newspaper3k dan BeautifulSoup. Input berupa daftar URL yang dikumpulkan secara manual, output berupa `data_berita_banjir_scraped.csv` yang berisi 2.454 artikel.

**02_cleaning.ipynb**
Pembersihan data hasil scraping, meliputi penghapusan artikel tanpa konten dan validasi relevansi menggunakan keyword banjir. Output berupa `data_banjir_clean.csv` yang siap digunakan untuk tahap selanjutnya.

**03_preprocessing.ipynb**
Preprocessing teks mencakup case folding, tokenisasi, stopword removal, dan lemmatization menggunakan PySastrawi.

**04_analysis.ipynb**
Analisis linguistik meliputi POS tagging, Named Entity Recognition (NER), dan N-gram untuk mengidentifikasi pola bahasa dalam berita banjir.

**05_tfidf.ipynb**
Representasi teks menggunakan TF-IDF dan pembuatan vektor fitur untuk keperluan klasifikasi.

**06_sentiment_classification.ipynb**
Klasifikasi berita ke dalam kategori banjir biasa atau banjir bandang menggunakan keyword-based classification dan TF-IDF dengan Naive Bayes, beserta perbandingan hasil keduanya.

## Dataset

Data berita dikumpulkan dari portal berita nasional dengan kata kunci pencarian banjir. Total 2.454 artikel berhasil dikumpulkan, dengan 1.654 artikel yang memiliki konten lengkap setelah proses scraping. Label kategori (banjir biasa atau banjir bandang) ditentukan secara manual berdasarkan isi dan judul artikel.

## Cara Menjalankan

Semua notebook dirancang untuk dijalankan di Google Colab. Jalankan notebook secara berurutan mulai dari 01 hingga 06 karena setiap notebook bergantung pada output notebook sebelumnya. Pastikan file CSV yang dibutuhkan sudah diupload ke sesi Colab sebelum menjalankan setiap notebook.

## Tools dan Library

Python 3, pandas, newspaper3k, BeautifulSoup, NLTK, PySastrawi, scikit-learn, matplotlib
