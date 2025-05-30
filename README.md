# Proyek Akhir: Menyelesaikan Permasalahan Perusahaan Edutech


# Persiapan Proyek

Agar proyek ini berjalan lancar,ada beberapa langkah-langkah yang disusun secara sistematis seperti berikut.

1. Sumber data

   Dataset yang digunakan dalam proyek ini adalah dataset attrition karyawan dari Dicoding Academy. Data ini dapat diakses melalui tautan berikut:

- Nama file: employee_attrition.csv
- Tautan Unduh:

  https://github.com/dicodingacademy/dicoding_dataset/tree/main/employee


  - Cara akses di Google Colab

    !wget https://github.com/dicodingacademy/dicoding_dataset/raw/main/employee/employee_attrition.csv



2. Membuat dan Mengaktifkan Virtual Environment

   Pada proyek ini karena di bangun dan dijalankan menggunakan Google Colab,sehingga tidak menggunakan virtual environment sehingga untuk langkah ini menggunakan environment yang sudah siap pakai di Colab. Namun jika misalnya akan dijalankan secara lokal maka harus menggunakan virtual environment dan dijalankan diterminal local seperti berikut.


- Membuat virtual environment
     - python -m venv env

- Mengaktifkan (Windows)
     - env\Scripts\activate

- Mengaktifkan (Mac/Linux)
     - source env/bin/activate
   

3. Menginstal Dependensi dari requirements.txt

   Karena proyek ini dijalankan di Colab,sehingga untuk mendapatkan file requirement.txt menggunakan perintah '!pip freeze > requirements.txt'. Namun jika menjalankannya dilocal dapat diinstal dengan perintah 'pip install -r requirements.txt'.


4. Menjalankan Skrip Python

   Proyek ini dijalankan di Google Colab, sehingga cukup membuka file .ipynb dan menjalankannya sel-sel notebook-nya secara berurutan.
Namun, jika telah mengubahnya menjadi file Python .py, berikut cara mengeksekusinya:

- python nama file.py

Jika skrip menerima parameter, contoh perintah:

- python nama file.py --input data/employee_attrition.csv --model logistic



# Business Understanding

# Latar Belakang Bisnis

Perusahaan Jaya Jaya Maju adalah perusahaan multinasional yang telah beroperasi sejak tahun 2000 dengan lebih dari 1.000 karyawan. Tingginya angka attrition (karyawan resign) dalam beberapa tahun terakhir telah menyebabkan peningkatan biaya rekrutmen, penurunan produktivitas, dan gangguan terhadap stabilitas tim. Departemen HR membutuhkan analisis mendalam untuk memahami faktor-faktor penyebab karyawan resign dan mengembangkan strategi retensi berbasis data.

# Permasalahan Bisnis

1. Tingginya Biaya Operasional: Biaya rekrutmen dan pelatihan karyawan baru meningkat akibat attrition.
2. Penurunan Produktivitas: Pergantian karyawan yang cepat mengganggu kontinuitas proyek dan kinerja tim.
3. Kurangnya Insight Penyebab Attrition: Tidak ada pemahaman jelas tentang faktor dominan yang mendorong karyawan resign.
4. Ketidakseimbangan Kelas Data: Data attrition tidak seimbang (hanya ~16% kasus resign), menyulitkan analisis prediktif.

# Cakupan Proyek

Proyek ini mencakup:

1. Analisis Eksplorasi Data (EDA):
   - Mengidentifikasi pola attrition berdasarkan departemen, peran pekerjaan, kepuasan kerja, pendapatan, dan faktor demografis.
  - Menemukan hubungan antara lembur (OverTime), kepuasan kerja, dan attrition.

2. Pembangunan Model Prediktif:
  - Membandingkan performa model Logistic Regression, Random Forest, dan XGBoost untuk memprediksi risiko attrition.
  - Fokus pada metrik Recall untuk memaksimalkan deteksi karyawan berisiko resign.

3. Business Dashboard Interaktif:
  - Visualisasi tren attrition per departemen, peran pekerjaan, dan tingkat kepuasan (dibangun menggunakan Tableau).

# Persiapan

1. Sumber Data: Dataset historis karyawan (employee_attrition.csv) dengan 35 fitur, termasuk:
  - Demografi: Age, Gender, MaritalStatus.
  - Pekerjaan: Department, JobRole, JobLevel.
  - Kepuasan: JobSatisfaction, EnvironmentSatisfaction.
  - Target: Attrition (0 = tidak resign, 1 = resign).

2. Setup Environment:
  - Bahasa Pemrograman: Python.
  - Library: Pandas, Scikit-learn, XGBoost, SHAP, Imbalanced-learn.
  - Tools: Google Colab (analisis), Tableau (dashboard).

# Business Dashboard

Dashboard interaktif dibangun untuk memvisualisasikan:

1. Tren Attrition:
  - Tingkat attrition per departemen, jenis pekerjaan, dan status perkawinan.
  - Hubungan antara kepuasan kerja (JobSatisfaction) dan attrition.

2. Faktor Kunci:
  - Dampak lembur (OverTime) dan pendapatan (MonthlyIncome) terhadap keputusan resign.
  - Distribusi karyawan berisiko tinggi berdasarkan prediksi model.

3. Akses Dashboard:

https://public.tableau.com/views/HRANALYTICSDAHSBOARD_17475104696060/JayaJayaMajuHRInsightsDashboard?:language=en-US&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link




# Conclusion

1. Faktor Dominan Attrition:
  - Lembur (OverTime_Yes): Karyawan yang lembur memiliki risiko resign 2× lebih tinggi.
  - Status Lajang (MaritalStatus_Single): 1.5× lebih mungkin resign dibandingkan yang menikah.
  - Kepuasan Kerja Rendah: Skor JobSatisfaction ≤2 meningkatkan risiko resign hingga 40%.

2. Model Terbaik:
  - Logistic Regression dengan Recall 71% dan AUC 0.80 menjadi model terpilih.

3. Insight Departemen:
  - Departemen Sales memiliki tingkat attrition tertinggi (25%), diikuti HR (15%).

# Rekomendasi Action Items

1. Kurangi Beban Lembur
  - Evaluasi kebijakan lembur dan tambahkan insentif untuk karyawan yang bekerja di luar jam normal.
  - Otomatisasi tugas repetitif untuk mengurangi beban kerja.

2. Tingkatkan Kepuasan Kerja
  - Program pengembangan karir dan promosi reguler (minimal 2 tahun sekali).
  - Survei kepuasan kerja berkala untuk identifikasi masalah spesifik.

3. Program Retensi untuk Sales & HR
  - Pelatihan manajemen stres untuk tim Sales.
  - Fleksibilitas jam kerja untuk tim HR.

4. Insentif Berbasis Kinerja
  - Tambahkan opsi saham (StockOptionLevel) untuk karyawan dengan masa kerja >3 tahun.
  - Kenaikan gaji kompetitif berdasarkan performa (PerformanceRating).

5. Prediksi Risiko Attrition
  - Implementasikan model prediktif untuk mengidentifikasi karyawan berisiko resign dan lakukan intervensi proaktif.
