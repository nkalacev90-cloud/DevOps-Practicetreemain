FROM python:3.12-slim

WORKDIR /app

# Сначала зависимости — так кэш Docker не сбрасывается при правках кода
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

# Потом код
COPY app.py .

EXPOSE 5000

CMD ["python", "app.py"]