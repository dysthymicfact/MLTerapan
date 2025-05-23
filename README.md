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
Dataset yang digunakan dalam proyek ini adalah "Student Habits vs Academic Performance", dapat diakses dan diunduh dari platform Kaggle melalui [tautan](https://www.kaggle.com/datasets/jayaantanaath/student-habits-vs-academic-performance/croissant/download). Dataset ini berisi informasi mengenai berbagai kebiasaan belajar dan gaya hidup mahasiswa serta nilai ujian akhir mereka. Tujuan dari penggunaan dataset ini adalah untuk menganalisis potensi hubungan antara kebiasaan-kebiasaan tersebut dengan kinerja akademik mahasiswa.

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

 b. Fitur Numerikal
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
 a. Fitur Kategorikal (menggunakan `catplot`) 
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
     Untuk fitur extracurricular_participation, tidak ada perbedaan signifikan dalam nilai ujian (exam_score) antara mahasiswa yang mengikuti ekstrakurikuler dan yang tidak. Peristiwa ini menunjukkan bahwa partisipasi dalam kegiatan tambahan di luar akademik (ekstrakurikuler) mungkin bukan faktor utama yang memengaruhi performa akademik \

b. Fitur Numerikal (menggunakan `pairplot` dan `heatmap`) \
     Visualisasi: \
     ![alt text](https://github.com/dysthymicfact/MLTerapan/blob/main/images/corr%20matrix.png?raw=true) \
     Informasi yang diperoleh: \
    - Study hours memiliki korelasi sangat kuat (0.83) dengan exam score, menunjukkan bahwa semakin lama mahasiswa menghabiskan waktu untuk belajar, semakin tinggi nilai ujian yang mereka peroleh. Dengan hubungan yang hampir mendekati 1, variabel ini menjadi prediktor utama dalam menentukan performa akademik, mengindikasikan bahwa alokasi waktu belajar yang cukup dan efektif berkontribusi langsung terhadap pencapaian akademik yang lebih baik \
    - Sleep hours memiliki korelasi positif lemah (0.12) dengan exam score, menunjukkan bahwa durasi tidur yang lebih lama memiliki sedikit hubungan dengan peningkatan performa akademik, tetapi tidak dalam skala yang signifikan. Meskipun pola tidur yang cukup bisa membantu dalam fokus dan pemulihan mental, data ini mengindikasikan bahwa jumlah jam tidur bukan faktor utama yang secara langsung menentukan keberhasilan ujian mahasiswa \
    - Exercise frequency memiliki korelasi positif lemah (0.16) dengan exam score, yang menunjukkan bahwa frekuensi olahraga mungkin memiliki sedikit efek positif terhadap performa ujian, tetapi bukan faktor utama yang mendorong keberhasilan akademik. Bisa jadi aktivitas fisik membantu dalam keseimbangan mental dan fisik mahasiswa, meningkatkan daya tahan dan fokus belajar, tetapi kontribusinya tetap kecil dibandingkan dengan waktu yang dialokasikan untuk belajar secara langsung \
    - Mental health rating memiliki korelasi moderat (0.32) dengan exam score, yang berarti bahwa semakin baik kesehatan mental mahasiswa, semakin besar kemungkinan mereka mendapatkan nilai ujian yang lebih tinggi. Ini mengindikasikan bahwa kesejahteraan psikologis memiliki peran yang lebih signifikan dibandingkan pola tidur atau frekuensi olahraga, di mana mahasiswa yang lebih sehat secara mental mungkin memiliki strategi coping yang lebih baik, manajemen stres yang lebih efektif, dan motivasi akademik yang lebih tinggi \
    
## Data Preparation
Tahap ini dilakukan untuk mempersiapkan data supaya siap untuk proses pemodelan. Adapun beberapa tahapan persiapan data, yaitu:
1. Seleksi fitur \
   Pada bagian ini, fitur student_id, age, dan attendance_percentage di drop karena memiliki korelasi yang rendah terhadap fitur target nilai ujian (exam_score)
2. Encoding fitur kategori \
   Bagian ini dilakukan karena model regresi membutuhkan input numerik. Oleh karena itu, fitur kategori bertipe object perlu dikonversi ke bentuk numerik agar model dapat memahami data dengan baik. Encoding dilakukan dalam dua metode berikut:\
   1). Label Encoding
    - Mengonversi kategori menjadi integer (0, 1, 2, ... n) berdasarkan urutan yang logis 
    - Digunakan untuk parental_education_level dan internet_quality, karena kategori ini memiliki tingkat berjenjang yang bisa direpresentasikan dengan angka \
   2). One-Hot Encoding
    - Mengubah setiap kategori menjadi kolom biner terpisah untuk fitur yang tidak memiliki urutan logis 
    - Digunakan untuk gender, part_time_job, diet_quality, dan extracurricular_participation, karena kategori dalam fitur ini bersifat nominal dan tidak memiliki hubungan berjenjang antar nilai 
    - Parameter `drop_first=True` digunakan agar menghindari dummy variable trap, sehingga hanya satu kolom yang dibuat untuk setiap variabel biner 
