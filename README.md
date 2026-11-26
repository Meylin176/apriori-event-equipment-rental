# Analisis Aturan Asosiasi Penyewaan Peralatan Acara Menggunakan Algoritma Apriori

## Deskripsi
Repository ini berisi implementasi Association Rule Mining (ARM) menggunakan algoritma Apriori untuk menganalisis data transaksi penyewaan peralatan acara.

Penelitian ini bertujuan untuk mengidentifikasi pola asosiasi antarperalatan yang disewa pelanggan serta menganalisis konsistensi aturan asosiasi pada periode bulanan.

## Dataset
Dataset diperoleh dari Green Flower, sebuah usaha penyewaan peralatan acara yang berlokasi di Murung Raya, Kalimantan Tengah, Indonesia.

Dataset mencakup transaksi periode September 2025 hingga Agustus 2026, dengan rincian:
- 190 transaksi
- 337 catatan item
- 9 kategori peralatan

Kategori peralatan meliputi:
- Tenda 4x6
- Tenda 8x6
- Tenda 3x3
- Meja dan Taplak
- Kursi
- Sarung Kursi
- Sound System
- Bunga
- Tanaman

Dataset yang disediakan dalam repository telah dianonimkan untuk melindungi informasi bisnis.

## Metodologi
Tahapan penelitian meliputi:

1. Preprocessing data
2. Exploratory Data Analysis (EDA)
3. Online Analytical Processing (OLAP)
4. Association Rule Mining global menggunakan dua konfigurasi parameter
5. Association Rule Mining bulanan
6. Analisis Rule Stability
7. Pemilihan aturan asosiasi

Algoritma Apriori digunakan untuk mengidentifikasi frequent itemsets dan menghasilkan aturan asosiasi.

### ARM Global
Penelitian menggunakan dua konfigurasi parameter:

| Konfigurasi | Minimum Support | Minimum Confidence |
|---|---:|---:|
| K1 | 0,05 | 0,50 |
| K2 | 0,02 | 0,30 |

### ARM Bulanan
Analisis aturan asosiasi bulanan menggunakan minimum support count sebanyak 3 transaksi dan minimum confidence sebesar 0,30.

Pendekatan ini digunakan untuk mengurangi pembentukan aturan asosiasi dari kombinasi item yang hanya muncul satu kali pada dataset transaksi bulanan yang berukuran kecil.

### Rule Stability
Rule stability dianalisis dengan mengamati kemunculan aturan asosiasi global pada 12 bulan periode pengamatan.

Persentase stabilitas dihitung berdasarkan jumlah bulan ketika suatu aturan memenuhi kriteria pembentukan aturan bulanan dibandingkan dengan total periode pengamatan.

## Struktur Repository

```text
apriori-event-equipment-rental/
├── README.md
├── requirements.txt
├── .gitignore
├── data/
│   └── dataset_anonymized.csv
├── notebooks/
│   └── PENERAPAN_ARM_KONFIGURASI.ipynb
└── results/
    ├── global_rules.csv
    ├── monthly_rules.csv
    └── rule_stability.csv
```

## Cara Menjalankan

### 1. Clone repository

```bash
git clone https://github.com/Meylin176/apriori-event-equipment-rental.git
cd apriori-event-equipment-rental
```

Ganti `USERNAME` dengan username GitHub pemilik repository.

### 2. Instal library yang diperlukan

```bash
pip install -r requirements.txt
```

### 3. Jalankan notebook

Buka notebook menggunakan Google Colab atau Jupyter Notebook:

`notebooks/PENERAPAN_ARM_KONFIGURASI.ipynb`

Pastikan dataset anonim tersedia di folder `data/` sebelum menjalankan notebook.

## Hasil Analisis

Hasil analisis disediakan dalam folder `results/`:

- `global_rules.csv`: Aturan asosiasi global yang dihasilkan dari dua konfigurasi parameter.
- `monthly_rules.csv`: Aturan asosiasi yang dihasilkan pada setiap periode bulanan.
- `rule_stability.csv`: Ringkasan kemunculan dan stabilitas aturan asosiasi antarbulan.

Hasil analisis dapat direproduksi dengan menjalankan notebook menggunakan dataset dan library yang disediakan.

## Reproduksibilitas

Repository ini menyediakan dataset anonim, notebook analisis, daftar library, dan hasil analisis untuk mendukung reproduksibilitas penelitian.

## Ketersediaan Data

Dataset transaksi yang telah dianonimkan disediakan dalam folder `data/` untuk keperluan reproduksibilitas penelitian.

## Lisensi

Repository ini ditujukan untuk keperluan akademik dan penelitian.
