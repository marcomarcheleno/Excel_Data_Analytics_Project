# Excel Salary Dashboard

![1_Salary_Dashboard.png](/0_Resources/Images/1_Salary_Dashboard_Final_Dashboard.gif)

## Introduction

Dasbor gaji ini dibuat untuk membantu orang-orang yang sedang mencari kerja untuk mengetahui perkiraan gaji dari pekerjaan yang mereka inginkan.

Data ini saya dapatkan dari kursus excel yang saya ikuti secara online dan data tersebut telah mengandung informasi yang cukup lengkap dari nama pekerjaan, gaji, lokasi, dan skill-skill yang dibutuhkan.

### Dashboard File
Finalisasi dasbor gajinya ada di link berikut [Dasbor](Dasbor_Analisis_Gaji_Data_Science.xlsx)

### Skill Excel Yang Digunakan

Berikut skill yang digunakan dalam analisis:

- **📉 Charts**
- **🧮 Formulas and Functions**
- **❎ Data Validation**

### Data Jobs Dataset

Dataset yang digunakan dalam proyek ini mengandung informasi data science real-world dari tahun 2023. File ini mengandung informasi yang dibutuhkan dalam analsis. Berikut detail informasinya:  

- **👨‍💼 Job titles**
- **💰 Salaries**
- **📍 Locations**
- **🛠️ Skills**

## Dashboard Build

### 📉 Charts

#### 📊 Data Science Job Salaries - Bar Chart

<img src="/0_Resources/Images/1_Salary_Dashboard_Chart1.png" width="850" height="550" alt="Salary Dashboard Chart1">

- 🛠️ **Excel Features:** menggunakan fitur bar chart (dengan format nilai gaji) dan layout tampilan yang jelas.
- 🎨 **Design Choice:** Horizontal bar chart untuk perbandingan visual atas median dari gaji.
- 📉 **Data Organization:** Menyusun nama pekerjaan berdasarkan nilai gaji dari tertinggi ke terendah agar mudah dibaca.
- 💡 **Insights Gained:** Memudahkan kita dalam mengidentifikasi tren gaji, bisa dilihat bahwa role Senior dan Engineer memiliki rata-rata gaji yang lebih tinggi dibanding role Analyst.

#### 🗺️ Country Median Salaries - Map Chart

![1_Salary_Dashboard_Chart2.png](/0_Resources/Images/1_Salary_Dashboard_Country_Map.gif)

- 🛠️ **Excel Features:** Menggunakan fitur Map Chart dalam Excel untuk memperlihatkan median dari gaji secara global.
- 🎨 **Design Choice:** Map berwarna yang dirancang untuk membedakan rata-rata gaji di berbagai negara secara visual.
- 📊 **Data Representation:** Data yang bisa memperlihatkan median dari gaji untuk tiap negara.
- 👁️ **Visual Enhancement:** Meningkatkan keterbacaan dan pemahaman yang lebih baik dari perbedaan gaji terhadap berbagai jenis faktor.

### 🧮 Formulas and Functions

#### 💰 Median Salary by Job Titles

```
=MEDIAN(
IF(
    (jobs[job_title_short]=A2)*
    (jobs[job_country]=country)*
    (ISNUMBER(SEARCH(type,jobs[job_schedule_type])))*
    (jobs[salary_year_avg]<>0),
    jobs[salary_year_avg]
)
)
```

- 🔍 **Multi-Criteria Filtering:** Mengecek job title, negara, jenis jadwal kerja, dan mengecualikan kolom gaji yang kosong.
- 📊 **Array Formula:** menggunakan fungsi `MEDIAN()` dengan nested `IF()`untuk menganalisis array.
- 🎯 **Tailored Insights:** Menyediakan informasi gaji yang spesifik untuk job titles, negara dan jenis jadwal kerja.
- **🔢 Formula Purpose:** Formula ini menciptakan tabel dibawah, menampilkan median dari gaji berdasarkan job title, negara dan jenis jawal kerja.

🍽️ Background Table

![1_Salary_Dashboard_Screenshot1.png](/0_Resources/Images/1_Salary_Dashboard_Screenshot1.png)

📉 Dashboard Implementation

<img src="/0_Resources/Images/1_Salary_Dashboard_Job_Title.png" width="400" height="500" alt="Salary Dashboard Title">

#### ⏰ Count of Job Schedule Type

```
=FILTER(J2#,(NOT(ISNUMBER(SEARCH("and",J2#))+ISNUMBER(SEARCH(",",J2#))))*(J2#<>0))
```

- 🔍 **Unique List Generation:** Formula Excel ini fungsi `FILTER()` untuk mengeluarkan nilai yang mengandung "and" atau koma, dan mengeluarkan nilai 0.
- **🔢 Formula Purpose:** Formula ini menciptakan tabel dibawah yang memperlihatkan kita list dari setiap jenis jadwal kerja.

🍽️ Background Table

![1_Salary_Dashboard_Type.png](/0_Resources/Images/1_Salary_Dashboard_Screenshot2.png)

📉 Dashboard Implementation:

<img src="/0_Resources/Images/1_Salary_Dashboard_Type.png" width="350" height="500" alt="Salary Dashboard Type">

### ❎ Data Validation

#### 🔍 Filtered List

- 🔒 **Enhanced Data Validation:** Mengimplementasikan list yang telah difilter untuk opsi `Job Title`, `Country`, dan `Type`dalam tab data untuk memastikan:  
   - 🎯 Input pengguna tetap terstruktur dan sesuai dengan pilihan yang telah ditentukan
   - 🚫 Mencegah entri data yang tidak valid atau tidak konsisten
   - 🧩 Meningkatkan kemudahan penggunaan serta efisiensi dashboard secara keseluruhan

<img src="/0_Resources/Images/1_Salary_Dashboard_Data_Validation.gif" width="425" height="400" alt="Salary Dashboard Data Validation">
