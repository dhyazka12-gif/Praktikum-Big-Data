# Antigravity System Rules — Praktikum Big Data

## Project Overview
Repository ini menyimpan modul, lembar praktikum, latihan mandiri, tugas, dan dataset untuk mata kuliah **Praktikum Big Data** (Teknologi Informasi — Universitas Tidar).

## ⚠️ Critical Rule: Menggunakan `uv` (Bukan Conda)
Modul praktikum asli dari kampus menggunakan referensi Anaconda/Conda (`conda activate bigdata`, dll). Namun lingkungan di mesin ini dikonfigurasi menggunakan **`uv` dan Python virtual environment (`/home/azka/bigdata`)**.

### 1. Mapping Perintah Conda ke uv / Native Python
| Tindakan | Modul Asli (Conda) | Yang Digunakan di Sini (uv / Linux) |
|---|---|---|
| Aktivasi env | `conda activate bigdata` | `source /home/azka/bigdata/bin/activate` |
| Install package | `conda install <pkg>` | `uv pip install <pkg>` atau `/home/azka/bigdata/bin/python -m pip install <pkg>` |
| Jalankan Jupyter | `jupyter notebook` / `jupyter lab` | `/home/azka/bigdata/bin/jupyter lab` (atau `uv run jupyter lab`) |
| Cek package | `conda list` | `uv pip list` |

*Catatan: Jangan pernah menyarankan perintah conda.*

### 2. Konfigurasi Jupyter Kernel & PySpark
- **Kernel Jupyter**: Seluruh notebook harus menggunakan kernel **`Python (bigdata)`** (`name: bigdata`).
- **Path Interpreter**: `/home/azka/bigdata/bin/python` (Python 3.11).
- **Environment Variables PySpark**:
  - `PYSPARK_PYTHON=/home/azka/bigdata/bin/python`
  - `PYSPARK_DRIVER_PYTHON=/home/azka/bigdata/bin/python`
  *(PENTING: Tanpa ini, Spark worker akan memanggil python sistem 3.12 sehingga terjadi error `PYTHON_VERSION_MISMATCH`).*

### 3. Layanan Hadoop (HDFS)
- Sebelum mengeksekusi cell notebook yang mengakses `hdfs://localhost:9000`:
  - Periksa apakah Hadoop aktif: `jps` (pastikan ada NameNode, DataNode, ResourceManager, NodeManager, SecondaryNameNode).
  - Jika belum aktif:
    ```bash
    start-dfs.sh
    start-yarn.sh
    ```
  - Mematikan Hadoop setelah praktikum selesai:
    ```bash
    stop-yarn.sh
    stop-dfs.sh
    ```

### 4. Struktur Direktori Bersih
- Setiap pertemuan berada di folder masing-masing: `pertemuan_1`, `pertemuan_2`, `pertemuan_3`, `pertemuan_4`, `pertemuan_5`.
- Folder `src/praktikum_bigdata` telah dihapus demi kesederhanaan dan keteraturan.
- Dataset disimpan di dalam folder pertemuan yang menggunakannya.
