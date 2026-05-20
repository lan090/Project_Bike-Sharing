# Proyek Analisis Data: Bike Sharing

## Deskripsi Proyek

Proyek ini merupakan analisis data mendalam terhadap dataset Bike Sharing yang mencakup data dari tahun 2011 hingga 2012. Analisis ini bertujuan untuk mengidentifikasi pola penggunaan sepeda, terutama dalam kaitannya dengan musim dan tren pertumbuhan dari waktu ke waktu.

## Pertanyaan Bisnis

Proyek ini dirancang untuk menjawab dua pertanyaan bisnis utama:

1. **Pengaruh Musim terhadap Preferensi Pengguna**: Bagaimana pengaruh musim terhadap preferensi pengguna terdaftar (registered) atau pengguna biasa (casual) dalam memilih untuk menyewa sepeda?

2. **Tren Pertumbuhan**: Apakah terdapat tren pertumbuhan atau penurunan dalam jumlah total sepeda yang disewakan dari tahun 2011 ke tahun 2012?

## Dataset

Dataset yang digunakan berisi informasi tentang:
- **Tanggal** (dteday): Tanggal peminjaman sepeda
- **Musim** (season): 1=Spring, 2=Summer, 3=Fall, 4=Winter
- **Tahun** (yr): 0=2011, 1=2012
- **Bulan** (mnth): 1-12
- **Hari dalam minggu** (weekday): 0-6
- **Kondisi cuaca** (weathersit): 1-3
- **Suhu** (temp, atemp): Suhu aktual dan suhu yang terasa
- **Kelembaban** (hum): Tingkat kelembaban
- **Kecepatan angin** (windspeed): Kecepatan angin
- **Pengguna casual** (casual): Jumlah pengguna biasa
- **Pengguna terdaftar** (registered): Jumlah pengguna terdaftar
- **Total peminjaman** (cnt): Total peminjaman sepeda

**Jumlah Data**: 731 baris (satu entri per hari)
**Periode**: 1 Januari 2011 - 31 Desember 2012

## Struktur Proyek

### 1. Data Wrangling
- **Gathering Data**: Membaca file CSV dan memuat data ke dalam DataFrame pandas
- **Assessing Data**: Memeriksa tipe data, duplikasi, dan statistik dasar
- **Cleaning Data**: Mengkonversi kolom `dteday` dari tipe object menjadi datetime

### 2. Exploratory Data Analysis (EDA)
- Analisis deskriptif data
- Pengelompokan data berdasarkan musim
- Perhitungan rata-rata peminjaman untuk pengguna casual dan registered
- Analisis tren pertumbuhan dari tahun ke tahun

### 3. Visualisasi dan Interpretasi
- Visualisasi pola peminjaman berdasarkan musim
- Visualisasi tren pertumbuhan antar tahun
- Presentasi hasil temuan

## Library yang Digunakan

```python
import numpy as np          # Komputasi numerik
import pandas as pd         # Manipulasi dan analisis data
import matplotlib.pyplot as plt  # Visualisasi dasar
import seaborn as sns       # Visualisasi statistik lanjutan
import streamlit as st      # Pembuatan dashboard interaktif
```

## Temuan Utama

### Insight Pertanyaan 1: Pengaruh Musim terhadap Peminjaman
- Pengguna casual dan registered menunjukkan pola yang berbeda berdasarkan musim
- Analisis rata-rata peminjaman per musim dilakukan untuk mengidentifikasi musim dengan peminjaman tertinggi dan terendah

### Insight Pertanyaan 2: Tren Pertumbuhan 2011-2012
- Perbandingan total peminjaman antara tahun 2011 dan 2012 menunjukkan tren pertumbuhan atau penurunan
- Data menunjukkan peningkatan signifikan dalam jumlah pengguna terdaftar

## Cara Menjalankan

### Prasyarat
```bash
pip install numpy pandas matplotlib seaborn streamlit
```

### Menjalankan Notebook
```bash
jupyter notebook notebook.ipynb
```

### Menjalankan Dashboard Streamlit (jika tersedia)
```bash
streamlit run dashboard.py
```

## Hasil Analisis

| Metrik | Nilai |
|--------|-------|
| Total Data | 731 hari |
| Rata-rata Peminjaman Harian | 4,504 sepeda |
| Pengguna Casual (rata-rata) | 848 per hari |
| Pengguna Registered (rata-rata) | 3,656 per hari |
| Peminjaman Minimum | 22 sepeda |
| Peminjaman Maksimum | 8,714 sepeda |

## Struktur File

```
Project_Bike-Sharing/
├── README.md              # File dokumentasi ini
├── notebook.ipynb         # Notebook Jupyter dengan analisis lengkap
├── data/
│   └── day.csv           # Dataset utama
└── [dashboard.py]        # Dashboard Streamlit (opsional)
```

## Kesimpulan

Analisis data Bike Sharing ini memberikan insights berharga tentang:
- Pola penggunaan sepeda berdasarkan musim
- Perbedaan perilaku antara pengguna casual dan registered
- Tren pertumbuhan dalam penggunaan layanan bike sharing

Temuan ini dapat membantu dalam pengambilan keputusan strategis untuk optimasi layanan bike sharing, seperti penyesuaian kapasitas, perencanaan maintenance, dan strategi marketing musiman.

## Kontak & Kolaborasi

Untuk pertanyaan atau kontribusi, silakan hubungi atau buat issue di repository ini.

---

**Dibuat oleh**: lan090  
**Tanggal Pembuatan**: 2026-05-20  
**Status**: Analisis Lengkap
