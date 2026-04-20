FROM python:3.9-slim

WORKDIR /app

COPY requirements.txt .

RUN pip install --default-timeout=300 --retries=10 --no-cache-dir -r requirements.txt
RUN pip install gunicorn==20.1.0

COPY . .

CMD ["gunicorn", "--bind", "0.0.0.0:8000", "kittygram_backend.wsgi"]