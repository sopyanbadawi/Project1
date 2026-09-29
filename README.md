# Analisis Data: Philippine Cities Air Quality Index Data 2026

Proyek Analisis Data Eksploratif (EDA) untuk mata kuliah **Probabilitas dan Statistika (StatProb)** oleh **Kelompok 11**.

---

## Anggota Kelompok 11

| No | Nama | NRP |
| :---: | :--- | :---: |
| 1 | **Ahmad Sofyan Badawi** | `5027261065` |
| 2 | **Arif Budianto** | `5027261029` |
| 3 | **Nandana Reswara** | `5027261102` |

---

## Tentang Dataset

Dataset yang digunakan memuat data indeks kualitas udara (*Air Quality Index* - AQI) dan berbagai konsentrasi polutan di berbagai kota di Filipina untuk tahun 2026.

- **Sumber Dataset**: [Kaggle - Philippine Cities Air Quality Index Data 2026](https://www.kaggle.com/datasets/bwandowando/philippine-cities-air-quality-index-data-2026)

---

## Kamus Data / Deskripsi Variabel

| Kolom | Arti | Jenis Variabel | Skala Pengukuran | Satuan | Contoh Nilai |
| :--- | :--- | :--- | :--- | :---: | :--- |
| `components.co` | Konsentrasi gas Karbon Monoksida di udara | Kuantitatif Kontinu | Rasio | µg/m³ | 139.32, 218.42 |
| `components.pm2_5` | Konsentrasi partikel debu halus (ukuran < 2,5 mikrometer) | Kuantitatif Kontinu | Rasio | µg/m³ | 9.25, 11.45 |
| `components.pm10` | Konsentrasi partikel debu kasar (ukuran < 10 mikrometer) | Kuantitatif Kontinu | Rasio | µg/m³ | 16.91, 30.16 |
| `components.o3` | Konsentrasi gas Ozon di permukaan tanah | Kuantitatif Kontinu | Rasio | µg/m³ | 32.26, 81.92 |
| `city_name` | Nama kota lokasi sensor pengukuran kualitas udara berada | Kualitatif | Nominal | - | Alaminos, Bacolod |

---

## Pertanyaan Analisis

1. **Bagaimana perbandingan pemusatan dan penyebaran kadar polutan utama (CO, PM2.5, dan O3)?**
2. **Apakah terdapat lonjakan polusi ekstrem atau anomali pada pengukuran partikel kasar (PM10)?**
3. **Bagaimana pola hubungan antara konsentrasi debu halus (PM2.5) dan debu kasar (PM10) di udara?**
4. **Apakah distribusi letak sensor pengukuran didominasi oleh kota-kota tertentu?**

## Kesimpulan
**Jawaban Pertanyaan Analisis:**
1. **Perbandingan Pemusatan dan Penyebaran:** Karbon Monoksida (CO) memiliki kadar pemusatan (rata-rata 208,07 µg/m³) dan tingkat penyebaran (jangkauan 883,93 µg/m³) paling tinggi dibandingkan polutan lain. Ketiga polutan (CO, PM2.5, O3) memiliki sebaran data yang miring ke kanan (*positive skewness*), karena nilai rata-ratanya lebih besar dari nilai mediannya.
2. **Anomali PM10:** Ya, berdasarkan grafik *boxplot*, terdapat sangat banyak titik anomali (pencilan/*outliers*) yang berada jauh di atas batas kumis atas (nilai maksimal mencapai 169,63 µg/m³ sedangkan Q3 hanya 9,93 µg/m³). Hal ini membuktikan seringnya terjadi lonjakan polusi debu kasar secara ekstrem yang patut diwaspadai.
3. **Hubungan PM2.5 dan PM10:** Terdapat pola hubungan linear positif yang sangat kuat (korelasi nyaris sempurna di angka 0.98) antara debu halus (PM2.5) dan debu kasar (PM10). Kenaikan pada salah satu ukuran partikel tersebut akan selalu diikuti oleh kenaikan partikel lainnya secara proporsional.
4. **Distribusi Letak Sensor:** Distribusi tidak didominasi oleh segelintir kota. Sebaliknya, sensor pengukuran didistribusikan dengan tingkat keteraturan yang luar biasa, di mana 99 kota (dari total 139 kota) menyumbang jumlah baris data yang sama persis (yaitu 623 pengukuran untuk setiap kota).

**Temuan Paling Menarik:**
* **Kualitas Data Sempurna:** Dataset ini memiliki rekam data yang luar biasa bersih (0 *missing values*, 0 *duplicates*) dan konsistensi pengambilan sampel waktu yang sangat adil di 99 kota Filipina.
* **Kerentanan Lonjakan Polusi:** Mayoritas polutan udara memiliki distribusi miring ke kanan, menandakan kualitas udara rata-rata sebenarnya normal, namun sangat rentan terhadap insiden polusi ekstrem (seperti kebakaran atau kemacetan parah).
* **Korelasi Partikulat:** Pergerakan kadar debu halus (PM2.5) dan debu kasar (PM10) di udara ternyata sangat beriringan layaknya satu kesatuan.

**Keterbatasan Data:**
Data ini hanya berisi hasil tangkapan indeks kualitas gas secara mandiri, tanpa dilengkapi oleh data parameter cuaca atau iklim pendukung (seperti kecepatan angin, curah hujan, dan suhu) yang sebenarnya merupakan faktor penentu (*confounding variables*) utama terjadinya pergerakan polusi di udara.

**Ide Pertanyaan Lanjutan:**
Apakah jam-jam tertentu (misalnya jam sibuk berangkat dan pulang kerja) memiliki pengaruh signifikan terhadap lonjakan Karbon Monoksida (CO) di udara jika kita mengekstrak komponen jam/waktu dari kolom `datetime`?