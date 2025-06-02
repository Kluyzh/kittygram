# 🐱 Kittygram - Платформа для котиков

**Kittygram** - это социальная платформа, где вы можете делиться информацией о своих котах: фотографиями, достижениями, годом рождения и окрасом.

## 🛠 Технологии
- **Бэкенд:** Django 3.2 + DRF + Djoser
- **Фронтенд:** React (судя по структуре)
- **База данных:** PostgreSQL
- **Веб-сервер:** Nginx
- **Развертывание:** Docker Compose

## ⚙️ Зависимости
Основные зависимости (полный список в `backend/requirements.txt`):
```python
Django==3.2.3
djangorestframework==3.12.4
djoser==2.1.0
psycopg2-binary==2.9.3
Pillow==9.0.0
gunicorn==20.1.0

🚀 Запуск проекта через Docker Compose
Создайте файл .env в корне проекта со следующим содержанием:

# Базовые настройки Django
SECRET_KEY=ваш_секретный_ключ
DEBUG=False
ALLOWED_HOSTS=localhost,127.0.0.1,ваш-домен.ru

# Настройки PostgreSQL
POSTGRES_DB=kittygram
POSTGRES_USER=kittygram_user
POSTGRES_PASSWORD=ваш_надежный_пароль
DB_HOST=db
DB_PORT=5432

Запустите проект:

docker-compose up --build
Применяйте миграции (в новом терминале):

bash
docker-compose exec backend python manage.py migrate

Создайте суперпользователя:

bash
docker-compose exec backend python manage.py createsuperuser
Проект будет доступен по адресу: http://localhost:9000

Структура проекта
kittygram_final/
├── backend/          # Django-приложение
│   ├── cats/         # Приложение с функционалом котиков
│   ├── kittygram_backend/ # Основные настройки проекта
│   ├── requirements/
│   └── manage.py
├── frontend/         # React-приложение
├── nginx/            # Конфигурация Nginx
│   ├── Dockerfile
│   └── nginx.conf
└── docker-compose.yml # Конфигурация Docker
Ручная установка (без Docker)
Бэкенд:
bash
cd backend
python -m venv venv
source venv/bin/activate или source venv/Scripts/activate
cd requirements
pip install -r requirements.txt

# Создайте .env файл как указано выше
python manage.py migrate
python manage.py runserver

Фронтенд:
bash
cd frontend
npm install
npm run build


Для продакшена установите:

DEBUG = False
ALLOWED_HOSTS = ['ваш-домен.ru', 'IP-адрес-сервера']
