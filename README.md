# Laporan Proyek Machine Learning - Dewi Rachmawati

## Domain Proyek: Pendidikan
Performa akademik mahasiswa dipengaruhi oleh kebiasaan hidup yang mencakup pola tidur, frekuensi olahraga, dan kesehatan mental. Tidur cukup berperan dalam meningkatkan daya ingat serta kemampuan kognitif, memungkinkan fokus dan produktivitas dalam studi tetap optimal. Penelitian menunjukkan bahwa kualitas tidur yang baik berkorelasi dengan peningkatan performa akademik dan penurunan stres akademik yang berlebihan (Xu et al., 2025). Sebaliknya, gangguan tidur yang berkepanjangan dapat meningkatkan tingkat kecemasan dan menurunkan efisiensi belajar, sehingga menghambat pencapaian akademik.

Selain pola tidur, aktivitas fisik memiliki peran penting dalam mendukung kesejahteraan psikologis. Studi menemukan bahwa rutinitas olahraga yang teratur berkontribusi pada penurunan tingkat stres dan peningkatan kualitas tidur (Li et al., 2022). Aktivitas fisik tidak hanya membantu meningkatkan kualitas tidur, tetapi juga memperkuat ketahanan mental terhadap tekanan akademik. Studi lain menunjukkan bahwa aktivitas fisik yang dilakukan secara konsisten berkontribusi terhadap pemulihan stres dan peningkatan performa akademik pada tingkat harian, memberikan dampak positif bagi mahasiswa selama periode ujian (Teuber et al., 2024). Dengan demikian, program akademik yang mendorong keseimbangan gaya hidup sehat dapat memberikan manfaat yang lebih besar dalam mendukung pencapaian akademik yang optimal.

Pendekatan berbasis educational data mining telah menunjukkan efektivitas dalam memprediksi performa akademik mahasiswa. Model pembelajaran mesin mampu memprediksi nilai ujian akhir dengan tingkat akurasi 70-75%, menggunakan data nilai ujian tengah semester (Yağcı, 2022). Namun, faktor eksternal seperti durasi tidur, kesehatan mental, dan kebiasaan olahraga masih kurang diperhitungkan dalam model prediksi akademik. Integrasi data kesehatan mental dan kebiasaan hidup dalam analisis pendidikan dapat memberikan wawasan lebih mendalam mengenai pola keberhasilan akademik serta membantu institusi pendidikan dalam merancang strategi intervensi yang lebih efektif untuk meningkatkan kesejahteraan dan prestasi akademik.

**Referensi**: </br>
- Li, W., Chen, J., Li, M., Smith, A. P., & Fan, J. (2022). The effect of exercise on academic fatigue and sleep quality among university students. Frontiers in Psychology, 13. https://doi.org/10.3389/fpsyg.2022.1025280
- Teuber, M., Leyhr, D., & Sudeck, G. (2024). Physical activity improves stress load, recovery, and academic performance-related parameters among university students: a longitudinal study on daily level. BMC Public Health, 24(1). https://doi.org/10.1186/s12889-024-18082-z
- Xu, L., Yan, W., Hua, G., He, Z., Wu, C., & Hao, M. (2025). Effects of physical activity on sleep quality among university students: chain mediation between rumination and depression levels. BMC Psychiatry, 25(1). https://doi.org/10.1186/s12888-024-06450-3
- Yağcı, M. (2022). Educational data mining: prediction of students’ academic performance using machine learning algorithms. Smart Learning Environments, 9(1). https://doi.org/10.1186/s40561-022-00192-z


## Business Understanding
Analisis kinerja akademik mahasiswa bertujuan untuk memahami faktor-faktor utama yang memengaruhi pencapaian akademik. Studi menunjukkan bahwa kebiasaan hidup, seperti pola tidur, aktivitas fisik, dan kesehatan mental, memiliki dampak signifikan terhadap performa akademik (Xu et al., 2025). Dengan pendekatan berbasis data, pola keterkaitan antar variabel ini dan nilai ujian mahasiswa dapat ditemukan untuk meningkatkan prediksi akademik serta membantu dalam pembuatan kebijakan pendidikan yang lebih efektif.

## Problem Statements
- Pernyataan Masalah 1: Dari serangkaian atribut(fitur) yang ada, atribut(fitur) apa yang paling berpengaruh terhadap nilai ujian mahasiswa (exam score)?
- Pernyataan Masalah 2: Apa model terbaik yang dapat digunakan untuk memprediksi nilai ujian mahasiswa (exam score)?

## Goals
- Tujuan 1: Mengidentifikasi atribut(fitur) yang paling berkorelasi terhadap nilai ujian mahasiswa (exam score)
- Tujuan 2: Menemukan model terbaik berdasarkan akurasi tertinggi untuk memprediksi nilai ujian mahasiswa (exam score)


**Rubrik/Kriteria Tambahan**:
### Solution statements
- Membangun model baseline menggunakan Linear Regression
- Membangun model alternatif menggunakan Random Forest, Support Vector Machine (SVM), dan Gradient Boosting Regressor
- Mengukur performa model menggunakan MAE, MSE, dan R2 Score
- Memilih model terbaik berdasarkan nilai MAE dan MSE terendah serta R2 Score tertinggi

## Data Understanding
Dataset yang digunakan dalam proyek ini adalah "Student Habits vs Academic Performance", dapat diakses dan diunduh dari platform Kaggle melalui [tautan]: https://www.kaggle.com/datasets/jayaantanaath/student-habits-vs-academic-performance/croissant/download. Dataset ini berisi informasi mengenai berbagai kebiasaan belajar dan gaya hidup mahasiswa serta nilai ujian akhir mereka. Tujuan dari penggunaan dataset ini adalah untuk menganalisis potensi hubungan antara kebiasaan-kebiasaan tersebut dengan kinerja akademik mahasiswa.

