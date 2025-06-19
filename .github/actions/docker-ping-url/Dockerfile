FROM ghcr.io/astral-sh/uv:python3.13-alpine

# RUN mkdir /uv 
# RUN mkdir /uvx
# COPY ghcr.io/astral-sh/uv:alpine3.21 /uv /bin/

WORKDIR /app

COPY pyproject.toml .
COPY uv.lock .

RUN python -V
RUN uv sync --locked

ENV PATH="/app/.venv/bin:$PATH"

COPY . .

CMD [ "uv", "run", "/app/main.py"]