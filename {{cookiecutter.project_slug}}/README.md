# {{ cookiecutter.project_name }}

{{ cookiecutter.description }}

**Author:** {{ cookiecutter.author_name }}

---

## Project Structure

```text
{{ cookiecutter.project_slug }}/
├── configs/            # Configuration files
├── data/               # Data storage (ignored except .gitkeep)
│   ├── raw/            # Original, immutable data
│   └── processed/      # The final, canonical data sets for modeling
├── docs/               # Documentation
├── examples/           # Example scripts or notebooks
├── models/             # Trained and serialized models
├── notebooks/          # Jupyter notebooks
├── src/                # Source code
│   ├── data/           # Scripts to download or generate data
│   ├── models/         # Scripts to train models and make predictions
│   └── utils/          # Utility functions
├── tests/              # Unit tests
├── Dockerfile          # Dockerfile for modern ML projects
├── docker-compose.yml  # Docker Compose configuration
├── pyproject.toml      # Python project configuration (uv, ruff, black)
└── README.md           # This file
```

---

## Getting Started

### Prerequisites

- [uv](https://github.com/astral-sh/uv)
- Docker & Docker Compose (optional)

### Installation

1. **Generate the project** using Cookiecutter:
   ```bash
   uvx cookiecutter https://github.com/attmhd/ml-projects-template
   ```

2. **Fill in the project details** when prompted:
   - `project_name`: Nama proyek yang lebih deskriptif (contoh: `My ML Project`).
   - `project_slug`: Nama identitas proyek (contoh: `my-ml-project`).
   - `author_name`: Nama penulis proyek.
   - `description`: Deskripsi singkat proyek.
   - `python_version`: Versi Python yang digunakan (contoh: `3.10`).

3. **Navigate to the project directory**:
   ```bash
   cd {{ cookiecutter.project_slug }}
   ```

4. **Sync dependencies**:
   ```bash
   uv sync
   ```

5. **Setup pre-commit**:
   ```bash
   uv run pre-commit install
   ```

---

## Usage

### Running Locally
```bash
uv run python src/main.py
```

### Running with Docker
```bash
docker compose up
```

---

## Development

- **Linting & Formatting**: 
  - `uv run ruff check .`
  - `uv run black .`
- **Testing**: 
  - `uv run pytest`
