# Laporan Proyek Machine Learning - Dewi Rachmawati

## Domain Proyek: Pendidikan
Kinerja akademik mahasiswa merupakan indikator penting dalam mengevaluasi keberhasilan proses pembelajaran di lingkungan perguruan tinggi. Isu ini kompleks dan dipengaruhi oleh faktor gaya hidup dan akademis (Lin et al., 2021). Pola penggunaan _smartphone_ untuk hiburan seringkali dikaitkan dengan peningkatan kecemasan dan gangguan tidur yang dapat berdampak negatif pada prestasi belajar (Lin et al., 2021; Troll et al., 2020). Mahasiswa yang kurang mampu mengendalikan diri lebih mudah terganggu oleh gawai saat belajar (Troll et al., 2020). Oleh karena itu, intervensi yang mendorong penggunaan aplikasi bijak, pengembangan pengendalian diri, dan pengurangan kecemasan terkait ponsel menjadi penting.   

Kualitas tidur yang buruk umum terjadi di kalangan mahasiswa (Alotaibi et al., 2020)  dan berkaitan dengan penurunan kinerja akademik (Lin et al., 2021). Stres juga merupakan faktor signifikan (Alotaibi et al., 2020), di mana stres dan kurang tidur dapat menciptakan lingkaran masalah yang mengganggu semangat belajar dan kesehatan mental (Alotaibi et al., 2020). Kebiasaan makan yang tidak sehat juga berperan; melewatkan sarapan dan sering mengonsumsi makanan cepat saji berhubungan negatif dengan kinerja akademik (Reuter et al., 2020).   

Sejalan dengan itu, _Educational Data Mining_ (EDM) memanfaatkan machine learning untuk memprediksi hasil belajar. Algoritma seperti Random Forests, Support Vector Machines (SVM), dan Logistic Regression efektif dalam memprediksi kinerja siswa. Model machine learning ini memberikan wawasan tambahan untuk mengidentifikasi mahasiswa berisiko (Yağcı, 2022). Kombinasi pemahaman faktor gaya hidup dan analisis prediktif machine learning dapat mengoptimalkan dukungan terhadap keberhasilan akademik mahasiswa.

**Referensi**: </br>
- Alotaibi, A. D., Alosaimi, F. M., Alajlan, A. A., & Bin Abdulrahman, K. A. (2020). The relationship between sleep quality, stress, and academic performance among medical students. Journal of Family and Community Medicine, 27(1), 23-28. DOI: 10.4103/jfcm.JFCM_132_19 </br>
- Lin, Y., Liu, Y., Fan, W., Tuunainen, V. K., & Deng, S. (2021). Revisiting the relationship between smartphone use and academic performance: A large-scale study. Computers in Human Behavior, 122, DOI: https://doi.org/10.1016/j.chb.2021.106835 </br>
- Reuter, P. R., Forster, B. L., & Brister, S. R. (2020). The influence of eating habits on the academic performance of university students. Journal of American College Health. 1-7. DOI: https://doi.org/10.1080/07448481.2020.1715986 </br>
- Troll, E. S., Friese, M., & Loschelder, D. D. (2020). How students' self-control and smartphone-use explain their academic performance. Computers in Human Behavior. 117 (Preprint). DOI: https://doi.org/10.1016/j.chb.2020.106624 </br>
- Yağcı, M. (2022). Educational data mining: prediction of students’ academic performance using machine learning algorithms. Smart Learning Environments, 9(1), 1-19. DOI: https://doi.org/10.1186/s40561-022-00192-z

## Business Understanding
Dalam konteks analisis dan prediksi kinerja akademik, diperlukan pemahaman komprehensif tentang faktor-faktor yang memengaruhi hasil belajar mahasiswa dan potensi data mining untuk membantu analisis ini. Kinerja akademik dipengaruhi oleh berbagai elemen, termasuk kebiasaan gaya hidup seperti _screen time_, pola tidur, dan kebiasaan makan, serta analisis data siswa dapat mengungkapkan pola dan memungkinkan prediksi pencapaian akademik. Pemahaman ini penting untuk studi yang bertujuan mengidentifikasi siswa berisiko, mengoptimalkan lingkungan belajar, dan mengembangkan intervensi untuk mendukung keberhasilan siswa.

## Problem Statements
- Pernyataan Masalah 1: Dari serangkaian atribut(fitur) yang ada, atribut(fitur) apa yang paling berpengaruh terhadap nilai ujian mahasiswa (exam score)?
- Pernyataan Masalah 2: Apa model terbaik yang dapat digunakan untuk memprediksi nilai ujian mahasiswa (exam score)?

## Goals
- Tujuan 1: Mengidentifikasi atribut(fitur) yang paling berkorelasi terhadap nilai ujian mahasiswa (exam score)
- Tujuan 2: Menemukan model terbaik berdasarkan akurasi tertinggi untuk memprediksi nilai ujian mahasiswa (exam score)

**Rubrik/Kriteria Tambahan**:
### Solution statements
- Membangun model baseline menggunakan Linear Regression
- Membangun model alternatif menggunakan Random Forest dan Support Vector Machine (SVM)
- Mengukur performa model menggunakan MAE, MSE, dan R2 Score
- Memilih model terbaik berdasarkan nilai MAE dan MSE terendah serta R2 Score tertinggi
