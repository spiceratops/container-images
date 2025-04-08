FROM python:3.12-slim

RUN apt-get update && apt-get install -y \
  libportaudio2 \
  portaudio19-dev \
  git \
  && rm -rf /var/lib/apt/lists/*

RUN pip install uv

RUN \
git clone --recurse-submodules https://github.com/dnhkng/GLaDOS.git /app

WORKDIR /app
COPY pyproject.toml README.md ./
COPY models/ ./models/
COPY src/ ./src/

RUN uv sync --extra api --extra cpu --no-dev \
  && uv run glados download

EXPOSE 5050
CMD ["uv", "run", "litestar", "--app", "glados.api.app:app", "run", "--host", "0.0.0.0", "--port", "5050"]

LABEL org.opencontainers.image.source="https://github.com/dnhkng/GLaDOS/"
