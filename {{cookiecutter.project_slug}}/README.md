# {{ cookiecutter.project_name }}

{{ cookiecutter.description }}

Author: {{ cookiecutter.author_name }}

## Project Structure

```text
{{ cookiecutter.project_slug }}/
├── configs/            # Configuration files
├── data/               # Data storage (ignored except .gitkeep)
│   ├── raw/            # Original, immutable data
│   └── processed/      # The final, canonical data sets for modeling
├── docs/               # Documentation
├── models/             # Trained and serialized models
├── notebooks/          # Jupyter notebooks
├── src/                # Source code
│   ├── data/           # Scripts to download or generate data
│   ├── models/         # Scripts to train models and then use trained models to make predictions
│   └── utils/          # Utility functions
├── tests/              # Unit tests
├── Dockerfile          # Dockerfile for modern ML projects
├── docker-compose.yml  # Docker Compose configuration
├── pyproject.toml      # Python project configuration (uv, ruff, black)
└── README.md           # This file
```

## Getting Started

### Prerequisites

- [uv](https://github.com/astral-sh/uv)
- Docker & Docker Compose (optional)

### Installation

1. Clone the repository:
   ```bash
   git clone <repo-url>
   cd {{ cookiecutter.project_slug }}
   ```

2. Sync dependencies:
   ```bash
   uv sync
   ```

3. Setup pre-commit:
   ```bash
   uv run pre-commit install
   ```

### Usage

#### Running locally
```bash
uv run python src/main.py
```

#### Running with Docker
```bash
docker compose up
```

## Development

- **Linting/Formatting**: `uv run ruff check .` and `uv run black .`
- **Testing**: `uv run pytest`
