# 🎬 ANALISIS KOMPREHENSIF TERHADAP FILM-FILM DI IMDB
## OVERVIEW
Dataset IMDB Movies merupakan kumpulan data terkait film-film yang tercatat dalam website IMDB, yang dikenal luas sebagai sumber referensi utama dalam industri film. Dataset ini mencakup informasi seperti judul film, tahun release, genre, skor, artist, serta berbagai metadata lainnya. Melalui analisis terhadap dataset ini, diharapkan dapat diperoleh pemahaman yang lebih mendalam mengenai karakteristik dari film-film yang mendapat apresiasi tinggi dari audiens. Ini memberikan kesempatan bagi peneliti untuk menggali tren serta pola yang berlaku di dalam industri film secara lebih ekstensif.
## OBJECTIVE
1. Studi komparatif berdasarkan pendapatan film dari berbagai negara
2. Menganalisis genre film untuk meningkatkan pendapatan
3. Pengaruh anggaran terhadap pendapatan dan kesuksesan sebuah film
4. Memprediksi kesuksesan sebuah film
## DATA PREPROCESSING
MISSING VALUE <br>
Terdapat 1,24% nilai NaN dan saya memilih untuk drop data tersebut untuk menjaga kualitas analisis<br><br>

DUPLICATES<br>
Tidak ada duplicate dalam dataset ini<br><br>

INACCURACIES<br>
Dalam dataset, terdapat kesalahan penulisan dimana film-film yang seharusnya bukan berasal dari Australia, tetapi tercatat sebagai produksi Australia. Untuk ini saya lakukan penyesuaian nilai berdasarkan riset dan Bahasa yang digunakan.<br><br>

FEATURES ENGINEERING<br>
Budget dan revenue saya rubah kedalam nilai jutaan. Agar dapat lebih mudah dipahami. Saya juga membuat kolom profit, dan kolom success. Untuk melihat keuntungan dan kesuksesan sebuah film.<br><br>

