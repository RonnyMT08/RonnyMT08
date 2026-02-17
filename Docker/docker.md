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
para dockerizar tu proyecto

> ![IMPORTANT]necesitas tener los siguientes archivos

`app.py`, `requirements.txt`

```docker
FROM python:3.11-slim

WORKDIR /app

COPY requirements.txt .

RUN pip instalJ --no-cache-dir -r requirements.txt

COPY . .

EXPOSE 5000

CMD ["flask", "run", "--host=0.0.0.0", "--port=5000"]
```

el archivo `.dockerignore`
```
__pycache__/
*.pyc
*.pyo
*.pyd
.env
```

> construye la imagen en la raiz del proyecto (aplicativo para otras pc)
```bash
docker build -t flask-app:name .
```

> levantar el contenedor con volumen con:
```bash
docker run -p 5000:5000 -v $(pwd):app -e FLASK_ENV=development flask-app:name
```

> configuración de flask en modo desarrollo
```python
if __name__ == "__main__":
    app.run(host="0.0.0.0", port=5000, debug=True)
```

> correr con:
```bash
python app.py
```

## Docker compose
