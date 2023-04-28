# Usa una imagen base de Node.js versión 14
FROM node:18.14.2 as build

# Establece el directorio de trabajo
WORKDIR /CreatePortfolio

# Copia los archivos necesarios para instalar las dependencias del proyecto
COPY CreatePortfolio/package*.json ./

# Instala las dependencias del proyecto
RUN npm install

# Copia el contenido del proyecto de Angular a la imagen
COPY CreatePortfolio/dist/create-portfolio/ /CreatePortfolio

# Configura Nginx como servidor web
FROM nginx:alpine
EXPOSE 80

# Copia el archivo de configuración de Nginx dentro del contenedor
COPY --from=build /CreatePortfolio /usr/share/nginx/html
#COPY nginx.conf /etc/nginx/nginx.conf

# Inicia Nginx en primer plano
CMD ["nginx", "-g", "daemon off;"]
