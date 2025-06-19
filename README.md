# Image Classification of Disease in Guava Fruits

## Deskripsi Proyek
Proyek ini bertujuan untuk mengembangkan sistem klasifikasi penyakit pada buah jambu biji secara otomatis menggunakan citra digital. Dengan bantuan teknik **pengolahan citra** dan **machine learning**, model dilatih untuk mengenali tiga kelas:
- **Anthracnose**
- **Fruit Flies**
- **Healthy Guava**

Dataset citra diperoleh dari lapangan dan telah divalidasi oleh ahli patologi tanaman. Proyek ini merupakan bagian dari mata kuliah *Pengolahan Citra Digital* Semester Genap 2024/2025.

---

## Tujuan Proyek
- Mengklasifikasikan penyakit jambu biji menggunakan fitur tekstur dan warna dari citra buah.
- Membandingkan performa berbagai algoritma machine learning seperti **KNN**, **SVM**, **Random Forest**, dan **XGBoost**.
- Membangun aplikasi prediksi penyakit berbasis web menggunakan **Streamlit**.

---

## Dataset
- 📁 **Jumlah Citra**: 473 (setelah augmentasi: 3784)
- 🏷️ **Kelas**: `Anthracnose`, `Fruit Flies`, `Healthy Guava`
- 📸 **Ukuran Gambar**: 512x512 piksel, format RGB
- 🔗 [Guava Fruit Disease Dataset (Kaggle)](https://doi.org/10.17632/bkdkc4n835.1)

---

## Teknologi dan Tools
- Python, OpenCV
- Scikit-learn, NumPy, Matplotlib
- GLCM & Gabor Filter (untuk ekstraksi fitur)
- PCA (untuk reduksi dimensi)
- Streamlit (untuk deployment lokal)

---

## Metodologi
### 1. Preprocessing
- **Resize** → 256x256 px
- **Normalisasi Warna** → konversi RGB ke HSV
- **Denoising** → Gaussian Blur + Median Blur
- **Segmentasi** → Otsu Thresholding pada channel Value

### 2. Ekstraksi Fitur
- **GLCM**: Contrast, Dissimilarity, Homogeneity, ASM, Energy, Correlation
- **Gabor Filter**: Mengidentifikasi pola frekuensi dan orientasi tekstur

### 3. Reduksi Dimensi
- **PCA** (Principal Component Analysis): mengurangi kompleksitas data

### 4. Modeling
- **K-Nearest Neighbors (KNN)**: `k=30`, Euclidean distance
- **Support Vector Machine (SVM)**: Kernel RBF, C=5000
- **Random Forest**: 1000 pohon keputusan
- **XGBoost**: Gradient Boosted Trees

### 5. Evaluasi
- **Akurasi**
- **Precision, Recall, F1-Score**
- **Confusion Matrix**

---

## Hasil Evaluasi Model
| Model         | Akurasi | Catatan |
|---------------|---------|---------|
| KNN           | 66.2%   | Kesulitan membedakan `healthy` & `fruit_fly` |
| SVM (RBF)     | 78.9%   | Kinerja paling konsisten dan stabil |
| Random Forest | 69.0%   | Baik pada `anthracnose`, lemah di kelas sehat |
| XGBoost       | 69.0%   | Variatif, kesulitan pada `healthy_guava` |

---

## Deployment
- Model diimplementasikan sebagai aplikasi web menggunakan **Streamlit**
- Aplikasi memuat model `.joblib`, melakukan preprocessing otomatis sebelum prediksi
- Saat ini dijalankan secara lokal

---

## Insight Visualisasi PCA
- Distribusi kelas `fruit_fly` sangat terpisah
- `Healthy` dan `Anthracnose` saling tumpang tindih
- Terlihat kemungkinan adanya fitur yang mirip antar kelas

---

## Kontributor
| Nama | NIM |
|------|-----|
| Putri Manika Rukmamaya | 23031554091 |
| Nazula Sinta Wati       | 23031554105 |
| Monika Intan Puspitasari | 23031554189 |

---

## Link Terkait
- 📂 [Dataset](https://drive.google.com/drive/folders/1dB5fxWnvcTy51oZzhVfy8wBVnuoX8siX?usp=sharing)

