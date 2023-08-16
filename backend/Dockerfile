FROM python:3.9

WORKDIR /app

COPY requirements.txt .
#ответ на вопрос про COPY.
#не стоит объединять эти два COPY, так как в первый раз мы копируем зависимости в директорию в рабочую текущую директорию образа
#а второй раз копируется содержимое лок.директорию в тек.директорию образа
#образ собирается слоями

RUN pip install -r requirements.txt --no-cache-dir

COPY . .

CMD ["gunicorn", "--bind", "0.0.0.0:9000", "kittygram_backend.wsgi"]