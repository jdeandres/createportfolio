# Usamos una imagen base de Python 3.10.1
FROM python:3.10.1

# Establecemos el directorio de trabajo
WORKDIR /CreatePortfolio

# Copiamos los archivos requeridos a la imagen
COPY requirements.txt ./
COPY . .

# Instalamos las dependencias de la aplicación
RUN pip install --no-cache-dir -r requirements.txt

# Exponemos el puerto 8000
EXPOSE 8000

# Definimos el comando de inicio de la aplicación
CMD ["python", "./createportfolio/manage.py", "runserver", "0.0.0.0:8000"]
