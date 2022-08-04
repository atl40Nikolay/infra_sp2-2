### Краткое описание проекта YaMDb

Проект YaMDb собирает отзывы пользователей на произведения. Произведения делятся на категории: «Книги», «Фильмы», «Музыка». В каждой категории есть произведения: книги, фильмы или музыка. Произведению может быть присвоен жанр. Новые жанры может создавать только администратор. Пользователи могут оставить к произведениям текстовые отзывы и поставить произведению оценку в диапазоне от одного до десяти. Из пользовательских оценок формируется усреднённая оценка произведения — рейтинг. Присутствует возможность комментирования отзывов.


### Стек технологий

![gunicorn](https://img.shields.io/badge/gunicorn-blue) ![Nginx](https://img.shields.io/badge/Nginx-blue) ![Docker](https://img.shields.io/badge/Docker-blue) ![Docker-compose](https://img.shields.io/badge/Docker--compose-blue) 


### Шаблон наполнения env-файла

```
DB_ENGINE=django.db.backends.postgresql
DB_NAME=postgres
POSTGRES_USER=postgres
POSTGRES_PASSWORD=postgres
DB_HOST=db
DB_PORT=5432
```


### Запуск контейнера и приложения в нем

Перейти в репозиторий для запуска докера

```
cd infra/
```

Запуск docker-compose

```
docker-compose up -d --build
```

После создайте суперпользователя
```
docker-compose exec web python manage.py createsuperuser
```
Войдите в админку и создайте одну-две записи объектов


### При необходимости можно создать дамп (резервную копию) базы:

```
docker-compose exec web python manage.py dumpdata > fixtures.json
```