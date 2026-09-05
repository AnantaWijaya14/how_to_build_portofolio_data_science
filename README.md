# German Credit Risk Prediction

## Project Overview

Project ini bertujuan untuk memprediksi risiko kredit calon debitur menjadi dua kategori, yaitu `Good Risk` dan `Bad Risk`, berdasarkan karakteristik demografi, kondisi finansial, pekerjaan, dan riwayat perbankan.

Project ini dibuat sebagai portfolio Data Science dengan menerapkan proses analisis data dan machine learning secara end-to-end.

## Objective

Membangun model machine learning yang dapat membantu mengklasifikasikan risiko kredit calon debitur berdasarkan informasi yang tersedia pada German Credit Dataset.

Target:
- `good` : risiko kredit baik
- `bad` : risiko kredit buruk

## Dataset

Dataset yang digunakan adalah German Credit Risk Dataset dengan:

- 1,000 data
- 10 kolom
- Target: `Risk`

### Numerical Features

- `Age`
- `Credit amount`
- `Duration`

### Categorical Features

- `Sex`
- `Job`
- `Housing`
- `Saving accounts`
- `Checking account`
- `Purpose`

## Exploratory Data Analysis

Beberapa analisis dilakukan untuk memahami karakteristik data sebelum membangun model.

### Temuan Utama

- `Credit amount` dan `Duration` memiliki distribusi yang cenderung menceng ke kanan.
- Terdapat missing value pada `Saving accounts` sebanyak 183 data dan `Checking account` sebanyak 394 data.
- Debitur dengan risiko `bad` memiliki rata-rata `Credit amount` yang lebih tinggi dibandingkan debitur dengan risiko `good`.
- Debitur dengan risiko `bad` juga memiliki rata-rata `Duration` yang lebih panjang.
- `Credit amount` dan `Duration` memiliki korelasi positif sebesar 0.625.

Hasil EDA bersifat deskriptif dan tidak digunakan untuk menyimpulkan hubungan sebab-akibat.

## Data Preprocessing

Tahapan preprocessing yang dilakukan:

1. Memisahkan fitur numerik dan kategorikal.
2. Menangani missing value pada fitur kategorikal menggunakan modus.
3. Melakukan One-Hot Encoding pada fitur kategorikal.
4. Melakukan scaling pada fitur numerik.
5. Membagi data menjadi 70% training dan 30% testing.
6. Menggunakan stratified split untuk menjaga proporsi target.

Preprocessing dilakukan menggunakan pipeline agar proses transformasi data tetap konsisten antara data training dan testing.

## Machine Learning

Beberapa algoritma machine learning dibandingkan dalam project ini:

- Logistic Regression
- Decision Tree
- Random Forest
- Extra Trees

Hyperparameter tuning dilakukan menggunakan GridSearchCV dengan 5-fold Stratified Cross Validation.

Metric utama yang digunakan untuk pemilihan model adalah F1-Score karena dataset memiliki distribusi kelas yang tidak seimbang.

## Model Performance

| Model | Accuracy | Precision | Recall | F1-Score | ROC-AUC |
|---|---:|---:|---:|---:|---:|
| Random Forest | 0.707 | 0.508 | 0.722 | 0.596 | 0.762 |
| Logistic Regression | 0.697 | 0.496 | 0.733 | 0.592 | 0.769 |
| Extra Trees | 0.673 | 0.471 | 0.711 | 0.566 | 0.755 |
| Decision Tree | 0.610 | 0.424 | 0.833 | 0.562 | 0.681 |

## Best Model

Random Forest dipilih sebagai model terbaik berdasarkan F1-Score sebesar 0.596.

Meskipun Logistic Regression memiliki nilai ROC-AUC yang sedikit lebih tinggi, pemilihan model dalam project ini didasarkan pada F1-Score.

## Key Insights

Beberapa insight yang diperoleh dari project ini:

- Debitur dengan risiko `bad` cenderung memiliki jumlah kredit yang lebih besar.
- Debitur dengan risiko `bad` cenderung memiliki durasi pinjaman yang lebih panjang.
- `Credit amount` memiliki hubungan positif yang cukup kuat dengan `Duration`.
- Random Forest memberikan F1-Score terbaik dibandingkan model lainnya.

## Tech Stack

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Imbalanced-learn
- Jupyter Notebook
- Google Colab

## Project Structure

```text
German-Credit-Risk/
│
├── german_credit_data.csv
│
├── German_Credit_Risk.ipynb
│
├── README.md
