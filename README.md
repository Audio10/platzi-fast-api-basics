# FastAPI



## SetUp

Dependencias:

- Uvicorn: es una librería de Python que funciona de servidor, es decir, permite que cualquier computadora se convierta en un servidor
- Starlette: es un framework de desarrollo web de bajo nivel, para desarrollar aplicaciones con este requieres un amplio conocimiento de Python, entonces FastAPI se encarga de añadirle funcionalidades por encima para que se pueda usar mas fácilmente
- Pydantic: Es un framework que permite trabajar con datos similar a pandas, pero este te permite usar modelos los cuales aprovechara FastAPI para crear la API

```
pip install fastapi uvicorn        
```



## Hello World: elaborando el código de nuestra primer API



Lo primero es importar el FastAPI, es una clase que viene del módulo fastapi. Es esta clase la que permite que todo el framework funcione

```python
from fastapi import FastAPI
```

Se crea una variable llamada app. esta variable va a contener toda la aplicación y para poder iniciarlizarla bien se le coloca una instancia de FastAPI -> le colocamos los paréntesis

```python
app = FastAPI()
```

#### Path operation

Esto es un path operation decoration

```python
@app.get("/")
```

Este decorador usa el método get, que viene del objeto app, que proviene de la instancia FastAPI

#### Ejecutar la aplicacion

```bash
uvicorn main:app --reload
```

### Example

```python
from fastapi import FastAPI

app = FastAPI()


@app.get("/")
def home():
    return {
        "Hello": "World"
    }
```

## Documentation

FastAPI crea documentacion autogenerado mediante Swagger en el endpoint **/docs**.

```
http://127.0.0.1:8000/docs
```

FastAPI crea documentacion autogenerado mediante Redoc en el endpoint **/redoc**.

```
http://127.0.0.1:8000/redoc
```

