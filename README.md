# Modern Machine Learning Project Template

Template Cookiecutter ini dirancang untuk mempercepat inisialisasi proyek Machine Learning dengan struktur yang terstandarisasi dan menggunakan perangkat Python modern untuk efisiensi pengembangan.

## Fitur Utama

- **Manajemen Dependensi**: Menggunakan `uv` untuk pengelolaan paket yang sangat cepat dan menjamin reproduksibilitas lingkungan pengembangan melalui file lock yang konsisten.
- **Kualitas Kode**: Terintegrasi dengan **Ruff** sebagai linter dan **Black** sebagai formatter untuk memastikan standar penulisan kode yang bersih dan seragam.
- **Git Hooks**: Automasi pengecekan kualitas kode sebelum proses commit menggunakan **Pre-commit** guna mencegah kode yang tidak standar masuk ke repositori.
- **Kontainerisasi**: Menyediakan `Dockerfile` multi-stage yang telah dioptimalkan untuk beban kerja Machine Learning serta konfigurasi `Docker Compose` untuk orkestrasi layanan.
- **Ruang Kerja Terstruktur**: Pengorganisasian direktori yang sistematis untuk pemisahan data, model, eksperimen (notebooks), dan kode sumber inti.
- **Konsistensi Repositori**: Penggunaan berkas `.gitkeep` untuk memastikan struktur direktori kosong tetap terjaga saat dilakukan sinkronisasi ke repositori jarak jauh.

## Prasyarat

Proyek ini sangat bergantung pada `uv` sebagai pengelola paket utama. Pastikan perangkat tersebut sudah terpasang di sistem Anda. Jika belum, Anda dapat menginstalnya melalui perintah berikut:

```bash
curl -LsSf https://astral.sh/uv/install.sh | sh
```

## Instruksi Penggunaan

Ikuti langkah-langkah di bawah ini untuk menginisialisasi proyek baru menggunakan template ini.

### 1. Inisialisasi Proyek
Jalankan perintah berikut untuk men-generate proyek baru:

```bash
uvx cookiecutter https://github.com/attmhd/ml-projects-template
```

Setelah menjalankan perintah di atas, Anda akan diminta memasukkan beberapa informasi untuk proyek ML Anda:

- **project_name**: Nama proyek yang lebih deskriptif (contoh: `My ML Project`).
- **project_slug**: Nama identitas proyek (contoh: `my-ml-project`).
- **author_name**: Nama penulis proyek.
- **description**: Deskripsi singkat proyek.
- **python_version**: Versi Python yang digunakan (contoh: `3.10`).

### 2. Konfigurasi Proyek Baru
Setelah proyek berhasil dibuat, masuk ke direktori proyek tersebut dan lakukan langkah-langkah berikut:

```bash
cd nama-project-anda

# Sinkronisasi dependensi dan pembuatan virtual environment secara otomatis.
# Anda dapat menambahkan dependensi dengan 'uv add <nama-paket>' atau melalui pyproject.toml secara manual lalu jalankan 'uv sync'.
# Gunakan 'uv run <nama-skrip/paket>' untuk menjalankan perintah di dalam environment.
uv sync

# Pemasangan git hooks untuk standarisasi kode
uv run pre-commit install
```

## Struktur Proyek

Berikut adalah gambaran hierarki direktori yang akan dihasilkan oleh template ini:

```text
{{project_slug}}/
├── configs/            # Berkas konfigurasi (YAML, JSON, dsb.)
├── data/               # Penyimpanan data mentah, data antara, dan hasil pemrosesan
├── docs/               # Dokumentasi teknis dan referensi proyek
├── examples/           # Contoh penggunaan atau skrip demonstrasi
├── models/             # Tempat penyimpanan artefak model dan metadata hasil pelatihan
├── notebooks/          # Jupyter Notebooks untuk analisis data dan eksperimen
├── src/                # Kode sumber utama (logika bisnis, pipeline data, pelatihan model)
├── tests/              # Kumpulan pengujian unit dan pengujian integrasi
├── Dockerfile          # Definisi citra Docker untuk standarisasi lingkungan
├── pyproject.toml      # Pusat konfigurasi alat pengembangan (uv, ruff, black)
└── README.md           # Dokumentasi spesifik untuk proyek yang dihasilkan
```

## Perintah Pengembangan (Development)

Tersedia beberapa perintah utama untuk menjaga kualitas kode selama siklus pengembangan:

- **Linting (Pengecekan Kode)**: `uv run ruff check .`
- **Formatting (Merapikan Kode)**: `uv run black .`
- **Testing (Pengujian)**: `uv run pytest`
- **Docker (Kontainerisasi)**: `docker compose up --build`

---
Proyek ini dikembangkan untuk mendukung standar pengembangan Machine Learning yang lebih profesional dan terorganisir.
