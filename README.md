# Postgres DB с поддержкой расширения CUBE

В текущей сборке максимальный размер мерности (dimension) изменен со 100 на 512. Для изменения мерности под свои задачи смотрите в ```db/Dockerfile``` и ```db/create_cube_extenstion_512dim.sql```, где **512** нужно изменить под требуемое вам значение.

### Пример файла **.env**
```
POSTGRES_DB=postgres_cube512  # Название БД
POSTGRES_USER=postgres_cube512  # Имя пользователя
POSTGRES_PASSWORD=postgres_cube512  # Пароль
PGDATA=/var/lib/postgresql/data/pgdata  # Место хранения данных в контейнере
PGDATA_VOLUME=~/databases/postgres_cube512:/var/lib/postgresql/data  # Место хранения на хосте
CONTAINER_NAME=postgres_cube512  # Название контейнера
```