Variabel-variabel (fitur) yang terdapat dalam dataset "Student Habits vs Academic Performance" adalah sebagai berikut:
- student_id: kode unik atau identifikasi untuk setiap mahasiswa dalam dataset
- age: usia mahasiswa dalam format bilangan bulat
- gender: menunjukkan jenis kelamin mahasiswa, yang dikategorikan sebagai female, male atau other
- study_hours_per_day:jumlah jam yang dihabiskan mahasiswa untuk belajar dalam sehari, dalam format bilangan desimal
- social_media_hours: jumlah jam yang dihabiskan mahasiswa untuk menggunakan media sosial dalam sehari, dalam format bilangan desimal
- netflix_hours: jumlah jam yang dihabiskan mahasiswa untuk menonton Netflix dalam sehari, dalam format bilangan desimal
- part_time_job: menunjukkan apakah mahasiswa memiliki pekerjaan paruh waktu (Yes/No)
- attendance_percentage: menyajikan persentase kehadiran mahasiswa di kelas, dalam format bilangan desimal
- sleep_hours: jumlah jam tidur mahasiswa dalam sehari, dalam format bilangan desimal
- diet_quality: mengkategorikan kualitas diet mahasiswa (Fair, Good, Poor). Variabel ini bersifat ordinal dan dapat dianalisis hubungannya dengan energi dan fungsi kognitif yang mendukung pembelajaran
- exercise_frequency: menunjukkan seberapa sering mahasiswa berolahraga dalam per minggu. Variabel ini bersifat numerik (interval) dan dapat menjadi indikator kesehatan fisik dan mental yang memengaruhi kinerja akademik
- parental_education_level: menyajikan tingkat pendidikan tertinggi orang tua mahasiswa (SMA, S1, S2). Variabel ini bersifat ordinal dan dapat menjadi indikator latar belakang sosio-ekonomi dan dukungan pendidikan di rumah
- internet_quality: Mengkategorikan kualitas koneksi internet yang dimiliki mahasiswa (Good, Average, Poor)
- mental_health_rating: penilaian subjektif mahasiswa terhadap kondisi kesehatan mental mereka dalam skala  1 hingga 10. Variabel ini bersifat numerik (interval) dan merupakan indikator kesejahteraan psikologis.
- extracurricular_participation: apakah mahasiswa berpartisipasi dalam kegiatan ekstrakurikuler (Yes/No)
- exam_score: nilai akhir ujian mahasiswa, dalam format bilangan desimal. Variabel ini bersifat numerik (rasio) dan menjadi variabel target utama yang akan dianalisis dalam kaitannya dengan variabel-variabel lainnya


**Rubrik/Kriteria Tambahan**
Melakukan Exploratory Data Analysis (EDA) secara bertahap:
1. Mengecek informasi pada dataset dengan fungsi `info()`\
   **Informasi yang dihasilkan:**
   - Terdapat 7 kolom bertipe object yaitu student_id, gender, part_time_job, diet_quality, parental_education_level, internet_quality dan extracurricular_participation
   - Terdapat 3 kolom bertipe integer yaitu age, exercise_frequency, dan mental_health_rating
   - Terdapat 6 kolom bertipe float54 yaitu study_hours_per_day, social_media_hours, netflix_hours, attendace_percentage, sleep_hours, dan exam_score
     
2. Mengecek deskripsi statistik dengan fungsi `describe()`\
   **Informasi yang dihasilkan:**
   - Study hours vs Entertainment (social media dan netflix hours)
     Rata-rata waktu belajar adalah 3,5 jam per hari tetapi waktu rata-rata bermain sosial media 2,5 jam dan netflix 1,82 jam. Apabila waktu bermain socmed dan netflix dijumlahkan maka lebih banyak waktu yang digunakan untuk hiburan daripada belajar
   - Sleep hours
     Rata-rata tidur 6,47 jam dengan standar deviasi 1,23 menyiratkan bahwa ada individu yang lebih sedikit atau lebih banyak tidur dari rata-rata sehingga bisa memengaruhi energi dan fokus saat belajar
   - Exercise frequency
     Olahraga rata-rata 3x dalam 1minggu, menunjukkan sebagian mahasiswa aktif berolahraga tetapi ada yang mungkin kurang memperhatikan kegiatan fisik
   - Attendace vs Exam Score
     Rata-rata kehadiran adalah 84,135 tetapi nilai ujian 69,60. Perlu ditelusuri alasan lain penyebab nilai ujian cenderung rendah
   - Mental health rating
     Rata-rata kesehatan mental mahasiswa adalah 5,44 dari 10 dengan standar deviasi 2,85 menunjukkan variasi yang cukup besar. Perlu ditelusuri lebih lanjut faktor eksternal lainnya (seperti pola hidup dan kebiasaan mahasiswa)

3. Mengecek dan menangani missing value dengan fungsi `isnull().sum()` serta data duplikat dengan fungsi `duplicated().sum()`
   **Informasi yang diperoleh:**
   - Terdapat 91 nilai kosong pada fitur kolom parental_education_level dan tidak ditemukan duplikasi data
   - Mengisi missing values dengan nilai kosong dalam fitur kolom parental_education_level karena merupakan fitur kategorikal sehingga missing values menjadi tidak terdapat pada seluruh kolom fitur

4. Mendeteksi outlier pada kolom fitur numerik
   **Informasi yang diperoleh:**
   Visualisasi:\
   
   
