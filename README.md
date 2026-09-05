# German Credit Risk Prediction

## PPT Source
link: https://canva.link/jtbj94mn67xhido

## Project Overview

Project ini bertujuan untuk memprediksi risiko kredit calon debitur menjadi dua kategori, yaitu `Good Risk` dan `Bad Risk`, berdasarkan karakteristik demografi, kondisi finansial, pekerjaan, dan riwayat perbankan.

Project ini dibuat sebagai portfolio Data Science dengan menerapkan proses analisis data dan machine learning secara end-to-end.

## Latar Belakang

Pemberian kredit memiliki risiko ketika calon debitur tidak mampu memenuhi kewajibannya. Oleh karena itu, lembaga keuangan perlu melakukan penilaian terhadap calon debitur sebelum memberikan kredit.

Informasi seperti usia, jumlah kredit, durasi pinjaman, pekerjaan, kondisi tempat tinggal, tabungan, dan rekening dapat digunakan untuk memahami karakteristik calon debitur dan membantu proses penilaian risiko kredit.

Melalui project ini, data tersebut dianalisis untuk menemukan pola yang berkaitan dengan risiko kredit, kemudian digunakan untuk membangun model machine learning yang dapat mengklasifikasikan calon debitur ke dalam kategori `Good Risk` dan `Bad Risk`.

## Permasalahan

Permasalahan utama yang ingin diselesaikan dalam project ini adalah bagaimana memprediksi risiko kredit calon debitur berdasarkan informasi yang tersedia.

Kesalahan dalam menilai risiko dapat menyebabkan calon debitur yang sebenarnya memiliki risiko tinggi dikategorikan sebagai debitur dengan risiko rendah. Hal tersebut dapat meningkatkan kemungkinan terjadinya kredit bermasalah.

Oleh karena itu, dibutuhkan pendekatan berbasis data yang dapat membantu mengidentifikasi karakteristik dan memprediksi risiko kredit calon debitur.

## Objective

Membangun model machine learning yang dapat membantu mengklasifikasikan risiko kredit calon debitur berdasarkan informasi yang tersedia pada German Credit Dataset.

Target:
- `good` : risiko kredit baik
- `bad` : risiko kredit buruk

## Manfaat

Project ini dapat memberikan manfaat sebagai alat bantu dalam proses penilaian risiko kredit.

Beberapa pihak yang dapat memanfaatkan hasil dari project ini antara lain:

- Lembaga keuangan atau bank sebagai pendukung dalam proses penilaian calon debitur.
- Credit analyst sebagai tambahan informasi dalam melakukan analisis risiko sebelum mengambil keputusan kredit.
- Manajemen sebagai gambaran mengenai karakteristik debitur dengan risiko kredit yang berbeda.

Model yang dibuat tidak dimaksudkan untuk menggantikan keputusan akhir, tetapi dapat digunakan sebagai salah satu informasi pendukung dalam proses evaluasi kredit.

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

## Rekomendasi

Berdasarkan hasil analisis, model Random Forest dapat digunakan sebagai alat bantu untuk mengidentifikasi calon debitur yang berpotensi memiliki risiko kredit buruk.

Selain hasil prediksi model, jumlah kredit dan durasi pinjaman dapat menjadi beberapa faktor yang perlu diperhatikan dalam proses evaluasi calon debitur karena pada dataset ini kelompok `bad` memiliki rata-rata nilai yang lebih tinggi pada kedua fitur tersebut.

Hasil prediksi sebaiknya tetap digunakan bersama analisis dan pertimbangan lain oleh credit analyst, bukan sebagai satu-satunya dasar dalam mengambil keputusan pemberian kredit.


## Project Structure

```text
how_to_build_portofolio_data_science/
│
├── german_credit_data.csv
│
├── German_Credit_Risk.ipynb
│
├── README.md