## EXPLORATORY DATA ANALYSIS
![image](https://github.com/ahfifahrul/analisis_terhadap_film_IMDB/assets/153416228/b68310ca-3bb6-4c61-aff0-9d0ca8d0dad8)<br>
Ada hubungan yang cukup kuat antara budget dengan revenue
![image](https://github.com/ahfifahrul/analisis_terhadap_film_IMDB/assets/153416228/ea4e506c-a6d9-4c9e-a55a-cf461e8bc80b)<br>
Amerika Serikat, Britania Raya, Korea Selatan adalah negara-negara dengan revenue tertinggi
![image](https://github.com/ahfifahrul/analisis_terhadap_film_IMDB/assets/153416228/151e8fe7-352a-48ee-bc34-23ec9689f782)<br>
Documentary, TV Movies, Animasi adalah genre dengan rata-rata revenue tertinggi
![image](https://github.com/ahfifahrul/analisis_terhadap_film_IMDB/assets/153416228/656ae081-33b7-47d4-8266-45cc9333f105)<br>
Documentary, TV Movies, Animasi adalah genre dengan rata-rata profit tertinggi
![image](https://github.com/ahfifahrul/analisis_terhadap_film_IMDB/assets/153416228/2bb9c512-1b25-434c-bfe5-3fb3c311a005)<br>
Bulan Mei, bulan Maret, bulan Juli, bulan November adalah bulan dengan rata-rata revenue tertinggi

## MECHINE LEARNING MODEL
PREDICTOR VARIABLE :<br>
released_year<br>
released_month<br>
score<br>
genre<br>
orig_lang<br>
budget<br>
country<br><br>
TARGET VARIABLE :<br>
success<br><br>
### MODEL EVALUATION
![image](https://github.com/ahfifahrul/analisis_terhadap_film_IMDB/assets/153416228/7f0a5ac5-c9bb-42b0-a59d-b1a3d90dc88a)
Precision: Rasio prediksi positif yang benar terhadap total prediksi positif.<br>

Recall: Rasio prediksi positif yang benar terhadap total positif sebenarnya.<br>

F1-Score: Rata-rata dari precision dan recall. Model ini memiliki F1-score 0.84 & 0.83, menunjukkan keseimbangan yang baik antara precision dan recall.<br>

Accuracy: Persentase prediksi yang benar dari semua prediksi. Model ini memiliki akurasi 0.84, menunjukkan bahwa sekitar 84% dari prediksi yang dibuat oleh model adalah benar.<br>

AUC-ROC score: score sebesar 0.8881 (88,81%), ini menunjukkan bahwa model cukup efektif dalam membedakan antara kedua kelas dan memiliki tingkat keakuratan yang tinggi dalam prediksi.<br>
![image](https://github.com/ahfifahrul/analisis_terhadap_film_IMDB/assets/153416228/0d8ad846-75ae-4757-9615-f204b1593732)
True Negatives (TN): 842 jumlah kasus yang model prediksi sebagai negatif dan memang benar negatif.<br>

False Positives (FP): 127 jumlah kasus yang model prediksi sebagai positif tapi sebenarnya negatif.<br>

False Negatives (FN): 190 jumlah kasus yang model prediksi sebagai negatif tapi sebenarnya positif.<br>

True Positives (TP): 789 jumlah kasus yang model prediksi sebagai positif dan memang benar positif.<br>

## CONCLUSION
Dataset IMDB yang digunakan dalam penelitian ini terdiri dari 10.178 entri dan 12 variabel. Untuk melakukan analisis, saya membuat kolom 'Profit' yang merupakan selisih antara 'revenue' dan 'budget'. Nilai 'budget' dan 'revenue' disederhanakan kedalam nilai jutaan untuk agar mudah dipahami. Dataset ini mengandung 1,24% missing values, yang kemudian dieliminasi untuk menjaga kualitas analisis. Data dibagi menjadi dua subset: 80% sebagai data pelatihan dan 20% sebagai data pengujian.<br>
Dalam melakukan klasifikasi dengan mechine learning, saya menggunakan teknik label encoder dan one-hot encoding untuk mengkonversi fitur non-numerik menjadi format numerik. Untuk melakukan prediksi saya menggunakan Model Random Forest Classifier, hasilnya adalah F1 Score sebesar 0.84 dan 0.83. Hal ini menunjukkan bahwa model memiliki keseimbangan yang baik antara presisi dan sensitivitas. Selain itu, model menunjukkan accuracy sebesar 0.84, yang menandakan bahwa sekitar 84% prediksi yang dibuat oleh model adalah akurat. AUC-ROC score 0.8881 (88,81%), ini menunjukkan bahwa model cukup efektif dalam membedakan antara kedua kelas dan memiliki tingkat keakuratan yang tinggi dalam prediksi.<br>

## RECOMENDATION
Berdasarkan hasil penelitian, kami merekomendasikan beberapa strategi untuk produser dalam meningkatkan potensi pendapatan dari produksi film:<br>
1. Alokasi Anggaran yang Strategis: Disarankan agar produser mengalokasikan anggaran produksi secara strategis. Analisis menunjukkan bahwa terdapat korelasi positif antara besarnya anggaran dengan pendapatan yang dihasilkan. Investasi yang lebih besar dalam produksi cenderung menghasilkan pendapatan yang lebih tinggi.<br>
2. Pemilihan Genre yang Tepat: Fokus pada genre film seperti dokumenter, Movie TV, dan animasi yang terbukti memiliki potensi pendapatan yang lebih tinggi. Penelitian menunjukkan bahwa genre-genre tersebut menarik minat penonton secara signifikan, yang berpotensi meningkatkan pendapatan.<br>
3. Penargetan Pasar yang Efektif: Penting bagi produser untuk menargetkan pasar yang tepat. Negara-negara seperti Amerika Serikat, Britania Raya, dan Korea Selatan teridentifikasi memiliki potensi pendapatan yang signifikan. Membuat film yang bertemakan negara-negara tersebut dapat secara substansial meningkatkan pendapatan.<br>
4. Penjadwalan Rilis yang Optimal: Memilih waktu rilis yang tepat juga dapat mempengaruhi pendapatan. Bulan Mei, Maret, dan November tercatat memiliki rata-rata pendapatan tertinggi. Menjadwalkan rilis film pada bulan-bulan tersebut dapat memberikan keuntungan tambahan.<br>
Rekomendasi ini diharapkan dapat membantu produser dalam merencanakan dan mengimplementasikan strategi produksi yang lebih efektif untuk meningkatkan pendapatan film.<br>
🎬🎬🎬🎬🎬🎬🎬🎬🎬🎬🎬🎬🎬
