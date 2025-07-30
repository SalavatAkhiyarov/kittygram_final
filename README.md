# Kittygram

## Описание
Kittygram - это веб-сервис, предназначенный для любителей котов. С его помощью пользователи могут публиковать информацию о своих питомцах, добавлять их фотографии, а также просматривать профили и фотографии других котов, загруженных на платформу.

### Ключевые возможности
- Загрузка фотографии кота;
- Указание имени питомца;
- Выбор цвета из предложенной палитры;
- Добавление достижений кота;
- Указание года рождения;
- Редактирование ранее опубликованной информации;
- Просмотр котов других пользователей

## Технологический стек
В данном проекте используются следующие инструменты и библиотеки:
- **Python** — основной язык программирования для разработки
- **Django** — фреймворк для веб-разработки
- **Django REST Framework (DRF)** — библиотека для создания API
- **PostgreSQL** - база данных
- **pytest** - для тестирования
- **nginx** - веб-сервер и прокси
- **gunicorn** — WSGI-сервер для запуска Django-приложения
- **Docker** - контейнеризация и управление многоконтейнерным окружением
- **GitHub Actions** — CI/CD, автоматизация тестов и деплоя

## Как запустить проект
1. Клонировать репозиторий и перейти в него в командной строке:
git clone git@github.com:SalavatAkhiyarov/kittygram_final.git
cd kittygram_final
2. Убедитесь, что у вас установлен Docker и Docker Compose
3. Создайте файл .env в корне проекта и добавьте переменные:
SECRET_KEY=ваш_секретный_ключ
DB_NAME=название_бд
POSTGRES_USER=пользователь
POSTGRES_PASSWORD=пароль
DB_HOST=db
DB_PORT=5432
*Вы можете использовать пример .env.example*
4. Запустите процесс сборки контейнеров:
docker compose -f docker-compose.production.yml up --build
5. Примените миграции:
docker compose -f docker-compose.production.yml exec backend python manage.py migrate
6. Соберите статические файлы:
docker compose -f docker-compose.production.yml exec backend python manage.py collectstatic
docker compose -f docker-compose.production.yml exec backend cp -r /app/collected_static/. /backend_static/static/

## Автор
[Салават Ахияров](https://github.com/SalavatAkhiyarov)

[![Main Kittygram workflow](https://github.com/SalavatAkhiyarov/kittygram_final/actions/workflows/main.yml/badge.svg)](https://github.com/SalavatAkhiyarov/kittygram_final/actions/workflows/main.yml)

