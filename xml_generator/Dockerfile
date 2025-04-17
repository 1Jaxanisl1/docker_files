# Использую multi-stage для уменьшения конечного образа 
FROM --platform=$BUILDPLATFORM python:3.12-alpine 

RUN adduser -D appuser

WORKDIR /app
RUN chown -R appuser:appuser /app
USER appuser


# Устанавливаем зависимости
COPY requirements.txt .
RUN pip install --user --no-cache-dir -r requirements.txt

# Копируем директорию
COPY . .

# Точка входа
ENTRYPOINT [ "python", "main.py" ]
