# Taller 2: Acceso público de containers por puertos

## Descripción
En este taller, aprenderás cómo exponer y acceder a los servicios que se ejecutan dentro de un contenedor Docker a través de puertos públicos. Esto es esencial para permitir que las aplicaciones dentro de los contenedores sean accesibles desde fuera del contenedor.

## Objetivos
- Comprender cómo funcionan los puertos en Docker.
- Aprender a mapear puertos del contenedor a puertos del host.
- Configurar y probar el acceso público a un contenedor.

## Requisitos
- Haber completado el [Taller 1: Introducción a Docker](taller1-introduccion.md).
- Tener Docker instalado en tu máquina.
- Conexión a internet para descargar imágenes de Docker.

## Contenidos

### 1. Conceptos Básicos de Puertos en Docker
Docker permite mapear puertos del contenedor a puertos del host para que los servicios dentro del contenedor sean accesibles desde fuera. Esto se hace utilizando la opción `-p` al ejecutar un contenedor.

### 2. Ejemplo Práctico: Servidor Web Nginx
Vamos a utilizar Nginx, un servidor web popular, para demostrar cómo exponer puertos.

#### Paso 1: Descargar la imagen de Nginx
Primero, descarga la imagen de Nginx desde Docker Hub:
```bash
docker pull nginx
```

#### Paso 2: Ejecutar el contenedor de Nginx
```bash
docker run -d -p 8080:80 --name mi_nginx nginx
```
En este comando:
  -  -d ejecuta el contenedor en segundo plano (detached mode).
  -  -p 8080:80 mapea el puerto 8080 del host al puerto 80 del contenedor.
  -  --name mi_nginx asigna el nombre mi_nginx al contenedor

#### Paso 3: Acceder al servidor web
Abre tu navegador web y navega a `http://localhost:8080`. Deberías ver la página de bienvenida de Nginx, lo que indica que el servidor web está funcionando correctamente y es accesible a través del puerto mapeado.

Si estás utilizando una máquina virtual, puedes acceder al servidor web ingresando la dirección IP de la máquina virtual seguida del puerto 8080 en tu navegador, por ejemplo, `http://<IP-de-la-maquina-virtual>:8080`.
