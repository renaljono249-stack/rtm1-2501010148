# Akuisisi Data Cuaca Wisata Labuan Bajo

## 1. Deskripsi Proyek

Proyek ini merupakan tugas mata kuliah Akuisisi dan Manajemen Data. Tujuan proyek ini adalah mengumpulkan data cuaca di kawasan wisata Labuan Bajo, Nusa Tenggara Timur, menggunakan Open-Meteo Forecast API.

Data cuaca yang diperoleh digunakan untuk memberikan informasi mengenai temperatur dan kondisi cuaca di kawasan wisata Labuan Bajo sebagai bahan pembelajaran dan analisis data.

## 2. Sumber Data

| Keterangan | Informasi |
|---|---|
| Nama sumber | Open-Meteo Forecast API |
| Penerbit | Open-Meteo |
| URL API | https://api.open-meteo.com/v1/forecast |
| Website | https://open-meteo.com/ |
| Lokasi | Labuan Bajo, Nusa Tenggara Timur |
| Latitude |-8,4964|
| Longitude | 119,8877 |
| Jenis data | Prakiraan cuaca |
| Format data | CSV  |

Atribusi sumber: Weather data by Open-Meteo.com.

## 3. Tanggal dan Jam Akses

Data diperoleh melalui Open-Meteo Forecast API.

- Tanggal akses: [15-11-2026]
- Jam akses: [13:05]
- Zona waktu: WITA (UTC+8).

## 4. Metode Akuisisi Data

Metode yang digunakan adalah API (Application Programming Interface).

Endpoint API:

`https://api.open-meteo.com/v1/forecast`

Parameter yang digunakan:

| Parameter | Keterangan |
|---|---|
| latitude | -8,4964|
| longitude |119,8877 |
| current | temperature_2m |
| hourly | temperature_2m |
| daily | weather_code |

Proses pengambilan data dilakukan menggunakan Python dengan bantuan beberapa library:

- pandas
- requests
- openmeteo_requests
- requests_cache
- retry_requests

Data yang diperoleh kemudian disimpan dalam format CSV untuk memudahkan pengolahan dan analisis.

## 5. Batasan Etika

Dalam proses akuisisi data, beberapa ketentuan etika yang diterapkan adalah:

1. Ketentuan API: Menggunakan API resmi Open-Meteo dan mengikuti ketentuan penggunaannya.
2. Lisensi: Data menggunakan lisensi Creative Commons Attribution 4.0 International (CC BY 4.0).
3. Atribusi: Mencantumkan Open-Meteo sebagai sumber data.
4. Batas permintaan: Tidak melakukan permintaan API secara berlebihan. Batas Free API adalah kurang dari 10.000 panggilan per hari, 5.000 per jam, dan 600 per menit.
5. Jeda permintaan: Menggunakan mekanisme retry dan jeda bertahap apabila terjadi kegagalan permintaan.
6. Data pribadi: Tidak mengambil informasi pribadi wisatawan maupun identitas pengguna.
7. Data yang tidak diambil: Tidak mengambil data identitas penduduk, nomor telepon, alamat pribadi, maupun informasi sensitif lainnya.

Karena menggunakan API resmi, pemeriksaan robots.txt tidak diperlukan seperti pada metode web scraping.

Dokumentasi:
- https://open-meteo.com/en/terms
- https://open-meteo.com/en/license

## 6. Penjelasan Kolom Dataset 

Dataset berisi informasi cuaca di kawasan wisata Labuan Bajo.

| Kolom | Penjelasan |
|---|---|
| time | Waktu pengamatan atau prakiraan cuaca |
| temperature_2m | Temperatur udara pada ketinggian 2 meter dalam derajat Celsius |
| weather_code | Kode kondisi cuaca berdasarkan standar WMO |

Catatan: Nama kolom mengikuti variabel yang digunakan dalam API. Sesuaikan dengan nama header sebenarnya pada file CSV.

## 7. Struktur Folder Proyek

```text
rtm1-2501010148/
│
├── data/
│   └── raw/
│       └── open-meteo-labuan-bajo.csv
│
├── notebooks/
│   └── akuisisi_cuaca_labuan_bajo.ipynb
│
└── README.md
```

## 8. Cara Menjalankan Ulang Notebook

Langkah-langkah menjalankan kembali notebook:

1. Download atau clone repository dari GitHub.
2. Pastikan Python atau Google Colab tersedia.
3. Buka folder `notebooks`.
4. Jalankan file `akuisisi_cuaca_labuan_bajo.ipynb`.
5. Instal library yang diperlukan:

```bash
pip install pandas requests openmeteo-requests requests-cache retry-requests
```

6. Jalankan seluruh cell notebook secara berurutan dari awal sampai akhir.
7. Pastikan proses pengambilan data berhasil.
8. Periksa hasil dataset pada folder `data/raw/`.

## 9. Kesimpulan

Melalui proyek ini, proses akuisisi data cuaca di kawasan wisata Labuan Bajo dilakukan menggunakan Open-Meteo Forecast API.

Data yang diperoleh dapat digunakan untuk pembelajaran mengenai pengumpulan, penyimpanan, dan pengolahan data menggunakan Python.

Sumber data: Open-Meteo  
https://open-meteo.com/
