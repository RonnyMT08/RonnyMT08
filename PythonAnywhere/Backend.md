# Levantar tu proyecto Backend + Base de Datos

> ## 1. Directorio para el proyecto

Crea un directorio adecuado para almacenar tu proyecto: `home/Proyecto/...`

> [!IMPORTANT]
> Descarga el repositorio de github
>
>``` bash
>    git clone https://turepositorio.github.com
>```

> [!CAUTION]
> ### Crea tu entorno virtual.
> ![como crear entono virtual]("https:...")
>
> ### Instala la librerias requeridas
> ![como archivar]("https:...") tus librerias utilizadas en el archivo `requeriminetos.txt` para el backend
>
> ```
>     pipenv install flask requerimientos
> ```

> ## 2. Achivo .env
> modifica o crea un archivo .env y guarda tus variables locales

```
DB_HOST=localhost
DB_USER=nameUser
DB_PASS=aaaaaaa
DB_NAME=proyectodb
PORT=5001
```

# Configurar pythonAnywhere Backend

> ## Code:

Source code: `/home/proyecto/P1Backend`

working directory: `/home/proyecto/P1Backend` 

> ## Virtualenv:

`/home/proyecto/P1Backend/.env`

> ## wsgi.py

``` python
import sys
import os

os.environ["DB_HOST"] = "proyecto.mysql.pythonanywhere-services.com"
os.environ["DB_USER"] = "proyecto"
os.environ["DB_PASS"] = "aaaaaa"
os.environ["DB_NAME"] = "proyecto$proyectodb"

os.environ["MAIL_USERNAME"] = "aplicarmt@gmail.com"
os.environ["MAIL_PASSWORD"] = "aaaaaaaaaaaaa"
os.environ["MAIL_DEFAULT_SENDER"] = "aplicarmt@gmail.com"


# add your project directory to the sys.path
project_home = '/home/proyecto/P1Backend'
if project_home not in sys.path:
    sys.path.insert(0, project_home)

# import flask app but need to call it "application" for WSGI to work
from app import create_app
application = create_app()
```

## Backend url

![link]("htpps://proyecto1.pythonanywhere.com")

# MySql

> ## 1. Crear una db
> ![crea una base de datos manualmente]("https://...")
> 
> ```
> Nombre:proyecto
> Nombre deault: proyecto$default
> Contraseña:aaaaaaaa
> dirección del hos de la db: EstanciaBruno.mysql.pythonanyhwew-services.com
> ```

> ## 2. Posibles cambios en tu proyecto original
> ```
> 
> CREATE DATABASE proyecto$nombredb
>
> En el archivo app.py
> port= 3306
>
> BACKEND_URL = "https://proyecto.pythonanywhere.com"
>
> requests.post(BACKEND_URL + "/...", json=...)
> ```
