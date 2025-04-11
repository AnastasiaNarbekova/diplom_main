# Социальная сеть для обмена фотографиями

Позволяет пользователям:
- публиковать посты с фото
- оставлять комментарии
- ставить и убирать лайки

Реализовано с использованием Django, Django REST Framework и PostgreSQL.

Установка и запуск проекта

### 1. Клонировать репозиторий

git clone <https://github.com/AnastasiaNarbekova/diplom_main.git>
cd social_network


### 2. Создать и активировать виртуальное окружение

python -m venv venv  
source venv/bin/activate 


### 3. Установить зависимости

pip install -r requirements.txt


### 4. Настройка базы данных

Создайте базу данных PostgreSQL с именем dj_diplom


### 5. Применение миграций и запуск сервера

python manage.py makemigrations  
python manage.py migrate

### 6. Создание суперпользователя

python manage.py createsuperuser


### 7. Запуск сервера

python manage.py runserver

## Авторизация
Аутентификация осуществляется через токен.
Получить токен можно:
1. Tokens → добавить для пользователя,
2. через Python shell:  

    from rest_framework.authtoken.models import Token
    from django.contrib.auth import get_user_model
    Token.objects.get_or_create(user=get_user_model().objects.first())

## Основные запросы
Посты

GET /api/posts/ — список всех постов
POST /api/posts/ — создать пост (текст + изображение)
GET /api/posts/<id>/ — получить пост с комментариями и количеством лайков
POST /api/posts/<id>/like/ — поставить лайк
POST /api/posts/<id>/unlike/ — убрать лайк

Комментарии

GET /api/comments/ — список всех комментариев
POST /api/comments/ — добавить комментарий к посту

### Автор
Нарбекова Анастасия

Дипломный проект курса «Python-разработчик с нуля» от Нетологии