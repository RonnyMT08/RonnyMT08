# DOCKER

## 1. Descargar imagenes
> ```
> docker pull python:3.11-slim
> docker images
> docker image rm python:3.11-slim
> ```

## 2. Creando contenedores
> se crea contenedores en base a imagenes descargadas

```
docker create --name monguito mongo
docker conteiner create mongo
```

> ejecutar contenedores ya sea por id o nombre

```
docker start ijijijijij
docker stop ijijijij
```

> ver los contenedores
```
docker ps
docker ps -a
```

## 3. Port mapping
> se utiliza primero en local depues de docker
```
docker create -p27017:27017 --name monguito mongo:18
```

> ver si el contenedor se esta ejecutando
```
docker logs monguito
```

> forma rapida de ejecutar el contenedor
> si no tiene la imagen la descarga
```
docker run --name monguito -p27017:27017 -d mongo
```

## 4.  Docker file
```
FROM python:3

WORKDIR /usr/src/app

COPY requirements.txt ./
RUN pip instal --no-cache-dir -r requirements.txt

COPY . .

CMD ["python", "./home/index.py"]
```

> correlo con:
> ```
> docker build -t my-python-app:1 .
> ```

> descargalo con:
> ``` 
> docker run it --rm --name my-running-app my-python-app
> ```
