
# TAS6 – Contenerización de una Aplicación React con Docker

## 1. Título  
**Contenerización de una Aplicación Web Frontend (React) con Docker**

## 2. Tiempo de duración  
**90 minutos.**

## 3. Fundamentos

### Docker y Contenerización  
Docker permite empaquetar una aplicación y todas sus dependencias en una imagen ligera, portátil y reutilizable llamada **contenedor**, que puede ejecutarse en cualquier sistema que tenga Docker instalado. Esto asegura que la aplicación funcione de la misma forma en desarrollo, pruebas y producción.

Al contenerizar una aplicación React, se utiliza un archivo `Dockerfile` que indica paso a paso cómo construir la imagen: desde instalar dependencias hasta servir el contenido estático mediante un servidor (como `nginx` o el propio `node`).

### Ventajas de contenerizar aplicaciones frontend

- Portabilidad y consistencia entre entornos.
- Despliegue sencillo en cualquier infraestructura compatible con Docker.
- Aislamiento respecto al entorno host.
- Reutilización de imágenes en diferentes entornos o proyectos.

<img src="./docker-r/react-docker.png" alt="contenedor react docker" width="500"/>

## 4. Conocimientos previos

El estudiante debe conocer:
- Fundamentos de React.
- Comandos básicos de Docker.
- Lectura y escritura de archivos `Dockerfile`.
- Uso de terminal y navegación de proyectos frontend.

## 5. Objetivos a alcanzar

- Clonar un repositorio React.
- Ejecutar el proyecto localmente.
- Crear un archivo `Dockerfile` para contenerizar la aplicación.
- Construir una imagen Docker.
- Ejecutar un contenedor a partir de la imagen.
- Verificar funcionamiento de la app en el navegador.

## 6. Equipo necesario

- Computador con Docker instalado.
- Navegador web.
- Conexión a internet para clonar el repositorio.

## 7. Material de apoyo

- Documentación oficial de Docker.
- Cheatsheet de comandos Docker.
- Documentación de React.
- Repositorio de la práctica:  
  https://github.com/Daviddotcoms/suda-frontend-s6

## 8. Procedimiento

### 1. Clonar el repositorio del frontend

```bash
git clone https://github.com/Daviddotcoms/suda-frontend-s6
cd suda-frontend-s6
```

### 2. Verificar funcionamiento local

Instalar dependencias y levantar la app localmente:

```bash
npm install
npm run dev
```

Verificar que la aplicación funcione accediendo a `http://localhost:5173`

### 3. Crear el archivo Dockerfile

En el directorio raíz, crear un archivo llamado `Dockerfile` con el siguiente contenido:

```Dockerfile
# Etapa de construcción
FROM node:18 AS builder
WORKDIR /app
COPY . .
RUN npm install
RUN npm run build

# Etapa de producción
FROM nginx:alpine
COPY --from=builder /app/dist /usr/share/nginx/html

EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]
```

### 4. Crear el archivo `.dockerignore`

Este archivo evita copiar archivos innecesarios al contenedor:

```
node_modules
dist
.dockerignore
Dockerfile
*.md
.git
```

### 5. Construir la imagen Docker

```bash
docker build -t react-suda-app .
```

### 6. Ejecutar el contenedor

```bash
docker run -d -p 8080:80 --name suda-frontend react-suda-app
```

### 7. Verificar en el navegador

Abrir en el navegador la URL:  
http://localhost:8080  
y verificar que se muestra la aplicación React correctamente.

<img src="./docker-r/resultado-react.png" alt="Resultado React" width="800"/>

## 9. Resultados esperados

La aplicación React del repositorio `suda-frontend-s6` fue correctamente contenida y ejecutada en un contenedor Docker. Se construyó la imagen a partir de un `Dockerfile`, utilizando una etapa de construcción con Node.js y una etapa final con `nginx` para servir el contenido estático. La aplicación fue accesible desde el navegador en el puerto `8080`, cumpliendo todos los objetivos planteados.

Se emplearon comandos Docker como `build`, `run`, y se utilizaron buenas prácticas como multistage builds y archivo `.dockerignore`.

## 10. Bibliografía

- Docker. (n.d.). What is Docker? https://www.docker.com/
- Docker Docs. (n.d.). Dockerfile reference. https://docs.docker.com/engine/reference/builder/
- React Docs. (n.d.). Getting Started. https://reactjs.org/docs/getting-started.html
- Hostinger. (n.d.). Cómo desplegar apps con Docker. https://www.hostinger.com/tutorials/how-to-deploy-docker-app
