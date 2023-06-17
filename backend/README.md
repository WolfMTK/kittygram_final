### Запуск backend-сервера

1. Создать виртуальное окружение:

    a. Linux/macOS:

    `python3 -m venv venv`

    `. /venv/bin/activate`

    б. Windows:

    `py -m venv venve`

    `source venv/Scripts/activate`

2. Установить необходимые зависимости: `pip install -r requirements.txt`

3. Выполнить миграции: `python manage.py migrate`

4. Запустить проект: `python manage.py runserver`

### Запуск backend-сервера в docker-контейнере

1. Установить docker: [документация по docker](https://docs.docker.com/engine/install/)

2. Собрать образ бэкенда (для linux от `sudo` вводить команды):

`docker build -t kittygram_backend .`

`docker run --name kittygram_backend_container --rm -p 9000:9000 kittygram_backend`
