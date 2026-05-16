
# Project 2 Analysis

## Introduction

Analisis ini dilakukan untuk mengetahui apa saja sih skill-skill yang paling dibutuhkan dalam berbagai jenis pekerjaan data dan rata-rata gaji yang diperoleh dari pekerjaan yang menggunakan skill tersebut.

### Masalah Yang Dianalisis

Untuk memahami pasar kerja di bidang data science, analisis ini berfokus pada beberapa pertanyaan berikut:

1. **Apakah semakin banyak skill dapat menghasilkan gaji yang lebih tinggi?**
2. **Berapa rata-rata gaji pekerjaan data di berbagai wilayah?**
3. **Apa saja skill utama yang dimiliki para profesional data?**
4. **Berapa rata-rata gaji untuk 10 skill teratas?**

### Skill Excel Yang Digunakan

The following Excel skills were utilized for analysis:

- **📊 Pivot Tables**
- **📈 Pivot Charts**
- **🧮 DAX (Data Analysis Expressions)**
- **🔍 Power Query**
- **💪 Power Pivot**

### Data Jobs Dataset

Dataset yang digunakan dalam proyek ini berisi data pekerjaan data science nyata dari tahun 2023. Dataset tersebut diperoleh dari kursus Excel yang saya ikuti dan digunakan sebagai dasar untuk melakukan analisis data menggunakan Excel.

Dataset ini mencakup informasi detail mengenai:

- **👨‍💼 Job titles**
- **💰 Salaries**
- **📍 Locations**
- **🛠️ Skills**

## 1️⃣ Apakah semakin banyak skill menghasilkan gaji yang lebih tinggi?

### 🔍 Skill: Power Query (ETL)

#### 📥 Extract

- Pertama, saya menggunakan Power Query untuk mengekstrak data asli (`data_salary_all.xlsx`) dan membuat dua query:
   - 🗃️ Query pertama berisi seluruh informasi pekerjaan di bidang data.
   - 🔧 Query kedua berisi daftar skill untuk setiap job ID.

#### 🔄 Transform
- Selanjutnya, saya melakukan transformasi pada masing-masing query dengan:
   - Mengubah tipe data kolom
   - Menghapus kolom yang tidak diperlukan
   - Membersihkan teks dari kata-kata tertentu
   - Menghapus spasi berlebih
     
    📊 **data_jobs_all**

     ![2_Project_Analysis_Screenshot1.png](/0_Resources/Images/2_Project_Analysis_Screenshot1.png)

    🛠️ **data_job_skills**

     ![2_Project_Analysis_Screenshot2.png](/0_Resources/Images/2_Project_Analysis_Screenshot2.png)

#### 🔗 Load

- Terakhir, kedua query yang telah ditransformasikan dimuat ke workbook sebagai dasar untuk analisis selanjutnya.
    📊 **data_jobs_all**

     ![2_Project_Analysis_Screenshot3.png](/0_Resources/Images/2_Project_Analysis_Screenshot3.png)

    🛠️ **data_job_skills**

    ![2_Project_Analysis_Screenshot4.png](/0_Resources/Images/2_Project_Analysis_Screenshot4.png)

### 📊 Analysis

### 💡 Insights

- 📈 Terdapat korelasi positif antara jumlah skill yang diminta pada lowongan pekerjaan dengan median gaji, terutama pada posisi seperti Senior Data Engineer dan Data Scientist.
- 💼 Posisi yang membutuhkan lebih sedikit skill, seperti Business Analyst, cenderung menawarkan gaji lebih rendah. Hal ini menunjukkan bahwa skill yang lebih spesifik/mendalam memiliki nilai pasar yang lebih tinggi.

    ![2_Project_Analysis_Chart1.png](/0_Resources/Images/2_Project_Analysis_Chart1.png)

### 🤔 Kesimpulan

Tren ini menunjukkan pentingnya mempelajari dan menguasai berbagai skill relevan, khususnya bagi individu yang ingin memperoleh posisi dengan gaji lebih tinggi.

## 2️⃣ Berapa rata-rata gaji pekerjaan data di berbagai wilayah?

### 🧮 Skills: PivotTables & DAX

### 📈Pivot Table

- 🔢 Saya membuat PivotTable menggunakan Data Model yang telah dibuat melalui Power Pivot.
- 📊 Kolom `job_title_short` ditempatkan pada bagian rows dan `salary_year_avg` pada bagian values.
- 🧮 Kemudian saya menambahkan measure baru untuk menghitung median gaji pekerjaan di Amerika Serikat.
    ```
    =CALCULATE(
        MEDIAN(data_jobs_all[salary_year_avg]),
        data_jobs_all[job_country] = "United States")
    ```

