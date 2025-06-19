FROM python:alpine3.21

RUN mkdir /uv 
RUN mkdir /uvx
COPY ghcr.io/astral-sh/uv:alpine3.21 /uv /uvx /bin/

WORKDIR /app

COPY pyproject.toml .

RUN python -V
RUN uv sync --locked

COPY . .

CMD [ "uv", "run", "/app/main.py"]