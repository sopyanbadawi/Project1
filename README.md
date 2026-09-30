# Analisis Data: Philippine Cities Air Quality Index Data 2026

Proyek Analisis Data Eksploratif (EDA) untuk mata kuliah **Probabilitas dan Statistika (StatProb)** oleh **Kelompok 11**.

## Judul dan identitas kelompok

#### Judul
Analisis Pola Kualitas Udara dan Konsentrasi Polutan di Kota-Kota Filipina Tahun 2026

#### Anggota Kelompok 11

| No | Nama | NRP |
| :---: | :--- | :---: |
| 1 | **Ahmad Sofyan Badawi** | `5027261065` |
| 2 | **Arif Budianto** | `5027261029` |
| 3 | **Nandana Reswara** | `5027261102` |

#### Topik Yang Dipilih: SmartCity

---

## Latar belakang dan pertanyaan

#### Kenapa Kami Memilih Dataset ini
Polusi udara merupakan salah satu tantangan utama di wilayah perkotaan yang berdampak langsung pada kesehatan masyarakat. Dataset **Philippine Cities Air Quality Index Data 2026** ini sangat menarik untuk dieksplorasi karena menyediakan rekaman konsentrasi berbagai polutan secara mendetail dan berkala (interval jam). 

Melalui data ini, kita dapat membedah kondisi udara di berbagai kota secara nyata, melihat polutan apa yang paling mendominasi, serta memahami sebaran tingkat bahayanya sebagai langkah awal membangun pemodelan sistem *Smart City*.

#### Pertanyaan Analisis:
1. **Bagaimana perbandingan pemusatan dan penyebaran kadar polutan utama (CO, PM2.5, dan O3)?**
2. **Apakah terdapat lonjakan polusi ekstrem atau anomali pada pengukuran partikel kasar (PM10)?**
3. **Bagaimana pola hubungan antara konsentrasi debu halus (PM2.5) dan debu kasar (PM10) di udara?**
4. **Apakah distribusi letak sensor pengukuran didominasi oleh kota-kota tertentu?**

---

## Deskripsi Data dan Kamus Data

### Tentang Dataset
Dataset yang digunakan memuat data indeks kualitas udara (*Air Quality Index* - AQI) dan berbagai konsentrasi polutan di berbagai kota di Filipina untuk tahun 2026.

Data ini publish oleh [BwandoWando](BwandoWando), menurut keterangannya data ini diambil dengan scrapping website https://openweathermap.org menggunakan python dengan rentang waktu interval 1 jam sekali (1-hour intervals) untuk 138 kota besar di Filipina.

Lalu data ini masih diupdate sampai sekarang, yang artinya dataset ini diperbarui secara berkala oleh si Author 

