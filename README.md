# Проект Kittygram

Проект Kittygram предназначен для пользователей, которые очень любят котиков и хотят поделиться их фотогографиями. Сервис Kittygram предоставляет данную возможность, позволяя похвастаться своим котиком, либо же посмотреть на других.

Проект Kittygram доступен по ссылке:

```
https://kittygramme.gotdns.ch/
```

### Используемые технологии

**Python 3.10**

**Django 3.2.3**- фреймворк для создания веб-приложений на языке Python. Он предоставляет множество инструментов для работы с базами данных, шаблонами, формами и многое другое.

**Django Rest Framework 3.12.4** - расширение для Django, которое позволяет быстро и удобно создавать RESTful API. Оно предоставляет множество инструментов для сериализации и десериализации данных, авторизации и аутентификации пользователей, обработки ошибок и многое другое.

**Pytest 6.2.4** - фреймворк для автоматического тестирования на языке Python. Он предоставляет множество инструментов для написания и запуска тестов, а также для генерации отчетов о результатах тестирования.

**Nginx** - http-сервер и обратный прокси-сервер, почтовый прокис-сервер, а также TCP/UDP прокси-сервер общего назначения, позволяющий обслуживать статические запросы, индексные файлы, автоматически создавать списки файлов и многое другое.

**Gunicorn 20.1.0** — это HTTP-сервер интерфейса шлюза веб-сервера Python.

**React** — JavaScript-библиотека с открытым исходным кодом для разработки пользовательских интерфейсов.

**Docker** - это открытая платформа для разработки, доставки и эксплуатации приложений, разработана для более быстрого выкладывания приложений. С помощью docker можно отделить приложение от инфраструктуры и обращаться с инфраструктурой как управляемым приложением.

### Как развернуть проект

Клонируем репозиторий:

```
git clone https://github.com/F1yShy/kittygram_final.git
```

Создаем файл .env в корневой директории и заполняем поля нужными значениями:

```
POSTGRES_USER=django_user
POSTGRES_PASSWORD=mysecretpassword
POSTGRES_DB=django
DB_HOST=db
DB_PORT=5432
```

Запускаем Docker Compose с конфигурацией из файла docker-compose.yml:

```
docker compose -f docker-compose.yml up -d
```

Собираем и копируем статику:

```
docker compose -f docker-compose.yml exec backend python manage.py collectstatic
docker compose -f docker-compose.yml exec backend cp -r /app/collected_static/. /backend_static/static/ 
```

Выполняем миграции:

```
docker compose -f docker-compose.yml exec backend python manage.py migrate
```

Готово! Сайт доступен по ссылке:

```
http://localhost:9000/
```

### Контактная информация
Для связи с мной в GitHub можно перейти по ссылке:

```
https://github.com/F1yShy
```
Также вы можете написать на электронную почту, указанную в профиле на GitHub.
Буду рад ответить на ваши вопросы и обсудить возможные совместные проекты
