# api_final_yatube
## Описание
REST API для социальной сети Yatube. Позволяет создавать посты, подписываться на авторов, комментировать и получать ленту публикаций.

## Установка
```bash
git clone git@github.com:chillpill128/api_final_yatube.git
cd api_final_yatube
python -m venv venv
source venv/Scripts/activate
pip install -r requirements.txt
cd yatube_api
python manage.py runserver
Ctrl + C
python manage.py makemigrations
python manage.py migrate
```
Документация 
```http://127.0.0.1:8000/redoc/```
## Примеры использования
Запрос на получение токена
```
POST /api/v1/jwt/create/
{
  "username": "admin",
  "password": "123"
}
```
Получение публикаций
```
GET /api/v1/posts/
[
    {
        "id": 1,
        "author": "admin",
        "image": null,
        "text": "прога",
        "pub_date": "2025-05-09T10:32:35.309129Z",
        "group": null
    }
]
```
Создание публикации
```
POST /api/v1/posts/
{
    "text": "прога"
}
```
## PEP8

```
pip install flake8
flake8 .