**Sumber Dataset**: [Kaggle - Philippine Cities Air Quality Index Data 2026](https://www.kaggle.com/datasets/bwandowando/philippine-cities-air-quality-index-data-2026)

**Lisensi**: [CC0: Public Domain](https://creativecommons.org/publicdomain/zero/1.0/)

**Jumlah Baris**: 85496

**Jumlah Kolom**: 11

### Kamus Data / Deskripsi Variabel

| Kolom | Arti | Jenis Variabel | Skala Pengukuran | Satuan | Contoh Nilai |
| :--- | :--- | :--- | :--- | :---: | :--- |
| `datetime` | Waktu dan tanggal pengambilan data kualitas udara | Kuantitatif | Interval | - |  2026-09-01 00:00:07+08:00 |
| `main.aqi` | Indeks Kualitas Udara (Air Quality Index) | Kuantitatif | Ordinal | - | 3 |
| `components.co` | Konsentrasi gas Karbon Monoksida di udara | Kuantitatif Kontinu | Rasio | µg/m³ | 139.32, 218.42 |
| `components.no` | Konsentrasi Nitrogen Monoksida di udara | Kuantitatif Kontinu | Rasion | µg/m³ | 0.15 |
| `components.no2` | Konsentrasi Nitrogen Dioksida di udara | Kuantitatif Kontinu | Rasion | µg/m³ | 0.22 |
| `components.o3` | Konsentrasi gas Ozon di permukaan tanah | Kuantitatif Kontinu | Rasio | µg/m³ | 64.05 |
| `components.so2` | Konsentrasi Sulfur Dioksida di udara | Kuantitatif Kontinu | Rasio | µg/m³ | 0.21 |
| `components.pm2_5` | Konsentrasi partikel debu halus (ukuran < 2,5 mikrometer) | Kuantitatif Kontinu | Rasio | µg/m³ | 9.25, 11.45 |
| `components.pm10` | Konsentrasi partikel debu kasar (ukuran < 10 mikrometer) | Kuantitatif Kontinu | Rasio | µg/m³ | 16.91, 30.16 |
| `components.nh3` | Konsentrasi Amonia di udara | Kuantitatif Kontinu | Rasio | µg/m³ | 0.06 |
| `city_name` | Nama kota lokasi sensor pengukuran kualitas udara berada | Kualitatif | Nominal | - | Alaminos, Bacolod |

---

## Kesimpulan
**Jawaban Pertanyaan Analisis:**
1. **Perbandingan Pemusatan dan Penyebaran:** 

    Karbon Monoksida (CO) memiliki kadar pemusatan (rata-rata 208,07 µg/m³) dan tingkat penyebaran (jangkauan 883,93 µg/m³) paling tinggi dibandingkan polutan lain. Ketiga polutan (CO, PM2.5, O3) memiliki sebaran data yang miring ke kanan (*positive skewness*), karena nilai rata-ratanya lebih besar dari nilai mediannya.
2. **Anomali PM10:** 

    Ya, berdasarkan grafik *boxplot*, terdapat sangat banyak titik anomali (pencilan/*outliers*) yang berada jauh di atas batas kumis atas (nilai maksimal mencapai 169,63 µg/m³ sedangkan Q3 hanya 9,93 µg/m³). Hal ini membuktikan seringnya terjadi lonjakan polusi debu kasar secara ekstrem yang patut diwaspadai.
3. **Hubungan PM2.5 dan PM10:** 

    Terdapat pola hubungan linear positif yang sangat kuat (korelasi nyaris sempurna di angka 0.98) antara debu halus (PM2.5) dan debu kasar (PM10). Kenaikan pada salah satu ukuran partikel tersebut akan selalu diikuti oleh kenaikan partikel lainnya secara proporsional.
4. **Distribusi Letak Sensor:** 

    Distribusi tidak didominasi oleh segelintir kota. Sebaliknya, sensor pengukuran didistribusikan dengan tingkat keteraturan yang luar biasa, di mana 99 kota (dari total 139 kota) menyumbang jumlah baris data yang sama persis (yaitu 623 pengukuran untuk setiap kota).

**Temuan Paling Menarik:**
* **Kualitas Data Sempurna:** 
    
    Dataset ini memiliki rekam data yang luar biasa bersih (0 *missing values*, 0 *duplicates*) dan konsistensi pengambilan sampel waktu yang sangat adil di 99 kota Filipina.
* **Kerentanan Lonjakan Polusi:** 

    Mayoritas polutan udara memiliki distribusi miring ke kanan, menandakan kualitas udara rata-rata sebenarnya normal, namun sangat rentan terhadap insiden polusi ekstrem (seperti kebakaran atau kemacetan parah).
* **Korelasi Partikulat:** 

    Pergerakan kadar debu halus (PM2.5) dan debu kasar (PM10) di udara ternyata sangat beriringan layaknya satu kesatuan.

---

## Cara Menjalankan Notebook

### Requirement
Pastikan hal-hal ini sudah terinstall di laptop anda:
- [Python](https://www.python.org/downloads/)
- [Miniconda](https://www.anaconda.com/docs/getting-started/installation)
- [Git](https://git-scm.com/install/)

### Langkah-langkah

1. **Git Clone Repository ini**


    Buka **Anaconda Prompt**, lalu jalankan perintah berikut untuk meng-clone repository ini:

    ```bash
    git clone https://github.com/sopyanbadawi/Project1.git
    ```
    Atau, Anda dapat mengunduh file ZIP dari halaman utama GitHub dan mengekstraknya.

2. **Masuk ke Direktori Project**

    ```bash
    cd ./Project1
    ```

3. **Buat dan Aktifkan Virtual Environment**

    ```bash
    conda create -n <nama-environment> python=3.11 -y
    conda activate <nama-environment>
    ```

4. **Install Dependensi yang dibutuhkan**

    ```bash
    conda install -c conda-forge jupyter pandas matplotlib seaborn -y
    ```

5. **Jalankan Jupyter Notebook**

    ```bash
    jupyter notebook
    ```