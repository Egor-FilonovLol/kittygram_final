FROM python:3.9

WORKDIR /app

COPY requirements.txt .
RUN pip install --no-cache-dir --upgrade pip setuptools
RUN pip install --no-cache-dir gunicorn==23.0.0
RUN pip install --no-cache-dir -r requirements.txt

COPY . .

RUN mkdir -p /app/static

CMD ["gunicorn", "--bind", "0.0.0.0:8000", "kittygram_backend.wsgi"]
