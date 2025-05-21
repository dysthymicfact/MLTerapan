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
   - Study hours vs Entertainment (social media dan netflix hours) \
     Rata-rata waktu belajar adalah 3,5 jam per hari tetapi waktu rata-rata bermain sosial media 2,5 jam dan netflix 1,82 jam. Apabila waktu bermain socmed dan netflix dijumlahkan maka lebih banyak waktu yang digunakan untuk hiburan daripada belajar
   - Sleep hours \
     Rata-rata tidur 6,47 jam dengan standar deviasi 1,23 menyiratkan bahwa ada individu yang lebih sedikit atau lebih banyak tidur dari rata-rata sehingga bisa memengaruhi energi dan fokus saat belajar
   - Exercise frequency \
     Olahraga rata-rata 3x dalam 1minggu, menunjukkan sebagian mahasiswa aktif berolahraga tetapi ada yang mungkin kurang memperhatikan kegiatan fisik
   - Attendace vs Exam Score \
     Rata-rata kehadiran adalah 84,135 tetapi nilai ujian 69,60. Perlu ditelusuri alasan lain penyebab nilai ujian cenderung rendah
   - Mental health rating \
     Rata-rata kesehatan mental mahasiswa adalah 5,44 dari 10 dengan standar deviasi 2,85 menunjukkan variasi yang cukup besar. Perlu ditelusuri lebih lanjut faktor eksternal lainnya (seperti pola hidup dan kebiasaan mahasiswa)

3. Mengecek dan menangani missing value dengan fungsi `isnull().sum()` serta data duplikat dengan fungsi `duplicated().sum()`
   **Informasi yang diperoleh:**
   - Terdapat 91 nilai kosong pada fitur kolom parental_education_level dan tidak ditemukan duplikasi data
   - Mengisi missing values dengan nilai kosong dalam fitur kolom parental_education_level karena merupakan fitur kategorikal sehingga missing values menjadi tidak terdapat pada seluruh kolom fitur

