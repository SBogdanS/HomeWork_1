# Docker-команда FROM вказує базовий образ контейнера
# Наш базовий образ - це Linux з попередньо встановленим python-3.10
FROM python:3.10-slim

# Встановимо змінну середовища
ENV APP_HOME /app

# Встановимо робочу директорію всередині контейнера
WORKDIR $APP_HOME


# Встановимо залежності всередині контейнера
COPY pyproject.toml $APP_HOME/pyproject.toml
RUN pip install poetry

RUN poetry config virtualenvs.create false && poetry install --only main
COPY . .



# Запустимо наш застосунок всередині контейнера
CMD ["python", "main.py"]
