FROM python:3.13.11-slim
COPY --from=ghcr.io/astral-sh/uv:latest /uv /bin/

WORKDIR /code

COPY pyproject.toml .python-version uv.lock ./
COPY ingest_data.py .

RUN uv sync --locked

ENTRYPOINT ["uv", "run", "ingest_data.py"]