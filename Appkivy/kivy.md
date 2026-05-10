# creacion de una aplicacion con kivy

## activar el entorno virtual

```bash
source env/bin/activate
```

## instalar kivy

```bash
pip install kivy
```

## crear el archivo main.py

```python 
from kivy.app import App
from kivy.uix.label import Label

class MyApp(App):
    def build(self):
        return Label(text='Hello, World!')

if __name__ == "__main__":
    MyApp().run()
```

## correr la aplicacion

```bash
python main.py
```

# crear una apk 

## instalar buildozer

```bash
pip install buildozer
```

## inicializar buildozer

```bash
buildozer init
```

## editar el archivo buildozer.spec

- buscar la linea `source.include_exts = py,png,jpg,kv,atlas` y agregar `,txt` al final de la linea
- buscar la linea `requirements = python3,kivy` y agregar `,buildozer` al final de la linea

## compilar la apk

```bash
buildozer -v android debug
```
- despues de compilar la apk se encuentra en la carpeta `bin` con el nombre `MyApp-0.1-debug.apk` y se puede instalar en un dispositivo android para probarla.

- para compilar la apk en modo release se debe ejecutar el siguiente comando:

```bash
buildozer -v android release
```
- despues de compilar la apk en modo release se encuentra en la carpeta `bin` con el nombre `MyApp-0.1-release.apk` y se puede instalar en un dispositivo android para probarla.

[que puedes hacer en kivy](/Appkivy/herramientas.md)
