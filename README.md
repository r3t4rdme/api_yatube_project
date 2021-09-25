Описание:

API для работы с проектом Yatube.

Как запустить проект:

Клонировать репозиторий и перейти в него в командной строке:

- git clone https://github.com/r3t4rdme/api_final_yatube.git
- cd yatube_api
- Cоздать и активировать виртуальное окружение:
- python -m venv env
- source env/bin/activate
- Установить зависимости из файла requirements.txt:
- python -m pip install --upgrade pip
- pip install -r requirements.txt

Выполнить миграции:
- python manage.py migrate
Запустить проект:
- python manage.py runserver

Примеры запросов:

Пример POST-запроса с токеном username: добавление нового поста.

POST .../api/v1/posts/

{
    "text": "Здесь могла бы быть Ваша реклама",
    "group": 1
} 
Пример ответа:

{
    "id": 1,
    "text": "Здесь могла бы быть Ваша реклама",
    "author": "username",
    "image": null,
    "group": 1,
    "pub_date": "2021-09-25T20:56:23.769063Z"
} 
Пример POST-запроса с токеном username: отправляем новый комментарий к посту с id=1.

POST .../api/v1/posts/1/comments/

{
    "text": "Текст комментария",
} 
Пример ответа:

{
    "id": 3,
    "author": "username",
    "post": 1,
    "text": "Ваш текст",
    "created": "2021-09-25T20:56:23.769063Z"
} 
Пример GET-запроса с токеном username: получаем информацию о группе.

GET .../api/v1/groups/2/

Пример ответа:

{
    "id": 2,
    "title": "Ваша группа",
    "slug": "your_group_name",
    "description": "Ваши любимые посты"
} 