3. Dataset Splitting \
   Target utama adalah fitur exam_score, yang akan digunakan untuk mengukur akurasi prediksi kategori kelas prestasi terbaik. Oleh karena itu, fitur ini akan dipisahkan dari data utama dan disimpan dalam variabel baru. Dataset dibagi menjadi data training (80%) untuk melatih model dan data testing (20%) untuk menguji performa model menggunakan data yang belum dilatih. Pembagian dilakukan dengan train_test_split dari scikit-learn, memastikan distribusi data tetap representatif
4. Feature Scaling (Standardisasi) \
   Pada bagian ini, digunakan `StandardScaler` terhadap data yang telab di split sebelumnya. Hasilnya distribusi angka rentang 1,0,-1. Hal ini dilakukan agar algoritma tidak terpengaruh oleh perbedaan skala antar fitur


## Modelling  
Tahap ini mencakup pengembangan model *machine learning* untuk memprediksi performa akademik mahasiswa melalui fitur **exam_score**. Model yang digunakan meliputi **Linear Regression, Random Forest Regressor, SVM Regressor, dan Gradient Boosting Regressor**. Evaluasi dilakukan untuk menentukan model dengan hasil prediksi terbaik berdasarkan metrik performa.  

### **1. Linear Regression**  
Model regresi dasar yang mencoba menemukan hubungan linear antara fitur dan target.  

- **Parameter yang digunakan:** Default dari `LinearRegression()`  
- **Kelebihan:**  
  - Sederhana dan cepat untuk dilatih  
  - Mudah diinterpretasikan  
- **Kekurangan:**  
  - Tidak mampu menangkap hubungan non-linear  
  - Sensitif terhadap outlier  

### **2. Random Forest Regressor**  
Metode *ensemble* berbasis pohon keputusan yang menggabungkan banyak pohon untuk meningkatkan akurasi dan mengurangi *overfitting*.  

- **Parameter yang digunakan:**  
  - `n_estimators=100`: jumlah pohon dalam hutan  
  - `random_state=42`: menjaga konsistensi hasil  
- **Kelebihan:**  
  - Mampu menangani data kompleks dan hubungan non-linear  
  - Tidak mudah *overfitting* karena menggunakan banyak pohon  
- **Kekurangan:**  
  - Model cukup kompleks dan sulit diinterpretasikan  
  - Waktu pelatihan lebih lama dibandingkan Linear Regression  

### **3. SVM Regressor**  
Metode regresi berbasis **Support Vector Machine (SVM)** yang berusaha menemukan hiperplane optimal untuk prediksi nilai ujian.  

- **Parameter yang digunakan:**  
  - `kernel='rbf'`: menggunakan **Radial Basis Function (RBF)** untuk menangkap pola non-linear  
  - `C=1.0`: parameter regulasi untuk mengontrol kompleksitas model  
  - `epsilon=0.1`: batas toleransi untuk kesalahan prediksi  
- **Kelebihan:**  
  - Dapat menangkap hubungan non-linear dengan kernel seperti **RBF**  
  - Cocok untuk data dengan **outlier minimal**  
- **Kekurangan:**  
  - Waktu komputasi lebih tinggi dibandingkan model regresi lainnya  
  - Sulit untuk diinterpretasikan dalam analisis bisnis  

### **4. Gradient Boosting Regressor**  
Metode *boosting* yang membangun model secara bertahap, di mana setiap model baru berusaha memperbaiki kesalahan dari model sebelumnya.  

- **Parameter yang digunakan:**  
  - `n_estimators=100`: jumlah tahap boosting  
  - `max_depth=3`: kedalaman maksimum setiap pohon  
  - `learning_rate=0.1`: kontribusi setiap pohon terhadap model akhir  
  - `random_state=42`: menjaga konsistensi hasil  
