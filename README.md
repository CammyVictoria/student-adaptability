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
<img width="943" height="242" alt="image" src="https://github.com/user-attachments/assets/8695c7a8-4f65-4d4b-a2d4-1590af99fa4f" />
<img width="969" height="233" alt="image" src="https://github.com/user-attachments/assets/231cedf2-5557-4c31-bccd-2ba0f7ea4916" />
<img width="964" height="232" alt="image" src="https://github.com/user-attachments/assets/8067f5af-7c13-4f19-999d-e5e61807de4f" />
<img width="968" height="236" alt="image" src="https://github.com/user-attachments/assets/24cd08f9-2b61-468f-bf8b-d6dc083dc3bf" />
<img width="928" height="221" alt="image" src="https://github.com/user-attachments/assets/3c1dafd2-89cc-4b4c-bddc-e9ceeb31470c" />



Berikut kelompok demografis yang membutuhkan perhatian lebih:
- Teenager
- College student
- Perempuan
- Tinggal di luar kota
- Memiliki financial condition yang kurang baik

### Class Duration Optimal
<img width="298" height="509" alt="image" src="https://github.com/user-attachments/assets/3596213c-5a19-4cae-977d-a2a338ff1984" />

Kelompok demografis yang membutuhkan atensi lebih cenderung lebih bisa beradaptasi di jam pembelajaran berkisar 3-6 jam perhari.

## Actionable Insights
- Sarankan setiap institusi pendidikan untuk mengembangkan sistem lms masing-masing.
- Berikan atensi lebih terhadap kelompok demografis yang kurang bisa beradaptasi
- Terapkan jam pembelajaran 3-6 jam perhari terutama untuk age group teenager. (attention span anak kecil cenderung rendah dan young adult biasanya sudah memiliki tanggung jawab diluar pendidikan sehingga kedua kategori usia tersebut kurang cocok apabila harus menjalani jam belajar yang lebih lama)
