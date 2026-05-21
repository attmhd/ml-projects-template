# Use a slim Python image
FROM python:{{ cookiecutter.python_version }}-slim-bookworm AS builder

# Install uv
COPY --from=ghcr.io/astral-sh/uv:latest /uv /uvx /bin/

# Set working directory
WORKDIR /app

# Copy dependency files
COPY pyproject.toml uv.lock ./

# Install dependencies (using uv for speed)
# We use --no-install-project to only install dependencies first (caching)
RUN uv sync --frozen --no-install-project

# Final stage
FROM python:{{ cookiecutter.python_version }}-slim-bookworm

WORKDIR /app

# Copy virtual environment from builder
COPY --from=builder /app/.venv /app/.venv

# Set path to use virtualenv
ENV PATH="/app/.venv/bin:$PATH"

# Copy source code
COPY . .

# Default command
CMD ["python", "src/main.py"]
