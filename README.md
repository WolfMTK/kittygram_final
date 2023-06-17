# Kittygram

### Запуск backend-сервера

Полное описание: [запуск backend-сервера](https://github.com/WolfMTK/kittygram_final/blob/main/backend/README.md)

### Запуск frontend-сервера

Полное описание: [запуск frontend-сервера](https://github.com/WolfMTK/kittygram_final/blob/main/frontend/README.md)

### Запуск nginx

1. Установить docker: [документация по docker](https://docs.docker.com/engine/install/)

2. Собрать образ бэкенда (для linux от `sudo` вводить команды):

`docker build -t kittygram_gunicorn .`

`docker run --name kittygram_gunicorn_container --rm -p 9000:9000 kittygram_gunicorn`

### Запуск проекта

1. Запустите Docker Compose (для linux от `sudo` вводить команды): `docker compose -f docker-compose.production.yml up`

2. Сделать необходимые миграции (для linux от `sudo` вводить команды):

`docker compose -f docker-compose.production.yml exec backend python manage.py migrate`

3. Собрать статику (для linux от `sudo` вводить команды):

`docker compose -f docker-compose.production.yml exec backend python manage.py collectstatic`

`docker compose -f docker-compose.production.yml exec backend cp -r /app/collected_static/. /backend_static/static/`

4. Проверить, что страница заработала:

`http://localhost:9000/`

`http://localhost:9000/api/`

`http://localhost:9000/admin/`

### Пример .env файла

Пример файла .env: [.env.example](https://github.com/WolfMTK/kittygram_final/blob/main/.env.example)
