# Уважаемый гость! Если пользуешься данным репозиторием буду рад если нажмешь ⭐ в правом верхнем углу экрана.

![Nginx](https://img.shields.io/badge/nginx-%23009639.svg?style=for-the-badge&logo=nginx&logoColor=white) ![JavaScript](https://img.shields.io/badge/javascript-%23323330.svg?style=for-the-badge&logo=javascript&logoColor=%23F7DF1E) ![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54) ![Django](https://img.shields.io/badge/django-%23092E20.svg?style=for-the-badge&logo=django&logoColor=white) ![DjangoREST](https://img.shields.io/badge/DJANGO-REST-ff1709?style=for-the-badge&logo=django&logoColor=white&color=ff1709&labelColor=gray) ![Postgres](https://img.shields.io/badge/postgres-%23316192.svg?style=for-the-badge&logo=postgresql&logoColor=white) ![Docker](https://img.shields.io/badge/docker-%230db7ed.svg?style=for-the-badge&logo=docker&logoColor=white) ![GitHub](https://img.shields.io/badge/github-%23121011.svg?style=for-the-badge&logo=github&logoColor=white) ![GitHub Actions](https://img.shields.io/badge/github%20actions-%232671E5.svg?style=for-the-badge&logo=githubactions&logoColor=white)

## Описание проекта

Task-organizer - задачный трекер с возможностью создавать и завершать задачи.

## Технологии

- Python 3.9
- Django 3.2.3, Django REST framework 3.12.4
- Postgresql 
- JavaScript

## Запуск проекта из образов с Docker hub

Для запуска необходимо на создать папку проекта, например `task-organizer` и перейти в нее:

```bash
mkdir task-organizer
cd task-organizer
```

В папку проекта скачиваем файл `docker-compose.production.yml` и запускаем его:

```bash
sudo docker compose -f docker-compose.production.yml up
```

Произойдет скачивание образов, создание и включение контейнеров, создание томов и сети.

## Запуск проекта из исходников GitHub

Клонируем себе репозиторий: 

```bash 
git clone git@github.com:MihailovAlexander/task-organizer.git
```

Выполняем запуск:

```bash
sudo docker compose -f docker-compose.yml up
```

### После запуска из исходников GitHub: Миграции, сбор статистики

После запуска необходимо выполнить сбор статистики и миграции бэкенда. Статистика фронтенда собирается во время запуска контейнера, после чего он останавливается. 

```bash
sudo docker compose -f [имя-файла-docker-compose.yml] exec backend python manage.py migrate

sudo docker compose -f [имя-файла-docker-compose.yml] exec backend python manage.py collectstatic

sudo docker compose -f [имя-файла-docker-compose.yml] exec backend cp -r /app/collected_static/. /static/static/
```

И далее проект доступен на: 

```
http://localhost:9000/
```

## Остановка оркестра контейнеров

В окне, где был запуск **Ctrl+С** или в другом окне:

```bash
sudo docker compose -f docker-compose.yml down
```

## Автор

Михайлов Александр https://t.me/MihailovAlexander
