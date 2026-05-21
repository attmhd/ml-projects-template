# Modern ML Project Cookiecutter Template 🚀

Template Cookiecutter untuk membuat struktur project Machine Learning yang sudah terstandarisasi dengan perkakas (tooling) Python modern.

## ✨ Fitur Utama

- **📦 Dependency Management**: Menggunakan [uv](https://github.com/astral-sh/uv) untuk manajemen paket yang sangat cepat dan reproducible.
- **🛠️ Code Quality**: Terintegrasi dengan [Ruff](https://github.com/astral-sh/ruff) (linter) dan [Black](https://github.com/psf/black) (formatter).
- **⚓ Git Hooks**: Automasi pengecekan kode sebelum commit dengan [Pre-commit](https://pre-commit.com/).
- **🐳 Containerization**: Dockerfile multi-stage yang dioptimalkan untuk ML dan Docker Compose.
- **📂 Structured Workspace**: Folder terorganisir untuk `data/`, `models/`, `notebooks/`, dan `src/`.
- **📁 Git Consistency**: Menggunakan `.gitkeep` agar struktur folder tetap terjaga saat dipush ke remote repository.

## 📋 Prasyarat

Pastikan Anda sudah menginstall [uv](https://github.com/astral-sh/uv). Jika belum, Anda bisa menginstallnya dengan:

```bash
curl -LsSf https://astral.sh/uv/install.sh | sh
```

## 🚀 Cara Penggunaan

Gunakan perintah berikut untuk men-generate project baru dari template ini:

### 1. Generate Project
```bash
uvx cookiecutter https://github.com/username/ml-template
```
*(Atau jalankan `uvx cookiecutter .` jika Anda sudah mendownload template ini secara lokal)*.

### 2. Setup Project Baru
Setelah project ter-generate, masuk ke folder tersebut dan jalankan:

```bash
cd nama-project-anda

# Install dependensi & buat venv
uv sync

# Install git hooks
uv run pre-commit install
```

## 🏗️ Struktur Project Hasil Generate

```text
{{project_slug}}/
├── configs/            # File konfigurasi (.yaml, .json, dll)
├── data/               # Data mentah dan hasil proses (di-ignore kecuali .gitkeep)
├── docs/               # Dokumentasi project
├── models/             # Penyimpanan model yang sudah dilatih
├── notebooks/          # Jupyter Notebooks untuk eksperimen
├── src/                # Kode sumber (Logic, Data Loading, Training)
├── tests/              # Unit testing
├── Dockerfile          # Struktur Docker modern
├── pyproject.toml      # Konfigurasi uv, ruff, dan black
└── README.md           # Dokumentasi spesifik project
```

## 🛠️ Perkakas yang Digunakan (Development)

- **Linting**: `uv run ruff check .`
- **Formatting**: `uv run black .`
- **Testing**: `uv run pytest`
- **Docker**: `docker compose up --build`

---
Dibuat dengan ❤️ untuk komunitas Machine Learning.
