# syntax=docker/dockerfile:1
FROM python:3.12.2-slim-bookworm

WORKDIR /app

COPY ./requirements.txt requirements.txt

# Dependencies required for psycopg2 (used for Postgres client)
RUN apt update -y && apt install -y build-essential libpq-dev

# Dependencies are installed during build time in the container itself so we don't have OS mismatch
RUN pip install -r requirements.txt

COPY . .

# Finally run python application
CMD ["python", "app.py"]