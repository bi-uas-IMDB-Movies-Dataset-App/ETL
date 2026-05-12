![Banner](https://capsule-render.vercel.app/api?type=waving&height=260&color=0:0f172a,50:1a3a2a,100:20BEFF&text=DataWarehouse&fontColor=ffffff&fontSize=52&fontAlignY=38&desc=Python%20%C2%B7%20SQLite%20%C2%B7%20Star%20Schema%20%C2%B7%20BI%20Pipeline&descAlignY=58&animation=fadeIn)

[![Python](https://img.shields.io/badge/Python-3.x-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://python.org/)
[![SQLite](https://img.shields.io/badge/SQLite-Data%20Warehouse-003B57?style=for-the-badge&logo=sqlite&logoColor=white)](https://sqlite.org/)
[![Pandas](https://img.shields.io/badge/Pandas-ETL-150458?style=for-the-badge&logo=pandas&logoColor=white)](https://pandas.pydata.org/)
[![Kaggle](https://img.shields.io/badge/Dataset-Kaggle%20IMDB-20BEFF?style=for-the-badge&logo=kaggle&logoColor=white)](https://www.kaggle.com/datasets/harshitshankhdhar/imdb-dataset-of-top-1000-movies-and-tv-shows)
[![Status](https://img.shields.io/badge/Status-Completed-00C851?style=for-the-badge)](https://github.com/mocharezky04/bi-uts-IMDB-Movies-Dataset)

---

### 🌐 Sumber Daya Proyek

| Sumber Daya | Tautan |
|---|---|
| 🗃️ **Dataset Kotor (Kaggle)** | [IMDB Top 1000 Movies & TV Shows](https://www.kaggle.com/datasets/harshitshankhdhar/imdb-dataset-of-top-1000-movies-and-tv-shows) |
| 💻 **Repository GitHub** | [bi-uts-IMDB-Movies-Dataset](https://github.com/mocharezky04/bi-uts-IMDB-Movies-Dataset.git) |
| 📓 **Notebook ETL (Google Colab)** | [Lihat Notebook ETL](ETL/IMDB_DataWarehouse_Colab.ipynb) |
| 📄 **Laporan Proyek (PDF)** | ntar diisi |
| 🖼️ **Poster Proyek** | [Poster Cinemascope](https://drive.google.com/file/d/1MXwWzetHHXq4dvNC6g_n4X1qS7LUFF7O/view?usp=sharing) |

---

## 📑 Daftar Isi

- [🎯 Ringkasan Proyek](#-ringkasan-proyek)
- [✨ Fitur & Insight](#-fitur--insight)
- [🛠️ Stack Teknologi](#️-stack-teknologi)
- [🗂️ Struktur Repository](#️-struktur-repository)
- [🏗️ Arsitektur Data Warehouse](#️-arsitektur-data-warehouse)
- [🔀 Alur ETL & Pipeline BI](#-alur-etl--pipeline-bi)
- [📊 Dataset](#-dataset)
- [🚀 Quick Start](#-quick-start)
- [📈 Sample Insights](#-sample-insights)
- [📦 Output & Deliverables](#-output--deliverables)
- [📄 Dokumentasi](#-dokumentasi)
- [👥 Anggota Tim — Invincible 🔥](#-anggota-tim--invincible-)

---

## 🎯 Ringkasan Proyek

**DataWarehouse IMDB** adalah proyek implementasi **Business Intelligence** berbasis dataset **IMDB Top 1000 Movies & TV Shows** dari Kaggle. Proyek ini membangun *Data Warehouse* menggunakan pendekatan **Star Schema**, mencakup seluruh pipeline BI secara end-to-end — dari pengumpulan data mentah, pembersihan, transformasi, hingga analisis dan visualisasi insight.

Proyek ini terbagi dalam dua lapisan utama:

- **Pipeline ETL** — Proses Extract, Transform, Load dari CSV mentah ke dalam SQLite Data Warehouse yang terstruktur dengan model dimensional Star Schema.
- **Lapisan Analitik** — Query dan visualisasi berbasis data warehouse yang menghasilkan insight actionable terkait tren, distribusi, dan korelasi data film.

> **Konteks UTS Business Intelligence:** Proyek ini menerapkan siklus BI secara penuh — mengumpulkan data IMDB Top 1000 dari Kaggle, membersihkan dan mentransformasinya dengan Python + Pandas, menyimpannya dalam SQLite dengan Star Schema, lalu mengekstrak insight melalui analisis dan visualisasi.

**Fokus pengembangan:**

- **Pipeline ETL end-to-end** — Dari CSV mentah Kaggle hingga Data Warehouse siap analisis.
- **Star Schema modeling** — Desain dimensional dengan 1 Fact Table dan 5 Dimension Tables.
- **Feature engineering** — Kolom turunan seperti `Decade`, `Era`, `Primary_Genre`, `Rating_Category`.
- **Visualisasi analitik** — Chart distribusi, tren dekade, korelasi metrik, dan top performers.

---

## ✨ Fitur & Insight

### ⚙️ Pipeline ETL

**1️⃣ Extract**
- Membaca data mentah dari `Dataset/imdb_top_1000.csv` (1000 records).
- Memvalidasi struktur kolom dan tipe data awal.

**2️⃣ Transform**
- Normalisasi kolom numerik: `Runtime`, `Gross`, `Released_Year`.
- Penanganan missing values pada `Certificate`, `Meta_score`, dan `Gross`.
- Feature engineering:
  - `Decade` — Pengelompokan film berdasarkan dekade rilis.
  - `Era` — Klasifikasi era sinema (Classic, Modern, Contemporary).
  - `Primary_Genre` — Genre utama dari multi-value genre string.
  - `Rating_Category` — Kategori rating (Must Watch, Recommended, Average).

**3️⃣ Load**
- Membangun skema Star Schema di SQLite.
- Mengisi tabel dimensi dan fakta dari data yang telah dibersihkan.
- Output: `DataWarehouse/imdb_datawarehouse.db`

---

### 📊 Lapisan Analitik

**📈 Visualisasi yang Dihasilkan**

| Visualisasi | File Output | Insight |
|---|---|---|
| Distribusi Rating Film | `plot_rating_distribution.png` | Sebaran IMDb rating seluruh film |
| Genre Paling Populer | `plot_genre_count.png` | Frekuensi tiap genre dalam top 1000 |
| Top Directors | `plot_top_directors.png` | Direktur dengan film terbanyak & rating tertinggi |
| Tren Film per Dekade | `plot_trend_decade.png` | Perkembangan produksi film per dekade |
| Top Gross Revenue | `plot_top_gross.png` | Film dengan pendapatan box office tertinggi |
| Korelasi Metrik | `plot_correlation.png` | Hubungan rating, votes, meta_score, gross |
| Distribusi Certificate | `plot_certificate.png` | Sebaran klasifikasi usia film |
| Top Popular Films | `plot_top_popular.png` | Film paling populer berdasarkan jumlah votes |

---

## 🛠️ Stack Teknologi

| Kategori | Teknologi |
|---|---|
| **Bahasa Pemrograman** | Python 3.x |
| **Data Processing** | Pandas, NumPy |
| **Database / DW** | SQLite |
| **Visualisasi** | Matplotlib, Seaborn, Plotly |
| **Modeling** | Star Schema (Dimensional Modeling) |
| **Environment** | Jupyter Notebook / Google Colab |
| **Sumber Dataset** | [Kaggle – IMDB Top 1000](https://www.kaggle.com/datasets/harshitshankhdhar/imdb-dataset-of-top-1000-movies-and-tv-shows) |

---

## 🗂️ Struktur Repository

<details>
<summary><strong>📂 Klik untuk memperluas struktur folder lengkap</strong></summary>

```
BI/
│
├── Dataset/
│   └── imdb_top_1000.csv               -> Dataset mentah dari Kaggle (1000 records)
│
├── ETL/
│   ├── IMDB_DataWarehouse_Colab.ipynb  -> Notebook ETL interaktif (Google Colab)
│   └── imdb_datawarehouse_colab.py     -> Script Python ETL (standalone)
│
├── DataWarehouse/
│   ├── imdb_datawarehouse.db           -> SQLite Data Warehouse (output ETL)
│   ├── plot_rating_distribution.png    -> Visualisasi distribusi rating
│   ├── plot_genre_count.png            -> Visualisasi genre populer
│   ├── plot_top_directors.png          -> Visualisasi top directors
│   ├── plot_trend_decade.png           -> Visualisasi tren per dekade
│   ├── plot_top_gross.png              -> Visualisasi top gross revenue
│   ├── plot_correlation.png            -> Visualisasi korelasi metrik
│   ├── plot_certificate.png            -> Visualisasi distribusi certificate
│   └── plot_top_popular.png            -> Visualisasi film terpopuler
│
├── Laporan/
│   ├── Laporan_DataWarehouse_Kelompok_5_Business_Intelligence_Top 1000_IMDB.docx
│   └── Laporan.rar
│
├── Tugas/
│   └── tugas_bi.jpeg
│
└── README.md
```

</details>

---

## 🏗️ Arsitektur Data Warehouse

### ⭐ Star Schema Design

Model dimensional yang digunakan adalah **Star Schema** dengan struktur berikut:

```
                        ┌─────────────────┐
                        │   dim_director  │
                        │─────────────────│
                        │ director_id PK  │
                        │ director_name   │
                        └────────┬────────┘
                                 │
┌───────────────┐       ┌────────┴────────────────┐       ┌─────────────────┐
│   dim_genre   │       │  fact_movie_performance  │       │    dim_time     │
│───────────────│       │─────────────────────────│       │─────────────────│
│ genre_id  PK  ├──────►│ movie_id         FK      │◄──────│ time_id     PK  │
│ genre_name    │       │ director_id      FK      │       │ released_year   │
└───────────────┘       │ genre_id         FK      │       │ decade          │
                        │ time_id          FK      │       │ era             │
┌───────────────┐       │ certificate_id   FK      │       └─────────────────┘
│  dim_movie    │       │─────────────────────────│
│───────────────│       │ imdb_rating  (measure)  │       ┌─────────────────┐
│ movie_id  PK  ├──────►│ meta_score   (measure)  │       │ dim_certificate │
│ title         │       │ no_of_votes  (measure)  │◄──────│─────────────────│
│ overview      │       │ gross        (measure)  │       │ cert_id     PK  │
│ runtime       │       └─────────────────────────┘       │ certificate     │
│ rating_cat.   │                                         └─────────────────┘
└───────────────┘
```

### Tabel Fakta

**`fact_movie_performance`** — Menyimpan seluruh measure numerik film.

| Kolom | Tipe | Keterangan |
|---|---|---|
| `movie_id` | FK | Referensi ke `dim_movie` |
| `director_id` | FK | Referensi ke `dim_director` |
| `genre_id` | FK | Referensi ke `dim_genre` |
| `time_id` | FK | Referensi ke `dim_time` |
| `certificate_id` | FK | Referensi ke `dim_certificate` |
| `imdb_rating` | REAL | Rating IMDb (0–10) |
| `meta_score` | INTEGER | Skor Metacritic |
| `no_of_votes` | INTEGER | Jumlah vote pengguna |
| `gross` | REAL | Pendapatan box office (USD) |

### Tabel Dimensi

| Tabel | Atribut Utama | Keterangan |
|---|---|---|
| `dim_movie` | title, overview, runtime, rating_category | Informasi utama film |
| `dim_director` | director_name | Data sutradara |
| `dim_genre` | genre_name | Genre utama (primary genre) |
| `dim_time` | released_year, decade, era | Dimensi waktu dengan hierarki |
| `dim_certificate` | certificate | Klasifikasi usia film |

---

## 🔀 Alur ETL & Pipeline BI

Berikut adalah alur lengkap dari data mentah hingga insight analitik:

```
1. EXTRACT
   Kaggle Dataset (imdb_top_1000.csv)
   └─> 1000 records · 16 kolom
       https://www.kaggle.com/datasets/harshitshankhdhar/imdb-dataset-of-top-1000-movies-and-tv-shows

2. TRANSFORM
   Python + Pandas (Google Colab / Jupyter)
   └─> Notebook: ETL/IMDB_DataWarehouse_Colab.ipynb
       ├─ Normalisasi: Runtime, Gross, Released_Year
       ├─ Handling missing values: Certificate, Meta_score, Gross
       └─ Feature engineering:
           ├─ Decade         (1920s, 1930s, ..., 2020s)
           ├─ Era            (Classic, Modern, Contemporary)
           ├─ Primary_Genre  (genre pertama dari string multi-genre)
           └─ Rating_Category (Must Watch ≥ 8.5 · Recommended ≥ 7.5 · Average)

3. LOAD
   SQLite Data Warehouse
   └─> DataWarehouse/imdb_datawarehouse.db
       ├─ 5 tabel dimensi
       └─ 1 tabel fakta (fact_movie_performance)

4. ANALYZE
   Query SQL + Python Visualization
   └─> Matplotlib · Seaborn · Plotly
       ├─ Distribusi rating & genre
       ├─ Top directors & top gross
       ├─ Tren produksi per dekade
       └─ Korelasi antar metrik (rating, votes, metascore, gross)

5. DELIVER
   Laporan & Visualisasi
   └─> Laporan lengkap (.docx) + 8 chart output (.png)
```

---

## 📊 Dataset

### Informasi Umum

| Atribut | Detail |
|---|---|
| **Sumber** | [Kaggle – IMDB Top 1000 Movies & TV Shows](https://www.kaggle.com/datasets/harshitshankhdhar/imdb-dataset-of-top-1000-movies-and-tv-shows) |
| **File** | `Dataset/imdb_top_1000.csv` |
| **Total Records** | 1.000 film/serial |
| **Total Kolom** | 16 kolom |

### Deskripsi Kolom

| Kolom | Tipe | Keterangan |
|---|---|---|
| `Series_Title` | String | Judul film / serial |
| `Released_Year` | Integer | Tahun rilis |
| `Certificate` | String | Klasifikasi usia (PG, R, UA, dll.) |
| `Runtime` | String | Durasi tayang (perlu parsing) |
| `Genre` | String | Genre film (multi-value, comma-separated) |
| `IMDB_Rating` | Float | Rating IMDb (0–10) |
| `Overview` | String | Sinopsis singkat |
| `Meta_score` | Integer | Skor dari Metacritic |
| `Director` | String | Nama sutradara |
| `Star1` – `Star4` | String | Pemeran utama (4 bintang) |
| `No_of_Votes` | Integer | Jumlah pengguna yang memberikan vote |
| `Gross` | String | Pendapatan box office (perlu parsing) |

---

## 🚀 Quick Start

<details>
<summary><strong>⚙️ Klik untuk instruksi menjalankan proyek</strong></summary>

### Prasyarat

- Python 3.x terinstal
- pip package manager
- Jupyter Notebook / Google Colab (opsional, untuk notebook interaktif)

### 1. Clone Repository

```bash
git clone https://github.com/mocharezky04/bi-uts-IMDB-Movies-Dataset.git
cd bi-uts-IMDB-Movies-Dataset/BI
```

### 2. Install Dependencies

```bash
pip install pandas numpy matplotlib seaborn plotly jupyter
```

### 3. Jalankan ETL

**Option A — Python Script (Standalone)**

```bash
cd BI
python ETL/imdb_datawarehouse_colab.py
```

**Option B — Jupyter Notebook (Interaktif)**

```bash
jupyter notebook ETL/IMDB_DataWarehouse_Colab.ipynb
```

Atau buka langsung di **Google Colab** dengan mengupload file `.ipynb`.

### 4. Cek Output

Setelah ETL selesai, cek folder `DataWarehouse/`:

```
DataWarehouse/
├── imdb_datawarehouse.db   ✅ Data Warehouse SQLite siap diquery
├── plot_*.png              ✅ 8 file visualisasi tergenerate
```

### 5. Query Data Warehouse (Opsional)

```python
import sqlite3
import pandas as pd

conn = sqlite3.connect("DataWarehouse/imdb_datawarehouse.db")

# Contoh: Top 10 film berdasarkan rating
query = """
    SELECT m.title, f.imdb_rating, f.no_of_votes, g.genre_name
    FROM fact_movie_performance f
    JOIN dim_movie m ON f.movie_id = m.movie_id
    JOIN dim_genre g ON f.genre_id = g.genre_id
    ORDER BY f.imdb_rating DESC
    LIMIT 10
"""
df = pd.read_sql_query(query, conn)
print(df)
conn.close()
```

</details>

---

## 📈 Sample Insights

Beberapa insight utama yang dihasilkan dari analisis data warehouse:

> 🎬 **Genre Dominan** — Drama dan Crime mendominasi top 1000, mencerminkan preferensi penonton IMDb terhadap cerita karakter yang mendalam.

> 🎥 **Konsistensi Sutradara** — Sejumlah direktur seperti Christopher Nolan dan Stanley Kubrick menunjukkan konsistensi rating tinggi di atas 8.0 di seluruh filmografi mereka.

> 📅 **Tren Produksi** — Jumlah film dalam top 1000 meningkat signifikan di dekade 2000–2010an, menunjukkan era ekspansi industri film modern.

> 💰 **Rating vs Revenue** — Korelasi antara IMDb rating dan gross revenue tidak linear — beberapa film dengan rating sedang justru memiliki gross tertinggi, mengindikasikan faktor komersial vs. kritikal yang berbeda.

> 📊 **Votes & Popularitas** — Film berrating tinggi tidak selalu memiliki jumlah vote terbanyak; film populer seperti franchise action cenderung mendominasi jumlah votes.

---

## 📦 Output & Deliverables

| Output | Lokasi | Keterangan |
|---|---|---|
| **SQLite DW** | `DataWarehouse/imdb_datawarehouse.db` | Data Warehouse siap query |
| **Plot Rating** | `DataWarehouse/plot_rating_distribution.png` | Histogram distribusi IMDb rating |
| **Plot Genre** | `DataWarehouse/plot_genre_count.png` | Bar chart genre terpopuler |
| **Plot Directors** | `DataWarehouse/plot_top_directors.png` | Top 10 direktur |
| **Plot Dekade** | `DataWarehouse/plot_trend_decade.png` | Tren film per dekade |
| **Plot Gross** | `DataWarehouse/plot_top_gross.png` | Top 10 gross revenue |
| **Plot Korelasi** | `DataWarehouse/plot_correlation.png` | Heatmap korelasi metrik |
| **Plot Certificate** | `DataWarehouse/plot_certificate.png` | Distribusi klasifikasi usia |
| **Plot Popular** | `DataWarehouse/plot_top_popular.png` | Film terpopuler by votes |

---

## 📄 Dokumentasi

### 📑 Laporan Proyek

Dokumen laporan lengkap mencakup: latar belakang, analisis kebutuhan, desain Star Schema, proses ETL, hasil analisis, visualisasi, dan kesimpulan.

📂 **File:** `Laporan/Laporan_DataWarehouse_Kelompok_5_Business_Intelligence_Top 1000_IMDB.docx`

***(insert link Google Drive laporan di sini)***

---

### 🖼️ Slide Presentasi

Slide deck untuk presentasi proyek — mencakup latar belakang, pipeline BI, arsitektur Star Schema, screenshot visualisasi, dan insight analitik.

***(insert link PPT/Canva di sini)***

---

## 👥 Anggota Tim — Invincible 🔥

| Nama | NIM | Role |
|---|---|---|
| Sayid Rafi A'thaya | 2409116036 | Project Manager 💡 |
| Muhammad Ilyasa' 'Izzuddin | 2409116033 | Frontend / UI 🎨 |
| Mochammad Rezky Ramadhan | 2409116029 | Backend / Database ⚙️ |

---

<div align="center">

![Footer](https://capsule-render.vercel.app/api?type=waving&height=120&color=0:20BEFF,100:0f172a&section=footer)

**DataWarehouse IMDB** &nbsp;·&nbsp; Dibangun oleh Tim Invincible  
*UTS Business Intelligence — Implementasi ETL & Star Schema End-to-End*

[![Kaggle](https://img.shields.io/badge/Dataset-Kaggle-20BEFF?style=flat-square&logo=kaggle&logoColor=white)](https://www.kaggle.com/datasets/harshitshankhdhar/imdb-dataset-of-top-1000-movies-and-tv-shows)
[![GitHub](https://img.shields.io/badge/Repository-GitHub-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/mocharezky04/bi-uts-IMDB-Movies-Dataset.git)
[![SQLite](https://img.shields.io/badge/Database-SQLite-003B57?style=flat-square&logo=sqlite&logoColor=white)](https://sqlite.org/)

</div>
