# 🔍 Fraud Analytics Dashboard

![Python](https://img.shields.io/badge/Python-3.10-blue?logo=python)
![Power BI](https://img.shields.io/badge/PowerBI-Dashboard-yellow?logo=powerbi)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen)
![Dataset](https://img.shields.io/badge/Dataset-7000%20rows-orange)

## 📌 Project Overview

Project ini merupakan analisis data transaksi keuangan untuk mendeteksi pola fraud menggunakan Python dan Power BI. Dataset berisi **7.000 transaksi** dengan berbagai atribut pelanggan dan transaksi yang digunakan untuk menjawab pertanyaan bisnis terkait deteksi fraud.

---

## 🎯 Business Questions (SMART Method)

| # | Pertanyaan Bisnis | Kolom Kunci |
|---|---|---|
| 1 | Seberapa tinggi fraud rate secara keseluruhan? | `is_fraud` |
| 2 | Jam mana paling rawan fraud? | `hour_of_day`, `is_fraud` |
| 3 | Apakah jarak dari rumah mempengaruhi fraud? | `distance_from_home`, `is_fraud` |
| 4 | Apakah pelanggan baru lebih rentan fraud? | `is_first_transaction`, `is_fraud` |
| 5 | Online vs offline — mana lebih berisiko? | `store_type`, `is_fraud` |
| 6 | Apakah velocity score tinggi = fraud? | `velocity_score`, `is_fraud` |
| 7 | Kelompok usia mana paling sering jadi target? | `customer_age`, `is_fraud` |

---

## 📂 Project Structure

```
Banking-Fraud-Analytics/
│
├── Dataset/
│   ├── fraud.csv                   ← Dataset asli (kotor)
│   └── clean_fraud_powerbi.csv     ← Dataset bersih (siap Power BI)
│
├── Notebook/
│   └── fraud_cleaning_eda.ipynb    ← Data Cleaning & EDA (Google Colab)
│
├── Dashboard/
│   └── fraud_dashboard.pbix        ← Power BI Dashboard
│
├── Screenshots/
│   ├── dashboard_overview.png
│   ├── eda_plots.png
│   └── cleaning_output.png
│
└── README.md
```

---

## 🛠️ Tools & Libraries

| Tool | Kegunaan |
|---|---|
| Python 3.10 | Data Cleaning & EDA |
| Pandas | Manipulasi data |
| NumPy | Komputasi numerik |
| Matplotlib & Seaborn | Visualisasi EDA |
| Scipy | Analisis statistik |
| Power BI | Dashboard interaktif |
| Google Colab | Environment coding |

---

## 🧹 Data Cleaning Process

Dataset awal mengandung berbagai masalah kualitas data:

| Masalah | Detail | Penanganan |
|---|---|---|
| Missing Values | 5.600 nilai kosong (tersebar di 12 kolom) | Median (numerik) & Mode (kategorikal) |
| Duplikat | 0 duplikat ditemukan | Tidak ada tindakan |
| Outlier | 6 kolom numerik mengandung outlier | IQR Capping & Clipping |
| Nilai Negatif | `velocity_score` memiliki nilai negatif | Clip ke 0 |
| Data Types | Semua kolom bertipe float64 | Konversi ke int64 |

---

## 📊 Dashboard Overview

Dashboard Power BI terdiri dari:

### KPI Cards
- **Total Transaksi**: 7.000
- **Total Fraud**: 721
- **Total Non-Fraud**: 6.279
- **Fraud Rate**: 10.30%

### Visualisasi
1. Bar Chart — Fraud Rate per Jam
2. Pie Chart — Fraud vs Non-Fraud
3. Scatter Plot — Jarak dari Rumah vs Nilai Transaksi
4. Bar Chart — Fraud Rate Online vs Offline
5. Bar Chart — Fraud Rate Pelanggan Baru vs Lama
6. Bar Chart — Rata-rata Velocity Score
7. Bar Chart — Fraud Rate per Kelompok Usia

### Filter Interaktif
- Status Fraud
- Jam Transaksi
- Tipe Toko
- Tipe Perangkat
- Hari (Weekday/Weekend)

---

## 💡 Key Insights

| Temuan | Insight |
|---|---|
| Fraud rate **10.30%** | Melebihi batas toleransi 5% — perlu tindakan segera |
| Pagi hari fraud rate **11.77%** | Jam pagi paling berisiko, perlu monitoring ekstra |
| Transaksi online sedikit lebih berisiko | Perlu verifikasi 2 langkah untuk transaksi online |
| Pelanggan baru & lama sama-sama berisiko | Fraud tidak hanya menyasar pelanggan baru |
| Usia 18-30 paling rentan | Program edukasi keamanan untuk usia muda |
| Velocity score tidak signifikan | Perlu kombinasi beberapa variabel untuk deteksi fraud |

---

## 🚀 How to Run

### 1. Clone Repository
```bash
git clone https://github.com/username/Banking-Fraud-Analytics.git
cd Banking-Fraud-Analytics
```

### 2. Install Dependencies
```bash
pip install pandas numpy matplotlib seaborn scipy
```

### 3. Jalankan Notebook
Buka file `Notebook/fraud_cleaning_eda.ipynb` di Google Colab atau Jupyter Notebook.

### 4. Buka Dashboard
Buka file `Dashboard/fraud_dashboard.pbix` menggunakan Power BI Desktop.

---

## 📈 EDA Highlights

- Distribusi fraud **imbalanced** — 89.7% non-fraud vs 10.3% fraud
- Transaction amount terdapat **spike di nilai ~100**
- Fraud tersebar **merata di semua range nilai transaksi**
- Pagi hari memiliki fraud rate tertinggi **11.77%**

---

## 👤 Author

**Danang**
- 💼 Data Analyst Portfolio Project
- 🗓️ 2024
- 📊 Tools: Python · Power BI · SQL

---

## 📄 License

This project is licensed under the MIT License.
