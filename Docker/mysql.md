# MY SQL

## Crear un contenedor :

### a) con docker run
  ``` bash
  docker run --name mysqlContainer \
    -e MYSQL_ROOT_PASSWORD=tu_password \
    -e MYSQL_DATABASE=dbName \
    -p 3306:3306 \
    -d mysql:8.0
  ```

### b) con docker compose (docker-compose.yml):
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

## Utilizar MYSQL:

> ### accede al contenedor de docker como cliente:
> ``` bash
> docker exec -it mysqlContainer mysql -u root -p
> ```
>
> ``` mysql
> SHOW TABLES;
> CREATE DATABASE dbName;
> USE dbName;
> DROP DATABASE dbName;
> ```
> 
> ``` mysql
> SHOW TABLES;
> CREATE TABLE tableName (id INT AUTO_INCREMENT PRIMARY KEY, nombre VARCHAR (100), email VARCHAR(100));
> DESCRIBE tableName;
> DROP TABLE tableName;
> ```
> 
> ``` mysql
> SELECT * FROM tableName;
> INSERT INTO tablenName (nombre) VALUES ('Ronny');
> UPDATE tableName SET email='nuevoEmail' WHERE nombre='Ronny';
> DELETE FROM tableName WHERE nombre='Ronny';
> ALTER TABLE tableName ADD (padron INT(10));
> TRUNCATE TABLE tableName; 
> ```

## Conectar docker mysql backend

>
> ``` bash
> docker run --name backend-container \
>   -p 5001:5001 \
>   --link mysql-container:db \
>   -d flask-backend
> ```



