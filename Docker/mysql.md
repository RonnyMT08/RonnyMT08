# MY SQL

## 1. Crear un contenedor :
> ### con docker run
``` bash
docker run --name mysql-container \
  -e MYSQL_ROOT_PASSWORD=tu_password \
  -e MYSQL_DATABASE=dbName \
  -p 3306:3306 \
  -d mysql:8.0
```

> ### con docker compose (docker-compose.yml):
``` bash
version: '3.8'
services:
  db:
    image: mysql:8.0
    container_name: mysql-container
    environment:
      MYSQL_ROOT_PASSWORD: tu_password
      MYSQL_DATABASE: dbName
    ports:
      - "3306:3306"
    volumes:
      - db_data:/var/lib/mysql

volumes:
  db_data:
```
> para levantarlo `docker-compose up -d`