4. Mendeteksi outlier pada kolom fitur numerik </br>
   Visualisasi: </br>
   ![alt text](https://github.com/dysthymicfact/MLTerapan/blob/main/images/pict1.png?raw=true)
    **Informasi yang diperoleh:** </br>
    Hanya sedikit data outlier yang ditemukan pada kolom fitur numerik yaitu pada study_hours_per_day, social_media_hours, netflix_hours, attendance_percentage dan exam_score. Outlier ini dibiarkan karena dapat membantu model belajar pola yang lebih umum tanpa dipengaruhi oleh data ekstrem yang mungkin tidak merepresentasikan populasi sebenarnya

5. Melakukan univariate analysis terhadap masing-masing fitur dengan `countplot` dan `histogram` </br>
   **Informasi yang dihasilkan:** </br>
   a. Fitur Kategorikal 
   - Grafik fitur gender menunjukkan bahwa persentase perempuan hampir imbang dengan laki-laki yakni 48,1% (481 sampel) dan 47,7% (477 sampel), sedangkan sisanya adalah lainnya sebesar 4,2% (42 sampel) \
     Visualisasi: \
     ![alt text](https://github.com/dysthymicfact/MLTerapan/blob/main/images/gender.png?raw=true)
   - Grafik fitur part_time_job menunjukkan bahwa terdapat mahasiswa yang bekerja part time sebanyak 215 mahasiswa, sementara mayoritas tidak bekerja part time sebanyak 785 mahasiswa \
     Visualisasi: \
     ![alt text](https://github.com/dysthymicfact/MLTerapan/blob/main/images/partTime.png?raw=true)
   - Grafik fitur diet_quality menunjukkan bahwa kebanyakan mahasiswa menjalani diet berkategori seimbang (Fair=437 sampel), diikuti diet berkategori baik (Good=378 sampel), dan sisanya tidak menjalani diet (185 sampel). Ini menyiratkan bahwa mahasiswa mayoritas memperhatikan pola makan gizi seimbang untuk menjaga kesehatan tubuh \
     Visualisasi: \
     ![alt text](https://github.com/dysthymicfact/MLTerapan/blob/main/images/diet.png?raw=true)
   - Grafik fitur parental_education_level menunjukkan bahwa latar belakang pendidikan orang tua mahasiswa mayoritas adalah High School atau lulusan SMA (48,3%) dan Bachelor atau lulusan Sarjana (35%). Sisanya berlatar belakang pendidikan Master atau lulusan Magister (16,7%) \
     Visualisasi: \
     ![alt text](https://github.com/dysthymicfact/MLTerapan/blob/main/images/parentEdu.png?raw=true)
   - Grafik internet_quality menunjukkan bahwa mayoritas mahasiswa sudah memiliki kualitas internet yang baik karena persentase kategori Good adalah 44,7% diikuti Average adalah 39,1%. Sisanya masih memiliki kualitas internet yang buruk (16,2%). Ini menyiratkan bahwa mayoritas mahasiswa sudah tidak memiliki kendala akses internet dalam mengikuti pembelajaran daring atau pengerjaan tugas online \
     Visualisasi: \
     ![alt text](https://github.com/dysthymicfact/MLTerapan/blob/main/images/internet.png?raw=true)
   - Grafik extracurricular_participation menunjukkan bahwa kebanyakan mahasiswa tidak aktif mengikuti kegiatan ekstrakurikuler sebagai kegiatan di luar ruang lingkup akademik (No=68,2%; Yes=31,8%). Ini menyiratkan bahwa semestinya mahasiswa tidak mengalami kendala belajar karena terlalu sibuk mengikuti kegiatan ekstrakurikuler \
     Visualisasi: \
     ![alt text](https://github.com/dysthymicfact/MLTerapan/blob/main/images/ekskul.png?raw=true) 

 b. Fitur Numerik
  - Rentang usia mahasiswa adalah 17 hingga 24 tahun, dengan puncak usia adalah 20 tahun
  - Sebagian besar mahasiswa belajar sekitar 2–4 jam per hari, dengan puncak di 3 jam
  - Rata-rata waktu yang dihabiskan di media sosial sekitar 2–4 jam, sementara Netflix berkisar antara 0–3 jam, dengan puncak di 0 jam
  - Mayoritas mahasiswa memiliki tingkat kehadiran tinggi, berkisar antara 80–100%, dengan puncak di 100%
  - Sebagian besar mahasiswa tidur antara 6–8 jam, dengan puncak di sekitar 6-7 jam, mencerminkan pola tidur yang ideal
  - Variasi dalam kebiasaan olahraga, dengan puncak di 1, 3, dan 6 kali per minggu, menunjukkan bahwa sebagian mahasiswa cukup aktif berolahraga
  - Rating kesehatan mental tersebar cukup merata, dengan beberapa puncak di 1, 3, 4, 6, dan 8, mengindikasikan variabilitas kondisi psikologis mahasiswa
  - Sebagian besar mahasiswa mendapatkan nilai ujian antara 60–80, dengan puncak di 100, menunjukkan adanya kelompok mahasiswa dengan performa akademik sangat tinggi \
    Visualisasi: \
    ![alt text](https://github.com/dysthymicfact/MLTerapan/blob/main/images/numericfeatures.png?raw=true) 

6. Melakukan multivariate analysis untuk menilai relasi antar fitur terhadap fitur target (exam_score) \
 a. Fitur Kategorikal (menggunakan catplot) 
   - Fitur gender \
    Visualisasi: \
    ![alt text](https://github.com/dysthymicfact/MLTerapan/blob/main/images/multianalisis.png?raw=true) \
    Informasi yang diperoleh: \
    Tidak ada perbedaan signifikan dalam rata-rata nilai ujian terhadap gender (Female, Male, dan Other) karena hampir seluruh gender memiliki rata-rata nilai ujian mendekati 70. Perbedaan kecil ini menunjukkan bahwa gender bukanlah faktor yang menentukan performa akademik (exam_score) 
   - Fitur part_time_job \
     Visualisasi: \
     ![alt text](https://github.com/dysthymicfact/MLTerapan/blob/main/images/multianalisis1.png?raw=true) \
     Informasi yang diperoleh: \
     Meskipun terdapat perbedaan pada kategori fitur part_time_job, gap antara kedua kategori (Yes/No) tidak terlampau besar sehingga bekerja paruh waktu tidak secara langsung menyebabkan nilai ujian menjadi turun drastis. Fenomena ini menunjukkan bahwa beberapa siswa mampu mengelola waktu dengan baik antara bekerja dan belajar sehingga tetap dapat mempertahankan performa akademik (exam_score)
   - Fitur diet_quality \
     Visualisasi: \
     ![alt text](https://github.com/dysthymicfact/MLTerapan/blob/main/images/multianalisis2.png?raw=true) \
     Informasi yang diperoleh: \
     Fitur diet_quality memiliki korelasi dengan performa akademik (exam_score), tetapi pola makan yang baik (Good) tidak selalu menghasilkan nilai ujian tertinggi. Pola makan yang seimbang dan fleksibel (Fair) cenderung lebih optimal dibandingkan yang terlalu ketat atau buruk (Poor)
   - Fitur parental_education_level \
     Visualisasi: \
     ![alt text](https://github.com/dysthymicfact/MLTerapan/blob/main/images/multianalisis3.png?raw=true) \
     Informasi yang diperoleh: \
     Pada fitur parental_education_level, Master memiliki rata-rata exam score paling rendah dibandingkan High School dan Bachelor. Fenomena ini menunjukkan bahwa tingkat pendidikan orang tua tidak selalu berbanding lurus dengan performa akademik anak (exam_score)
   - Fitur internet_quality \
     Visualisasi: \
     ![alt text](https://github.com/dysthymicfact/MLTerapan/blob/main/images/multianalisis4.png?raw=true) \
     Informasi yang diperoleh: \
     Pada fitur internet_quality, rata-rata nilai ujian (exam_score) tidak memiliki perbedaan signifikan berdasarkan kualitas internet (internet_quality), karena semua kategori —Average, Poor, dan Good — memiliki nilai ujian yang hampir sama, sekitar 70. Hal ini menunjukkan bahwa dalam dataset ini, internet quality tampaknya bukan faktor utama yang memengaruhi performa akademik
   - fitur extracurricular_participation \
     Visualisasi: \
     ![alt text](https://github.com/dysthymicfact/MLTerapan/blob/main/images/multianalisis5.png?raw=true) \
     Informasi yang diperoleh: \
     Untuk fitur extracurricular_participation, tidak ada perbedaan signifikan dalam nilai ujian (exam_score) antara mahasiswa yang mengikuti ekstrakurikuler dan yang tidak. Peristiwa ini menunjukkan bahwa partisipasi dalam kegiatan tambahan di luar akademik (ekstrakurikuler) mungkin bukan faktor utama yang memengaruhi performa akademik
