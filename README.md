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

