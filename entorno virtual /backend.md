<h1 align="center">ENTORNO VIRTUAL (BACKEND)</h1>

## 1. crea tu carpeta con:

```bash
  python3 -m venv .venv
```

## 2. activa el entorno:
   
```bash
   source .venv/bin/activate
```

## 3. instala flask dentro del entorno:

```bash
   pip install flask
```

## 4. verifica si se instalo:

```bash
  pip list
```

> ## Crea tu archivo
> app.py
> ``` python
> from flask import Flask, jsonify, request
> import mysql.connector
>
> app = Flask(__name__)  
> 
> #crear coneccion a la base de datos MySQL
> conexiondb ={
>    host="localhost",
>    user="root",
>    password="mysql",
>    database="dbName",
>    port=3306
> }
>
> print("Conexión exitosa a MySQL!")
> 
> @app.route('/registrar', methods=['POST'])
> def registrar_usuario():
>     data = request.get_json()
>     nombre = data.get('nombre')
>     contrasena = data.get('contrasena') 
>
>     conexion = mysql.connector.connect(**conexiondb)
>     cursor = conexion.cursor()
>
>     sql = "INSERT INTO usuarios (nombre, contrasena) VALUES (%s, %s)"
>     cursor.execute(sql, (nombre, contrasena))
>     conexion.commit()
> 
>     cursor.close()
>     conexion.close()
>
>     return jsonify({'message': 'Registration successful'}), 201 
> 
> if __name__ == '__main__':
>     app.run(host="0.0.0.0", port=5001, debug=True)
> ```

> ## Ejecuta tu proyecto

```bash
  python3 app.py
```

> ## Desactiva el entorno
```bash
  deactivate
```