- **Kelebihan:**  
  - Akurasi prediksi tinggi  
  - Dapat menangani hubungan kompleks dalam data  
- **Kekurangan:**  
  - Waktu pelatihan lebih lama dibandingkan Linear Regression  
  - Rentan terhadap *overfitting*  

### **Pemilihan Model Terbaik**  
Berdasarkan hasil evaluasi pada data uji, model dengan performa terbaik dipilih berdasarkan **MAE terendah, MSE terendah, dan R² tertinggi**.  

Jika dibandingkan, **Linear Regression menunjukkan performa terbaik** dengan **R² paling tinggi** dalam menjelaskan variabilitas nilai ujian.  

### **Kesimpulan**  
**Linear Regression dipilih sebagai model terbaik karena:**  
- Memberikan hasil prediksi yang paling akurat dalam konteks dataset yang digunakan.  
- Memiliki interpretasi yang lebih sederhana, memudahkan analisis hubungan antar fitur.  
- Performa lebih stabil dibandingkan **Random Forest, SVM Regressor, dan Gradient Boosting** dalam menangkap pola data tanpa kompleksitas tambahan.


## Evaluasi Model  

Untuk menilai performa model regresi dalam memprediksi nilai ujian mahasiswa, digunakan tiga metrik utama: **Mean Absolute Error (MAE), Mean Squared Error (MSE), dan R-Squared (R²)**.  

1. **MAE** mengukur rata-rata selisih absolut antara nilai aktual dan hasil prediksi, menunjukkan seberapa jauh estimasi model dari kenyataan. Sebagai contoh, jika model memperkirakan nilai ujian **82**, tetapi nilai sebenarnya **79**, maka selisihnya **3**, yang akan berkontribusi dalam perhitungan MAE. Metrik ini memberikan gambaran langsung tentang akurasi prediksi tanpa memperhitungkan outlier secara berlebihan.  

2. **MSE** menghitung rata-rata kuadrat dari selisih antara prediksi dan nilai aktual, dengan penalti lebih tinggi untuk kesalahan besar. Misalnya, jika selisih prediksi adalah **3**, maka setelah dikuadratkan menjadi **9**, mencerminkan dampak kesalahan yang lebih besar dalam evaluasi model. MSE berguna untuk menyoroti model yang sering membuat kesalahan ekstrem, sehingga lebih sensitif dibandingkan MAE.  

3. **R-Squared (R²)** menilai sejauh mana model dapat menjelaskan variasi dalam data. Dalam dataset ini, **Linear Regression mencapai R² sebesar 0.89**, menunjukkan bahwa model berhasil menjelaskan **89% variabilitas dalam nilai ujian** berdasarkan fitur gaya hidup mahasiswa. Nilai ini menandakan bahwa hubungan antara variabel input dan output cukup linear, membuat model ini lebih unggul dibandingkan metode lain seperti **Random Forest, SVM Regressor, dan Gradient Boosting Regressor**, yang tidak menunjukkan peningkatan performa signifikan.  

### **Hasil Performa Model**  
Berikut adalah perbandingan hasil evaluasi dari empat algoritma regresi yang digunakan dalam analisis nilai ujian mahasiswa:

| **Model**                  | **MAE**  | **MSE**  | **R²**  |
|----------------------------|---------|---------|---------|
| Linear Regression          | **4.36** | **28.30** | **0.89** |
| Random Forest Regressor    | **4.99** | **38.35** | **0.85** |
| SVM Regressor              | **5.43** | **50.70** | **0.80** |
| Gradient Boosting Regressor | **4.77** | **32.67** | **0.87** |

Berdasarkan hasil evaluasi ini, dapat disimpulkan bahwa **Linear Regression menunjukkan performa terbaik** karena:
- Memiliki **nilai R² tertinggi (0.89)**, menunjukkan bahwa model dapat menjelaskan 89% variabilitas nilai ujian mahasiswa  
- **Nilai MSE lebih rendah**, yang mencerminkan konsistensi prediksi model  
- **MAE cukup kecil**, artinya rata-rata kesalahan prediksinya lebih rendah dibandingkan model lain  

## Evaluasi Deskriptif  

