# Use the official uv base image
FROM ghcr.io/astral-sh/uv:python3.11-bookworm-slim

WORKDIR /app

COPY pyproject.toml uv.lock* ./

RUN uv sync --no-cache

COPY . .

# Activate venv
ENV PATH="/app/.venv/bin:$PATH"

EXPOSE 8000

CMD ["python", "src/main.py"]