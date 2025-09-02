# Builder stage
FROM python:3.11-slim 

RUN curl -LsSf https://astral.sh/uv/install.sh | sh \
    && rm -rf /var/lib/apt/lists/*

ENV PATH="/root/.local/bin:${PATH}"
WORKDIR /app

COPY pyproject.toml uv.lock* ./

RUN uv venv --seed \
    && uv sync --no-cache

COPY . .

# Activate venv
ENV PATH="/app/.venv/bin:$PATH"

EXPOSE 8000
CMD ["python", "src/main.py"]