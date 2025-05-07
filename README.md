# TaskManager API

TaskManager es una API RESTful desarrollada con Django Rest Framework, diseñada para gestionar tareas de manera sencilla y eficiente. Esta API permite a los usuarios crear, editar y eliminar tareas, y es desplegable utilizando Docker y Render.

## Tabla de Contenidos
1. [Tecnologías Usadas](#tecnologías-usadas)
2. [Instalación](#instalación)
3. [Uso](#uso)
4. [Despliegue](#despliegue)
5. [Estructura del Proyecto](#estructura-del-proyecto)
6. [Licencia](#licencia)

## Tecnologías Usadas
- Django 4.2.5
- Django Rest Framework 3.15.2
- WhiteNoise 6.6.0
- Gunicorn 20.1.0
- Docker
- Render (para el despliegue en la nube)

## Instalación

1. **Clonar el repositorio**:

   ```bash
   git clone https://github.com/tu_usuario/taskmanager.git
   cd taskmanager
   ```
   
2. **Crear y activar un entorno virtual:**
   
- Para Windows:

   ```bash
    python -m venv venv
   .\venv\Scripts\activate
   ```

- Para macOS/Linux:

  ```bash
    python3 -m venv venv
    source venv/bin/activate
  ```

3. **Instalar las dependencias:**

Asegúrate de que tu entorno virtual esté activado y luego ejecuta:
  
  ```bash
  pip install -r requirements.txt
  
  ```

4. **Migraciones de base de datos:**

Realiza las migraciones necesarias para configurar la base de datos:
  
  ```bash
  python manage.py migrate
  ```

5. **Recopilar archivos estáticos:**

Si no lo has hecho antes, ejecuta:

  ```bash
  python manage.py collectstatic
  ```

## Uso

1. **Ejecutar el servidor localmente:**

Para iniciar el servidor de desarrollo de Django en tu máquina local, usa el siguiente comando:

  ```bash
  
  python manage.py runserver
  ```

Ahora, puedes acceder a la API a través de http://127.0.0.1:8000/.

2. **Probar la API:**

- Endpoint para obtener tareas: GET /api/tareas/

- Endpoint para crear tareas: POST /api/tareas/

- Endpoint para editar tareas: PUT /api/tareas/{id}/

- Endpoint para eliminar tareas: DELETE /api/tareas/{id}


Puedes probar estos endpoints con herramientas como Postman, Thunder Client o cURL.

## Despliegue

**Con Docker:**
1. **Construir la imagen Docker:**

En la raíz del proyecto, ejecuta:

  ```bash
  docker build -t taskmanager .
  ```

2. **Ejecutar el contenedor Docker:**

Después de construir la imagen, ejecuta el siguiente comando:

  ```bash
  docker run -p 8000:8000 taskmanager
  ```

Esto expondrá el servidor Django en el puerto 8000 de tu máquina local.

## En Render:
1. **Subir el código a GitHub** (si aún no lo has hecho).

2. **Conectar el repositorio a Render:**

- Entra a Render y crea una nueva aplicación.

- Conecta tu repositorio de GitHub y selecciona la rama correcta.

- Configura la variable de entorno ALLOWED_HOSTS en Render con el dominio de tu aplicación (por ejemplo, cdprueba.onrender.com).

- Render se encargará de la construcción y despliegue automáticamente.

## Estructura del Proyecto
  
  ```
  taskmanager/
  ├── taskmanager/          # Código principal de la aplicación
  │   ├── settings.py       # Configuración de Django
  │   ├── urls.py           # Enrutamiento de URLs
  │   └── wsgi.py           # Configuración de WSGI
  ├── productos/            # Aplicación de productos (si aplicable)
  ├── static/               # Archivos estáticos (como imágenes, CSS, JS)
  ├── manage.py             # Script de gestión de Django
  ├── Dockerfile            # Dockerfile para crear la imagen
  ├── docker-compose.yml    # Configuración de Docker Compose (si es necesario)
  ├── requirements.txt      # Dependencias del proyecto
  └── README.md             # Este archivo
  
  ```

## Licencia
Este proyecto está bajo la Licencia MIT. Consulta el archivo LICENSE para más detalles.
