# API de Traducción con Flask y Hugging Face

Este proyecto proporciona un servicio web basado en Flask para traducir texto entre idiomas utilizando modelos de Hugging Face. La API permite traducir texto entre inglés y español, y también tiene soporte para traducción de español a quechua.

## Requisitos

Para ejecutar la API, es necesario contar con los siguientes requisitos:

- **Python 3.x**
- **Flask** (Para el servicio web)
- **Hugging Face Transformers** (Para cargar los modelos de traducción)
- **Pyngrok** (Para exponer la API a internet con ngrok)

Puedes instalar las dependencias necesarias con el siguiente comando:

```bash
pip install flask transformers pyngrok
```

## Instalación y Ejecución

Clona el repositorio y accede a la carpeta del proyecto:

```bash
git clone <URL_DEL_REPOSITORIO>
cd <NOMBRE_DEL_REPOSITORIO>
```

Ejecuta el servicio Flask:

```bash
python app.py
```

Esto iniciará el servidor en `http://127.0.0.1:5000/`.

Para exponer la API a internet mediante ngrok:

```bash
ngrok http 5000
```

Esto generará una URL pública que podrás compartir.

ejemplo: https://2989-35-245-209-8.ngrok-free.app/traducir

también puedes acceder a ejeutarlo desde colab y no necesitas instalar nada en tu computador:

https://colab.research.google.com/drive/1-AXEO6a5wwTFSW5O0NF-fl2G5Q0YomNC?usp=sharing

## Endpoints

### **1. Traducción de texto**

- **URL:** `/traducir`
- **Método:** `POST`
- **Cuerpo de la petición:** JSON

Ejemplo de petición:

```json
{
    "texto": "Hola mundo",
    "origen": "es",
    "destino": "en"
}
```

**Idiomas disponibles:**

- `es` -> `en` (Español a Inglés)
- `en` -> `es` (Inglés a Español)
- `es` -> `qu` (Español a Quechua)

**Respuesta esperada:**

```json
{
    "texto traducido": "Hello world"
}
```

## Ejemplo de Uso con cURL

Puedes probar la API con `cURL` desde la terminal:

```bash
curl -X POST "http://127.0.0.1:5000/traducir" -H "Content-Type: application/json" -d '{"texto": "Hola mundo", "origen": "es", "destino": "en"}'
```

## Despliegue en la Nube (Opcional)

Si deseas desplegar el servicio en la nube, puedes utilizar plataformas como **Heroku**, **AWS Lambda**, o **Google Cloud Run**.

Ejemplo de despliegue en Heroku:

```bash
heroku create mi-api-traduccion
heroku git:remote -a mi-api-traduccion
git push heroku main
```

## Autores

- **Emily Chimbo**

