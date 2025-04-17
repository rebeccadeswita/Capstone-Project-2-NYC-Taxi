# 🚕 Capstone Project 2 – Strategi Optimalisasi Pendapatan Taksi Hijau New York City Berdasarkan Zona dan Waktu

## 📘 Latar Belakang

Pengemudi taksi di New York City memiliki tantangan besar dalam mengoptimalkan pendapatan harian mereka karena berbagai faktor seperti:
1. Krisis finansial yang dipicu oleh fluktuasi harga lisensi taksi (medali) dan beban utang pengemudi
2. Persaingan ketat dengan layanan transportasi berbasis aplikasi daring seperti Uber dan Lyft
3. Penerapan congestion pricing yang berpotensi menurunkan jumlah penumpang dan pendapatan pengemudi

Melalui proyek ini, dilakukan analisa dari dataset perjalanan taksi yang disediakan oleh NYC Taxi and Limousine Commission (TLC) untuk menggali waktu dan zona terbaik bagi pengemudi taksi dalam meningkatkan pendapatan, baik melalui tarif maupun tip dari pelanggan.

---

## 🎯 Tujuan Proyek

Proyek ini memiliki 4 tujuan utama:

1. Mengidentifikasi pola waktu dan lokasi (zona) yang secara konsisten menghasilkan pendapatan tertinggi bagi pengemudi 
2. Mengukur efisiensi pendapatan pengemudi berdasarkan metrik seperti pendapatan per menit
3. Menganalisa tren pendapatan terhadap faktor waktu seperti hari dalam seminggu dan jam operasional
4. Menyusun rekomendasi strategis berbasis data agar pengemudi dapat meningkatkan penghasilan secara signifikan


---

## 📁 Dataset yang Digunakan

| Nama File                        | Deskripsi |
|----------------------------------|-----------|
| `NYC_TLC_Trip_Record.csv`        | Dataset utama berisi catatan perjalanan taksi |
| `taxi_zone_lookup.csv`           | Dataset referensi yang memetakan `LocationID` ke zona dan borough di NYC |

---

## 🧰 Peralatan & Teknologi

- **Bahasa Pemrograman:** Python 3.x
- **Platform:** Jupyter Notebook
- **Library yang digunakan:**
  - `pandas` – manipulasi data
  - `numpy` – komputasi numerik
  - `matplotlib` & `seaborn` – visualisasi data
  - `scipy.stats` – uji statistik inferensial

---

## 🧪 Tahapan Proyek

### 1. Pengolahan Data
- Pemahaman Data (Data Understanding)
  a. Mengeksplorasi struktur data: dimensi, tipe data, deskripsi variabel
  b. Menampilkan sampel data dan statistik ringkas

- Persiapan Data (Data Preparation)
  a. Mengidentifikasi data anomali (durasi trip negatif, tarif nol, dll)
  b. Mengidentifikasi data kosong
  c. Mengidentifikasi data berulang
  b. Mengidentifikasi pencilan, khususnya dengan nilai yang sangat ekstrim

- Pembersihan Data (Data Cleaning)
  a. Menangani anomali (durasi trip negatif, tarif nol, dll)
  b. Menghapus data kosong yang tidak signifikan pada analisa
  c. Menangani data berulang 
  b. Menangani pencilan, khususnya dengan nilai yang sangat ekstrim
  
- Rekayasa Fitur (Feature Engineering)
  a. Menambahkan kolom turunan yang dibutuhkan untuk analisa, seperti tanggal, jam, dan nama hari penjemputan & pengantaran
  b. Dataset digabung dengan data referensi zona untuk mendapatkan nama zona dan borough lokasi
  c. Dibuat fitur trip_duration_min (durasi perjalanan dalam menit)
  d. Dibuat fitur fare_per_minute untuk mengukur efisiensi pendapatan per perjalanan

### 2. Analisa Data (Exploratory Data Analysis/EDA)
- Distribusi durasi dan tarif perjalanan
- Sebaran zona penjemputan dan pengantaran terbanyak
- Rata-rata pendapatan per menit per zona dan jam
- Rata-rata jumlah tip berdasarkan hari dan jam
- Visualisasi heatmap untuk efisiensi pendapatan

### 5. Statistik Inferensial
- Uji T: Apakah terdapat perbedaan signifikan pendapatan per menit saat akhir pekan dengan hari biasa
- Uji ANOVA: Apakah terdapat perbedaan signifikan pendapatan per perjalanan antar hari dalam seminggu
- Interpretasi hasil uji statistik dan signifikansinya

---

## 📈 Kesimpulan

1. Zona seperti Saint Albans, Randalls Island, dan Eastchester menawarkan pendapatan per menit hingga $6.36 USD, sekitar 5x lebih tinggi dari rata-rata  ($1.27 USD).
2. Zona seperti East Harlem North unggul dari sisi jumlah trip (12.037), dan Sunset Park East mencatat tip tertinggi sebesar $12.44 USD/perjalanan, jauh di atas rata-rata $2.11 USD.
3. Jam pagi (06:00–09:00) dan malam (22:00–01:00) terbukti menghasilkan pendapatan per menit tertinggi, mencapai $1.56 USD.
4. Pendapatan per perjalanan juga lebih tinggi di akhir pekan, dengan Sabtu dan Minggu masing-masing menghasilkan $17.80 USD dan $17.40 USD/perjalanan dibanding hari biasa rata-rata $14.80 USD.
5. Perjalanan berdurasi pendek (<10 menit) cenderung menghasilkan pendapatan per menit yang lebih tinggi.
6. 25% perjalanan tidak menghasilkan tip, namun perjalanan dengan pendapatan per menit tinggi lebih sering mendapat tip di atas rata-rata.

---

## 💡 Rekomendasi

1. Pengemudi taksi sebaiknya memprioritaskan zona efisien (pendapatan/min tinggi) dan zona loyal (tip tinggi) di awal atau akhir hari, dan mengisi waktu di zona sibuk untuk volume stabil. Misalnya kombinasi zona efisien (Saint Albans), zona loyal (Sunset Park East), dan zona sibuk (East Harlem North).
2. Secara harian, pengemudi taksi dapat menerapkan strategi seperti mulai dari zona dengan efisiensi tertinggi, lanjut ke zona volume tinggi saat transisi, dan tutup kembali di zona premium.
3. Fokuskan jam kerja pada pagi dan malam, terutama saat akhir pekan, karena terbukti secara statistik signifikan memberikan pendapatan lebih tinggi (p-value < 0.05 dari uji T dan ANOVA).
4. Tingkatkan kualitas pelayanan (ramah, bersih, efisien) di zona strategis seperti Sunset Park East untuk peluang tip yang maksimal.

---

## 📂 Struktur Folder

Capstone-Project-2/ ├── data/ │ ├── NYC_TLC_Trip_Record.csv │ ├── taxi_zone_lookup.csv │ ├── notebooks/ │ └── Capstone_Project_2_draft.ipynb │ ├── figures/ │ └── [grafik visualisasi analisis] │ ├── README.md └── requirements.txt

---

## 🧑‍💻 Penulis

- **Nama:** Rebecca Deswita 
- **Program:** Data Science & Machine Learning
- **Instansi:** Purwadhika Technology School 
- **Tahun:** 2025  

---

## 🔖 Catatan Tambahan

- Dataset bersifat historis dan memiliki keterbatasan seperti tidak adanya informasi cuaca atau kondisi lalu lintas.
- Proyek ini dapat dikembangkan lebih lanjut ke model prediksi zona terbaik berbasis waktu menggunakan machine learning.

