# Klasifikasi URL Phishing untuk SIEM: Perbandingan XGBoost dan TabNet

![Python 3.11+](https://img.shields.io/badge/Python-3.11+-blue.svg)
![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)

Repositori ini berisi kode dan notebook eksperimen untuk penelitian berjudul: **"Klasifikasi URL Phishing untuk SIEM: Perbandingan Model Machine Learning XGBoost dan Deep Learning TabNet dalam Deteksi Ancaman Siber"**.

## Tentang Proyek Ini

Penelitian ini melakukan analisis perbandingan mendalam antara dua arsitektur model yang kuat untuk tugas klasifikasi data tabular:
1.  **XGBoost**: Sebagai representasi model *Gradient-Boosted Decision Tree* (GBDT) yang menjadi standar industri.
2.  **TabNet**: Sebagai representasi arsitektur *Deep Learning* yang dirancang khusus untuk data tabular.

Tujuan utamanya adalah untuk menentukan model mana yang menawarkan kombinasi terbaik antara **akurasi deteksi**, **efisiensi komputasi (kecepatan inferensi)**, dan **kepraktisan implementasi** untuk kasus penggunaan pada sistem *Security Information and Event Management* (SIEM) secara *real-time*.

## Struktur Repositori

Proyek ini diorganisir ke dalam beberapa notebook modular untuk keterulangan (reproducibility) dan kejelasan:

-   **/data**: Direktori placeholder. Tempatkan file `dataset_training.csv` dan `dataset_testing.csv` di sini.
-   `01_XGBoost_Experiment.ipynb`: Notebook lengkap untuk proses *hyperparameter tuning*, pelatihan, dan evaluasi model XGBoost.
-   `02_TabNet_Experiment.ipynb`: Notebook lengkap untuk proses *hyperparameter tuning*, pelatihan, dan evaluasi model TabNet.
-   `03_Analysis_and_Visualization.ipynb`: Notebook untuk memuat hasil dari kedua eksperimen, membuat tabel perbandingan, dan menghasilkan visualisasi grafik yang digunakan dalam paper.
-   **/outputs**: Direktori ini akan dibuat secara otomatis untuk menyimpan semua artefak hasil, termasuk model terlatih (`.json`/`.zip`) dan file metrik (`.json`).


## Hasil Utama

Studi ini menemukan bahwa model **XGBoost (Tuned)** secara konsisten mengungguli **TabNet (Tuned)** di semua metrik performa dan efisiensi untuk tugas ini.

| Model             | F1-Score | Inference Time (CPU) | Inference Time (GPU) |
| ----------------- | :------: | :------------------: | :------------------: |
| **XGBoost (Tuned)** | **0.9533** | **0.0267 ms/sampel** | **0.0008 ms/sampel** |
| TabNet (Tuned)    |  0.9007  |   0.0346 ms/sampel   |   0.0267 ms/sampel   |
