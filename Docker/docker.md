# Aprender docker
> ## Contenedores
> versiones
> base de datos
> ....
> se debe descargar una imagen!!


> ## Repositorios para contenedores
> Docker hub
>
> ### Descargar imagen
> 

> podes ver las imagenes que tienes descagadas
```
  docker images
```

> podes versionar con `:version` 
```
  docker pull node:18
  docker image rm node:18
```

> ## Creando contenedores
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

> ## Port mapping
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

> ##  Docker file
```
FROM node:18

RUN mkdir -p /home/app

COPY . /home/app

EXPOSE 3000

CMD ["node", "/home/index.js"]
```
