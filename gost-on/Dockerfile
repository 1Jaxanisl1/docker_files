# Указываем image
FROM --platform=$BUILDPLATFORM python:3.9-alpine

# Создаём папку с правами на нового юзера
RUN adduser -D appuser
WORKDIR /app
RUN chown -R appuser:appuser /app
USER appuser

# Устанавливаем зависимости
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt


# Копируем всю директорию, с открытием порта 5000
COPY . .
EXPOSE 5000


ENTRYPOINT [ "python3.9", "main.py" ]
