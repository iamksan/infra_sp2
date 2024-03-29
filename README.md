# api_yamdb

Проект YaMDb собирает отзывы пользователей на произведения.

## Описание
Проект YaMDb собирает отзывы пользователей на различные произведения.

## Как запустить проект

>*Клонировать репозиторий и перейти в него в командной строке:*


* ```bash
  git clone git@github.com:IlDezmond/api_yamdb.git
  ```

* ```bash
  cd api_yamdb/
  ```

>*Cоздать и активировать виртуальное окружение:*

* ```bash
  python -m venv env
  ```

* *Если у вас Linux/macOS*

* ```bash
   source env/bin/activate
   ```

* *Если у вас windows*

* ```bash
  source env/scripts/activate
  ```

* ```bash
  python -m pip install --upgrade pip
  ```

>*Установить зависимости из файла requirements.txt:*

* ```bash
  pip install -r requirements.txt
  ```

* ```bash
  cd api_yamdb/
  ```

>*Выполнить миграции:*

* ```bash
  python manage.py migrate
  ```

>*Запустить проект:*

* ```bash
  python manage.py runserver
  ```

>*Для загрузки тестовых данных в БД, выполните команду:*

* ```bash
    python manage.py load_csv
  ```

## Примеры работы с API

### GET запрос. Получение списка произведений

```URL
http://127.0.0.1:8000/api/v1/titles/
```

```JSON
    {
        "count": 0,
        "next": "string",
        "previous": "string",
        "results": [
            {
                "id": 0,
                "name": "string",
                "year": 0,
                "rating": 0,
                "description": "string",
                "genre": [
                    {
                        "name": "string",
                        "slug": "string"
                    }
                ],
                "category": {
                    "name": "string",
                    "slug": "string"
                }
            }
        ]
    }
```

### POST запрос. Добавление произведения. Права доступа: Администратор

```URL
http://127.0.0.1:8000/api/v1/titles/
```

>*request:*

```JSON
    {
        "name": "string",
        "year": 0,
        "description": "string",
        "genre": [
            "string"
        ],
        "category": "string"
    }
```

>*response:*

```JSON
    {
        "id": 0,
        "name": "string",
        "year": 0,
        "rating": 0,
        "description": "string",
        "genre": [
            {
                "name": "string",
                "slug": "string"
            }
        ],
        "category": {
            "name": "string",
            "slug": "string"
        }
    }
```

### POST запрос. Регистрация нового пользователя

```URL
http://127.0.0.1:8000/api/v1/auth/signup/
```

>*request:*

```JSON
    {
        "email": "user@example.com",
        "username": "string"
    }
```

>*response:*

```JSON
    {
        "email": "string",
        "username": "string"
    }
```

### POST запрос. Получение JWT-токена пользователем для доступа к API

```URL
http://127.0.0.1:8000/api/v1/auth/token/
```

>*request:*

```JSON
    {
        "username": "string",
        "confirmation_code": "string"
    }
```

>*response:*

```JSON
    {
        "token": "string"
    }
```

### Полная документация находится по адресу

```URL
http://127.0.0.1:8000/redoc/
```
