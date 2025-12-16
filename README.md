# Data Analytic Project - Students Adaptability Level in Online Education
## Latar Belakang
Sistem pembelajaran daring sebenarnya sudah lama ada sebelum terjadinya pandemi COVID-19. Namun, pada saat pandemi dimulai semua pelajar dari berbagai tingkatan akademik dipaksa beradaptasi dalam sistem yang belum disempurnakan tersebut.

### Masalah yang Ditimbulkan
Dalam kasus pendidikan, adaptabilitas merupakan hal yang krusial. Namun, tidak semua orang dapat langsung beradaptasi terhadap perubahan, terutama transisi metode pelajaran konvensional ke metode pembelajaran daring yang terjadi dalam kurun waktu yang singkat. 

### Goals
Berdasarkan masalah yang ada, berikut tujuan analisa pada projek ini:
1. Mengetahui apakah keberadaan LMS sudah efektif membantu siswa dalam beradaptasi di sistem pembelajaran online.
2. Mengetahui Pengaruh faktor demografis terhadap adaptasi siswa.
3. Mengetahui class duration yang optimal untuk diterapkan berdasarkan faktor demografis yang perlu atensi lebih.

## Data Understanding
- Judul Dataset: Students Adaptability Level in Online Education
- Author: Md. Mahmudul Hasan Suzan dan Nishat Ahmed Samrin
- Link Dataset: https://www.kaggle.com/datasets/mdmahmudulhasansuzan/students-adaptability-level-in-online-education

### Kolom

| No | Column Name | Description | Tipe Data | 
|-----------|------------|-------------|-----------|
| 1 | Gender | Jenis kelamin siswa | Object |
| 2 | Age | Umur siswa | Object |
| 3 | Education Level | Tingkatan edukasi (school/university/dll) | Object |
| 4 | IT student | Apakah siswa merupakan siswa dari jurusan IT? (information technology) | Object |
| 5 | Location | Apakah siswa tinggal di daerah perkotaan? | Object |
| 6 | Load-shedding | Tingkat pemadaman bergilir di daerah tinggal siswa | Object |
| 7 | Financial condition | Kondisi ekonomi keluarga siswa | Object |
| 8 | Internet type | Jenis koneksi internet (mobile data / wifi) | Object |
| 9 | Network type | Tipe jaringan (4G / 3G / dll) | Object |
| 10 | Class duration | Durasi kelas per hari | Object |
| 11 | Self LMS | Apakah institusi akademis memiliki LMS sendiri? | Object |
| 12 | Device | Perangkat yang digunakan untuk mengikuti kelas | Object |
| 13 | Adaptability level | Tingkat adaptasi | Object |

Dataset tersebut memiliki 13 kolom x 1205 baris

## Data Cleaning
- Jumlah data NULL: 0
- Jumlah data duplikat: 0

Karena keseluruhan kolom yang ada merupakan data kategorikal, maka pengecekan outlier dilakukan melalui penalaran konteks data. Berikut data-data yang ditangani:
- Class Duration = 0 -> kemungkinan salah input/bukan murid yang mengikuti pembelajaran daring, data ini dibuang
- Network Type = 2G -> Sudah tidak umum digunakan, dikelompokkan bersama 3G ke dalam kategori Low Network

## Data Manipulation
- Age Group -> Dilakukan grouping untuk kolom ini menjadi Child, Teen, dan Young Adult. Kategorisasi ini membantu menyederhanakan data sehingga proses analisis bisa lebih terarah.
- Effectiveness Score -> Menerapkan konsep weighted score pada kolom Adaptibility Level untuk mencari tahu skor efektifitas pembelajaran. (High: 2, Moderate: 1, Low: 0.5)

## EDA
### Apakah LMS Pribadi Membantu Para Murid Beradaptasi?
<img width="756" height="209" alt="image" src="https://github.com/user-attachments/assets/9e29730a-0876-40b5-be1d-390a0c9f073a" />

Persentase adaptivity level high lebih banyak tersebar di siswa yang memiliki lms dan persentase adaptivity level lebih tersebar di murid yang tidak memiliki lms. Yang berarti LMS sedikit membantu murid dalam sistem pembelajaran online

### Pengaruh Faktor Demografis terhadap Adaptasi Murid
<img width="191" height="242" alt="image" src="https://github.com/user-attachments/assets/c48ed120-ad6c-4b97-980e-78b9cb5b4540" />

Berikut kelompok demografis yang membutuhkan perhatian lebih:
- Teenager
- College student
- Perempuan
- Tinggal di luar kota
- Memiliki financial condition yang kurang baik

### Class Duration Optimal

