# Yatube API

**Yatube API** — это RESTful API для социальной сети Yatube. С его помощью пользователи могут публиковать посты, оставлять комментарии, подписываться на других авторов и управлять своими подписками.

---

## Запуск проекта

### 1. Клонируем репозиторий и переходим в папку проекта:
```sh
git clone https://github.com/...
cd ...
```
### 2. Создаём и активируем виртуальное окружение:
```sh
python3 -m venv env
source env/bin/activate  # для macOS/Linux
venv\Scripts\activate   # для Windows
```
### 3. Устанавливаем зависимости:
```sh
python3 -m pip install --upgrade pip
pip install -r requirements.txt
```
### 4. Выполняем миграции:
```sh
python3 manage.py migrate
```
### 5. Запускаем сервер:
```sh
python3 manage.py runserver
```

---

## Примеры API-запросов

### 🔹 Регистрация и получение токена  
**POST** `/api/v1/token/`
```json
{
    "username": "leo",
    "password": "mypassword"
}
```
**Ответ:**
```json
{
    "refresh": "your_refresh_token",
    "access": "your_access_token"
}
```
---
### 🔹 Получение списка постов  
**GET** `/api/v1/posts/`
```sh
curl -X GET http://127.0.0.1:8000/api/v1/posts/
```
**Ответ:**
```json
{
    "count": 2,
    "results": [
        {
            "id": 1,
            "text": "Привет, это мой первый пост!",
            "author": "leo",
            "pub_date": "2025-03-26T12:00:00Z"
        }
    ]
}
```

