# API de Gestión de Tareas

## Descripción
Esta API permite a los usuarios gestionar tareas. Los usuarios pueden crear, leer, actualizar y eliminar tareas.

## Instalación
1. Clona el repositorio
2. Crea un entorno virtual: `python -m venv venv`
3. Instala las dependencias: `pip install -r requirements.txt`

## Ejecutar en Docker
1. Construye la imagen Docker: `docker build -t mi_api .`
2. Ejecuta el contenedor: `docker run -p 8000:8000 mi_api`
3. Accede a la API en `http://localhost:8000/api/`

## Endpoints
- `GET /api/tasks/` - Lista todas las tareas
- `POST /api/tasks/` - Crea una nueva tarea
- `GET /api/tasks/{id}/` - Obtiene detalles de una tarea
- `PUT /api/tasks/{id}/` - Actualiza una tarea
- `DELETE /api/tasks/{id}/` - Elimina una tarea
