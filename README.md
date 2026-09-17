# Praktikum Big Data

Repository ini berisi seluruh modul materi, lembar kerja praktikum (Jupyter Notebook), latihan mandiri, tugas, dan dataset untuk mata kuliah **Praktikum Big Data** (Program Studi Teknologi Informasi — Universitas Tidar).

---

## 📁 Struktur Direktori

```text
praktikum-bigdata/
├── pertemuan_1/                        # Teori Dasar & Arsitektur Big Data
│   └── README.md
├── pertemuan_2/                        # Python Data Environment & Pandas Dasar
│   ├── Modul_Praktikum_BigData_Pertemuan2.ipynb
│   └── df_nilai.ipynb
├── pertemuan_3/                        # Apache Hadoop & HDFS Command Line
│   ├── Modul_Praktikum_BigData_Pertemuan3.ipynb
│   ├── praktikum3.ipynb
│   ├── latihan mandiri praktikum3.ipynb
│   ├── Tugas3_0065_Aghnia Azka.ipynb
│   ├── biodata.txt
│   ├── contoh_lokal.txt
│   ├── hasil_unduh_dari_hdfs.txt
│   ├── transaksi_magelang.csv
│   ├── transaksi_semarang.csv
│   ├── transaksi_yogyakarta.csv
│   ├── data_gabungan_bersih.csv
│   └── ringkasan_kota_kategori.csv
├── pertemuan_4/                        # Apache Spark & PySpark DataFrame Dasar
│   ├── Modul_Praktikum_BigData_Pertemuan4.ipynb
│   ├── Pertemuan4.ipynb
│   ├── Latihan Mandiri Praktikum 4.ipynb
│   ├── pertemuan_4_dataset_tugas.ipynb
│   ├── data_transaksi_ecommerce.csv
│   └── transaksi_september_2026.csv
├── pertemuan_5/                        # PySpark DataFrame Lanjutan: Join, Window Function & SQL
│   ├── Modul_Praktikum_BigData_Pertemuan5.ipynb
│   ├── praktikum5.ipynb
│   └── Latihan mandiri5.ipynb
├── drafts/                             # File catatan / draft eksperimen
│   ├── Untitled.ipynb
│   └── Untitled1.ipynb
├── GEMINI.md                           # System rules & panduan AI assistant
├── SYSTEM_NOTES.md                     # Catatan konfigurasi environment uv & Spark
├── pyproject.toml                      # Konfigurasi dependensi project (uv)
└── .gitignore                          # Daftar filter git ignore
```

---

## ⚙️ Lingkungan Kerja & Cara Menjalankan

### 1. Python Virtual Environment (`uv` / `bigdata`)
Project ini dikonfigurasi menggunakan **`uv`** dan environment Python 3.11 (`/home/azka/bigdata`), bukan Anaconda/Conda.

Untuk mengaktifkan environment di terminal:
```bash
source /home/azka/bigdata/bin/activate
```

Untuk menjalankan Jupyter Lab:
```bash
/home/azka/bigdata/bin/jupyter lab
```
> **Penting**: Pastikan kernel notebook yang dipilih di Jupyter adalah **`Python (bigdata)`**.

### 2. Apache Hadoop (HDFS)
Beberapa praktikum (Pertemuan 3, 4, dan 5) berinteraksi langsung dengan HDFS (`hdfs://localhost:9000`).

Sebelum menjalankan notebook yang mengakses HDFS:
```bash
# Menyalakan Hadoop
start-dfs.sh
start-yarn.sh

# Memeriksa status service (pastikan 5 proses Java aktif)
jps

# Mematikan service setelah selesai
stop-yarn.sh
stop-dfs.sh
```

---

## 🚀 Panduan Push ke GitHub

Jika belum menginisialisasi repository Git:
```bash
# 1. Pastikan git terinstall (jika belum: sudo apt update && sudo apt install git -y)
git --version

# 2. Inisialisasi git di folder praktikum-bigdata
cd /home/azka/praktikum-bigdata
git init

# 3. Konfigurasi identitas (jika belum)
git config --global user.name "Aghnia Azka"
git config --global user.email "email_anda@example.com"

# 4. Tambahkan file dan commit perdana
git add .
git commit -m "feat: rapikan struktur per pertemuan dan lengkapi modul & latihan"

# 5. Hubungkan ke repository GitHub Anda
git branch -M main
git remote add origin https://github.com/<username-github>/praktikum-bigdata.git

# 6. Push ke GitHub
git push -u origin main
```
