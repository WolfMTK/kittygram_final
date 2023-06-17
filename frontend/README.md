### Запуск frontend-сервера:

1. Установить зависимости: `npm i`

2. Запустить проект: `npm run start`

### Запуск frontend-сервера в docker-контейнере

1. Установить docker: [документация по docker](https://docs.docker.com/engine/install/)

2. Собрать образ бэкенда (для linux от `sudo` вводить команды):

`docker build -t kittygram_frontend .`

`docker run --name kittygram_frontend_container --rm -p 9000:9000 kittygram_frontend`
