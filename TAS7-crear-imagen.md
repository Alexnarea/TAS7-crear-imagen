# TAS7 - Crear imagen personalizada 
## 1. Título  
Contenerización de una Aplicación Web Frontend con Dockerfile

## 2. Tiempo de duración  
El tiempo fue de 120 minutos. 

## 3. Fundamentos

### Dockerfile 

Un contenedor Docker tiene una vida limitada e interactúa con su entorno. Imagina que contenedor es como un organismo vivo. Piensa en un organismo unicelular, como una célula de levadura. Siguiendo esta analogía, una imagen Docker equivale, digamos, a la información genética: todos los contenedores creados a partir de una imagen son iguales, como todos los organismos unicelulares clonados a partir de una unidad de información genética. El Dockerfile define los pasos a seguir para crear una nueva imagen. Hay que entender que se empieza siempre con una imagen base existente. La nueva imagen nace de la imagen base. Además, hay ciertos cambios puntuales. En nuestro ejemplo de la célula de levadura, los cambios serían mutaciones (¿Qué Es El Dockerfile? - IONOS, n.d.). 

### ¿Cómo funciona un Dockerfile y cómo se crea una imagen a partir de él?

Dockerfile es un archivo de texto totalmente normal. El Dockerfile contiene un conjunto de instrucciones, cada una en una línea distinta. Para crear una Docker Image, las instrucciones se ejecutan una tras otra. Quizás te suene este esquema de la ejecución de un script por lotes. Durante la ejecución, se añaden paso por paso más capas a la imagen.  Una imagen Docker se crea ejecutando las instrucciones de un Dockerfile. Este paso se conoce como el proceso build y empieza con la ejecución del comando “docker build”. El contexto de construcción es un concepto crucial: define a qué archivos y directorios tiene acceso el proceso de construcción, donde un directorio local hace las veces de fuente. El contenido del directorio fuente se transfiere al Docker Daemon al accionar “docker build”. Las instrucciones contenidas en el Dockerfile reciben acceso a los archivos y directorios contenidos en el contexto de construcción (¿Qué Es El Dockerfile? - IONOS, n.d.).

<img src="./dockimage/dfile.jpeg" alt="contenedor react docker" width="500"/>

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
- Generar la imagen Docker a partir del Dockerfile creado.
- Crear el contenedor con la aplicación


## 6. Equipo necesario

- Computador.
- Navegador web.
- Conexión a internet.

## 7. Material de apoyo

- Documentación oficial de Docker.
- Cheatsheet de comandos Docker.
- Repositorio de la práctica.
- Videos tutoriales.
- Guía de asignatura.

## 8. Procedimiento

### Pasos 

1. Clona el repositorio del proyecto frontend.

Figura 8-1 Clonacion del repositorio frontend.

<img src="./compos/c1.PNG" alt="drawing0" width="500"/>

2. Ejecuta el proyecto localmente para verificar su correcto funcionamiento.

Figura 8-2 Ejecutacion del proyecto localmente.

<img src="./compos/c2.PNG" alt="drawing0" width="500"/>

3.Crea un archivo Dockerfile adecuado para contenerizar la aplicación.

Figura 8-3 Creacion del archivo dockerfile.

<img src="./compos/wp.PNG" alt="drawing0" width="500"/>


4. Genera la imagen Docker a partir del Dockerfile creado.

Figura 8-4 Generacion de la imagen docker.

<img src="./compos/net.PNG" alt="drawing0" width="500"/>

5. Crear el contenedor con la aplicación.

Figura 8-5 Creacion del contenedor 

<img src="./compos/net.PNG" alt="drawing0" width="500"/>

## 9. Resultados esperados

Al finalizar la práctica, se logró cumplir exitosamente los objetivos planteados. Se creó una imagen Docker que contiene la aplicación React ``“suda-frontend-s6”`` y se desplegó correctamente un contenedor con esta imagen. La aplicación fue accesible a través del puerto ``8000`` del localhost.Durante el desarrollo se aplicaron conceptos fundamentales de contenerización, tales como la creación de imágenes Docker mediante un Dockerfile con multi-stage build para optimizar el tamaño de la imagen, el manejo de puertos para exponer el servicio y la ejecución de contenedores en modo desacoplado.

 Todo el desarrollo de la práctica fue documentado con capturas de pantalla que evidencian la clonación, la prueba local, la creación del Dockerfile, la construcción de la imagen y el despliegue del contenedor. Finalmente, se verificó que la aplicación funcionara correctamente en el entorno Docker.

## 10. Bibliografía

- ¿Qué es el Dockerfile? - IONOS. (n.d.). Retrieved May 16, 2025, from https://www.ionos.com/es-us/digitalguide/servidores/know-how/dockerfile/

