# YAMDB_FINAL
Упаковывает проект api_yamdb в docker контейнер и запукает совместно с nginx и postgresql контейнерами. 
#
### Шаблон наполнения env-файла
```
SECRET_KEY=# Секретный ключ приложения Django
DB_ENGINE=django.db.backends.postgresql
DB_NAME=# Имя базы данных
POSTGRES_USER=# Пользователь базы данных
POSTGRES_PASSWORD=# Пароль пользователя базы данных
DB_HOST=db
DB_PORT=5432
```
### Как запустить проект:

Клонировать репозиторий и перейти в его директорию infra:

```
git clone https://github.com/abp-ce/infra_sp2.git
cd infra_sp2/infra
```

Cоздать и запустить докер-контейнеры:

```
docker-compose up -d --build
```

Создать базу, заполнить её и соберите статику, выполнив start.sh:

```
chmod +x start.sh
./start.sh
```

Cоздайте суперпользователя:

```
docker-compose exec web python manage.py createsuperuser
```

Описание доступных endpoint смотрите:

```
http://localhost/redoc/
```

![YAMDB_final workflow](https://github.com/abp-ce/yamdb_final/actions/workflows/yamdb_workflow.yml/badge.svg)
