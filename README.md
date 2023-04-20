Создаем проект, в нем главный файл, требования и докер для
поднятия базы.

Зависимости:
- pydantic[email] - проверка мейла
- envparse=2.9.5 - парсинг переменных окружения
- acyncpg==0.27.0 - асинхронно с Бд через алхимию
- alembic==1.9.0 - накатывание миграций
- psyporg2==2.9.5 - взаимодействие с БД

Чтобы установить все прописанные, в терминале pip install -r requirements.txt

Сеттингс:

Переменные окружения
   "REAL_DATABASE_URL",
   default="postgresql+asyncpg://postgres:postgres@0.0.0.0:5432/postgres", где 
        postgresql+asyncpg - драйвер подключения, крайне важно указать так, иначе алхимия пойдет синхронно
        логин:пароль@хост:порт/имяБД


База:
1. Откроем Движок докера и поставим галочку Использовать V2
2. Запустим базу через консоль: docker compose -f docker-compose-local.yaml up -d
3. Проверим: docker ps и увидим текущий статус
4. Запустим Бобра, установить соединение, логин и пароль postgres, порт 5432
5. Проверяем коннтект, норм, Бобер видит базу