#### 🧮 DAX

- Untuk menghitung median gaji tahunan, saya menggunakan DAX:

    ```
    Median Salary := MEDIAN(data_jobs_all[salary_year_avg])
    ```

### 📊 Analysis

#### 💡 Insights

- 💼 Posisi seperti Senior Data Engineer dan Data Scientist memiliki median gaji tinggi baik di Amerika Serikat maupun secara internasional, menunjukkan tingginya permintaan terhadap keahlian data tingkat lanjut.
- 💰 Perbedaan gaji antara pekerjaan di Amerika Serikat dan luar Amerika cukup signifikan, terutama pada pekerjaan teknologi tinggi. Hal ini kemungkinan dipengaruhi oleh tingginya konsentrasi industri teknologi di Amerika Serikat.

    ![2_Project_Analysis_Chart2.png](/0_Resources/Images/2_Project_Analysis_Chart2.png)

#### **🤔 Kesimpulan **

- Informasi gaji ini penting untuk perencanaan karier dan negosiasi gaji, baik bagi profesional maupun perusahaan agar dapat menyesuaikan standar pasar berdasarkan wilayah geografis.

## 3️⃣ Apa saja skill utama para profesional data?  
### 🔧 Skill: Power Pivot

#### 💪 Power Pivot

- 🔗 Saya membuat data model dengan menggabungkan tabel `data_jobs_all` dan `data_jobs_skills`.
- 🧹 Karena data sebelumnya sudah dibersihkan menggunakan Power Query, Power Pivot dapat langsung membuat relasi antar tabel.

#### 🔗 Data Model

- Aku membuat relasi antar kedua tabel menggunakan kolom `job_id`.

    ![2_Project_Analysis_Screenshot5.png](/0_Resources/Images/2_Project_Analysis_Screenshot5.png)

#### 📃 Power Pivot Menu

- Menu Power Pivot digunakan untuk menyempurnakan data model dan mempermudah pembuatan measure.
  
    ![2_Project_Analysis_Screenshot6.png](/0_Resources/Images/2_Project_Analysis_Screenshot6.png)

### 📊Analysis

#### 💡Insights

- 💻 SQL dan Python menjadi skill paling dominan pada pekerjaan di bidang data, menunjukkan peran penting keduanya dalam pengolahan dan analisis data.
- ☁️ Teknologi cloud seperti AWS dan Azure juga memiliki tingkat penggunaan yang tinggi, menandakan pergeseran industri menuju layanan cloud dan teknologi big data.

    ![2_Project_Analysis_Chart3.png](/0_Resources/Images/2_Project_Analysis_Chart3.png)

#### 🤔Kesimpulan

- Memahami skill yang paling banyak digunakan di industri membantu para profesional tetap kompetitif sekaligus menjadi acuan bagi program pelatihan dan pendidikan untuk fokus pada teknologi yang paling relevan.

## 4️⃣ What’s the pay of the top 10 skills?

### 📊 Skill: Advanced Charts (Pivot Chart)

#### 📈 PivotChart

- I created a combo PivotChart to plot median salary and skill likelihood (%) from my PivotTable.
    - 🪙 **Primary Axis:** Median Salary (as a Clustered Column)
    - 👍 **Secondary Axis:** Skill Likelihood (as a Line with Markers)
      
Untuk menyesuaikan tampilan chart, saya:
- Menambahkan judul chart dan axis
- Menghapus garis pada skill likelihood
- Mengubah marker menjadi bentuk diamond

### 📊 Analysis

#### 💡Insights

- 💰 Median gaji yang lebih tinggi banyak dikaitkan dengan skill seperti Python, Oracle, dan SQL, yang menunjukkan pentingnya skill tersebut dalam pekerjaan teknologi dengan bayaran tinggi.
- 📉 Skill seperti PowerPoint dan Word memiliki median gaji dan tingkat kebutuhan yang lebih rendah, menunjukkan bahwa skill tersebut kurang spesifik dan kurang diminati pada sektor dengan gaji tinggi.

    ![2_Project_Analysis_Chart4.png](/0_Resources/Images/2_Project_Analysis_Chart4.png)

### 🤔Kesimpulan

- Chart ini menunjukkan pentingnya berinvestasi waktu untuk mempelajari skill bernilai tinggi seperti Python dan SQL karena keduanya terbukti berkaitan dengan peluang karier dan gaji yang lebih besar di industri teknologi.



Saya berharap proyek ini dapat menjadi referensi praktis bagi para profesional data maupun individu yang ingin memahami skill apa saja yang diperlukan untuk mendapatkan peluang kerja dengan gaji yang lebih tinggi.
