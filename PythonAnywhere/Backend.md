# Levantar tu proyecto Backend

> ## Logearte

> ## Directorio para el proyecto

`/Proyecto/...`

Descarga el repositorio

``` bash
git clone https://...
```

> ## Crea tu entonovirtual.
![como crear entono virtual]("https:...")

> ## Instala la librerias requeridas

```
pipenv install flask requerimientos
```

> ## Achivo .env

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


