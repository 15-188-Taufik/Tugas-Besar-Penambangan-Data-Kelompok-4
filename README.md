# 📘 README — Tugas Besar Kelompok
## Analisis Deteksi Anomali pada Indeks Standar Pencemaran Udara (ISPU) DKI Jakarta 2010–2021

---

## 🧑‍💻 Identitas Kelompok

**Mata Kuliah:** Penambangan Data (IF25-32025) — Semester Genap 2025/2026  
**Dosen Pengampu:** Meida Cahyo Untoro, S.Kom., M.Kom.  
**Kelompok:** Anomaly Detection  
**Topik:** Topik 3 — Anomaly Detection  
**Tanggal:** April 2026

---

## 👥 Anggota Kelompok

| No | NIM | Nama Lengkap | Kontribusi |
|----|-----|--------------|------------|
| 1 | 123140188 | Taufik Hidayat NST | Pendahuluan, Tinjauan Pustaka (15%) |
| 2 | 123140062 | Nabila Ramadhani M | Metodologi, EDA (15%) |
| 3 | 123140071 | Willy Syifa Luthfia | Hasil & Pembahasan (14%) |
| 4 | 123140121 | Fanisa Aulia Safitri | Kesimpulan, Saran, Referensi (14%) |
| 5 | 123140070 | Annisa Salsabila | Implementasi DBSCAN & Consensus Voting (14%) |
| 6 | 123140044 | Jesika Filosovi Br P-A | Implementasi Isolation Forest & LOF (14%) |
| 7 | 123140043 | Tengku Hafid Diraputra | Coding Notebook, Testing & Pipeline (14%) |

---

## 📌 Deskripsi Proyek

Proyek ini bertujuan untuk mengevaluasi tiga metode deteksi anomali — **Isolation Forest**, **Local Outlier Factor (LOF)**, dan **DBSCAN** — pada dataset ISPU DKI Jakarta tahun 2010–2021 yang memuat 5.533 rekaman dari 5 stasiun pemantauan.

Pipeline bebas data leakage diterapkan dengan melakukan train-test split (80:20, stratified) sebelum seluruh proses preprocessing dan deteksi anomali. **Consensus voting** (threshold ≥ 2/3 metode) digunakan untuk mengidentifikasi anomali yang lebih robust.

---

## 🗂️ Struktur Notebook

```
Tubes_DM_AnomalyDetection_ISPU_Jakarta_fixed.ipynb
│
├── BAB 1 — Pendahuluan
├── BAB 2 — Tinjauan Pustaka
├── BAB 3 — Metodologi
├── BAB 4 — Implementasi & Hasil
│   ├── Isolation Forest
│   ├── Local Outlier Factor (LOF)
│   ├── DBSCAN
│   └── Consensus Voting
└── BAB 5 — Kesimpulan & Saran
```

---

## 🔍 Metode yang Digunakan

| Metode | Pendekatan | Parameter Kunci |
|--------|-----------|-----------------|
| Isolation Forest | Tree-based | contamination, n_estimators |
| Local Outlier Factor (LOF) | Density-based | n_neighbors, contamination |
| DBSCAN | Clustering-based | eps, min_samples |
| Consensus Voting | Ensemble | threshold ≥ 2 dari 3 metode |

---

## 📊 Dataset

- **Sumber:** Kaggle — `senadu34/air-quality-index-in-jakarta-2010-2021`
- **Periode:** 2010 – 2021
- **Jumlah Data:** 5.533 rekaman dari 5 stasiun pemantauan
- **Fitur:** PM10, SO₂, CO, O₃, NO₂
- **Target:** Biner — `0` = Normal (BAIK/SEDANG), `1` = Tidak Sehat (TIDAK SEHAT/SANGAT TIDAK SEHAT/BERBAHAYA)

---

## 📈 Metrik Evaluasi

Evaluasi dilakukan dengan membandingkan performa **Random Forest Classifier** sebelum dan sesudah pembersihan anomali menggunakan:

- Accuracy
- Precision
- Recall
- F1-Score
- AUC-ROC

---

## ⚙️ Cara Menjalankan

1. Clone atau unduh repository ini.
2. Pastikan dependensi berikut telah terinstall:
   ```bash
   pip install pandas numpy scikit-learn matplotlib seaborn
   ```
3. Buka notebook menggunakan Jupyter:
   ```bash
   jupyter notebook Tubes_DM_AnomalyDetection_ISPU_Jakarta_fixed.ipynb
   ```
4. Jalankan sel secara berurutan dari atas ke bawah.

---

## 📝 Catatan

- PM2.5 dikecualikan dari analisis karena memiliki missing value >70%.
- Parameter `contamination` diestimasi menggunakan aturan 3-sigma.
- Parameter `eps` untuk DBSCAN ditentukan melalui k-distance plot pada data yang direduksi PCA 2 komponen.

---

*Institut Teknologi Sumatera — Program Studi Informatika*
