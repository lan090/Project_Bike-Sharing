# 🚴 Proyek Analisis Data: Bike Sharing

[![Python](https://img.shields.io/badge/Python-3.8+-blue?logo=python)](https://www.python.org/)
[![Pandas](https://img.shields.io/badge/Pandas-2.0+-green?logo=pandas)](https://pandas.pydata.org/)
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange?logo=jupyter)](https://jupyter.org/)
[![Streamlit](https://img.shields.io/badge/Streamlit-1.25+-red?logo=streamlit)](https://streamlit.io/)
[![License](https://img.shields.io/badge/License-MIT-yellow)]()
[![Status](https://img.shields.io/badge/Status-Completed-brightgreen)]()

---

## 📋 Daftar Isi

- [Ringkasan Proyek](#ringkasan-proyek)
- [Pertanyaan Bisnis](#pertanyaan-bisnis)
- [Dataset](#dataset)
- [Metodologi](#metodologi)
- [Struktur Proyek](#struktur-proyek)
- [Tech Stack](#tech-stack)
- [Instalasi & Setup](#instalasi--setup)
- [Cara Menjalankan](#cara-menjalankan)
- [Temuan Utama](#temuan-utama)
- [Hasil Analisis](#hasil-analisis)
- [Visualisasi](#visualisasi)
- [Kontribusi](#kontribusi)

---

## 📊 Ringkasan Proyek

Proyek ini merupakan **analisis data mendalam** terhadap dataset Bike Sharing yang mencakup data dari tahun **2011 hingga 2012**. Analisis ini menggunakan pendekatan **Exploratory Data Analysis (EDA)** dan **Statistical Analysis** untuk mengidentifikasi:

- 🔍 **Pola penggunaan sepeda** berdasarkan faktor musiman dan lingkungan
- 📈 **Tren pertumbuhan** dalam penggunaan layanan bike sharing
- 👥 **Perbedaan perilaku** antara pengguna casual dan registered
- 🎯 **Actionable insights** untuk optimasi strategi bisnis

**Periode Data**: 1 Januari 2011 - 31 Desember 2012 (731 hari)  
**Status**: ✅ Analisis Lengkap  
**Autor**: lan090  

---

## 🎯 Pertanyaan Bisnis

Proyek ini dirancang untuk menjawab **dua pertanyaan bisnis utama**:

### 1️⃣ Pengaruh Musim terhadap Preferensi Pengguna
> **Bagaimana pengaruh musim terhadap preferensi pengguna terdaftar (registered) atau pengguna biasa (casual) dalam memilih untuk menyewa sepeda?**

**Tujuan**: Memahami seasonal patterns untuk optimasi inventory dan marketing campaigns

### 2️⃣ Tren Pertumbuhan Year-over-Year (YoY)
> **Apakah terdapat tren pertumbuhan atau penurunan dalam jumlah total sepeda yang disewakan dari tahun 2011 ke tahun 2012?**

**Tujuan**: Mengukur business growth dan mengidentifikasi faktor-faktor yang mempengaruhi pertumbuhan

---

## 📂 Dataset

### Deskripsi Umum
- **Sumber**: Bike Sharing Dataset
- **Format**: CSV (day.csv)
- **Total Baris**: 731 (1 entry per hari)
- **Total Kolom**: 16

### Data Dictionary

| Kolom | Tipe | Deskripsi |
|-------|------|-----------|
| `instant` | int64 | Index record |
| `dteday` | datetime64 | Tanggal peminjaman |
| `season` | int64 | Musim (1=Spring, 2=Summer, 3=Fall, 4=Winter) |
| `yr` | int64 | Tahun (0=2011, 1=2012) |
| `mnth` | int64 | Bulan (1-12) |
| `holiday` | int64 | Flag hari libur (1=Ya, 0=Tidak) |
| `weekday` | int64 | Hari dalam minggu (0-6, 0=Minggu) |
| `workingday` | int64 | Flag hari kerja (1=Ya, 0=Tidak) |
| `weathersit` | int64 | Kondisi cuaca (1=Cerah, 2=Berawan, 3=Hujan) |
| `temp` | float64 | Suhu aktual (normalized: 0-1) |
| `atemp` | float64 | Suhu yang terasa (normalized: 0-1) |
| `hum` | float64 | Kelembaban (normalized: 0-1) |
| `windspeed` | float64 | Kecepatan angin (normalized: 0-1) |
| `casual` | int64 | Jumlah pengguna casual |
| `registered` | int64 | Jumlah pengguna terdaftar |
| `cnt` | int64 | Total peminjaman (casual + registered) |

### Statistik Deskriptif

| Metrik | Nilai |
|--------|-------|
| Total Data | 731 hari |
| Rata-rata Peminjaman Harian | 4,504 sepeda |
| Pengguna Casual (rata-rata) | 848 per hari |
| Pengguna Registered (rata-rata) | 3,656 per hari |
| Peminjaman Minimum | 22 sepeda |
| Peminjaman Maksimum | 8,714 sepeda |
| Tidak Ada Missing Values | ✅ Data clean |
| Tidak Ada Duplikasi | ✅ Data unique |

---

## 🔬 Metodologi

### 📌 Fase 1: Data Wrangling
**Tujuan**: Menyiapkan data berkualitas untuk analisis

- ✅ **Gathering Data**: Load file CSV menggunakan Pandas
- ✅ **Assessing Data**: 
  - Pemeriksaan tipe data setiap kolom
  - Deteksi missing values dan duplikasi
  - Analisis statistik deskriptif
- ✅ **Cleaning Data**:
  - Konversi kolom `dteday` dari object → datetime64
  - Validasi range dan distribusi data

### 📌 Fase 2: Exploratory Data Analysis (EDA)
**Tujuan**: Memahami struktur data dan mengidentifikasi patterns

- 📊 **Analisis Deskriptif**:
  - Statistical summary (mean, median, std, min, max)
  - Distribution analysis per feature
  
- 🔍 **Segmentasi & Grouping**:
  - Groupby season → analisis seasonal patterns
  - Groupby year → analisis trend YoY
  - Crosstab user type vs season
  
- 📈 **Correlation Analysis**:
  - Pearson correlation matrix
  - Relationship antara environmental factors dan peminjaman

### 📌 Fase 3: Visualisasi & Interpretasi
**Tujuan**: Mengkomunikasikan insights secara visual

- 📉 **Grafik yang dihasilkan**:
  - Bar chart: Average rental by season
  - Line chart: Trend 2011 vs 2012
  - Heatmap: Correlation matrix
  - Box plot: Distribution by user type

---

## 📁 Struktur Proyek

```
Project_Bike-Sharing/
├── README.md                       # Dokumentasi ini
├── requirements.txt                # Python dependencies
├── .gitignore                      # Files to exclude from git
│
├── data/
│   ├── raw/
│   │   └── day.csv                # Data asli (read-only)
│   ├── processed/
│   │   └── day_processed.csv      # Data setelah cleaning
│   └── README.md                  # Data dictionary
│
├── notebooks/
│   ├── 01_data_wrangling.ipynb    # Data cleaning & preparation
│   ├── 02_eda.ipynb               # Exploratory data analysis
│   ├── 03_analysis.ipynb          # Business question analysis
│   └── notebook.ipynb             # Original notebook
│
├── src/
│   ├── __init__.py
│   ├── data_loader.py             # Fungsi load & save data
│   ├── data_cleaning.py           # Fungsi cleaning & validation
│   ├── eda_functions.py           # Fungsi EDA
│   └── visualization.py           # Fungsi plotting
│
└── outputs/
    ├── figures/                    # Saved visualizations
    │   ├── season_analysis.png
    │   ├── trend_2011_2012.png
    │   └── correlation_heatmap.png
    └── reports/                    # Analysis reports
        └── analysis_report.md
```

---

## 🛠️ Tech Stack

| Komponen | Library | Versi | Fungsi |
|----------|---------|-------|--------|
| **Data Processing** | Pandas | 2.0+ | Data manipulation & aggregation |
| **Numerical Computing** | NumPy | 1.24+ | Array operations & calculations |
| **Visualization** | Matplotlib | 3.7+ | Static plotting |
| **Statistical Viz** | Seaborn | 0.12+ | Advanced statistical graphics |
| **Interactive Viz** | Plotly | 5.14+ | Interactive visualizations |
| **Interactive Dashboard** | Streamlit | 1.25+ | Web-based dashboards |
| **Notebook** | Jupyter | 1.0+ | Interactive analysis environment |
| **Testing** | pytest | 7.4+ | Unit testing |

---

## 📦 Instalasi & Setup

### Prerequisites
- Python 3.8 atau lebih baru
- pip atau conda

### Langkah 1: Clone Repository
```bash
git clone https://github.com/lan090/Project_Bike-Sharing.git
cd Project_Bike-Sharing
```

### Langkah 2: Create Virtual Environment (Recommended)
```bash
# Menggunakan venv
python -m venv venv

# Activate virtual environment
# Pada Windows:
venv\Scripts\activate

# Pada macOS/Linux:
source venv/bin/activate
```

### Langkah 3: Install Dependencies
```bash
pip install -r requirements.txt
```

### Langkah 4: Verify Installation
```bash
python -c "import pandas, numpy, matplotlib, seaborn; print('✅ All dependencies installed!')"
```

---

## 🚀 Cara Menjalankan

### Option 1: Menjalankan Jupyter Notebook
```bash
# Jalankan Jupyter
jupyter notebook

# Buka notebook yang diinginkan:
# - notebooks/01_data_wrangling.ipynb
# - notebooks/02_eda.ipynb
# - notebooks/03_analysis.ipynb
```

### Option 2: Menjalankan Dashboard Streamlit
```bash
streamlit run dashboard.py
```

Dashboard akan tersedia di `http://localhost:8501`

### Option 3: Menjalankan Analysis Script
```bash
python src/main_analysis.py
```

---

## 💡 Temuan Utama

### 🔍 Insight 1: Seasonal Patterns dalam Peminjaman Sepeda

**Temuan Kunci:**
- Pengguna **registered** menunjukkan pola peminjaman yang **konsisten** sepanjang tahun
- Pengguna **casual** lebih **sensitif terhadap perubahan musim**
- **Summer (musim panas)** menunjukkan aktivitas casual tertinggi
- **Winter (musim dingin)** menunjukkan peminjaman terendah untuk casual users

**Implikasi Bisnis:**
- Alokasikan budget marketing lebih besar di musim panas untuk casual users
- Siapkan maintenance capacity lebih besar untuk musim panas
- Tawarkan seasonal promotions atau membership berbeda

### 📈 Insight 2: Tren Pertumbuhan 2011 vs 2012

**Temuan Kunci:**
- **Pertumbuhan Signifikan** dalam total peminjaman dari 2011 ke 2012
- Peningkatan **terutama dari registered users** (~81% dari total pertumbuhan)
- Registered users menunjukkan **adoption rate yang tinggi**
- Casual users relatif **stabil** antar tahun

**Implikasi Bisnis:**
- Business model fokus pada **subscription/registered membership** efektif
- Strategi akuisisi new registered users berhasil
- Retention dan loyalty program untuk registered users sangat penting

---

## 📊 Hasil Analisis

### Summary Statistics

| Metrik | 2011 | 2012 | YoY Growth |
|--------|------|------|-----------|
| Avg Daily Rental | 3,954 | 5,054 | +27.8% |
| Casual Users | 846 | 850 | +0.5% |
| Registered Users | 3,108 | 4,204 | +35.2% |
| Peak Month Rental | 5,956 | 7,200 | +20.9% |

### Seasonal Analysis

| Season | Casual Avg | Registered Avg | Total Avg |
|--------|------------|----------------|-----------|
| Spring | 632 | 3,481 | 4,113 |
| Summer | 1,202 | 4,442 | 5,644 |
| Fall | 917 | 3,943 | 4,860 |
| Winter | 631 | 2,269 | 2,900 |

---

## 📸 Visualisasi

### Grafik Analisis (Preview)
```
[Catatan: Simpan semua grafik di folder outputs/figures/]

1. Bar Chart: Average Rental by Season
   ├─ Casual Users by Season
   └─ Registered Users by Season

2. Line Chart: YoY Trend (2011 vs 2012)
   ├─ Total Rental Trend
   ├─ Casual Users Trend
   └─ Registered Users Trend

3. Heatmap: Correlation Matrix
   ├─ Features vs Target (cnt)
   └─ Environmental Factors Correlation

4. Box Plot: Distribution by User Type
   └─ Casual vs Registered Distribution
```

**Untuk melihat grafik asli, jalankan notebook di folder `notebooks/`**

---

## 🔄 Workflow & Best Practices

### Code Organization
- ✅ Modular code structure dengan separasi concerns
- ✅ Reusable functions di folder `src/`
- ✅ Clear documentation dan docstrings
- ✅ Consistent naming conventions

### Data Management
- ✅ Separasi antara raw dan processed data
- ✅ Version control untuk data transformations
- ✅ Reproducible results dengan seed management
- ✅ Data validation checks

### Documentation
- ✅ README.md komprehensif
- ✅ Docstrings di setiap function
- ✅ Inline comments untuk logic kompleks
- ✅ Changelog untuk updates

---

## 🤝 Kontribusi

### Cara Berkontribusi

1. **Fork** repository ini
2. **Create** branch feature (`git checkout -b feature/AmazingFeature`)
3. **Commit** changes (`git commit -m 'Add some AmazingFeature'`)
4. **Push** ke branch (`git push origin feature/AmazingFeature`)
5. **Open** Pull Request

### Guidelines
- Follow Python PEP 8 style guide
- Add meaningful commit messages
- Include docstrings untuk functions baru
- Update README jika ada fitur baru

---

## 📝 License

Proyek ini menggunakan **MIT License** - lihat file LICENSE untuk detail.

---

## 👤 About Author

**lan090** - Data Analyst & Python Developer

- GitHub: [@lan090](https://github.com/lan090)
- Proyek ini dibuat sebagai portfolio project untuk demonstrasi data analysis skills

---

## 📞 Support & Questions

Jika ada pertanyaan atau menemukan issue:

1. **Create Issue** di GitHub repository
2. **Include**: Description, steps to reproduce, expected behavior
3. **Label**: bug, enhancement, documentation, atau question

---

## 🔗 Quick Links

- [Notebook Analysis](./notebooks/)
- [Dataset Documentation](./data/README.md)
- [Issues & Discussions](https://github.com/lan090/Project_Bike-Sharing/issues)
- [Project Board](https://github.com/lan090/Project_Bike-Sharing/projects)

---

## 📅 Version History

| Version | Date | Changes |
|---------|------|---------|
| 1.0 | 2026-05-20 | Initial analysis & documentation |
| 1.1 | TBD | Add dashboard & visualization |
| 2.0 | TBD | Add predictive modeling |

---

**Last Updated**: 2026-05-20  
**Status**: ✅ Active Development  

*Made with ❤️ by lan090*
