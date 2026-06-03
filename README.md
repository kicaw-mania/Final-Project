# Final-Project
**Klasifikasi Penyakit Daun Jagung Menggunakan CNN dan Ensmable Classifier**

**1. Deskripsi Proyek**
Penelitian ini mengembangkan sistem klasifikasi otomatis penyakit daun jagung berbasis citra digital menggunakan MobileNetV2 sebagai feature extractor dan dua model ensemble classifier, yaitu Random Forest dan XGBoost. Penelitian ini bertujuan mendukung transformasi digital sektor pertanian dalam rangka mewujudkan smart agriculture dan ketahanan pangan nasional
Penyakit yang diklasifikasikan yaitu: Blight, Common Rust, Gray Leaf Spot, dan Healthy.

**2. Pre-Processing**
a. Resize & Penanganan RGBA
b. Split Dataset
c. Undersampling
d. CLAHE
e. Gaussian Blur 
f. Normalisasi

**3. Arsitektur Model**
a. Feature Extraction-MobileNetV2
Citra hasil preprocessing diekstrak menggunakan MobileNetV2 pre-trained ImageNet. Layer klasifikasi dilepas sehingga output berupa vektor fitur sebanyak 1.280 fitur per citra.
b. Classifier (Random Forest - XGBoost)
Dengan hasil evaluasi: 
-Accuracy Random Forest(93%)
-Accuaracy XGBoost (94%)
Dapat disimpulkan XGBoost menjadi model terbaik karena memiliki accuracy yang lebih unggul dibandingan Random Forest.

**4. Temuan Khusus**
1.**Undersampling setelah split** — dilakukan untuk menghindari data leakage pada data validasi dan uji.
2.**Perubahan BGR → RGB pada CLAHE** — mengubah cv2.COLOR_BGR2LAB menjadi cv2.COLOR_RGB2LAB berdampak pada penurunan akurasi Random Forest sebesar 1%.
3.**Inkonsistensi hasil akurasi** — diatasi dengan mengunci seluruh seed keacakan global pada angka 42.
4.**Indikasi overfitting ringan** — akurasi train (≈99,9%) vs test (≈93–94%), diatasi dengan hyperparameter tuning.

