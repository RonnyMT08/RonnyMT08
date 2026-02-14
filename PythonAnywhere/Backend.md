# Levantar tu proyecto Backend + Base de Datos

> ## 1. Directorio para el proyecto

Crea un directorio adecuado para almacenar tu proyecto: `/Proyecto/...`

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
DB_USER=EstanciaBruno
DB_PASS=aaaaaaa
DB_NAME=HotelBruno
PORT=5001
```

# Configurar pythonAnywhere Backend

> ## Code:

Source code: `/home/EstanciaBrunoBack/Grupo-IDS-TP2/Backend`

working directory: `/home/EstanciaBrunoBack/GrupoIDS-TP2/Backend` 

> ## Virtualenv:

`/home/EstanciaBrunoBack/Grupo-IDS-TP2/Banckend/.env`

> ## wsgi.py

``` python
import sys
import os

os.environ["DB_HOST"] = "EstanciaBruno.mysql.pythonanywhere-services.com"
os.environ["DB_USER"] = "EstanciaBruno"
os.environ["DB_PASS"] = "aaaaaa"
os.environ["DB_NAME"] = "EstanciaBruno$HotelBruno"

os.environ["MAIL_USERNAME"] = "aplicarmt@gmail.com"
os.environ["MAIL_PASSWORD"] = "aaaaaaaaaaaaa"
os.environ["MAIL_DEFAULT_SENDER"] = "aplicarmt@gmail.com"


# add your project directory to the sys.path
project_home = '/home/EstanciaBruno/HotelBrunoBack/Grupo-IDS-TP2/Backend'
if project_home not in sys.path:
    sys.path.insert(0, project_home)

# import flask app but need to call it "application" for WSGI to work
from app import create_app
application = create_app()
```

## Backend url

![link]("htpps://EstanciaBruno.pythonanywhere.com")

# MySql

> ## 1. Crear una db
> ![crea una base de datos manualmente]("https://...")
> 
> ```
> Nombre:EstanciaBruno
> Nombre deault: EstanciaBruno$default
> Contraseña:aaaaaaaa
> dirección del hos de la db: EstanciaBruno.mysql.pythonanyhwew-services.com
> ```

> ## 2. Posibles cambios en tu proyecto original
> ```
> 
> CREATE DATABASE EstanciaBruno$nombredb
>
> En el archivo app.py
> port= 3306
>
> BACKEND_URL = "https://EstanciaBruno.pythonanywhere.com"
>
> requests.post(BACKEND_URL + "/...", json=...)
> ```