Proyek ini berfokus pada **prediksi performa akademik mahasiswa** untuk mengidentifikasi faktor-faktor yang paling berpengaruh terhadap nilai ujian mereka. Dengan pemanfaatan *machine learning*, analisis ini memungkinkan pengambilan keputusan yang lebih akurat dan efisien dalam memahami keterkaitan antara kebiasaan mahasiswa dengan hasil akademik mereka. Model yang digunakan diharapkan dapat meningkatkan prediksi performa akademik serta memberikan wawasan tentang pola belajar yang efektif berdasarkan fitur gaya hidup mahasiswa.  

### **Evaluasi terhadap Problem Statement**  

#### **Fitur apa yang paling berpengaruh terhadap nilai ujian mahasiswa (exam score)?**  
Masalah ini telah dianalisis melalui **eksplorasi data dan feature importance** dari model regresi yang digunakan. Fitur-fitur yang berkontribusi signifikan terhadap nilai ujian mahasiswa akan dibahas lebih lanjut di bagian **Evaluasi Goals**, memberikan wawasan tentang faktor utama yang mempengaruhi keberhasilan akademik.  

#### **Apa model terbaik yang dapat digunakan untuk memprediksi nilai ujian mahasiswa (exam score)?**  
Proses ini telah diselesaikan dengan membangun empat model regresi: **Linear Regression (baseline), Random Forest Regressor, SVM Regressor, dan Gradient Boosting Regressor**. Model ini membantu dalam menghasilkan prediksi yang lebih akurat terkait nilai ujian mahasiswa. Hasil evaluasi menunjukkan bahwa **Linear Regression memberikan performa terbaik**, dengan R² paling tinggi, menjadikannya model unggulan dalam analisis ini.  

### **Evaluasi terhadap Goals**  

#### **Mengetahui fitur yang paling berkorelasi dengan nilai ujian**  
Tujuan ini telah tercapai melalui **analisis korelasi dan feature importance**, memberikan pemahaman yang lebih mendalam tentang faktor-faktor yang paling berpengaruh terhadap performa akademik. Fitur **study_hours, mental_health_rating, dan diet_quality** terbukti memiliki dampak yang paling signifikan terhadap hasil ujian.  

#### **Membuat model *machine learning* untuk memprediksi nilai ujian**  
Model **Linear Regression, Random Forest Regressor, SVM Regressor, dan Gradient Boosting Regressor** telah dibandingkan berdasarkan **MAE, MSE, dan R²** untuk menentukan performa terbaik. Berdasarkan evaluasi, **Linear Regression** menunjukkan hasil terbaik dengan R² tertinggi sebesar **0.89**, menjadikannya model yang paling efektif dalam menangkap pola hubungan antar fitur.  

### **Evaluasi terhadap Solution Statements**  

- **Membangun model baseline dengan Linear Regression**  
Model baseline telah dikembangkan sebagai tolok ukur awal untuk menilai performa model lainnya.  

- **Membangun model alternatif dengan Random Forest, SVM, dan Gradient Boosting**  
Ketiga model ini berhasil dikembangkan sebagai perbandingan terhadap Linear Regression, dengan hasil yang menunjukkan bahwa hubungan antar fitur lebih bersifat linear.  

- **Mengukur performa model menggunakan MAE, MSE, dan R² Score**  
Evaluasi dilakukan dengan tiga metrik utama untuk memastikan hasil yang objektif dan menyeluruh.  

- **Memilih model terbaik berdasarkan evaluasi metrik**  
Model **Linear Regression dipilih sebagai model final** karena memiliki **MAE dan MSE lebih rendah serta R² tertinggi**, menjadikannya pilihan terbaik untuk analisis akademik mahasiswa.  

### **Kesimpulan Evaluasi**  

Dengan menggunakan model yang telah dikembangkan, khususnya **Linear Regression**, diharapkan analisis ini dapat memberikan manfaat dalam meningkatkan pemahaman tentang performa akademik mahasiswa, termasuk:  

- **Prediksi nilai ujian yang akurat**, membantu dalam perencanaan strategi belajar yang lebih efektif  
- **Identifikasi faktor utama dalam keberhasilan akademik**, memungkinkan rekomendasi intervensi yang lebih tepat sasaran  
- **Optimasi pola belajar dan keseimbangan gaya hidup mahasiswa**, berkontribusi pada peningkatan produktivitas akademik  
- **Pemanfaatan teknologi dalam analisis pendidikan**, mendukung pengambilan keputusan berbasis data untuk optimalisasi performa mahasiswa 

