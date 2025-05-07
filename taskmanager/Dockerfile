# Usa una imagen base de Python
FROM python:3.8-slim

# Establece el directorio de trabajo
WORKDIR /app

# Copia los archivos de la aplicación al contenedor
COPY . /app/

# Instala las dependencias
RUN pip install --no-cache-dir -r requirements.txt

# Expón el puerto 8000 para que se pueda acceder a la API
EXPOSE 8000

# Comando para ejecutar la aplicación usando Gunicorn
CMD ["gunicorn", "taskmanager.wsgi:application", "--bind", "0.0.0.0:8000"]
